# Spec-Driven Development with the Kiro IDE Workshop

## Presentation Overview

- **Title:** Kiro IDE and Spec-Driven Development: Building Production-Ready Solutions with Agentic AI
- **Target Duration:** 60–75 minutes (including interactive exercise)
- **Audience:** Developers, architects, engineering leads

---

## Speaker Notes (2–3 minutes per slide)

> The following text is written as a companion knowledge base article and is not a transcript of the workshop.

### Slide 1: Title — Kiro IDE and Spec-Driven Development
**⏱️ Duration: 2 minutes**

Today we're going to talk about something that I think is one of the most important shifts happening in software development right now.

We all know AI has fundamentally changed how fast we can produce code. Tools like Copilot, ChatGPT, Claude — they've made it trivially easy to generate code. But here's the thing that not enough people are talking about: the bottleneck was never really code generation. The bottleneck has always been *understanding what to build* and *building it correctly*.

Even *understanding what to build* and *building it correctly* isn't new. The methods, patterns, and concepts have been taught in computer science courses for decades. However, for smaller organizations, and even within larger ones, as I said, they were bottlenecks, often bypassed as developers went straight to coding a solution.

We were manually vibe coding all along!

With AI we no longer have an excuse to ignore the fundamentals of *understanding what to build* and *building it correctly*.

What I want to show you today is Kiro — an IDE that's built around this insight. It's not just another code generation tool. It's an agentic development environment that helps you go from a rough idea to production-ready software through a structured, disciplined process.

By the end of this session, you'll understand why process matters more than ever in the age of AI, and you'll have hands-on experience with a workflow that can genuinely reduce technical debt while increasing development speed.

---

### Slide 2: The Challenge
**⏱️ Duration: 2.5 minutes**

Let me frame the problem we're solving. AI has made software creation easier than ever — that's undeniable. I can ask an AI to generate a REST API, a React component, a database schema, and I'll have working code in seconds.

But here's what I've observed across teams: code generation is no longer the bottleneck. The bottleneck is now *decisions*. What should we build? How should it integrate? What are the security implications? How does it fit into our existing architecture?

And here's the dangerous part: because AI makes it so easy to generate code, technical debt can now accumulate *faster* than ever before. If I can generate 10x more code in a day, but that code doesn't follow our standards, doesn't have proper error handling, doesn't integrate cleanly — I've just created 10x more technical debt.

This is why process matters more than ever. AI amplifies whatever practices you already have. Good practices? AI makes you faster and better. Bad practices? AI makes you faster at creating problems. The question isn't whether to use AI — it's how to use AI within a framework that ensures quality outcomes.

---

### Slide 3: Workshop Objectives
**⏱️ Duration: 1.5 minutes**

Let me set expectations for what you'll walk away with today. We're covering six areas, and they build on each other intentionally.

First, Kiro fundamentals — what it is, how it differs from other AI coding tools. Then we'll look at three capabilities that make it unique for teams: Steering Documents, which encode your organization's standards; MCP Servers, which give AI access to trusted documentation; and Hooks, which automate repetitive workflows.

The core of what I want you to understand is Spec-Driven Development — a structured workflow that takes you from an idea through requirements, design, and tasks before you write a single line of production code.

And finally, we'll connect all of this to the concept of opinionated platforms — the idea that your team shouldn't be making the same infrastructure decisions over and over.

Each section has a "why this matters" component. I'm not just showing you features — I'm showing you a philosophy of engineering that AI finally makes practical for even small shops and sole developers and non-developers alike.

---

### Slide 4: The Sandbox Principle
**⏱️ Duration: 2 minutes**

I want to introduce a concept that underlies everything else today: the sandbox principle. Think about building sandcastles. When you're at the beach with kids, nobody drafts blueprints before they start piling sand. You experiment, you try things, you knock it down and start over.

That's learning mode. And it's incredibly valuable. But nobody would build an actual house that way. For production, you need blueprints, permits, inspections, standards.

The same applies to AI-assisted development. When you're exploring a new library, learning a framework, prototyping an idea — go wild. Use AI freely. Generate code. Break things. Throw it all away.

But when you shift to production — when the code will serve real users, handle real data, need real maintenance — that's when you need to switch modes. Production starts with requirements, not with code generation.

The mistake I see teams making is treating production code like sandbox code. They skip straight to "generate it" without first asking "what are we actually building and why?" Kiro gives you tools for both modes, but more importantly, it makes the *transition* between them deliberate and clear.

---

### Slide 5: Structure Creates Freedom
**⏱️ Duration: 2.5 minutes**

