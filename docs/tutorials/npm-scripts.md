# npm scripts

npm scripts let you create shortcuts for commands you run often. Instead of typing a long command every time, you define it once in `package.json` and run it with a short name.

## Where scripts live

Scripts are defined in the `scripts` section of `package.json`:

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "cowsay": "cowsay",
    "moo": "cowsay 'Hello!'"
  }
}
```

## Running scripts

To run a script, use `npm run` followed by the script name:

```bash
npm run cowsay
npm run moo
```

## Passing arguments to scripts

Sometimes you want to pass additional arguments when you run a script. Use `--` to separate npm's arguments from the script's arguments:

```bash
npm run cowsay -- "Hello World"
npm run cowsay -- -f tux "I use Linux"
```

**Why the double dash?**

Without `--`, npm might think the arguments are for npm itself. The `--` says "everything after this goes to the script."

| Command                     | What happens                          |
| --------------------------- | ------------------------------------- |
| `npm run cowsay "Hello"`    | npm might misinterpret "Hello"        |
| `npm run cowsay -- "Hello"` | "Hello" is passed to cowsay correctly |

## Reserved script names

Some script names have special meaning:

| Script name   | Special behavior                        |
| ------------- | --------------------------------------- |
| `start`       | Run with `npm start` (no `run` needed)  |
| `test`        | Run with `npm test` (no `run` needed)   |
| `preinstall`  | Runs automatically before `npm install` |
| `postinstall` | Runs automatically after `npm install`  |

For all other script names, you must use `npm run <name>`.

## Why use npm scripts?

### 1. Shorter commands

Instead of:

```bash
cowsay -f dragon -e "@@" -T "U " "Fear me!"
```

Define it once:

```json
"dragon": "cowsay -f dragon -e \"@@\" -T \"U \" \"Fear me!\""
```

Then just run:

```bash
npm run dragon
```

### 2. Documentation

Your scripts section documents what commands your project uses. Anyone looking at `package.json` can see how to run things.

### 3. Consistency

Everyone on a team runs the exact same command. No more "it works on my machine" because someone typed the command differently.

### 4. Chaining commands

You can chain multiple commands with `&&`:

```json
"build-and-test": "npm run build && npm test"
```

## Adding a new script

To add a new script:

1. Open `package.json`
2. Find the `scripts` section
3. Add a new line with your script name and command
4. **Remember the comma** on the line before (see [json-syntax.md](json-syntax.md))

### Example: Adding a cowsay script

Before:

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1"
}
```

After:

```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "cowsay": "cowsay"
}
```

Note the comma after the `test` line.

## Viewing available scripts

To see what scripts are defined in a project:

```bash
npm run
```

This lists all scripts without running any of them.

## Common mistakes

### Forgetting the comma

```json
"scripts": {
  "test": "echo test"
  "cowsay": "cowsay"
}
```

This breaks because there's no comma after the test line.

### Forgetting `npm run`

```bash
cowsay "Hello"
```

This might not work if cowsay isn't installed globally. Use:

```bash
npm run cowsay -- "Hello"
```

### Forgetting the `--` for arguments

```bash
npm run cowsay -f tux "Hello"
```

npm might interpret `-f` as an npm flag. Use:

```bash
npm run cowsay -- -f tux "Hello"
```

## Summary

- Scripts are defined in the `scripts` section of `package.json`
- Run scripts with `npm run <name>`
- Pass arguments after `--`
- `start` and `test` are special—they don't need `run`
- Scripts make commands shorter, documented, and consistent
