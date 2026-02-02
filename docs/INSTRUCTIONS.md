# Week 2: Use Agent mode

```text
_______
< Hello world! >
 -------
   \
    \
     \
        __ \ / __
       /  \ | /  \
           \|/
       _.---v---.,_
      /            \  /\__/\
     /              \ \_  _/
     |__ @           |_/ /
      _/                /
      \       \__,     /
   ~~~~\~~~~~~~~~~~~~~`~~~

```

> **Before you begin:** Following detailed, step-by-step instructions is a core developer skill. Technical documentation, setup guides, and onboarding procedures are part of every professional environment. Take your time and keep track of where you are. If something doesn't work as expected, first ask your AI agent for help—describe what you tried and what happened. If you're still stuck, reach out to your team and then your instructor.

## Overview

This week you will use Copilot Agent to set up a real npm project, then experiment with cowsay—a fun command-line tool that makes ASCII art animals say things. Along the way, you'll create a documentation file with Agent's help, learning how to turn AI assistance into lasting knowledge.

## Learning objectives

By completing this assignment, you will be able to:

- Use Agent mode for project setup tasks (npm init, install)
- Understand npm and package.json fundamentals
- Edit JSON files manually
- Run npm scripts from the terminal
- Create documentation with Agent's help

## The big picture

Software development is fundamentally about communication—with other humans, with your future self, and now with AI agents. This week focuses on tasks where AI excels: setup, documentation, and explanation. These all require translating between technical precision and human understanding.

See [ai-as-communication-tool.md](guides/ai-as-communication-tool.md) for why AI is particularly good at these tasks.

## Prerequisites

Before starting:

- Complete Week 1 (VS Code setup and Markdown basics)
- Have SpecStory installed and working
- Verify Node.js is installed (see below)

### Verify Node.js is installed

Open your terminal and run:

```bash
node --version
```

You should see a version number like `v20.11.0`. Any version starting with v18, v20, or v22 is fine. If you see "command not found," visit [nodejs.org](https://nodejs.org) and install the LTS version before continuing.

## Getting started

1. Open this folder in VS Code
2. Open Copilot Chat (`Ctrl+Cmd+I` on Mac, `Ctrl+Alt+I` on Windows)
3. Read [agent-for-setup.md](guides/agent-for-setup.md) before your first prompt
4. Review [CHECKLIST.md](CHECKLIST.md) to see what you'll submit

---

## Part 1: Let Agent set up your project

**Goal:** Use Agent mode to configure npm and install cowsay.

### Before you start

Read [npm-basics.md](tutorials/npm-basics.md) to understand what npm is and why we use it.

### Switch to Agent mode

1. Open Copilot Chat
2. Look for the mode selector dropdown (it might say "Ask", "Chat", or show an icon)
3. Switch to **Agent** mode

### Give Agent your setup prompt

Copy and paste this prompt:

```text
Initialize a new npm project and install cowsay.
```

### Watch Agent work

Agent will run two commands:

1. `npm init --yes`
2. `npm install cowsay`

**Accept the changes** when Agent prompts you.

**What to look for:** Agent will show file changes in the chat panel. Look for buttons like "Accept" or "Apply" next to each change, or an "Accept All" button at the top of the response.

### What just happened?

After Agent finishes, you should see new files in your project:

- `package.json` — Your project's configuration file
- `package-lock.json` — Automatically generated, don't edit this
- `node_modules/` — Folder containing cowsay and its dependencies

### Common npm messages you might see

| Message                              | What it means                                               |
| ------------------------------------ | ----------------------------------------------------------- |
| "X packages are looking for funding" | Normal. Package authors can request donations. Ignore this. |
| "deprecated" warnings                | Some packages use older code. Usually fine for learning.    |
| "WARN" messages                      | Warnings, not errors. Your install probably still worked.   |

If you see "ERROR" in red, something actually went wrong—check the Troubleshooting section at the end.

---

## Part 2: Understand what Agent did

**Goal:** Use `/explain` and create your first documentation file.

### Examine package.json

1. Open `package.json` in VS Code
2. Look at the fields Agent created

### Use /explain

1. Select all the contents of `package.json` (Cmd+A on Mac, Ctrl+A on Windows)
2. Open Copilot Chat
3. Type `/explain What is each field in this file?`
4. Read the explanation

### Create a tutorial doc: tutorial-package-json.md

Now you'll create a documentation file with Agent's help.

**Suggested Prompt For Agent:**

```text
Create a file called docs/tutorial-package-json.md that explains each field in my package.json file. Write it for a beginner who has never seen package.json before. Include:
- What each field means
- Why it matters
- What happens if it's missing
```

**Accept the file** Agent creates, then review it. Does it make sense? If not, ask Agent to clarify specific parts.

### CPR checkpoint

Stage and commit these files:

- `package.json`
- `package-lock.json`
- `docs/tutorial-package-json.md`

**Staging tip:** In VS Code's Source Control panel, click the **+** next to each file to stage it, then type your commit message and click Commit.

**Example commit message:** "Add package.json and tutorial docs from Part 1-2"

**Do NOT commit** the `node_modules/` folder—it should already be in `.gitignore`.

Push to GitHub and review your repo on GitHub.com to make sure everything looks right.

**Tip:** Ask Agent to write your commit message. It can see what changed and summarize it clearly. This is another communication task AI handles well.

---

## Part 3: Write your own npm scripts

**Goal:** Manually edit package.json to add cowsay scripts.

### Before you start

Read [npm-scripts.md](tutorials/npm-scripts.md) to understand how npm scripts work.

Also read [json-syntax.md](tutorials/json-syntax.md) so you don't accidentally break your JSON.

### Open package.json

Find the `"scripts"` section. It probably looks like this:

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1"
}
```

