# Writing prompts for Agent

Getting good results from Copilot Agent starts with how you ask. This guide shows you how to write prompts that help Agent understand what you want.

## The basics: Be specific

Agent works best when you tell it exactly what you want. Compare these prompts:

| Vague prompt        | Specific prompt                                                                           |
| ------------------- | ----------------------------------------------------------------------------------------- |
| "Set up npm"        | "Configure npm with my name (Jane Smith) and email (jane@example.com), then run npm init" |
| "Install something" | "Install cowsay as a dependency"                                                          |
| "Make a script"     | "Add an npm script called 'moo' that runs 'cowsay Hello!'"                                |

The specific prompts give Agent clear direction. The vague prompts leave Agent guessing—and it might guess wrong.

## The anatomy of a good prompt

A helpful prompt often includes:

1. **What** you want (the action or result)
2. **Details** that matter (names, values, options)
3. **Context** if needed (why you want it)

**Example:**

> "Configure npm with my author information: Name is 'Your Name', email is 'your@email.com', and license should be MIT. Then initialize a new project with npm init."

This prompt tells Agent:

- **What**: Configure npm and initialize
- **Details**: Specific name, email, and license
- **Context**: It's for a new project

## Start simple, then refine

You don't need to describe everything in one prompt. It's often better to:

1. Start with a basic request
2. See what Agent does
3. Ask for adjustments

**Example conversation:**

> **You:** "Initialize npm and install cowsay"
>
> **Agent:** _Runs npm init and npm install cowsay_
>
> **You:** "Add a script called 'moo' that runs cowsay with a greeting"
>
> **Agent:** _Adds the script to package.json_
>
> **You:** "Change the greeting to say 'Hello from npm!'"
>
> **Agent:** _Updates the script_

This iterative approach is how professionals work with AI tools. You don't need to think of everything upfront.

## Prompts for common Week 2 tasks

### Setting up npm

```text
Configure npm with my author information: Name is "Your Name", email is "your@email.com", license is MIT.
```

```text
Initialize a new npm project with default values.
```

```text
Install cowsay as a dependency.
```

### Working with scripts

```text
Add an npm script called "cowsay" that runs the cowsay command.
```

```text
Add a script called "moo" that runs cowsay with the message "Hello World".
```

```text
Add a script that uses the tux character to say "Linux rules!".
```

### Creating documentation

```text
Create a file called docs/tutorial-package-json.md that explains each field in my package.json for a beginner.
```

```text
Create a reference file listing my favorite cowsay creatures with example commands.
```

```text
Add a troubleshooting section to the README with common npm errors.
```

## What to avoid

### Too vague

> "Set it up"

Agent doesn't know what "it" refers to or what setup means to you.

### Too complex all at once

> "Configure npm with my info, initialize the project, install cowsay and prettier, add scripts for both, create documentation for everything, and update the README with examples"

This is too much for one prompt. Break it into smaller pieces.

### Assuming Agent knows your preferences

> "Use the usual settings"

Agent doesn't know what's "usual" for you.

**Better:** "Configure npm with name 'Jane Smith', email 'jane@example.com', license MIT"

## When Agent asks questions

Sometimes Agent will ask for clarification:

> "What name should I use for the npm author?"
> "Should I install cowsay as a regular dependency or devDependency?"
> "What message do you want the cow to say?"

This is good! Answer the questions, and Agent will have a better understanding of what you want.

## Describing what's wrong

When something isn't working, describe:

1. **What you expected** to happen
2. **What actually happened** (or didn't happen)
3. **Any error messages** you saw

**Example:**

> "When I run 'npm run moo', I get an error saying 'cowsay is not recognized'. I expected to see a cow saying hello."

This gives Agent the information it needs to diagnose the problem.

## The feedback loop

Working with Agent is a conversation, not a one-shot request. The pattern is:

1. **Prompt** → Ask for something
2. **Review** → Look at what Agent did
3. **Refine** → Ask for adjustments or move to the next task
4. **Repeat**

Each cycle teaches you more about how to communicate with AI tools effectively.

## Practice prompts

Try these prompts with Agent and see what happens:

1. "Show me my current npm configuration"
2. "Add a script that lists all available cowsay creatures"
3. "Create a docs file explaining how npm scripts work"
4. "Update the cowsay script to use the dragon character"

After each one, use `/explain` if you don't understand what Agent did.

## Summary

- Be specific about what you want and include relevant details
- Start simple and refine through conversation
- Describe problems clearly: expected vs. actual behavior
- Answer Agent's questions to help it understand your intent
- Iterate—you don't need to get it perfect on the first try
