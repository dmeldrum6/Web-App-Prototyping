# WebAppPrototyping
Serverless, local web prototyping tool. Like CodePen Light for your desktop.

Open `WebAppPrototyping.html` in a browser (double-clicking it works). There's nothing to install and no build step. Everything lives in that one file.

<img width="1918" height="911" alt="image" src="https://github.com/user-attachments/assets/a0dba5c8-ab48-4fdd-a807-695b25e56238" />

## Features
- **Code editors:** HTML, CSS and JavaScript editors powered by [CodeMirror 6](https://codemirror.net/), with syntax highlighting, line numbers, bracket matching, auto-closing tags, autocomplete and find/replace.
- **Live preview:** re-runs as you type (turn off *Auto-run* to run manually with **Run** or <kbd>Ctrl/⌘</kbd>+<kbd>Enter</kbd>). Each run starts in a fresh, sandboxed iframe, so timers and globals from earlier runs never leak into the next one.
- **Console:** shows `console.log/info/warn/error/table/group/count/time/assert`, expandable objects, repeated-message counters, filters, and uncaught errors (including syntax errors). Each error includes a clickable `js:LINE` link that jumps to the line in the editor. You can also type JavaScript at the `›` prompt to run it in the preview.
- **Formatting:** the **Format** button in each editor (or <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>F</kbd>) formats the code with [Prettier](https://prettier.io/).
- **Projects:** keep any number of named prototypes. They auto-save to your browser's local storage. You can duplicate or delete them, or import any `.html` file (it's split back into HTML, CSS, JS and resources).
- **Resources & settings:** add external stylesheets and scripts from CDNs, extra `<head>` HTML, and ES-module mode for the JavaScript (so you can use `import`).
- **Share links:** the whole project is compressed into the URL. Links work wherever the page is reachable at the same address, e.g. if you host this file on GitHub Pages.
- **Download** a project as a single standalone HTML file, or open the preview in a new tab.
- **Layout:** drag the dividers to resize, collapse editors, switch between side-by-side and stacked layouts, preview at phone, tablet or desktop widths, and use light/dark themes (following your OS by default). On narrow screens the panels become tabs.

## Notes
- CodeMirror and Prettier load from the [jsDelivr](https://www.jsdelivr.com/) CDN. Offline, the app still works with plain text editors, but formatting is unavailable.
- The preview runs in a sandbox without access to this page. `localStorage` and `sessionStorage` inside the preview are emulated: `localStorage` is saved per project, and `sessionStorage` resets on every run. Cookies and IndexedDB aren't available in the preview, but they work in downloaded files.
- If a run never finishes (for example an infinite loop) and you reload the page, auto-run stays paused until you fix the code and press **Run**.