This is the central theme of the entire presentation, and I want you to hold onto it: structure creates freedom. It sounds paradoxical, but it's true at every level of engineering.

Think about it. When you have clear standards, you don't have to make decisions about things that don't matter. Should we use camelCase or snake_case? If there's a standard, that decision is made. You're free to focus on the actual problem.

When you have predictable project structures, onboarding takes days instead of weeks. A new developer knows where to find things, how to run tests, where configuration lives.

When you have defined architectural patterns, you reduce cognitive load. You're not reinventing the wheel for every service — you're building on proven foundations.

This applies to AI assistance too. When Kiro knows your standards through steering documents, when it has access to your internal documentation through MCP, when hooks enforce your processes automatically — the AI becomes dramatically more useful because it's operating within the right constraints.

Every section we cover today is an example of this principle. Steering documents, opinionated platforms, spec-driven development — they're all forms of structure that ultimately give you more freedom to focus on what actually matters: solving the business problem.

---

### Slide 6: Cognitive Load
**⏱️ Duration: 2 minutes**

Let's talk about what developers actually deal with day to day. When you're writing a feature, you're not just thinking about the business logic. You're juggling security — "am I handling auth correctly? Am I sanitizing inputs?" You're thinking about monitoring — "will I know when this breaks in production?" Testing — "what are the edge cases?" Compliance — "does this meet our data handling requirements?" Deployment — "how does this get to production safely?" Documentation — "will the next person understand this?"

That's an enormous amount of cognitive load. And here's the key insight: AI should *reduce* this cognitive load, not add to it. If your AI tool requires you to carefully review every generated line for security issues, for standards compliance, for architectural fit — it's not reducing your burden, it's just shifting it.

What we want is an AI that already knows the answers to these questions. An AI that's been told "we use least privilege, we're serverless-first, we follow Well-Architected Framework, we require documentation." That's what steering documents and MCP servers accomplish — they pre-load the AI with your team's decisions so you don't have to re-explain them every time.

---

### Slide 7: What is Kiro?
**⏱️ Duration: 2 minutes**

So what is Kiro, concretely? It's an agentic IDE — meaning it's not just auto-completing your code, it's actively working alongside you as a collaborator. Think of it as a development environment that has opinions and workflows, not just suggestions.

It gives you multiple interaction modes. Chat is your basic conversation — ask questions, get answers. Vibe Mode is for free-form exploration, prototyping, learning. Spec Mode is the structured workflow we'll spend the most time on today.

Then there are three infrastructure features: Steering gives the AI organizational memory. MCP Servers give it access to trusted external knowledge. Hooks give it automation capabilities.

[SCREENSHOT: Show the Kiro interface here — the sidebar with spec panel, the chat area, the editor]

What makes Kiro different from just using an AI in your existing editor is that these features are *integrated into a workflow*. They're not just bolt-ons. The spec mode understands steering documents. Hooks can trigger based on spec task completion. MCP context informs requirements analysis. It's a coherent system, not a collection of features.

---

### Slide 8: Demo Roadmap
**⏱️ Duration: 1 minute**

Before we dive into the deeper concepts, I want to show you Kiro in action with three quick demos. We'll progress through three ways of using AI: Discovery — understanding existing things; Transformation — converting information from one form to another; and Planning — generating engineering artifacts.

These demos are intentionally *not* about code generation. I want to show you that an AI development tool is useful long before you write your first line of code. Understanding a codebase, restructuring documentation, generating proposals — this is where AI assistance often delivers the most value with the least risk.

Let's jump in.

---

### Slide 9: Demo — Discovery
**⏱️ Duration: 3 minutes**

[LIVE DEMO or SCREENSHOT WALKTHROUGH]

The first category is Discovery. You have an existing system — maybe you're new to the team, maybe it's a codebase nobody's touched in two years — and you need to understand it.

Watch what happens when I ask Kiro to summarize this project's README. It doesn't just regurgitate the text — it synthesizes the key points, identifies the architecture decisions, highlights what's unusual or noteworthy.

Now let me ask it to explain a specific module. See how it traces the data flow, identifies the dependencies, explains the design decisions? This is what used to take a developer a full day of reading code.

And here's the most powerful one: generating architecture documentation from existing code. It reads the project structure, identifies the patterns, maps the integrations, and produces a document that would have taken a human several hours to write.

Key point: none of this generated any new code. It's purely about understanding. And understanding must come before building. This is Discovery — the first step in any engineering workflow.

---

### Slide 10: Demo — Transformation
**⏱️ Duration: 2.5 minutes**

[LIVE DEMO or SCREENSHOT WALKTHROUGH]

