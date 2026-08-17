# Happy Birthday — Surprise Site 🎉

A single-page interactive birthday surprise designed to be uploaded directly to GitHub Pages.

## Project flow

The experience follows the concept described by the original project:

1. **Secret code gate** — the visitor enters the private code using a calculator-style keypad or keyboard.
2. **Welcome screen** — the visitor enters a name and chooses a message style.
3. **Virtual letter** — an animated envelope opens with the selected birthday message.
4. **Editable letter** — the message can be edited and saved in `localStorage` for the current browser.
5. **Cake reveal** — opening the cake plays a simple Happy Birthday melody, floating messages, balloons, candle flicker, and confetti.
6. **Disco mode** — after the cake is revealed, pressing **Surprise Me 🎂** starts a dancing disco mode with animated stick figures and optional generated audio.
7. **Mute / reset** — audio preference is saved, and the experience can be reset without refreshing the page.

## Files

- `index.html` — semantic page structure and UI elements.
- `style.css` — responsive layout, animations, cake, balloons, letter, overlays, and disco visuals.
- `main.js` — application state, interactions, local storage, confetti, Web Audio, and animation logic.
- `style-clean.css` — compatibility entry point that imports the main stylesheet.

## Important implementation notes

### Secret code

The code is currently stored in `main.js` as:

```js
const SECRET_CODE = '11142006';
```

This is a **fun UI lock, not real security**. Anyone who can inspect the JavaScript source can find the code.

### Saved settings

The site uses `localStorage` to remember:

- the birthday name,
- selected message template,
- mute preference,
- custom letter content.

### Audio

The birthday melody and disco sound are generated with the browser's Web Audio API. Browsers may require a user interaction before audio can play, which is why the sounds are triggered by button clicks.

### Accessibility

The improved version includes:

- keyboard-friendly controls,
- visible focus states,
- semantic labels,
- `aria-live` feedback,
- reduced-motion support,
- responsive layouts for mobile screens.

## Run locally

Open `index.html` in a browser, or serve the folder with a small local web server.

For example, with Python:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

## Publish with GitHub Pages

```powershell
git init
git add .
git commit -m "Improve birthday surprise site"
git branch -M main
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main
```

Then enable GitHub Pages from the repository's **Settings → Pages** and select the `main` branch and `/ (root)` folder.
