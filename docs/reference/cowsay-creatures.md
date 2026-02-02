# Cowsay creatures reference

A selection of fun cowsay creatures to try. Use the `-f` flag to pick one.

---

## How to use a creature

```bash
npm run cowsay -- -f creature-name "Your message"
```

---

## Classic creatures

### cow (default)

```bash
npm run cowsay -- "Hello world"
```

```text
 _____________
< Hello world >
 -------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

### tux (Linux penguin)

```bash
npm run cowsay -- -f tux "Linux rules"
```

Great for tech-themed messages.

### dragon

```bash
npm run cowsay -- -f dragon "I am fire"
```

A detailed ASCII dragon. Good for dramatic messages.

### stegosaurus

```bash
npm run cowsay -- -f stegosaurus "Rawr"
```

A dinosaur with distinctive back plates.

---

## Fun creatures

### sheep

```bash
npm run cowsay -- -f sheep "Baa"
```

### turtle

```bash
npm run cowsay -- -f turtle "Slow and steady"
```

### elephant

```bash
npm run cowsay -- -f elephant "Never forget"
```

### fox

```bash
npm run cowsay -- -f fox "What does the fox say?"
```

---

## Silly creatures

### daemon

```bash
npm run cowsay -- -f daemon "Hello from BSD"
```

The BSD daemon mascot.

### ghostbusters

```bash
npm run cowsay -- -f ghostbusters "Who you gonna call?"
```

### vader

```bash
npm run cowsay -- -f vader "I am your father"
```

---

## Useful flags

| Flag | What it does       | Example             |
| ---- | ------------------ | ------------------- |
| `-f` | Choose creature    | `-f tux`            |
| `-l` | List all creatures | (no message needed) |
| `-e` | Change eyes        | `-e "@@"`           |
| `-T` | Change tongue      | `-T "U "`           |
| `-W` | Set text width     | `-W 30`             |

### List all available creatures

```bash
npm run cowsay -- -l
```

This shows every cowfile on your system. Pick ones that sound interesting and try them!

---

## Combining flags

```bash
npm run cowsay -- -f tux -e "**" "Excited penguin!"
```

You can combine multiple flags in one command.
