# Copilot slash commands

Slash commands are shortcuts that tell Copilot Chat exactly what kind of help you want. Instead of explaining what you need in a full sentence, you type a command that triggers a specific behavior.

## How slash commands work

1. Open Copilot Chat (`Ctrl+Cmd+I` on Mac, `Ctrl+Alt+I` on Windows)
2. Type a forward slash `/`
3. A menu appears showing available commands
4. Select one or keep typing the command name
5. Optionally add more context after the command

## The slash commands you'll use most

### /explain

**What it does:** Explains selected code or content in plain language.

**When to use it:** After Agent creates files or runs commands you don't understand.

**How to use it:**

1. Select content in the editor (highlight it with your mouse or keyboard)
2. Open Copilot Chat
3. Type `/explain`
4. Press Enter

**Example:**

You select the contents of `package.json` that Agent created:

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "dependencies": {
    "cowsay": "^1.6.0"
  }
}
```

You type: `/explain`

Copilot responds with a breakdown of what each field means and why it matters.

**Pro tip:** Add context to get better explanations:

- `/explain` — Basic explanation
- `/explain what does this do?` — Same thing, slightly more conversational
- `/explain I'm a beginner, explain simply` — Asks for simpler language
- `/explain what does the ^ mean in the version?` — Focuses on a specific part

---

### /fix

**What it does:** Suggests fixes for problems in your code.

**When to use it:** When something isn't working and you're not sure why.

**How to use it:**

1. Select the code that might have a problem
2. Type `/fix`
3. Copilot analyzes the code and suggests corrections

**Example scenario:**

Your npm script doesn't run. You select the scripts section in `package.json` and type `/fix`. Copilot might notice you have a missing comma or mismatched quotes.

**Note:** You'll use `/fix` more in Week 3. For now, if something doesn't work, you can ask Agent to fix it directly: "The npm script doesn't run. Can you fix it?"

---

### /doc

**What it does:** Adds documentation comments to your code.

**When to use it:** When you want to add explanatory comments to functions.

**How to use it:**

1. Select a function or block of code
2. Type `/doc`
3. Copilot generates comments explaining what the code does

**Example:**

You select a function and type `/doc`. Copilot adds a comment block above it explaining the function's purpose, parameters, and return value.

**Note:** This is more relevant in Week 3 when you work with larger codebases.

---

### /tests

**What it does:** Generates test code for your functions.

**When to use it:** When you want to verify your code works correctly.

**Note:** You won't use this in Week 2. It's mentioned here so you know it exists.

---

### /new

**What it does:** Helps scaffold new projects or files.

**When to use it:** When starting something from scratch.

**Note:** You won't need this in Week 2 since you're working with an existing starter project.

---

## Slash commands vs. Agent mode

These are different tools that work together:

| Tool           | What it does                                | When to use                         |
| -------------- | ------------------------------------------- | ----------------------------------- |
| Agent mode     | Takes actions, runs commands, creates files | "Initialize npm and install cowsay" |
| Slash commands | Specific operations on selected content     | "Explain this package.json file"    |

**Typical workflow:**

1. Use **Agent** to set up your project
2. Use **/explain** to understand what Agent created
3. Use **/fix** if something isn't working
4. Use **Agent** again to create documentation

## Week 2 focus: /explain

For this assignment, `/explain` is your most important slash command. The workflow is:

1. **Agent runs commands** — You ask Agent to initialize npm and install packages
2. **You select content** — Highlight package.json or terminal output
3. **You use /explain** — Type `/explain` in Copilot Chat
4. **You read and understand** — Read Copilot's explanation
5. **You ask follow-up questions** — "What does dependencies mean?" or "Why is there a ^ in the version?"

This cycle—generate, explain, understand—is how you turn AI-generated content into knowledge.

## Common questions

### Do I need to select code first?

For most slash commands, yes. If you don't select anything:

- `/explain` will try to explain the entire current file (probably not what you want)
- `/fix` won't know what to fix

**Best practice:** Always select the specific code you want help with.

### Can I use slash commands in Agent mode?

Yes! Slash commands work regardless of whether you're in Ask mode or Agent mode. The mode affects how Copilot responds to general prompts, but slash commands work the same way in both.

### What if the explanation is too technical?

Ask for clarification:

- "Can you explain that more simply?"
- "What does [specific term] mean?"
- "I don't understand the part about [x]. Can you give an example?"

Copilot remembers your conversation, so follow-up questions work naturally.

### Are there other slash commands?

Yes, there are more. Type `/` in Copilot Chat to see the full list. The ones covered here are the most useful for beginners. You'll explore more in Week 3.

## Quick reference

| Command    | Purpose                    | Select code first? |
| ---------- | -------------------------- | ------------------ |
| `/explain` | Understand what code does  | Yes                |
| `/fix`     | Find and fix problems      | Yes                |
| `/doc`     | Add documentation comments | Yes                |
| `/tests`   | Generate test code         | Yes                |
| `/new`     | Start a new project/file   | No                 |

## Summary

- Slash commands are shortcuts for common Copilot tasks
- `/explain` is your most important command this week
- Always select code before using most slash commands
- Use slash commands together with Agent mode for the best workflow
- Ask follow-up questions if explanations are unclear

Next week, you'll learn more slash commands and other Copilot features like chat participants (`@workspace`, `@terminal`).
