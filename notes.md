# AI for real engineers

My personal notes taken throughout the [AI Coding for Real Engineers](https://www.aihero.dev/cohorts/claude-code-for-real-engineers-2026-04) cohort. This is a 2-week course where we explore how to use Claude Code — an AI coding assistant built by Anthropic — to build and maintain a full-stack course platform.

## Day 1: Fundamentals

LLM constraints, subagents, cobebase exploration, building features.

### The constraints of LLMS

The context window, is the first and main constraint of LLMs. It represents the amount of information the model can consider at once. As the amount of information in the context window increases, the cost of using the model also increases and it starts to get dumber, which is specially noticeable when we are using more than 40% of the context window.

Additionally, LLMs are stateless, which means that they don't have memory of previous interactions. This can be a problem when we want to build complex applications that require multiple interactions with the model.

### Subagents

Subagents are specialized agents that can be called by the main agent to perform specific tasks. They can help to overcome the limitations of the main agent by providing additional capabilities or expertise. They also help to keep the main agent's context window clear by offloading specific tasks to the subagents.

### Exploring the codebase

When willing to explore the codebase in depth it's important to use the word "explore" instead of words like "understand" or "read", as it triggers the exploration subagent, which is designed to navigate and understand the codebase. It's also important to provide specific instructions on what we want to explore, such as "explore the user authentication flow" or "explore the database schema" so that the subagent can focus on the relevant parts of the codebase.

### Plan Mode

Plan mode is a feature of Claude Code that allows us to create a plan for a specific task or feature. It helps to break down complex tasks into smaller, manageable steps and provides a clear roadmap for implementation. To use plan mode, we can simply say "Let's switch to plan mode" and then provide the details of the task or feature we want to implement. The model will then generate a plan with the necessary steps to complete the task.

### Plan Execution Clear Loop

The plan execution clear loop is a technique used to ensure that the model stays focused on the task at hand and doesn't get overwhelmed by the amount of information in the context window. 

It involves executing the following steps:

1. Create a plan for the task or feature we want to implement.
2. Execute the plan.
3. Check if we entered the dumb zone.
4. If we entered the dumb zone, clear the context window and start again from step 1.
5. If we didn't enter the dumb zone, continue with the implementation.
6. Repeat it until the task or feature is complete and all the bugs are fixed.

### Compaction

Compaction is a technique used to reduce the amount of information in the context window by summarizing or condensing it. This can be useful when we have a lot of information that we want to keep in the context window, but we don't want to exceed the limits. To use compaction, we can simply say "Let's compact this information" and then provide the details of what we want to compact. The model will then generate a condensed version of the information that can fit within the context window.

## Day 2: Steering

Agent files (CLAUDE.md), skills, memory, custom workflows.

### Agents.md

You can think of `AGENTS.md` as a readme for agents, a dedicated predictable place to provide the context and instructions to help AI coding agents work on your project. The appeal of `AGENTS.md` is how many places it is supported by, or rather how many tools use it. Gemini CLI, Devin, Codex, Cursor. The very notable exception here is actually Claude Code. Claude Code doesn't use AGENTS.md and doesn't recognise it, it uses instead a file called `CLAUDE.md`, which serves the same purpose but is specific for Claude Code.

_What should I include in `AGENTS.md`?_

Since your `AGENTS.md` is always going to be included in your context window, it's important to keep the file lean and focused on the most important information. Some of the most common sections to include in `AGENTS.md` are:

- **Project Overview**: A brief description of the project, its purpose, and its main features.
- **Architecture**: An overview of the project's architecture, including the main components and how they interact with each other.
- **Key Files and Directories**: A list of the most important files and directories
- **Coding Standards and Conventions**: Any specific coding standards or conventions that should be followed when working on the project.
- **Common Tasks and Workflows**: A description of common tasks and workflows for working on the project, such as how to run tests, how to deploy the application, etc.
- **Resources and References**: Links to important resources and references, such as documentation, design documents, API references, etc.

### Prograssive disclosure

Progressive disclosure is a technique used to manage the amount of information in the context window by revealing information gradually as needed. This can be useful when we have a lot of information that we want to keep in the context window, but we don't want to overwhelm the model with too much information at once. 

In the `AGENTS.md` file, we can use progressive disclosure by organizing the information in a way that allows us to reveal more details as needed. For example, we can start with a high-level overview of the project and then provide links to more detailed sections for specific topics. This way, the model can focus on the most relevant information without getting overwhelmed by too much detail at once.

So intead of having a long `AGENTS.md` file like this oe:

![Long AGENTS.md file](./docs/images/without-progressive-disclosure.png)

We can have a more concise `AGENTS.md` file that uses progressive disclosure like this one:

![AGENTS.md file with progressive disclosure](./docs/images/with-progressive-disclosure.png)

### Agent Skills

Agent skills are a simple, open format for giving agents new capabilities and expertise. They are basically folders of instructions, scripts, and resoureces that agents can discover and use to do things more accurately and efficiently.

You can find more information about agent skills in the [official documentation](https://agentskills.io/home).

Matt Pocock suggests that when we are going to create an agent skill, we should do that using a skill like [this one](https://github.com/mattpocock/skills/blob/main/write-a-skill/SKILL.md), which provides a clear structure and format for the skill, making it easier for the model to understand and use it effectively.

### Automatic Memory

Automatic memory is a feature of Claude Code that allows the model to remember information from previous interactions and use it in future interactions. This can be useful for maintaining context and continuity in conversations with the model, especially when working on complex projects with a log of gotchas.

On the other hand though, there is also the risk of the model remembering incorrect information or getting confused by conflicting information. To mitigate this risk, it's important to regularly review and update the model's memory to ensure that it remains accurate and relevant.


