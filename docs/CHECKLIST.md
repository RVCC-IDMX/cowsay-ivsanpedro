# Assignment checklist

Use this checklist to verify your work before submitting. Every item should be checked.

---

## Project setup

- [ ] `package.json` exists in root folder
- [ ] `package-lock.json` exists (auto-generated)
- [ ] `node_modules/` folder exists with cowsay installed

## npm scripts

- [ ] `package.json` contains a `"cowsay"` script
- [ ] `package.json` contains a `"moo"` script
- [ ] `package.json` contains a custom `"favorite"` script with your chosen creature/message
- [ ] Running `npm run moo` displays a cow saying "Hello from npm scripts!"
- [ ] Running `npm run favorite` displays your custom cowsay

## Student-created documentation

- [ ] `docs/tutorial-package-json.md` — explains package.json fields

## README

- [ ] `README.md` has a level 1 heading with your project title
- [ ] `README.md` includes at least one cowsay ASCII art output
- [ ] Cowsay output is wrapped in a code fence (triple backticks)
- [ ] README displays correctly on GitHub.com

## Reflection

- [ ] `ai-collaboration-summary-template.md` is filled out

## Git history

- [ ] Multiple commits (not just one giant commit at the end)
- [ ] Commit messages describe what changed
- [ ] All changes pushed to GitHub

---

## Quick verification commands

Run these in your terminal to verify your setup:

```bash
# Should show cowsay in dependencies
npm list cowsay

# Should display a cow
npm run moo

# Should display your custom creature/message
npm run favorite
```

## Files to submit

Your GitHub repository should contain:

```text
your-repo/
├── docs/
│   ├── tutorial-package-json.md     (you created)
│   └── (pre-made tutorials and reference docs)
├── node_modules/                    (auto-generated)
├── ai-collaboration-summary-template.md (filled out)
├── package.json                     (with your scripts)
├── package-lock.json                (auto-generated)
└── README.md                        (with cowsay output)
```
