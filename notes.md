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