The second category is Transformation — taking information in one form and converting it to another. This is where AI genuinely shines because it's tedious work that humans do poorly at scale.

Here's a Word document. Maybe it's a requirements doc from a stakeholder, written in prose. Watch me convert it to structured Markdown with proper headings, linked requirements, and acceptance criteria. Instant, and it preserves the meaning while adding structure. I could also do the reverse, suppose I had a markdown document that I needed to hand off to someone else as a Word document.

JSON restructuring — I have a JSON file with properties and values, but a CLI command needs it in another format. Instead of manually writing a transformer, I can describe the desired output shape and transform it.

And here's a fun one — I have a design mockup image, and I need to extract the color palette for my CSS variables. AI reads the image, identifies the colors, and generates the variable declarations.

These are non-code uses of an AI IDE. They demonstrate that AI is a general-purpose assistant in your development workflow, not just a code generator.

---

### Slide 11: Demo — Planning
**⏱️ Duration: 2.5 minutes**

[LIVE DEMO or SCREENSHOT WALKTHROUGH]

The third category is Planning — generating engineering artifacts that help you make decisions. This is the bridge between understanding and building.

A deployment proposal: I describe what I want to deploy, the constraints, the requirements, and Kiro generates a proposal with infrastructure choices, cost considerations, timeline, and risks.

An executive summary: I have a detailed technical document and I need to communicate it to leadership in one page. AI understands the technical content and translates it to business impact.

Architecture recommendations: Given a set of requirements and constraints, generate options with trade-offs clearly stated. This isn't AI making the decision — it's AI preparing the information so *you* can make a better decision faster.

This is where we transition into the core message: AI is most valuable in the planning and thinking phases, not just the typing phase. And Kiro is built around that insight. Let's look at how it formalizes this into workflows.

---

### Slide 12: Steering Documents
**⏱️ Duration: 2.5 minutes**

Now we get into the features that make Kiro powerful for *teams*, not just individuals. Steering documents are organizational memory for AI.

Think about it: every team has (or have have) standards. Security practices, documentation requirements, testing expectations, architectural patterns. These exist in wikis, in Confluence pages, in knowledge base articles, and team memory. And every time a developer asks AI for help, they have to manually remind it of all these standards. "Oh, and make sure you use parameterized queries. And follow our naming conventions. And include error handling per our patterns."

Steering documents solve this by encoding these standards in files that are automatically included in AI context. They live in `.kiro/steering/` and they can be always-on, triggered by file patterns, or manually included.

[SCREENSHOT: Show a steering directory with example files]

The key insight is that steering documents scale across a team. Write them once, and every developer on the team gets AI that already knows your standards. A new hire doesn't need to learn all the patterns manually — the AI guides them correctly from day one.

[DIAGRAM: Show the hierarchy — org standards → team standards → project standards → AI context]

---

### Slide 13: Steering Document Examples
**⏱️ Duration: 2 minutes**

Let me show you what these look like in practice. They're Markdown files with optional YAML frontmatter for configuration.

A security steering doc might say: "Always use least privilege IAM policies. Never use inline credentials. Prefer Secrets Manager for sensitive values. All API endpoints require authentication."

An architecture steering doc: "We are serverless-first. Use Lambda for compute, DynamoDB for state, API Gateway for REST endpoints. Follow AWS Well-Architected Framework principles."

A documentation steering doc: "All public functions require JSDoc comments. README files are mandatory. Architecture Decision Records are required for significant changes."

You can even reference external files using the `#[[file:relative-path]]` syntax, so your OpenAPI spec or GraphQL schema automatically informs code generation.

The AGENTS.md document in the root of the repository can be used for project specific guidance, and is recognized by many AI agents.

Steering documents can kept be somewhat generic, not relating to the project itself, but organization guidelines. They can even be managed by the organization either through organization-wide Kiro managment, or an import from a shared repository during project scaffolding.

The beauty is that developers don't need to memorize these rules. The AI applies them automatically. And when standards change, you update one file and the entire team benefits immediately.

---

### Slide 14: Why Steering Matters
**⏱️ Duration: 2 minutes**

Why does this matter at scale? Three reasons.

First, consistency. When 10 developers are using AI, and each is giving it different instructions about your standards, you get 10 different interpretations. Steering documents ensure everyone gets the same guidance. The same security patterns. The same naming conventions. The same architectural choices.

Second, cross-team alignment. In larger organizations, you might have a platform team defining standards that product teams should follow. Steering documents become the mechanism for distributing those standards directly into the development workflow.

Third, better AI outputs. This is practical: the more context AI has about your actual requirements, the better its suggestions are. Without steering, AI generates generic code. With steering, it generates code that fits *your* system. It's the difference between "here's how to implement authentication" and "here's how to implement authentication using your existing Cognito user pool with your team's session management pattern."

