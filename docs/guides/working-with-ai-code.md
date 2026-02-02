# Working with AI-generated content

This guide explains how to use Copilot Agent effectively as a learning tool—not just a task automator.

## What is vibe coding?

"Vibe coding" is when you describe what you want to an AI tool and accept whatever it generates without really understanding it. You give the AI the "vibe" of what you want, and it handles the details.

The term comes from how people sometimes use AI coding assistants: describe a task, hit accept, move on. It works—the command runs—but you haven't learned anything.

**Vibe coding is not inherently bad.** Professional developers sometimes vibe code when doing repetitive setup tasks. But in a learning context, there's a problem: if you don't understand what the AI did, you're not building skills you can use later.

## The goal of this assignment

This week, Copilot Agent will run commands and create files for you. **This is intentional.** Agent mode is a legitimate professional tool, and learning to use it effectively is valuable.

But here's the expectation: you should understand what Agent did. That's why the `/explain` command exists—it turns commands you didn't type into knowledge you can apply.

## The engagement spectrum

Think of AI-assisted work as a spectrum:

| Level     | What it looks like                                   | Learning value |
| --------- | ---------------------------------------------------- | -------------- |
| Pure vibe | Accept without reading                               | None           |
| Passive   | Read the output but don't investigate                | Minimal        |
| Active    | Use `/explain`, ask follow-up questions              | Good           |
| Engaged   | Modify the result, experiment, try variations        | High           |
| Mastery   | Could explain or recreate the core concepts yourself | Full           |

**Your target for this assignment:**

- **npm commands and package.json**: Active or Engaged level. Use `/explain` and be able to describe what each part does.
- **Terminal output**: At least Passive level. Know what success and failure look like.

## What good engagement looks like

### Example: Setting up npm

Here's how an engaged student might work with Agent:

**Step 1: Give Agent a task**

> "Configure npm with my author info and initialize the project"

Agent runs several commands and creates package.json.

**Step 2: Read what Agent created**

Don't just click "Accept." Look at the output first. Notice:

- Commands that ran in the terminal
- package.json appeared in your file explorer
- node_modules folder appeared after install

**Step 3: Use `/explain` on package.json**

Select the contents and ask:

> "/explain What does each field in this file mean? I'm a beginner."

Copilot will break it down field by field.

**Step 4: Ask follow-up questions**

> "What does the ^ symbol mean in the version number?"
> "Why is there both package.json and package-lock.json?"

**Step 5: Experiment**

Try running a command. Try adding a script. What happens when you break the JSON syntax? What error do you see?

### Example: When you don't understand something

Agent creates this in package.json:

```json
"dependencies": {
  "cowsay": "^1.6.0"
}
```

You might wonder: "What's the `^` thing?"

**Good response:** Ask Copilot or use `/explain`. Learn that it means "compatible versions" and how semantic versioning works.

**Vibe coding response:** Shrug and accept it. Never think about it again.

The difference matters. Next time you see version numbers, will you understand them?

## What we're NOT asking you to do

- **Memorize commands.** You can always look things up.
- **Understand every npm feature.** Focus on the basics: init, install, run.
- **Avoid using Agent.** Use it! That's the point. Just stay curious about what it does.
- **Type commands from scratch.** Agent is here to help. The skill is learning _from_ what it generates.

## The configuration exception

This week, it's okay to have only a general sense of some npm configuration details. If Agent runs:

```bash
npm config set init-author-name "Your Name" -g
```

You should know: "This sets my default author name for new projects." You don't need to memorize every flag.

**But for package.json**, you should understand the main fields:

- `name` — What your project is called
- `version` — The version number
- `scripts` — Commands you can run
- `dependencies` — Packages your project needs

Use `/explain` on package.json and make sure you understand these basics.

## Red flags: Signs you're pure vibe coding

Ask yourself these questions:

- Did I accept Agent's changes without reading them?
- Have I used `/explain` at all today?
- Could I describe what package.json does to a classmate?
- Did I ever wonder "why did it do that?" and then investigate?

If you answered "no" to most of these, slow down. You're getting working commands but not building understanding.

## Your AI collaboration summary

The summary you submit asks you to reflect on what you learned. This is your accountability mechanism. You need to:

- Describe specific npm concepts you encountered
- Explain in your own words what the files and commands do
- Show evidence of curiosity—questions you asked, things you tried

If you purely vibe coded, you won't have much to write. That's the point.

## A professional perspective

Here's something working developers know: vibe coding has its place. When a developer needs to quickly set up a new project, they might let AI handle configuration they don't fully examine. Speed matters; deep understanding can come later.

But that developer already has a foundation. They understand project setup concepts well enough to vibe code safely—they can troubleshoot problems, recognize when something is wrong, and learn new patterns quickly.

You're building that foundation right now. The point of this assignment isn't to produce a working cowsay script—it's to understand how npm projects work. Later, you can vibe code all you want. First, build the knowledge base that makes vibe coding safe.

## Summary

| Do this                                   | Not this                          |
| ----------------------------------------- | --------------------------------- |
| Use `/explain` on package.json            | Accept files without reading them |
| Ask follow-up questions                   | Assume you understand             |
| Experiment and try variations             | Only do the minimum               |
| Paraphrase explanations in your summary   | Copy AI text directly             |
| Know what the main package.json fields do | Stress about every npm flag       |
| Treat Agent as a teacher                  | Treat Agent as a shortcut         |

Agent mode is powerful. Use it to learn, not just to finish.
