<div align="center">

# JSME

### The molecule editor built for the web.

A free, open-source JavaScript molecule and reaction editor that runs in any modern browser — desktop, tablet, or phone. Direct successor to the JME applet, with no plugins required.

[![NPM version][npm-image]][npm-url]
[![NPM downloads][download-image]][download-url]
[![License: BSD-3-Clause][license-image]][license-url]
[![Live demo][demo-image]][demo-url]

[**Live demo**](https://jsme-editor.github.io/dist/JSME_test.html) ·
[**Documentation**](https://jsme-editor.github.io/dist/index.html) ·
[**Help**](https://jsme-editor.github.io/help.html) ·
[**npm**](https://www.npmjs.com/package/jsme-editor)

</div>

---

## Highlights

- **Zero install** — pure JavaScript, runs in every modern browser
- **Touch-ready** — designed for iPhone, iPad, and Android alongside desktop
- **Reactions & SMIRKS** — draw reactions, modulators, and reaction mapping natively
- **Canonical SMILES** — order-independent output, plus SMARTS for substructure search
- **Molfile I/O** — read and write MDL/Symyx Molfiles (V2000 and V3000)
- **Built-in InChI** — bundled InChI library
- **SVG export** — render the current structure as SVG
- **Keyboard-first** — shortcuts for atoms, bonds, rings, and common functional groups
- **Clipboard + drag-and-drop** — paste MOL/SDF/RXN, drag molecules into other apps
- **BSD-3-Clause** — use it anywhere, commercial or academic

## Quick start

### As an npm package

```bash
npm install jsme-editor
```

### As a static script tag

```html
<script src="jsme/jsme.nocache.js"></script>

<script>
  function jsmeOnLoad() {
    new JSApplet.JSME("editor", "380px", "340px", {
      options: "newlook,fullScreenIcon",
      smiles: "CC(=O)Oc1ccccc1C(=O)O"
    });
  }
</script>

<div id="editor"></div>
```

Drop the `dist/jsme/` directory into your project, point a script tag at `jsme.nocache.js`, then define a global `jsmeOnLoad()` callback — JSME will call it once the runtime is ready.

## Reading the structure

```js
// SMILES
const smi = jsmeApplet.smiles();

// Molfile (V2000 by default; V3000 via .molFile(true))
const mol = jsmeApplet.molFile();

// JME string
const jme = jsmeApplet.jmeFile();

// Live updates
jsmeApplet.setCallBack("AfterStructureModified", e => {
  console.log("new SMILES:", e.src.smiles());
});
```

## Try it live

| Page | What it shows |
| --- | --- |
| [Landing page](https://jsme-editor.github.io/) | Hero with embedded editor + template chips + live SMILES |
| [API playground](https://jsme-editor.github.io/dist/JSME_test.html) | Every API control: options, rendering, import/export |
| [Examples index](https://jsme-editor.github.io/dist/index.html) | 30+ integration examples |
| [Help page](https://jsme-editor.github.io/help.html) | Toolbar reference + keyboard shortcuts |

## Repository layout

```
jsme-editor.github.io/
├── index.html              landing page
├── help.html               user guide
├── styles.css              design system (OKLCH, layers, dark mode)
├── dist/                   JSME distribution
│   ├── jsme/                 runtime bundles (GWT, browser-optimized)
│   ├── api_javadoc/          API reference
│   ├── JSME_*.html           ~25 integration examples
│   ├── test_*.html           developer test pages
│   ├── doc.html              implementation guide
│   ├── license.txt           BSD-3-Clause text
│   └── release_notes.txt     changelog
├── downloads/              versioned distribution zips
└── images/                 toolbar icon screenshots
```

## Ecosystem

| Project | Description |
| --- | --- |
| [JSME-webpack-example](https://github.com/jsme-editor/JSME-webpack-example) | JSME + webpack with static assets |
| [jsme-react](https://github.com/douglasconnect/jsme-react) | React component wrapper |
| [Panel-Chemistry](https://github.com/awesome-panel/panel-chemistry) | JSME inside a Python Holoviz Panel |

## Documentation

- [Embedding guide](https://jsme-editor.github.io/dist/doc.html) — start here
- [API reference (Javadoc-style)](https://jsme-editor.github.io/dist/api_javadoc/index.html)
- [Help & toolbar reference](https://jsme-editor.github.io/help.html)
- [Release notes](./dist/release_notes.txt)

## Citation

If you use JSME in published work, please cite:

> B. Bienfait and P. Ertl, **JSME: a free molecule editor in JavaScript**, *J. Cheminformatics* 5:24 (2013).
> [http://www.jcheminf.com/content/5/1/24](http://www.jcheminf.com/content/5/1/24)

```bibtex
@article{bienfait2013jsme,
  title   = {JSME: a free molecule editor in JavaScript},
  author  = {Bienfait, Bruno and Ertl, Peter},
  journal = {Journal of Cheminformatics},
  volume  = {5},
  number  = {1},
  pages   = {24},
  year    = {2013},
  doi     = {10.1186/1758-2946-5-24}
}
```

## Contributing

Found a bug or have an idea? Open an [issue](https://github.com/jsme-editor/jsme-editor.github.io/issues) or start a [discussion](https://github.com/jsme-editor/jsme-editor.github.io/discussions).

## License

Released under the [3-Clause BSD License](./dist/license.txt). Use it freely in commercial or academic projects.

## Authors

JSME is developed by **Peter Ertl** and **Bruno Bienfait**.

<!-- badges -->
[npm-image]: https://img.shields.io/npm/v/jsme-editor.svg?style=flat-square&color=3a6df0
[npm-url]: https://www.npmjs.com/package/jsme-editor
[download-image]: https://img.shields.io/npm/dm/jsme-editor.svg?style=flat-square&color=14b8a6
[download-url]: https://www.npmjs.com/package/jsme-editor
[license-image]: https://img.shields.io/badge/license-BSD--3--Clause-blue.svg?style=flat-square
[license-url]: ./dist/license.txt
[demo-image]: https://img.shields.io/badge/demo-live-success.svg?style=flat-square
[demo-url]: https://jsme-editor.github.io/dist/JSME_test.html