Code becomes more deterministic, and developers will be able to recognize code patterns across projects.

This connects directly to opinionated platforms, which we'll discuss later. Steering documents are how you encode platform opinions into the AI's understanding.

---

### Slide 15: MCP Servers
**⏱️ Duration: 2.5 minutes**

MCP stands for Model Context Protocol, and it solves a specific problem: how do you give AI access to information that isn't in its training data?

Your internal documentation, your framework's latest API, your platform's deployment guide, your team's architecture patterns — these aren't things a general-purpose AI knows about. MCP servers act as bridges to trusted knowledge sources.

[DIAGRAM: Show the flow — Developer asks question → Kiro queries MCP → MCP fetches from source → Response with context]

Think of MCP servers as specialized research assistants. You might have one for AWS documentation, one for your internal wiki, one for your framework references, one for your platform standards.

[SCREENSHOT: Show mcp.json configuration with server entries]

The key phrase here is "better informed, not smarter." The AI model doesn't change. What changes is the information it has access to. And because MCP pulls from *your* trusted sources — not random internet content — the answers are relevant and reliable.

Configuration is straightforward — a JSON file in `.kiro/settings/mcp.json`. You can have user-level servers that apply everywhere and workspace-level servers specific to a project.

---

### Slide 16: MCP Demo Examples
**⏱️ Duration: 2 minutes**

Let me show you the practical impact. 

Say I'm writing CloudFormation. Instead of searching AWS docs, I ask Kiro. The MCP server for AWS documentation retrieves the current syntax, the valid property types, the constraints. I get an answer that's pulled from the official source.

[SCREENSHOT: Show retrieval from AWS docs MCP server]

Atlantis starters — platform engineering resource with starter code. Through MCP, I can ask "what's the best Atlantis starter to create a Lambda service that will periodically monitor stack drift?" and get the current version, not something from six months ago.

Framework guidance — when using an internal framework, MCP gives AI access to its documentation. So when I ask "how do I add middleware to this framework?" the answer reflects *our* framework's actual API, not a generic pattern.

This is AI with *current, relevant, trusted* context. Not outdated training data. Actual documentation from the sources your team trusts.

---

### Slide 17: Hooks
**⏱️ Duration: 2.5 minutes**

Here's a truth about development: people forget. We forget to run tests. We forget to update docs. We forget to check dependencies. Not because we're careless — because we're human, and our attention is finite.

Hooks solve this by automating repetitive tasks. They're event-driven actions that trigger automatically based on what's happening in the IDE.

[DIAGRAM: Show event types flowing to actions]

A file gets saved? Run the linter. A task completes? Run the test suite. A prompt is submitted? Check if it aligns with project standards. A tool is about to execute? Verify it's safe.

[SCREENSHOT: Show the Hooks panel in Kiro]

Hooks can also be ran manually to perform user-initiated checks of Lambda layer or package versions, or even scaffold an entire project to your team's specifications. Step by step instructions of run `npx`, run `npm install`, update `config.js`, set `projectName` in `extension.js` can now be automated rather than manual and tedious.

Hooks support two action types: `runCommand` for executing shell commands, and `askAgent` for sending instructions to the AI. The event types cover the full development lifecycle — file changes, prompt submission, tool execution, task completion.

The power is in composition. A hook runs tests after every task. Another hook updates documentation when code files change. A third hook reviews dependency additions for security. You build up layers of automated quality assurance that run without human intervention.

People forget. Hooks don't.

---

### Slide 18: Vibe Mode
**⏱️ Duration: 2 minutes**

Let's talk about modes. Vibe Mode is Kiro's exploration mode — think of it as the sandbox we discussed earlier. It's conversational, free-form, and intentionally low-friction.

When should you use Vibe Mode? Weekend projects. Prototypes you'll throw away. Learning a new library. Researching approaches. Comparing options. Generating quick scripts you'll use once.

[SCREENSHOT: Show a vibe mode conversation — casual, exploratory]

Vibe Mode is useful and important. Not everything needs formal requirements. Not everything needs architectural review. Sometimes you just need to try something quickly.

But — and this is the critical "but" — Vibe Mode has limits. It's great for exploration. It's not great for production. The code it helps you generate isn't informed by formal requirements. There's no design review. There are no acceptance criteria to verify against.

Use Vibe Mode for learning. Use it for prototyping. Use it for experiments. But recognize when the idea has graduated from experiment to "this needs to be real" — and that's when you switch to Spec Mode.

---

### Slide 19: Spec Mode
**⏱️ Duration: 2.5 minutes**

