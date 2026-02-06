# Understanding package.json

`package.json` is a file that tells npm everything about your project. Think of it like an instruction manual for your project: it lists what your project needs to work, who created it, and special commands you can run.

Every npm project needs a `package.json` file. When you initialized your project with `npm init -y`, npm created this file automatically.

## The fields in your package.json

### name

**What it means:** Your project's unique identifier inside npm.

**Example:** `"name": "cowsay-ivsanpedro"`

**Why it matters:** If you ever publish your project to npm (the public package registry), this name is how other developers will find and install it. It acts like your project's official name.

**What happens if it's missing:** npm requires this field. If you remove it, npm commands may stop working properly.

---

### version

**What it means:** What release or version of your project this is, using a system called "semantic versioning."

**Example:** `"version": "1.0.0"`

**Format:** Major.Minor.Patch
- `1` = major version (big changes)
- `0` = minor version (new features)
- `0` = patch version (bug fixes)

**Why it matters:** As you update your project, changing the version number helps users know if they're using an old or new version. If you publish to npm, version numbers tell other developers about the size of changes you made.

**What happens if it's missing:** npm will warn you but won't prevent the project from working.

---

### description

**What it means:** A short explanation of what your project does.

**Example:** `"description": "Welcome to Week 2! This assignment teaches you to use Copilot Agent..."`

**Why it matters:** When someone looks up your project on npm or GitHub, the description helps them understand what it does before they dig deeper.

**What happens if it's missing:** No major problems—the project will work fine, but it's harder for people to understand what your project is for.

---

### main

**What it means:** The entry point file. This is the JavaScript file that runs first when someone imports your project.

**Example:** `"main": "index.js"`

**Why it matters:** If you create an `index.js` file and someone else uses your project with `require('cowsay-ivsanpedro')`, Node.js automatically loads this `index.js` file.

**What happens if it's missing:** Node.js will look for an `index.js` file anyway, so for learning projects it doesn't hurt much. But for published packages, this field prevents confusion.

---

### directories

**What it means:** Tells npm where you've organized your folders.

**Example:**
```json
"directories": {
  "doc": "docs"
}
```

**Why it matters:** This is mostly informational. npm uses this to help understand your project structure, and tools can use it to find your documentation.

**What happens if it's missing:** No problems—your project works the same. This field is optional.

---

### scripts

**What it means:** Custom commands you can run with `npm run`.

**Example:**
```json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "cowsay": "cowsay",
  "moo": "cowsay 'Hello from npm scripts!'"
}
```

**How to use it:**
- Type `npm run test` to run the command after `"test"`
- Type `npm run cowsay` to run the cowsay command
- Type `npm run moo` to run cowsay with that message

**Why it matters:** Scripts are a convenient way to run commands without typing the whole thing. Instead of typing `cowsay 'Hello from npm scripts!'`, you can just type `npm run moo`. This saves time and prevents typos.

**What happens if it's missing:** The `scripts` field becomes empty, and you have no shortcuts to run. You'd have to type commands manually.

---

### repository

**What it means:** Information about where your code is stored (like on GitHub).

**Example:**
```json
"repository": {
  "type": "git",
  "url": "git+https://github.com/RVCC-IDMX/cowsay-ivsanpedro.git"
}
```

**Why it matters:** This links your npm package to your GitHub repository so people can find the source code. If you publish to npm, this helps others contribute to your project.

**What happens if it's missing:** Your project still works, but it's harder for people to find your code on GitHub.

---

### keywords

**What it means:** Words that describe your project, used for searching on npm.

**Example:** `"keywords": ["cowsay", "npm", "tutorial"]`

**Why it matters:** If you publish your project, these keywords help people find it when they search npm.

**What happens if it's missing:** Your project is less discoverable, but everything else works fine.

---

### author

**What it means:** The person (or people) who created the project.

**Example:** `"author": "Your Name <your.email@example.com>"` or just `"author": "Your Name"`

**Why it matters:** This credits you as the creator. If someone uses your project and has questions, they know who to contact.

**What happens if it's missing:** The field shows as empty, and it's unclear who maintains the project.

---

### license

**What it means:** The legal license that says how others can use your code.

**Example:** `"license": "ISC"`

**Common licenses:**
- `ISC` — Permissive (people can use it freely)
- `MIT` — Very permissive (very popular)
- `Apache-2.0` — Permissive with more details
- `GPL` — Restrictive (people must share their code too)

**Why it matters:** A license clarifies the rules. Without one, people don't know if they're allowed to copy, modify, or sell your code.

**What happens if it's missing:** Legally, you haven't given permission for anyone to use your code, which is confusing. For learning projects, this is fine.

---

### type

**What it means:** The module format your project uses.

**Example:** `"type": "commonjs"`

**Two main formats:**
- `commonjs` — Uses `require()` to import code (older style)
- `module` — Uses `import` (modern style)

**Why it matters:** This tells Node.js how to interpret your JavaScript files. If you don't match this to your code, Node.js gets confused.

**What happens if it's missing:** Node.js assumes `commonjs` by default, so your project usually still works.

---

### bugs

**What it means:** Where people should report problems with your project.

**Example:**
```json
"bugs": {
  "url": "https://github.com/RVCC-IDMX/cowsay-ivsanpedro/issues"
}
```

**Why it matters:** If someone finds a bug, this tells them exactly where to report it (usually your GitHub issues page).

**What happens if it's missing:** People might email you instead of using the proper channel, and bugs are harder to track.

---

### homepage

**What it means:** The website or URL for your project.

**Example:** `"homepage": "https://github.com/RVCC-IDMX/cowsay-ivsanpedro#readme"`

**Why it matters:** This points people to the main place to learn about your project (usually your GitHub README).

**What happens if it's missing:** No problems—it's just convenient to have.

---

### dependencies

**What it means:** The packages your project needs to work.

**Example:**
```json
"dependencies": {
  "cowsay": "^1.6.0"
}
```

**What the symbols mean:**
- `^1.6.0` means "version 1.6.0 or newer, but not version 2.0.0"
- `~1.6.0` means "version 1.6.0 or 1.6.1, 1.6.2, etc., but not 1.7.0"
- `1.6.0` means "exactly version 1.6.0"

**Why it matters:** This list is critical. When someone downloads your project and runs `npm install`, npm uses this list to get the exact packages you need.

**What happens if it's missing:** Your project can't run because it doesn't know what packages to install.

---

## The big picture

When you work on a team or publish your project, `package.json` is the agreement between you and other developers: "Here's what my project needs, here's what it does, here's how to reach me."

For learning, `package.json` helps you organize your project and remember what commands do what.

The most important fields for beginners are:
- `name` — identifies your project
- `scripts` — shortcuts for commands you run often
- `dependencies` — packages your project uses
