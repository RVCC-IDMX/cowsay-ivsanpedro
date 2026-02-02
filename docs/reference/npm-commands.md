# npm command reference

Quick reference for npm commands used in this course.

---

## Configuration commands

### Set author name globally

```bash
npm config set init-author-name "Your Name" -g
```

### Set author email globally

```bash
npm config set init-author-email "you@example.com" -g
```

### Set default license globally

```bash
npm config set init-license "MIT" -g
```

### View current configuration

```bash
npm config list
```

---

## Project commands

### Initialize a new project

```bash
npm init
```

Creates `package.json` interactively. Use `npm init --yes` to accept defaults.

### Install all dependencies

```bash
npm install
```

Reads `package.json` and downloads packages into `node_modules/`.

### Install a specific package

```bash
npm install cowsay
```

Adds the package to `dependencies` in `package.json`.

### List installed packages

```bash
npm list
```

Shows installed packages. Use `npm list cowsay` to check a specific package.

---

## Running scripts

### Run a named script

```bash
npm run script-name
```

Runs the script defined in `package.json` under `"scripts"`.

### Run the start script

```bash
npm start
```

Shortcut for `npm run start`.

### Run the test script

```bash
npm test
```

Shortcut for `npm run test`.

---

## Passing arguments to scripts

Use `--` to pass arguments through to the underlying command:

```bash
npm run cowsay -- "Hello"
npm run cowsay -- -f tux "Linux!"
```

Everything after `--` goes to the script, not to npm.

---

## Quick troubleshooting

| Problem                    | Solution                                             |
| -------------------------- | ---------------------------------------------------- |
| `npm: command not found`   | Install Node.js from nodejs.org                      |
| `Cannot find package.json` | You're in the wrong folder                           |
| `WARN` messages            | Usually fine—check for `ERR!` instead                |
| Script hangs               | Forgot `--` before arguments? Press Ctrl+C to cancel |