Spec Mode is the star of this workshop. It's the production-oriented workflow that embodies everything we've been discussing: structure creates freedom.

[SCREENSHOT: Show the Spec panel with the phase indicators]

The workflow is: Requirements → Design → Tasks → Implementation. Notice what comes first. Not code. Not even design. *Requirements*. What are we building? For whom? What defines success?

Each phase produces a document. Requirements.md captures what needs to be true. Design.md captures how we'll make it true. Tasks.md breaks the how into actionable steps. Only then does implementation begin.

[DIAGRAM: Pipeline showing the four stages with deliverables]

And here's what makes this different from just "write requirements before coding": Kiro *enforces* the workflow. It helps you generate each document, it analyzes them for gaps and ambiguities, it ensures the design addresses all requirements, it ensures tasks cover the full design.

This is spec-driven development: the specification drives the implementation, not the other way around. AI finally makes this practical because the tedious parts — writing detailed acceptance criteria, checking for gaps, generating task breakdowns — are handled by the AI within the structured workflow.

---

### Slide 20: When to Stop Vibe Coding
**⏱️ Duration: 2 minutes**

This is a strong talking point and I want to be explicit about it: there's a moment in every project where you should stop vibe coding and start speccing.

How do you know when that moment arrives? Three signals:

First, requirements are becoming clear. You started exploring vaguely — "what if we built a notification system?" — and now you're saying specific things: "users need email and SMS, with opt-in preferences, and rate limiting." When requirements crystallize, it's time to capture them formally.

Second, architecture is emerging. You've prototyped enough to see the shape of the system. You know which services you'll need, how they'll communicate, where data lives. That emerging architecture needs to be documented before you build on it.

Third, production planning begins. The moment someone asks "when will this be ready?" or "can we deploy this?" — you've left sandbox territory. Production demands accountability, and accountability demands specification.

The discipline is in recognizing this transition point. Kiro doesn't force you — you can vibe code forever if you want. But Spec Mode is there for the moment you realize "this needs to be real."

---

### Slide 21: Spec-Driven Workflow
**⏱️ Duration: 3 minutes**

Let me walk you through the full workflow. I'm going to spend extra time here because this is the core methodology.

[DIAGRAM: Full workflow with review loops — show this prominently]

It starts with an Idea. Maybe a user story, maybe a bug report, maybe a stakeholder request. You bring that idea to Kiro.

Phase 1: Requirements. Kiro helps you articulate what needs to be true. Not how to build it — what the system should *do*. User stories. Acceptance criteria. Constraints. These get reviewed — by you, by your team, by stakeholders. If they're wrong, you revise before moving forward.

Phase 2: Design. Given approved requirements, Kiro helps you design the solution. Architecture. Data models. API contracts. Integration points. Security model. Again, review. Is this the right approach? Does it address all requirements? Are there risks?

Phase 3: Tasks. Given approved design, Kiro breaks the work into implementable tasks. Each task is scoped, has clear acceptance criteria, and references the relevant requirement and design section.

Phase 4: Implementation. Now — and *only* now — you write code. But you're not writing code in a vacuum. You're implementing against a specification. You know what "done" looks like because you defined it upfront.

The review loops are critical. Fixing a requirement is cheap — it's just text. Fixing a design is more expensive but still manageable. Fixing implementation is expensive. Fixing production bugs is very expensive. This workflow pushes problems left, where they're cheapest to solve.

---

### Slide 22: Gather Requirements
**⏱️ Duration: 2.5 minutes**

Let's go deeper into the requirements phase.

Have Kiro start with questions — not answers. This is deliberate. The hardest part of building software isn't the building, it's knowing what to build.

I use a three step approach before I even have Kiro start generating a requirements document.

First I write out an EXPLORATORY.md or even an INITIAL-SPEC.md (depending on my mood for the day). This is where I propose ideas and ask Kiro questions, request recommendations and options to be placed in RECOMMENDATIONS.md.

From this, I then create SPEC.md, where I gather everything I know including external API specs, user requirements, incorporate the recommendations, ask myself or my team clarifying questions, and start to piece together how I understand the requirements.

Then, I give Kiro SPEC.md and request it to review and ask any clarifying questions (with recommendations) in SPEC-QUESTIONS.md. Once I have answered all questions in SPEC-QUESTIONS.md, Kiro can review and begin on the requirements. I even tell Kiro, if there are remaining questions, pose them in SPEC-QUESTIONS-2.md if needed.

In this process, before we even formalize the requirements, we capture the raw idea, then systematically refine it into structured requirements with user stories and acceptance criteria.

