# JSON syntax guide

JSON (JavaScript Object Notation) is a format for storing data. Your `package.json` file is written in JSON. This guide helps you edit JSON files without breaking them.

## The golden rules

1. **Property names must be in double quotes**
2. **String values must be in double quotes**
3. **No trailing commas**
4. **Commas between items, but not after the last one**

## Basic structure

JSON uses two main structures:

### Objects (curly braces)

Objects hold named properties:

```json
{
  "name": "my-project",
  "version": "1.0.0"
}
```

### Arrays (square brackets)

Arrays hold lists of values:

```json
{
  "keywords": ["cowsay", "ascii", "fun"]
}
```

## The comma rule

Every item except the last needs a comma after it.

**Correct:**

```json
{
  "name": "my-project",
  "version": "1.0.0",
  "description": "A fun project"
}
```

**Wrong (missing comma):**

```json
{
  "name": "my-project"
  "version": "1.0.0"
}
```

**Wrong (trailing comma):**

```json
{
  "name": "my-project",
  "version": "1.0.0",
}
```

Note the comma after the last line—JSON doesn't allow this.

## Adding a new line

When you add a new property, remember:

1. Add a comma to the line **above** your new line
2. Don't put a comma on your new line (if it's the last one)

### Example: Adding a script

Before:

```json
"scripts": {
  "test": "echo test"
}
```

After:

```json
"scripts": {
  "test": "echo test",
  "cowsay": "cowsay"
}
```

Notice: comma added to the `test` line, no comma on the new `cowsay` line.

## Quotes in JSON

JSON requires double quotes (`"`) for both property names and string values.

**Correct:**

```json
{
  "name": "my-project"
}
```

**Wrong (single quotes):**

```json
{
  "name": "my-project"
}
```

**Wrong (no quotes on property name):**

```json
{
  "name": "my-project"
}
```

## Escaping quotes inside strings

If your string contains a quote, escape it with a backslash:

```json
{
  "message": "The cow says \"Hello!\""
}
```

## Common mistakes and fixes

### Missing comma

**Error:** `Unexpected string` or `Expected comma`

**Problem:**

```json
{
  "name": "project"
  "version": "1.0.0"
}
```

**Fix:** Add a comma after `"project"`:

```json
{
  "name": "project",
  "version": "1.0.0"
}
```

### Extra comma (trailing comma)

**Error:** `Unexpected token }` or `Expected property name`

**Problem:**

```json
{
  "name": "project",
  "version": "1.0.0"
}
```

**Fix:** Remove the comma after `"1.0.0"`:

```json
{
  "name": "project",
  "version": "1.0.0"
}
```

### Wrong quote type

**Error:** `Unexpected token`

**Problem:**

```json
{
  "name": "project"
}
```

**Fix:** Use double quotes:

```json
{
  "name": "project"
}
```

### Unquoted property name

**Error:** `Expected property name`

**Problem:**

```json
{
  "name": "project"
}
```

**Fix:** Quote the property name:

```json
{
  "name": "project"
}
```

## Checking your JSON

VS Code helps you find JSON errors:

1. **Red squiggly lines** show where errors are
2. **Hover over the error** to see what's wrong
3. **Problems panel** (View → Problems) lists all errors

If you're stuck, you can also paste your JSON into a validator like [jsonlint.com](https://jsonlint.com/).

## Quick reference

| Rule                  | Correct                     | Wrong                           |
| --------------------- | --------------------------- | ------------------------------- |
| Property names        | `"name"`                    | `name` or `'name'`              |
| String values         | `"value"`                   | `'value'`                       |
| Commas                | After each item except last | Trailing comma or missing comma |
| Quotes inside strings | `"say \"hi\""`              | `"say "hi""`                    |

## Summary

- Use double quotes for property names and string values
- Put commas after every item except the last
- Watch for red squiggly lines in VS Code
- When adding a line, add a comma to the line above
