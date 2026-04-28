# Seyfert AGN — VS Code Theme & Icons

**"Monokai, observed from a Seyfert galaxy."**

An elite dark theme for VS Code, built for the Seyfert AI design language. Takes Monokai's signature contrast architecture — muted warm ground, saturated accent tokens — and re-instruments it through Seyfert's deep-space indigo palette. Includes a complete icon theme ("Accretion Icons") with 100+ hand-designed SVGs.

Named after Seyfert galaxies — the class of galaxy characterized by an Active Galactic Nucleus radiating at the heart of the host. Fitting for a theme about what's at the center of your code.

---

## Contents

- **Seyfert AGN** — primary dark theme
- **Seyfert AGN — High Contrast** — lifted-foreground variant for presentations and code review
- **Seyfert AGN — Soft Contrast** — relaxed, reduced-eye-strain variant with lifted ground, desaturated accents, and high-visibility scrollbars
- **Accretion Icons** — 148-glyph file + folder icon theme
- **Full signal coverage** — git state, problem severity, test results, inlay hints, lightbulb, and AI ghost-text are all palette-mapped across every variant (v1.1.1+)

## Install

### From VSIX (recommended for internal distribution)

```bash
# Package it first (one-time):
cd seyfert-agn
npx @vscode/vsce package

# Then install the resulting .vsix:
code --install-extension seyfert-agn-1.1.1.vsix
```

### Side-load for development

Copy or symlink the `seyfert-agn/` folder into your VS Code extensions directory:

| OS | Path |
|---|---|
| macOS / Linux | `~/.vscode/extensions/seyfert-ai.seyfert-agn-1.0.0/` |
| Windows | `%USERPROFILE%\.vscode\extensions\seyfert-ai.seyfert-agn-1.0.0\` |

Then restart VS Code.

### Activate

1. `Cmd/Ctrl + Shift + P` → **"Color Theme"** → pick *Seyfert AGN*
2. `Cmd/Ctrl + Shift + P` → **"File Icon Theme"** → pick *Seyfert AGN — Accretion Icons*

## Design notes

### Chrome — a 7-stop tonal ramp

| Stop | Hex | Used for |
|---|---|---|
| `void.0` | `#060A14` | Activity bar, terminal |
| `void.1` | `#0A0F1C` | Editor background |
| `void.2` | `#0E1424` | Sidebar, panel |
| `void.3` | `#131A2D` | Inactive tabs, inputs |
| `void.4` | `#1A2238` | Hover backgrounds |
| `void.5` | `#242D47` | Borders, indent guides |
| `void.6` | `#3A4263` | Muted text |

Pure black is avoided. Everything is indigo-tinted near-black — the UI reads as one continuous gradient of depth, not stacked flat panels.

### Syntax accents — the "stars"

| Role | Hex | Notes |
|---|---|---|
| Keyword | `#F472B6` plasma-pink | Bold. `if`, `return`, `import` |
| Function | `#A5B4FC` indigo-light | Replaces Monokai's lime |
| **String** | `#E5B867` **AGN-gold** | The sacred color. Strings only. |
| Number / const | `#C4B5FD` violet | |
| Type / class | `#7DD3FC` corona-cyan | |
| Parameter | `#F5D8A3` starlight | Italic |
| `this` / `self` | `#FB7185` coral | Italic |
| Operator / punct | `#94A3B8` dust-gray | Recedes |
| Comment | `#5B6478` | Italic, desaturated — "nebula dust" |

**Gold is sacred.** AGN-gold appears only for strings, modified-tab indicator, active-tab underline, and the modified-git gutter stripe. This mirrors the Seyfert AI site, where the same gold is reserved for the founder section.

### Terminal ANSI 16

Full 16-color ANSI palette follows the same rules — ground is `void.1`, bright-black is `void.5`, red biased to coral, cyan biased to stellar corona, yellow is the AGN gold.

### Icons — "Accretion"

- **Monochrome indigo base** for most files, so the file tree reads as a calm star field.
- **Strategic accent colors** only:
  - **AGN-gold** → config, env, lock files (gravitational centers of a project)
  - **Plasma-pink** → tests, stories
  - **Corona-cyan** → type definitions, Docker, Kubernetes
  - **Violet** → data files (JSON, YAML, CSV, video)
  - **White** → text, Markdown, README
  - **Dust-gray** → hidden files, archives
- **Folders** are a "horizon silhouette" — a flat base with an arc above, like a planet's limb against space. Open folders add a sweep of light across the arc.
- **Named folder glyphs** — `src`, `components`, `app`, `docs`, `public`, `test`, `config`, `dist` each get a unique color-coded variant.

### Italics

Enabled on: comments, parameters, `this`/`self`, storage modifiers, decorators, primitive types, and built-in library functions. Nothing else — italics carry meaning, not decoration.

## Palette reference

```
void.0        #060A14
void.1        #0A0F1C    ← editor bg
void.2        #0E1424
void.3        #131A2D
void.4        #1A2238
void.5        #242D47
void.6        #3A4263

indigo        #6366F1    Seyfert canonical accent
indigo-light  #818CF8    hover / highlight
indigo-bright #A5B4FC    function names
violet        #C4B5FD    numbers / const
cyan          #7DD3FC    types / corona
pink          #F472B6    keywords / plasma
coral         #FB7185    this / self / regex
AGN-gold      #E5B867    strings (sacred)
starlight     #F5D8A3    parameters
moss          #A5D6B4    shell / yaml
dust-gray     #94A3B8    operators
star-white    #F8FAFC    foreground
```

## Credits

Designed for Seyfert AI.
Built on the [VS Code theming API](https://code.visualstudio.com/api/extension-guides/color-theme).

## License

MIT
