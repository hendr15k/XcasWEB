# XcasWEB

**Browser-based Xcas Computer Algebra System**

A self-contained, offline-capable deployment of [Giac/Xcas](https://www-fourier.univ-grenoble-alpes.fr/~parisse/giac.html) compiled to JavaScript via Emscripten. Open `xcas.html` in any modern browser — no server, no install, no internet required.

> Xcas © B. Parisse et al., GPL3 License. See [COPYING](COPYING) for details.

---

## Usage

### Local / Offline (Recommended)

```bash
# Simply open in browser — works fully offline
open xcas.html          # macOS
xdg-open xcas.html      # Linux
start xcas.html         # Windows
```

### Web Server

Deploy on any static file server (Apache, Nginx, GitHub Pages, Netlify, etc.):

```bash
# Clone and serve
git clone https://github.com/hendr15k/XcasWEB.git
cd XcasWEB
python3 -m http.server 8080
# → Open http://localhost:8080
```

### Deep-linking Sessions

Link directly to saved `.xws` sessions via URL hash:

```html
<a href="xcas.html#url=session.xws&" target="_blank">Open Session</a>
```

All computation runs locally on the client's device.

---

## Features

- Full Xcas/Giac computer algebra system in the browser
- Symbolic math, calculus, linear algebra, statistics, programming
- Works offline (no external dependencies)
- Embeddable via iframe or direct link
- Share `.xws` session files with deep-link support

---

## Source Code

The Giac engine is compiled with Emscripten from the upstream Giac/Xcas source:

- **Upstream Giac:** https://www-fourier.univ-grenoble-alpes.fr/~parisse/giac.html
- **Emscripten build:** `emgiac3.tgz` at the above URL

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| CAS Engine | Giac (Bernard Parisse) |
| Compilation | Emscripten 3 |
| Delivery | Single `xcas.html` (~50 MB, self-contained) |
| Deployment | Static hosting / GitHub Pages |

---

## License

[GPL-3.0](COPYING) — Xcas © B. Parisse et al.

---

## Deployment Notes

- The single `xcas.html` file contains base64-encoded Emscripten output
  and is decoded/extracted at runtime in the browser.
- For sharing sessions, place `.xws` files in the same directory.
- GitHub Pages: configure `main` branch root as source.