What makes this powerful is the AI-assisted analysis we can introduce. Kiro analyzes our specifications for ambiguities, inconsistencies, and gaps. "You said users need to upload files, but you didn't specify size limits or allowed types." "You mentioned authentication but didn't clarify whether existing users migrate or register fresh."

These are the questions that, without a formal process, don't often get asked until implementation — when the answer is expensive. The specs and requirements phase makes them explicit upfront.

Each requirement gets formal acceptance criteria — testable statements that define when the requirement is satisfied. This becomes the contract between what was requested and what gets built.

---

### Slide 23: Architect Review Loop
**⏱️ Duration: 2 minutes**

Before we design, we review. And the review isn't just "does this look right?" — it's structured.

Kiro generates recommendations based on the requirements. These are architectural suggestions: "Given the real-time requirement, consider WebSockets over polling." "Given the data volume, consider DynamoDB over RDS." These aren't mandates — they're informed suggestions for the team to evaluate.

[Reference RECOMMENDATIONS.md from your project documentation]

The review loop includes questions back to the team. "You specified 99.9% availability — does that apply to all endpoints or just critical paths?" "You mentioned third-party integration — is there an existing service account or do we need to provision one?"

Clarifications get folded back into the requirements. This iterative refinement is the heart of good engineering: asking questions costs nothing compared to building the wrong thing.

I typically go through the requirements document and if something needs changing I just write an inline note:

```md
**TODO:** Change this to ... or I want to clarify that ...
```

Once I have reviewed and added notes, I have Kiro review, make my suggested changes, and move on. Multiple people can review if you commit your Kiro directory to your project's repository.

In a team setting, this review happens asynchronously. The architect reviews the requirements document, leaves comments, and the document gets updated. Kiro can help synthesize feedback from multiple reviewers into updated requirements. The goal is consensus before commitment.

---

### Slide 24: Design Phase
**⏱️ Duration: 2.5 minutes**

Once requirements are approved, we design. And "design before implementation" is the cheapest possible place to make architectural decisions.

[SCREENSHOT: Show a design.md with architecture section, data models, API contracts]

The design document covers: Architecture — what components exist and how they interact. Security — authentication, authorization, data protection. Data models — schemas, relationships, migrations. Integrations — external services, APIs, event flows. And diagrams — visual representations of the system.

Here's why this phase matters: fixing a design mistake costs significantly less than fixing an implementation mistake. If the design says "use a queue between these services" and review reveals that's wrong, changing the design document takes minutes. Changing implemented code with deployed infrastructure takes days.

Kiro generates the design informed by your requirements *and* your steering documents. So the design already reflects your team's architectural standards. It already uses your preferred patterns. It already addresses your security requirements.

The design also becomes documentation. When a new team member joins six months from now, the design document explains *why* the system is built the way it is — not just *how*.

---

### Slide 25: Tasks Phase
**⏱️ Duration: 2 minutes**

Only now do we plan implementation. And I want to emphasize that point because many developers want to start here. "Just give me the tasks." But tasks without requirements and design are just guesses.

With approved requirements and design, the task breakdown is grounded in reality. Each task maps to a specific design component. Each task has clear acceptance criteria derived from the requirements. Each task is scoped to be completable independently.

Trust the process. I know it feels slower to go through requirements and design first. But the tasks you get are *better*. They're properly scoped. They account for dependencies. They include testing criteria. They don't have hidden assumptions.

And once you have tasks? Now you can actually estimate. Now you can parallelize work across team members. Now you can track progress meaningfully. Because "implement the user authentication flow per design section 3" is a real, completable task — unlike "figure out auth."

---

### Slide 26: Opinionated Platforms
**⏱️ Duration: 2.5 minutes**

Let's zoom out to a bigger picture: opinionated platforms. The idea is that developers should start with 90% of their needs already solved.

[DIAGRAM: Platform layers — show that business logic sits on top of pre-built infrastructure]

CI/CD? Defined. Monitoring and alerting? Configured. Logging and tracing? Integrated. Security controls? Applied. Infrastructure patterns? Templated. Standards and compliance? Encoded.

Reference our Atlantis platform and platform engineering approach: platform engineers build and maintain these foundational layers. Developers build on top of them.

Why does this matter for Kiro and spec-driven development? Because opinionated platforms reduce the *scope* of what you need to design. If deployment is standardized, your design document doesn't need a deployment section. If monitoring is built in, you don't need to design observability. You focus on business logic.

Steering documents encode platform opinions into AI context. So when Kiro helps you design a new service, it already knows to use the platform's CI/CD pipeline, to follow the platform's security patterns, to use the platform's logging library. The 90% that's pre-decided doesn't need to be re-decided.

