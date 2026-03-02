# Oh My hsh — Registry

The official package registry for [hsh](https://github.com/takakix2/hsh) themes and pipes.

> **Website**: [oh-my-hsh.navii.online](https://oh-my-hsh.navii.online)

## 📦 What's in this repo?

| File | Description | CLI command |
|---|---|---|
| `themes.json` | Theme catalog (colors, prompts, PS1 styles) | `hsh install-theme <name>` |
| `pipes.json` | Pipe catalog (NDJSON stream processors) | `hsh install-pipe <name>` |

> **Note**: Widgets (`.hm`) and Scripts (`.hm`) are **not distributed via this registry** for security reasons. Write them locally in `~/.hsh/widgets/` and `~/.hsh/scripts/`.

## 🎨 Submit Your Theme

1. **Create a GitHub repo** for your theme with these files:
   ```
   your-repo/
   ├── theme.json      # Theme definition (required)
   └── preview.png     # Terminal screenshot (recommended, 600x400px)
   ```

2. **Fork this registry** (`oh-my-hsh/registry`)

3. **Add your entry** to `themes.json`:
   ```json
   {
     "id": "your-theme-id",
     "name": "Your Theme Name",
     "description": "A short description of your theme.",
     "author": "your-github-username",
     "author_url": "https://github.com/your-github-username",
     "repo": "your-github-username/hsh-your-theme",
     "tags": ["dark", "minimal"],
     "requires_nerd_fonts": false,
     "min_hsh_version": "0.1.0"
   }
   ```

4. **Open a Pull Request** — we'll review and merge it!

Once merged, every hsh user can install your theme instantly:
```bash
$ hsh install-theme your-theme-id
```

## 🔧 Submit Your Pipe

Same process, but add your entry to `pipes.json` instead. Pipes must be compiled Rust binaries that accept NDJSON on stdin and emit NDJSON on stdout.

## 📋 theme.json Schema

Each theme repo must contain a `theme.json` file:

```json
{
  "name": "Tokyo Night",
  "version": "1.0.0",
  "description": "A dark theme celebrating Downtown Tokyo.",
  "author": "takakix2",
  "ps1": "\\e[38;5;75m\\u@\\h\\e[0m:\\e[38;5;214m\\w\\e[0m ❯ ",
  "colors": {
    "background": "transparent",
    "foreground": "#c0caf5",
    "prompt_primary": "#7aa2f7",
    "prompt_secondary": "#e0af68",
    "success": "#9ece6a",
    "error": "#f7768e",
    "info": "#7dcfff",
    "muted": "#565f89"
  },
  "requires_nerd_fonts": true
}
```

## 📄 License

MIT