### Add cowsay scripts

**You will type this yourself** (not Agent). Add these scripts.

**Watch the commas!** Every line except the last one inside the `{ }` needs a comma. If you get a syntax error, that's usually the problem.

**Valid JSON:**

```json
"scripts": {
  "test": "echo test",
  "build": "echo build"
}
```

**Invalid JSON** (trailing comma):

```json
"scripts": {
  "test": "echo test",
  "build": "echo build",
}
```

Add these scripts:

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "cowsay": "cowsay",
  "moo": "cowsay 'Hello from npm scripts!'"
}
```

**Note about quotes:** The outer quotes must be double quotes (JSON rule), but the message inside the command can use single quotes (shell rule). That's why `'Hello from npm scripts!'` uses single quotes.

### Save and test

1. Save `package.json`
2. Open the VS Code terminal (`Ctrl+`` ` or View → Terminal)
3. Run: `npm run moo`

You should see a cow saying "Hello from npm scripts!"

**Tip:** Need a quick reference for npm commands? Check out [npm-commands.md](reference/npm-commands.md).

### CPR checkpoint

Commit `package.json` (with your new scripts) and push to GitHub.

---

## Part 4: Experiment with cowsay

**Goal:** Try cowsay's features and add a custom script.

### Reference doc available

Check out [cowsay-creatures.md](reference/cowsay-creatures.md) for a list of fun creatures and flags to try.

### Run cowsay with a message

In your terminal:

```bash
npm run cowsay -- "Hello World"
```

**Note:** The `--` tells npm to pass everything after it to the cowsay command.

### Pick a favorite creature

Browse the reference doc or run `npm run cowsay -- -l` to see all available creatures. Pick ONE favorite to use for the rest of this part.

Try your chosen creature:

```bash
npm run cowsay -- -f tux "Your message here"
```

### Try 2-3 flags

Experiment with a couple of these flags on your favorite creature:

| Flag | What it does             | Example   |
| ---- | ------------------------ | --------- |
| `-e` | Change eye characters    | `-e "@@"` |
| `-T` | Change tongue characters | `-T "U "` |
| `-W` | Set column width         | `-W 40`   |

Example combining flags:

```bash
npm run cowsay -- -f tux -e "**" "Excited penguin!"
```

### Add a custom script

Add a new line inside your `"scripts"` section in `package.json` for your favorite creature and message:

```json
"favorite": "cowsay -f dragon 'Your custom message here'"
```

Test it with `npm run favorite`.

### CPR checkpoint

Commit `package.json` (with your favorite script) and push to GitHub.

**Remember the comma rule!** When adding your `favorite` script, add a comma after the `moo` line.

---

## Part 5: Document in README

**Goal:** Update your README with cowsay output using Markdown code fences.

### Start fresh

Open `README.md` and delete its contents. The starter content was just placeholder text—your work is what matters now.

### Add your own content

Write a new README that includes:

1. A level 1 heading with your project title
2. A level 2 heading for a section
3. Your favorite cowsay output in a **code fence**

### Using code fences

To display ASCII art properly, wrap it in triple backticks. The word after the backticks (`text`, `bash`, `json`) tells renderers how to format the content—use `text` for plain ASCII art:

````markdown
```text
 _______