This reduces risk, saves tokens, and makes management and maintenance tasks sustainable.

This is structure creating freedom at the organizational level.

---

### Slide 27: Building Standards Analogy
**⏱️ Duration: 2 minutes**

Let me make this concrete with an analogy. Think about building standards across industries.

Homes: nobody designs a new electrical wiring standard for each house. There are codes. Builders follow them. You focus on floor plans and finishes — the parts that matter to the homeowner.

Cars: no manufacturer designs a new screw thread for each model. There are standards. They focus on what differentiates their vehicle — performance, comfort, features.

Satellites: even in cutting-edge aerospace, standard bus architectures provide power, communications, and attitude control. Mission teams focus on the payload — the science instrument or communications package that's unique. (Even with Starlink and AWS Leo, a different team or company builds, manages, and maintains the the launch pad and carrier vehicle.)

Cloud platforms should work the same way. Your platform provides the standard infrastructure — networking, security, deployment, monitoring. Your development teams focus on the payload — the business logic that differentiates your product.

When AI understands this distinction — through steering documents and platform templates — it stops suggesting you reinvent standard infrastructure and starts helping you with the genuinely novel parts of your system. Focus on business logic, not plumbing.

---

### Slide 28: Interactive Exercise
**⏱️ Duration: 10 minutes**

Now it's your turn. We're going to walk through the spec-driven workflow together using a practical example: a Campus Event Management System.

Here's the scenario: the university needs a system for students to discover, register for, and manage campus events. Think club meetings, speaker series, career fairs, intramural signups.

We're going to work through this in phases, just like we discussed:

1. **Exploration** (3 minutes): What are the user types? What must the system do? What are the constraints? I want you to think about: Who registers? Who creates events? What about capacity limits? Waitlists? Notifications?

2. **Specs** (2 minutes): Given those recommendations from Kiro, what architectural decisions surface? Should this be a mobile app, web app, or both? What about authentication — university SSO? Where does event data live?

3. **Spec Questions** (2 minutes): If Kiro has questions, answer them.

3. **Requirements** (2 minutes): Review and make a small change for Kiro to update.

3. **Design** (2 minutes): Review.

4. **Tasks** (2 minutes): Given the design, what are the first five implementable tasks?

[Facilitate group discussion or individual think time at each phase. Use Kiro live if possible to demonstrate the actual spec generation.]

Notice how each phase builds on the previous one. Notice how questions in the requirements phase prevent problems in the design phase. This is the spec-driven development workflow in practice.

---

### Slide 29: Common Pitfalls
**⏱️ Duration: 2 minutes**

Before we wrap up, let me summarize the anti-patterns I see teams fall into.

**Skipping requirements.** "We know what we need, let's just build it." No, you don't. Every time I hear this, the project hits ambiguity within the first week. Requirements aren't bureaucracy — they're clarity.

**Over-trusting AI.** AI generates confident-sounding code that might be subtly wrong. Without requirements and acceptance criteria to verify against, how would you know? AI is a tool, not an oracle. It needs guardrails.

**Ignoring standards.** "It works, ship it." Until it doesn't work. Until the next person can't maintain it. Until the security review catches it. Standards exist because someone learned a lesson the hard way. Encode those lessons in steering documents.

**Starting from scratch.** Every new project reinvents infrastructure decisions. "How should we do logging?" "What's our deployment strategy?" These should be solved once by the platform and reused everywhere. Don't rebuild the plumbing for every house.

Each pitfall has the same root cause: prioritizing speed over sustainability. AI makes speed trivial — sustainability is now the differentiator. With AI, sustainability is now attainable for every organization and developer.

---

### Slide 30: Key Takeaways
**⏱️ Duration: 2.5 minutes**

Let me leave you with four messages.

**Structure creates freedom.** Standards, specifications, and opinionated platforms don't slow you down — they remove the decisions that don't matter so you can focus on the decisions that do. This is the central insight.

**AI amplifies process.** Good process plus AI equals exceptional productivity. Bad process plus AI equals exceptional chaos. Invest in your process — steering documents, spec-driven workflows, platform standards — and AI becomes dramatically more valuable.

**Plan first, build second.** Requirements → Design → Tasks → Implementation. This order matters. It's not waterfall — it's front-loading the thinking that you'd do anyway. AI makes this planning phase fast enough to be practical.

**Reduce technical debt.** Every line of AI-generated code that doesn't meet your standards is debt. Every architectural decision made without context is debt. Every feature built without requirements is debt. The spec-driven approach doesn't eliminate debt, but it dramatically reduces how much gets created in the first place.

