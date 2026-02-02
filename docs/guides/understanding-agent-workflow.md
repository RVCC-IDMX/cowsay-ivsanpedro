# Understanding Agent workflow

When you give Agent a task, it doesn't just instantly produce code. It follows a process you can watch in the chat panel. Understanding this process helps you work with Agent more effectively.

## The five phases

Agent works through these phases for each task:

### 1. Analyze

**What's happening:** Agent reads your project files to understand what already exists.

**What you see:** Messages like "Checking for package.json" or "Looking at project structure"

**Why it matters:** Agent needs to understand your current project before it can add to it. This is why Agent can work across multiple files—it sees the whole picture.

### 2. Plan

**What's happening:** Agent decides what changes to make and in what order.

**What you see:** Agent explains its approach: "I'll configure your npm settings, then initialize the project and install cowsay..."

**Why it matters:** This is your chance to catch misunderstandings. If Agent's plan doesn't match what you wanted, say so before it starts making changes.

### 3. Execute

**What's happening:** Agent writes or modifies code in your files.

**What you see:** Code changes appear with additions highlighted. Agent shows you exactly what it's adding or changing.

**Why it matters:** You can review the changes before accepting them. If something looks wrong, you can reject or request modifications.

### 4. Verify

**What's happening:** Agent checks if its changes make sense and work together.

**What you see:** Sometimes Agent will note potential issues or explain why it made certain choices.

**Why it matters:** Agent catches some of its own mistakes during this phase.

### 5. Iterate

**What's happening:** If something didn't work or you want changes, Agent adjusts.

**What you see:** Agent acknowledges your feedback and makes another round of changes.

**Why it matters:** The conversation continues until you're satisfied. You're not stuck with the first attempt.

## Watching Agent work

When you give Agent a prompt, pay attention to the chat panel. You'll see:

1. **Thinking indicators** — Agent is processing your request
2. **File references** — Agent mentions which files it's examining
3. **Plan explanation** — Agent describes what it intends to do
4. **Code proposals** — The actual changes, with Accept/Reject options

This transparency helps you understand what Agent is doing and why.

## The accept/reject decision

After Agent proposes changes, you have choices:

| Option                    | When to use it                                         |
| ------------------------- | ------------------------------------------------------ |
| **Accept**                | The changes look correct and complete                  |
| **Reject**                | The changes are wrong or you want a different approach |
| **Ask for modifications** | Close, but needs adjustments                           |

**Before accepting, ask yourself:**

- Did Agent modify the files I expected?
- Does the code look reasonable (even if you don't understand every line)?
- Did Agent change anything I didn't ask it to change?

You can always undo (`Cmd+Z` / `Ctrl+Z`) after accepting if you change your mind.

## Why Agent reads multiple files

Unlike Ask mode (which focuses on one file), Agent looks at your whole project. This allows it to:

- **Understand structure:** Agent sees your package.json, existing docs, and project layout
- **Maintain consistency:** Agent matches the style of existing configuration
- **Make coordinated changes:** Setting up npm might involve config commands, creating package.json, and installing packages

This is powerful, but it also means Agent might change files you didn't expect. Always review the full list of proposed changes.

## When Agent gets stuck

Sometimes Agent's process doesn't go smoothly:

### "I don't have enough context"

Agent might ask questions because it needs more information:

> "What email should I use for the npm author config?"
> "Should I install cowsay as a regular dependency or dev dependency?"

Answer the questions, and Agent will continue.

### "I'm not sure what you want"

If your prompt was vague, Agent might:

- Ask for clarification
- Make assumptions (which might be wrong)
- Propose multiple options

Be more specific in your follow-up.

### Circular fixes

Sometimes Agent fixes one thing but breaks another, then fixes that but breaks the first thing again. If this happens:

> "Let's start fresh. Delete package.json and reinitialize the project with npm init."

## Ask mode vs Agent mode

Understanding when to use each:

| Use Ask mode when...           | Use Agent mode when...                 |
| ------------------------------ | -------------------------------------- |
| You have a question            | You want something built or installed  |
| You need an explanation        | You need commands run or files created |
| You're exploring ideas         | You're ready to set up                 |
| You want to discuss approaches | You want configuration done            |

**Example:**

- Ask mode: "What does the scripts section in package.json do?"
- Agent mode: "Initialize npm and install cowsay"

You can switch between modes anytime using the mode selector in Copilot Chat.

## The Agent advantage

Agent's ability to run commands and create files is what makes it powerful for project setup:

**Example task:** "Configure npm and install cowsay"

**What Agent does:**

1. Checks if npm is available
2. Runs `npm config set` commands for your author info
3. Runs `npm init --yes` to create package.json
4. Runs `npm install cowsay` to add the dependency
5. Verifies everything was created correctly

All of this happens automatically. You just describe what you want.

## Summary

- Agent follows five phases: Analyze → Plan → Execute → Verify → Iterate
- Watch the chat panel to see what Agent is doing
- Review proposed changes before accepting them
- Agent reads multiple files to understand your project context
- Use Ask mode for questions, Agent mode for building
- If Agent gets stuck in a loop, start fresh with a clear prompt
