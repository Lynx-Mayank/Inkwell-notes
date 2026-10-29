#  Inkwell

**A private, Notion-style note editor that runs entirely in your browser.** No sign-up, no backend, no AI, and no data leaving your machine. Notes live only for the length of your session and vanish when you close the tab, so download what you want to keep.

> Single-file app: just open `index.html`.

<!-- Add a screenshot or GIF here: ![Inkwell screenshot](docs/screenshot.png) -->

---

## ✨ Features

- **Rich text editing**
  - Headings 1–6, paragraphs, quotes
  - Bold, italic, underline, strikethrough
  - Text colors and highlights
  - Bullet, numbered and checklist lists
  - Tables, links, dividers, text alignment
- **Code that looks like code**
  - Fenced-style code blocks and inline code
  - Their own monospace font, text color and background, all customizable from the sidebar
- **Paste with formatting intact**
  - Copy from ChatGPT, Claude, Wikipedia, docs or any website and headings, lists, tables, bold/italic, links and colors carry over
  - Pasted code is cleaned into a proper code block
  - Junk styles (fonts, sizes, classes) are stripped, and default black/white text adapts to your theme
- **Import and export**
  - Open existing `.md`, `.txt` and `.html` files and keep editing them
  - Download any note as **Markdown**, **plain text** or **HTML**
- **Dark / light mode** (follows your system by default)
- **Privacy-first storage**
  - Notes are kept in `sessionStorage`, so they are erased automatically when the tab or browser closes
  - Nothing is sent to a server
- **Unsaved-work protection**
  - Notes you haven't downloaded are flagged with ●
  - A warning appears before you close the tab with unsaved notes
- Multiple notes with a sidebar and search

---

## 🚀 Getting started

No build step and no dependencies to install.

```bash
git clone https://github.com/<your-username>/inkwell.git
cd inkwell
```

Then either:

- double-click `index.html`, **or**
- serve it locally: `python -m http.server 8000` and visit <http://localhost:8000>

> An internet connection is needed on load because [marked](https://github.com/markedjs/marked) and [Turndown](https://github.com/mixmark-io/turndown) (Markdown conversion) are loaded from a CDN. To use Inkwell fully offline, download those scripts and point the `<script>` tags at the local copies.

---

## 🧭 How to use

| Action | How |
| --- | --- |
| New note | **+ New note** in the sidebar |
| Open an existing file | **📂 Open file**, choosing `.md`, `.txt` or `.html` (multiple allowed) |
| Download a note | **⬇ Download as…** in the toolbar (`.md` / `.txt` / `.html`), or `Ctrl/Cmd + S` for Markdown |
| Change heading / block type | Block dropdown at the left of the toolbar |
| Change code font and colors | Settings at the bottom of the sidebar |
| Toggle theme | 🌙 / ☀️ button in the toolbar |

**Keyboard shortcuts:** `Ctrl/Cmd + B` bold · `I` italic · `U` underline · `S` download as Markdown · `Z` / `Y` undo / redo

---

## 🔒 Privacy and data

- Everything happens locally in your browser. There is no server and no analytics.
- Notes are stored in `sessionStorage` and **deleted when the tab or browser is closed**. Reloading the page keeps them.
- Only preferences (theme and code appearance) are saved in `localStorage`, never note content.
- Because the browser's close-tab dialog can't be customized by websites, Inkwell shows the standard "Leave site?" prompt. If you choose **Stay**, it shows its own styled reminder with a quick download option.

---

## ⚠️ Known limitations

- Formatting is applied with the browser's built-in `contentEditable` / `execCommand` APIs. They are deprecated but still supported by all major browsers, and they keep the app tiny and dependency-free.
- Markdown export handles common formatting well, but text colors, highlights and alignment have no Markdown equivalent, so use **HTML** export to keep them.
- Complex or deeply nested content pasted from some sites may be simplified.
- Some browsers can restore a closed tab, including its session data, via "Reopen closed tab".

---

## 🛠️ Tech stack

- Vanilla HTML, CSS and JavaScript (one file)
- [marked](https://github.com/markedjs/marked): Markdown → HTML when opening `.md` files
- [Turndown](https://github.com/mixmark-io/turndown) + GFM plugin: HTML → Markdown when downloading

---

## 🗺️ Ideas for the future

- Optional Python (Flask/FastAPI) backend to save notes as real files
- Slash-command menu (`/heading`, `/code`, …)
- Drag-and-drop block reordering
- Image upload/paste support
- Export all notes as a ZIP
- PWA support for offline use

---

## 🤝 Contributing

Issues and pull requests are welcome. Keep it simple: the goal is a small, readable, single-file app.

## 📄 License

Released under the [MIT License](LICENSE).