AI finally makes good software engineering affordable. The thinking, the documentation, the review — the parts that felt expensive and slow — AI handles the tedious aspects while you maintain the judgment and decision-making. That's the promise of Kiro and spec-driven development.

Thank you. Questions?

---

## Supplemental Slide Content

### Supplemental: Kiro Setup Guide

```
1. Install Kiro IDE from kiro.dev
2. Open your workspace
3. Create .kiro/ directory structure:
   .kiro/
   ├── steering/
   │   └── standards.md
   ├── settings/
   │   └── mcp.json
   └── specs/
       └── (generated by spec workflow)
4. Configure MCP servers in mcp.json
5. Add steering documents for your team's standards
6. Start with Vibe Mode to explore, transition to Spec Mode for production
```

### Supplemental: Steering Document Template

```markdown
---
inclusion: auto          # auto | fileMatch | manual
fileMatchPattern: '*.ts' # (only for fileMatch inclusion)
---

# [Standard Name]

## Overview
Brief description of what this steering document covers.

## Rules
- Rule 1: Specific, actionable guidance
- Rule 2: Reference to external standard
- Rule 3: Pattern to follow

## Examples
Good: [example]
Bad: [example]

## References
- #[[file:docs/architecture.md]]
- Link to external documentation
```

### Supplemental: MCP Server Configuration

```json
{
  "mcpServers": {
    "aws-docs": {
      "command": "uvx",
      "args": ["awslabs.aws-documentation-mcp-server@latest"],
      "env": { "FASTMCP_LOG_LEVEL": "ERROR" },
      "disabled": false,
      "autoApprove": []
    },
    "internal-wiki": {
      "command": "node",
      "args": ["./tools/wiki-mcp-server.js"],
      "env": { "WIKI_URL": "https://wiki.internal.example.com" },
      "disabled": false,
      "autoApprove": ["search", "read"]
    }
  }
}
```

### Supplemental: Hook Configuration Examples

```json
{
  "name": "Run Tests After Task",
  "version": "1.0.0",
  "when": { "type": "postTaskExecution" },
  "then": { "type": "runCommand", "command": "npm run test" }
}
```

```json
{
  "name": "Lint on Save",
  "version": "1.0.0",
  "when": { "type": "fileEdited", "patterns": ["*.ts", "*.tsx"] },
  "then": { "type": "runCommand", "command": "npm run lint" }
}
```

```json
{
  "name": "Security Review for Write Operations",
  "version": "1.0.0",
  "when": { "type": "preToolUse", "toolTypes": ["write"] },
  "then": { "type": "askAgent", "prompt": "Verify this operation follows security standards" }
}
```

### Supplemental: Spec File Structure

```
.kiro/specs/
└── campus-event-system/
    ├── .config.kiro          # Spec type & workflow config
    ├── requirements.md       # User stories & acceptance criteria
    ├── design.md             # Architecture & technical design
    └── tasks.md              # Implementation task list

Requirements.md includes:
- Introduction & glossary
- Numbered requirements with user stories
- Acceptance criteria per requirement
- Correctness properties (for property-based testing)

Design.md includes:
- High-level architecture (components, interactions)
- Data models & schemas
- API contracts
- Security design
- Integration points

Tasks.md includes:
- Dependency graph
- Ordered tasks with acceptance criteria
- References to requirements & design sections
```

### Supplemental: Resources & Links

```
Kiro IDE:             https://kiro.dev
Kiro Documentation:   https://kiro.dev/docs
AWS MCP Servers:      https://github.com/awslabs/mcp
Atlantis MCP Servers: https://mcp.atlantis.63klabs.net
Sample Repository:    https://github.com/chadkluck/workshop-kiro-spec-driven

Related Concepts:
- Spec-Driven Development
- Property-Based Testing
- Platform Engineering
- AWS Well-Architected Framework
- Serverless-First Architecture
```

### Supplemental: Glossary

| Term | Definition |
|------|-----------|
| Steering Document | Markdown file that encodes team standards for AI context |
| MCP Server | Model Context Protocol server providing trusted knowledge to AI |
| Hook | Event-driven automation that triggers on IDE events |
| Vibe Mode | Exploratory, conversational AI interaction mode |
| Spec Mode | Structured workflow: requirements → design → tasks → implementation |
| Property-Based Testing (PBT) | Testing approach using formal correctness properties |
| Acceptance Criteria | Testable conditions that define when a requirement is satisfied |
| Opinionated Platform | Pre-configured infrastructure that reduces decision-making |
| Agentic IDE | Development environment where AI acts as an active collaborator |
| Cognitive Load | The mental effort required to process information and make decisions |
