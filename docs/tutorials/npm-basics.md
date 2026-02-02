# Understanding npm

npm (Node Package Manager) is a tool that helps you use code other people have written. Instead of writing everything from scratch, you can install packages—bundles of code that solve common problems.

## What problem does npm solve?

Imagine you want to make ASCII art animals say things (like cowsay). You could:

1. **Write it yourself** — Research ASCII art, figure out the bubble formatting, create different animal templates, handle text wrapping... This could take days or weeks.

2. **Use someone else's code** — Install cowsay with `npm install cowsay` and you're done in seconds.

npm makes option 2 easy. It connects you to a registry of over 2 million packages that other developers have shared.

## The npm registry

The npm registry is like an app store for code. When you run `npm install cowsay`, npm:

1. Looks up "cowsay" in the registry
2. Downloads the package and any packages it depends on
3. Saves everything in your `node_modules` folder

You can browse packages at [npmjs.com](https://www.npmjs.com/).

## Key concepts

### package.json

Every npm project has a `package.json` file. It's your project's configuration file that tracks:

- Your project's name and version
- Who wrote it (that's you!)
- What packages it depends on
- Scripts you can run

When you run `npm init`, npm creates this file for you.

### node_modules

When you install a package, npm creates a `node_modules` folder containing:

- The package you installed
- Any packages that package depends on
- Any packages _those_ packages depend on
- And so on...

This folder can get large (hundreds of megabytes). That's normal. **Never edit files in node_modules** — they're managed by npm.

### package-lock.json

npm automatically creates `package-lock.json` to record the exact versions of every package installed. This ensures that if someone else clones your project and runs `npm install`, they get the exact same versions you have.

**Never edit this file manually.** Let npm manage it.

### Dependencies

When you run `npm install cowsay`, npm adds cowsay to the "dependencies" section of your `package.json`:

```json
"dependencies": {
  "cowsay": "^1.6.0"
}
```

This means: "My project needs cowsay version 1.6.0 or compatible."

If you share your project with someone else, they can run `npm install` (with no package name) and npm will install everything listed in dependencies.

## Common npm commands

| Command                 | What it does                                      |
| ----------------------- | ------------------------------------------------- |
| `npm init`              | Creates a new package.json                        |
| `npm init --yes`        | Creates package.json with defaults (no questions) |
| `npm install <package>` | Installs a package and adds it to dependencies    |
| `npm install`           | Installs all packages listed in package.json      |
| `npm run <script>`      | Runs a script defined in package.json             |
| `npm config list`       | Shows your npm configuration                      |

## Why node_modules isn't committed to Git

You'll notice `.gitignore` includes `node_modules/`. This is intentional:

1. **Size** — node_modules can be huge. No need to store it in Git.
2. **Reproducibility** — Anyone can recreate it by running `npm install`.
3. **Platform differences** — Some packages compile differently on Mac vs Windows.

The rule: Commit `package.json` and `package-lock.json`. Ignore `node_modules`.

## npm vs Node.js

These terms are related but different:

- **Node.js** is a JavaScript runtime—it lets you run JavaScript outside a browser
- **npm** is a package manager that comes bundled with Node.js

When you install Node.js, you get npm automatically.

## Summary

- npm is a package manager that lets you install and use code others have written
- `package.json` is your project's configuration file
- `node_modules` holds installed packages (don't edit, don't commit)
- `package-lock.json` records exact versions (don't edit manually)
- The npm registry has over 2 million packages available
