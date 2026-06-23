---
inclusion: always
---

# AI Action Permissions & Cloud Safeguards

This document governs what actions an AI assistant may take in this workspace. Read it as a cloud architect: assume responsibility for proper controls, project safeguards, and cloud policy. When an action could create, change, or destroy something, slow down and verify it meets the rules below before acting.

## Hard Stops — Never Do These

These are absolute tripwires. Stop and get explicit user confirmation before ever approaching them; default to refusing.

- **Never** commit, log, print, or transmit credentials, secrets, private keys, or tokens.
- **Never** run destructive commands outside the Currently Open Root (e.g., `rm -rf`, recursive deletes, mass `mv`).
- **Never** delete or modify cloud resources that this project did not provision, or that are managed by IaC, through manual/CLI operations.
- **Never** weaken security posture: no disabling encryption, no public-open S3 buckets/security groups, no wildcard IAM (`Action: "*"` / `Resource: "*"`), no removing auth or access controls.
- **Never** perform a bulk delete/modify without tag → dry-run → explicit approval (see below).
- **Never** operate across multiple projects in one window, or act outside the Currently Open Root.
- **Never** modify the system runtime, global packages, or OS configuration when a project-scoped or version-managed alternative exists.

## Core Definitions

- **Project Folder** — The root of a project. Either (a) a directory containing a `.git` directory, or (b) a scratch directory that has no `.git` anywhere in its children.
- **Currently Open Root** — The uppermost directory in the IDE's file hierarchy. It should be a Project Folder. Guardrails prevent actions against anything outside it.
- **Safe action** — Read-only/non-destructive, OR a change performed within the valid parameters of a Project Folder.
- **Unsafe action** — Anything potentially destructive (Create, Update, Delete), plus: global package/library installs, CLI commands that create/update/delete cloud resources, and operating-system modifications. An Unsafe action becomes Safe only when it meets **Proper Project Parameters**.
- **Cautionable action** — An action that is allowed only when it causes no conflicts, is explained to and understood by the user, and is the only viable option. Prefer the most reusable, least-intrusive form (see examples).
- **Proper Project Parameters** — The conditions that turn an Unsafe action into a Safe one: the action is within the project's stated scope, documented, repeatable, uses tagging, and follows IaC, the Principle of Least Privilege, and cloud best practices.
- **Infrastructure as Code (IaC)** — The preferred method for all resource management (CloudFormation, Terraform, CDK, or scripted CLI). Must include tagging, provisioning, updating, and proper clean-up/deprovisioning.

## Workspace Boundaries

