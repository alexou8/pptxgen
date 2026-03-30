# PptxGen Playground

A browser-based playground that lets you write (or paste) **PptxGenJS** JavaScript code and instantly download the generated PowerPoint (`.pptx`) presentation — no build step, no server-side code.

## ✨ Features

- **Live code editor** with JavaScript syntax highlighting (CodeMirror)
- **Pre-loaded sample code** covering text, shapes, and bullet lists
- **Run & Download** button (or `Ctrl`/`Cmd`+`Enter`) executes your code and triggers the browser download
- **Custom file name** — set the output `.pptx` file name before running
- **Error reporting** — mistakes in your code are caught and shown inline
- Entirely **client-side** — pptxgenjs v4 is loaded from CDN; nothing leaves your browser

## 🚀 Quick start

### Option 1 — Open directly in the browser

Just double-click `index.html` (or drag it into a browser tab).  
> Note: some browsers block CDN scripts when opening from `file://`. Use option 2 if you see blank/broken output.

### Option 2 — Local dev server

```bash
npm start        # serves at http://localhost:3000
```

### Option 3 — Deploy as a static site

Upload `index.html` to any static hosting provider (GitHub Pages, Netlify, Vercel, etc.).  
No build step required — all dependencies are loaded from CDN.

## 🖊️ Writing code

The editor pre-populates with sample code. You can replace it entirely or tweak it. The `PptxGenJS` constructor and the `FILENAME` variable (taken from the file-name input) are injected automatically, so your code can start immediately:

```js
let pres = new PptxGenJS();

let slide = pres.addSlide();
slide.addText("Hello World!", {
  x: 1, y: 1, w: 8, h: 1,
  fontSize: 36, bold: true, color: "363636",
});

await pres.writeFile({ fileName: FILENAME });
```

Top-level `await` is supported — the code runs inside an `async` wrapper.

## 📚 Resources

- [PptxGenJS docs](https://gitbrent.github.io/PptxGenJS/)
- [API reference](https://gitbrent.github.io/PptxGenJS/docs/api-presentation.html)