< Hello >
 -------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```
````

**Common mistake:** Make sure you have exactly three backticks (```) at the start AND end. If your ASCII art looks broken, check that both lines have the same number of backticks.

**How to get the output:**

1. Run your cowsay command in the terminal
2. Select the ASCII art with your mouse
3. Copy it (select the text first, then Cmd+C on Mac or Ctrl+C on Windows). Right-click > Copy also works.
4. Paste it inside the code fence in your README

### Preview your README

Right-click on `README.md` in the file explorer and select "Open Preview" to see how it looks.

### CPR checkpoint

Commit `README.md` and push. Check your repo on GitHub.com—the README should display nicely with your ASCII art visible.

---

## Part 6: Write your reflection

**Goal:** Complete your AI collaboration summary.

### Before you start

Read [ai-as-communication-tool.md](guides/ai-as-communication-tool.md) if you haven't already. It's short (5 minutes) and will help you answer the reflection questions.

### Review your work

Look at:

- Your SpecStory history (`.specstory/history/`)—this folder contains your conversation logs. If you don't see it, that's okay; you can also scroll through your Copilot Chat panel history instead.
- The tutorial doc you created with Agent
- Your README

### Complete the template

Open `ai-collaboration-summary-template.md` and fill it out. Be specific about:

- What prompts worked well
- What you had to adjust
- What you learned about working with Agent
- How creating docs helped you understand the material

**Example response** (for the "Agent mode for setup" question):

> Using Agent for npm setup was faster than typing commands myself because I didn't have to remember the exact syntax. Agent showed me what each command did as it ran them. The downside was that I initially accepted the changes without really reading what happened—I had to go back and look at my package.json to understand the result.

### Final CPR

Commit and push your completed summary.

---

## Deliverables

Submit to Canvas:

1. **GitHub repository link** containing:
   - Working npm project with cowsay installed
   - Your custom scripts in package.json
   - Your tutorial doc (docs/tutorial-package-json.md)
   - README with cowsay output in code fence

2. **AI collaboration summary** (committed to your repo)

Use [CHECKLIST.md](CHECKLIST.md) to verify everything before submitting.

---

## Quick reference

### Files you should have created

| File                                   | Created by                               |
| -------------------------------------- | ---------------------------------------- |
| `package.json`                         | Agent (Part 1), then you edited (Part 3) |
| `docs/tutorial-package-json.md`        | You with Agent (Part 2)                  |
| `README.md`                            | You (Part 5)                             |
| `ai-collaboration-summary-template.md` | Filled out by you (Part 6)               |

### Troubleshooting

| Problem                              | Solution                                                                                                                                                                                                                                                           |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `npm: command not found`             | Node.js isn't installed. Download from [nodejs.org](https://nodejs.org)                                                                                                                                                                                            |
| JSON syntax error                    | Look for red squiggly lines in VS Code. Common causes: missing comma, extra comma after last item, mismatched quotes. Try pasting your JSON into [jsonlint.com](https://jsonlint.com) to find the exact error. See also [json-syntax.md](tutorials/json-syntax.md) |
| Cowsay doesn't run                   | Make sure you're in the project folder. Run `npm install` again                                                                                                                                                                                                    |
| npm can't find package.json          | You're in the wrong folder. Make sure your terminal is in the project folder (you should see package.json in the file explorer).                                                                                                                                   |
| Agent won't create files             | Make sure you're in Agent mode, not Ask mode                                                                                                                                                                                                                       |
| Push fails with authentication error | VS Code will prompt you to sign in to GitHub. Follow the prompts. If that doesn't work, ask your instructor for help with git credentials.                                                                                                                         |
| Cowsay hangs after running           | You may have forgotten the `--` before your flags/message. Press Ctrl+C to cancel, then try again with `npm run cowsay -- "your message"`                                                                                                                          |

---

## Tips

- **Watch Agent work** — Don't just accept blindly. See what commands it runs.
- **Use /explain often** — Turn confusion into understanding.
- **CPR regularly** — Small commits are easier to track than one giant commit.
- **The docs you create are yours** — Make them useful to future-you.
