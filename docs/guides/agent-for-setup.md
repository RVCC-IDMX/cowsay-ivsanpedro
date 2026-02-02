# Using Agent for project setup

Agent mode excels at setup tasks—the tedious configuration work that takes time but doesn't require creativity. This guide shows you how to use Agent effectively for npm project setup.

## Why Agent is good at setup

Setup tasks are:

- **Repetitive** — You configure npm the same way for most projects
- **Command-heavy** — Lots of terminal commands to run
- **Easy to forget** — Was it `npm init -y` or `npm init --yes`?

Agent handles these tasks reliably, letting you focus on the interesting parts of your project.

## Before your first prompt

### Make sure you're in Agent mode

1. Open Copilot Chat (`Ctrl+Cmd+I` on Mac, `Ctrl+Alt+I` on Windows)
2. Look at the mode selector near the text input
3. If it says "Ask" or "Chat", click it and switch to **Agent**

Agent mode lets Copilot run commands and create files. Ask mode only answers questions.

### Make sure you're in the right folder

Agent runs commands in your current VS Code workspace. Check that:

1. You opened the correct project folder in VS Code
2. The terminal shows you're in that folder

## Writing setup prompts

### Be specific about what you want

**Vague prompt:**

```text
Set up npm
```

Agent might not know exactly what configuration you want.

**Specific prompt:**

```text
Configure npm with my author information:
- Name: Jane Smith
- Email: jane@example.com
- License: MIT

Then initialize a new npm project and install cowsay.
```

This tells Agent exactly what to do.

### Include your actual information

Replace placeholder values with your real information:

- Your actual name
- Your actual email (use your school email)
- The license you want (MIT is common)

### One setup, multiple steps

You can ask Agent to do several setup steps in one prompt:

```text
1. Set my npm author name to "Your Name"
2. Set my npm author email to "your@email.com"
3. Set the default license to MIT
4. Run npm init with default values
5. Install cowsay as a dependency
```

Agent will run each step in order.

## What to watch for

### Agent shows its plan

Before running commands, Agent explains what it's going to do:

> "I'll configure your npm settings, then initialize the project and install cowsay. This will create package.json and download cowsay to node_modules."

Read this to make sure Agent understood your request.

### Agent asks for permission

Agent will show you each command before running it:

```bash
npm config set init-author-name "Your Name" -g
```

You can **Accept** to let it run, or **Reject** if something looks wrong.

### Commands run in the terminal

Watch the terminal panel at the bottom of VS Code. You'll see:

- Commands being executed
- Output from those commands
- Any errors that occur

## Common setup prompts

### Basic npm setup

```text
Configure npm with my author information (Name: Your Name, Email: your@email.com, License: MIT), then initialize a new project and install cowsay.
```

### Check current configuration

```text
Show me my current npm configuration using npm config list.
```

### Install additional packages

```text
Install prettier as a dev dependency.
```

### Explain terminal output

```text
What does this npm output mean? Is it an error or just a warning?
```

## After Agent finishes

### Verify the results

Check that Agent did what you expected:

1. **package.json exists** — Look in the file explorer
2. **Your author info is there** — Open package.json and check the author field
3. **cowsay is installed** — Check the dependencies section
4. **node_modules exists** — A folder appeared with installed packages

### Use /explain if confused

If Agent did something you don't understand:

1. Select the relevant part of package.json (or terminal output)
2. Type `/explain`
3. Read the explanation

### Don't worry about mistakes

If something went wrong:

- Ask Agent to fix it: "The author name is wrong. Change it to 'Correct Name'."
- Or delete package.json and start over: "Remove package.json and reinitialize the project."

Setup is easy to redo. That's one reason Agent is good for it.

## Agent vs. doing it yourself

| Task                        | Agent               | Yourself                             |
| --------------------------- | ------------------- | ------------------------------------ |
| Running npm commands        | Fast, no typos      | Slower, might forget syntax          |
| Remembering flags           | Perfect memory      | Might need to look up                |
| Understanding what happened | You watch and learn | You type but might not understand    |
| Editing package.json        | Can do it           | Better done by hand (you learn more) |

**Recommendation:** Use Agent for initial setup commands. Edit `package.json` scripts yourself to learn the syntax.

## Summary

- Switch to Agent mode before giving setup prompts
- Be specific about your name, email, and what packages to install
- Watch Agent's plan and the terminal output
- Use `/explain` if you don't understand what happened
- Agent handles setup; you handle the creative work