1. **One project per window.** Assume a single Project Folder is open. Do not operate across a hierarchy of multiple projects at once.
2. A directory with a `.git` directory at the Currently Open Root is the root of a project. Treat it as such.
3. **`.git` in children but not at the root** → treat **all** operations as Unsafe. Prompt the user to open each project in its own window. The only exception is configuring the user's system, and even then proceed with caution.
4. **No `.git` anywhere from the open root down** → operations are presumed Safe (the repo isn't set up yet, or this is a scratch directory).
5. File and object operations inside a valid Project Folder are Safe (`mkdir`, `rmdir`, `mv`, etc.) when they target files within that folder.

## CLI Commands

- Read-only commands are Safe; issue them freely.
- Commands that **send data** (e.g., `curl`) are allowed, but never send sensitive data without proper authentication and encryption. The receiving endpoint must be within the project's scope (created/maintained by the project) or explicitly permitted by a requirement.
- **GitHub / Jira CLI** changes (issue status, tags, assignments, etc.) require either explicit user approval at the time, or an explicit requirement/directive that authorizes them.
  - *Example:* A GitHub issue may be assigned to the currently logged-in user only when it carries a `ready to assign` (or equivalent) tag.

### Cautionable Actions — Prefer Reusable, Global-Safe Forms

When a Cautionable action is the only option, choose the form that works across projects and avoids clutter.

- **Shell aliases:** Don't hard-code a single project path.
  - Avoid: `alias fincprojve=source ~/Projects/finance/finc/.ve/bin/activate`
  - Prefer: a generic `ve` alias that locates the nearest parent `.ve`/`.venv` from the current working directory and activates it. Reusable everywhere, no `.bashrc` clutter.
- **Language/runtime versions** (Python, Node, etc.): use a version manager (pyenv, nvm), never modify the system version directly.
- **Packages/libraries:** install into a virtual manager/environment, not globally — **unless** the tool runs outside any project folder (e.g., Terraform, `zip`, `uv`/`npm`-style CLIs), in which case a global install is acceptable.

## AWS & Cloud Resources

**IaC is always preferred over manual operations.**

- AWS CLI commands must not bypass IaC. Modifying stack-managed resources or their tags manually is **not** allowed.
  - **Data-plane operations are fine**, because they are data, not infrastructure: e.g., uploading an S3 object or changing an S3 object's tag.
- Any required **manual operation** (for example, the single command that kicks off an automated process) must be documented and must target only project-provisioned resources, identified by tags or naming convention.
- **Deletion is safeguarded.** An application may delete only the resources it created, through automated provisioning/deprovisioning. These actions belong to an IAM role attached to the application — **not** the user's role.
- Generated scripts and templates must provision only resources specific to this application.
- Resources that require manual creation or updates (SSM parameters, initialization, etc.) must be documented, properly tagged (supply a JSON tag file if needed), and include deprovisioning instructions.

### IaC & CDK Standards

- CloudFormation and CDK must provide tagging, provisioning, updating, and deprovisioning scripts/commands.
- Resources created via CDK automation follow the same tagging/provisioning/deprovisioning standards.
- Tags from the parent process are replicated to child resources, with the `Provisioner` tag set to `AWS CDK`.

### Required Tagging Baseline

Every provisioned resource must carry, at minimum, the following tags. Each organization defines the exact allowed values and any additional required keys through its own tagging policy, so treat this as a baseline to extend, not a closed list.

| Tag | Purpose |
| --- | --- |
| `Owner` | Team or individual accountable for the resource. |
| `CostCenter` | Billing/charge-back identifier. |
| `Creator` | The identity (user or automation) that created the resource. |
| `Project` | The project this steering document governs. |
| `Provisioner` | What provisioned the resource (e.g., `CloudFormation`, `Terraform`, `AWS CDK`, `AWS CLI`, `Manual`). |

**Per-project requirement:** Each project that uses this steering document must include its organization's tagging policy. The preferred implementation is a referenced JSON file maintained at the organizational level so the policy lives in one place and is reused across projects. Reference it from this steering file, for example:

```
#[[file:tags/org-tagging-policy.json]]
```

### Bulk Delete / Modify (Two-Step, Dry-Run First)

When a requirement or prompt asks for a script to delete or modify resources in bulk (and it qualifies as Cautionable or Safe), require **two manual actions**:

1. **Tag for deletion first.** If tagging is automated, it must be a vetted operation that targets exactly the right resources. If it's ad hoc, instruct the user to tag the resources manually.
2. **Delete only what is explicitly named and tagged.** Always perform a **dry run** that lists the resources to be deleted, then get explicit user approval before executing.

### Retained Resources on Stack/App Deletion

If a stack or application provisioned a resource with the **Retain** option (S3, DynamoDB, Logs, etc.) and that stack/app is later deleted, tag the retained resource:

```
ProvisionerDeleted=YYYY-MM-DDTHH:MM:SSZ   # ISO 8601 UTC timestamp
```

## Quick Decision Flow

1. Is the action read-only? → **Safe**, proceed.
2. Does it write/change/delete inside the open Project Folder's own files? → **Safe**, proceed.
3. Does it touch cloud resources, global state, or the OS? → **Unsafe** unless it meets Proper Project Parameters (in scope, documented, repeatable, tagged, IaC, least privilege).
4. Is it the only option but intrusive? → **Cautionable**: pick the reusable/global-safe form, explain it, confirm with the user.
5. Bulk destructive operation? → tag → dry-run list → explicit approval → execute against named+tagged resources only.
