# When Agent makes mistakes

Agent is powerful, but it's not perfect. Sometimes commands fail, or the result won't be exactly what you wanted. This is normal—and learning to handle these situations is part of working with AI tools.

## Mistakes are expected

Professional developers who use AI coding assistants expect to iterate. The first attempt rarely works perfectly. This isn't a failure—it's how the process works.

**Your mindset should be:**

- "Let's see what Agent does"
- "That's close, but I need to adjust it"
- "Something's not working—let me figure out what"

**Not:**

- "It should work perfectly the first time"
- "Agent is broken"
- "I must have done something wrong"

## Common situations and how to handle them

### The command doesn't work

**What happened:** Agent ran a command, but you see an error in the terminal.

**What to try:**

1. Read the error message in the terminal
2. Tell Agent what you see:

> "The npm install command failed. The terminal shows: 'npm ERR! code ENOENT'. Can you fix this?"

Or simply:

> "The command didn't work. Can you check what went wrong and try again?"

### It works, but not how you wanted

**What happened:** Agent created something functional, but it's not quite right.

**What to try:**

Be specific about the difference between what you got and what you wanted:

> "The script runs, but it uses the default cow. I wanted it to use the dragon character."

> "The package.json was created, but my author name is wrong. Can you fix it to say 'Jane Smith'?"

> "Cowsay works, but the message is different from what I asked for."

### Agent changed something you didn't want changed

**What happened:** You asked Agent to add something, but it also modified something else.

**What to try:**

1. **Before accepting:** Review all the changes Agent proposes. You can see which files it wants to modify.
2. **If you already accepted:** Ask Agent to undo the unwanted change:

> "You changed the test script when you added the cowsay script. Can you change the test script back?"

Or use VS Code's undo feature (`Cmd+Z` / `Ctrl+Z`) to revert changes.

### JSON syntax error

**What happened:** After editing package.json, npm commands fail with syntax errors.

**What to try:**

> "I'm getting a JSON syntax error when I run npm commands. Can you check package.json and fix it?"

Common causes:

- Missing comma between properties
- Extra comma after the last property
- Mismatched quotes

See [json-syntax.md](../tutorials/json-syntax.md) for help fixing JSON errors.

### You don't understand what Agent did

**What happened:** Agent ran commands or created files, and they work, but you have no idea why.

**What to try:**

This is what `/explain` is for:

1. Select the content you don't understand (terminal output, package.json, etc.)
2. Type `/explain`
3. Read the explanation
4. Ask follow-up questions if needed

> "I don't understand what the ^ symbol means in the version number. Can you explain it simply?"

## The debugging conversation

Here's what an iterative debugging conversation looks like:

> **You:** "Initialize npm and install cowsay"
>
> **Agent:** _Runs commands_
>
> **You:** _Tests it_ "When I run npm run cowsay, I get 'missing script: cowsay'"
>
> **Agent:** "I see—I installed cowsay but didn't add a script for it. Let me add one to package.json."
>
> **Agent:** _Adds the script_
>
> **You:** _Tests again_ "Now it works! But I want it to use the tux character by default."
>
> **Agent:** _Updates the script to include -f tux_
>
> **You:** "Perfect, that's what I wanted."

Notice the pattern: test → report what happened → let Agent fix it → test again.

## When to start over

Sometimes it's easier to start fresh than to fix a tangled mess:

> "This has gotten complicated. Can you delete package.json and reinitialize the project? I want a clean start with just cowsay installed."

Starting over isn't giving up—it's a practical choice when things have become hard to follow.

## Checking your work

After Agent makes changes, always:

1. **Save all files** (auto-save should handle this)
2. **Run the command** in the terminal to test it
3. **Read the output** to see if it worked
4. **Check for errors** in the terminal output

If you skip testing, you won't know if something is broken until later—when it's harder to figure out what went wrong.

## Reading terminal output

The terminal shows you what's happening when commands run.

**What to look for:**

- `npm ERR!` = Something went wrong (read the message for details)
- `npm WARN` = Warning (might be a problem, might be fine)
- Normal output = Command worked

**Common errors you might see:**

| Error                       | What it usually means                                     |
| --------------------------- | --------------------------------------------------------- |
| `npm ERR! code ENOENT`      | A file or folder doesn't exist                            |
| `npm ERR! JSON.parse`       | package.json has a syntax error                           |
| `missing script: <name>`    | The script you tried to run doesn't exist in package.json |
| `command not found: cowsay` | Cowsay isn't installed, or you're not using npm run       |

You don't need to understand these fully—just copy the error message and share it with Agent.

## Frustration is normal

If you're feeling frustrated:

1. **Take a breath.** This happens to everyone, including professionals.
2. **Re-read your prompt.** Was it clear? Could Agent have misunderstood?
3. **Start smaller.** Ask for one simple thing instead of a complex setup.
4. **Ask Agent to explain.** Sometimes understanding the problem helps solve it.

Working with AI tools has a learning curve. Each mistake teaches you something about how to communicate more effectively.

## Summary

- Expect to iterate—first attempts rarely work perfectly
- Describe problems clearly: what you expected vs. what happened
- Read terminal output for error messages
- Use `/explain` when you don't understand what Agent did
- Starting over is sometimes the right choice
- Test after every change
- Frustration is normal; it gets easier with practice
