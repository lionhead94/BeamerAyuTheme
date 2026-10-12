# Beamer Ayu Theme

Modern [Beamer](https://ctan.org/pkg/beamer) themes for LaTeX presentations built around the [ayu](https://github.com/ayu-theme/ayu-colors) color palette, available in light, mirage and dark variants.

## Features

- **AyuLight** — near-white background (`#fcfcfc`), saturated ayu light accents
- **AyuMirage** — blue-grey background (`#242936`), soft pastel accents
- **AyuDark** — deep navy background (`#10141c`), vivid ayu dark accents
- Colors taken from the official ayu palette (v9.1.0): syntax colors, `editor.fg`/`editor.bg`, `ui.fg` and `common.accent`. In Mirage and Dark the accent hues are more saturated (OKLCH chroma) and slightly brighter than ayu's editor syntax colors, so they pop on slides
- **Roboto Slab** for titles and headings, **Fira Sans** for body text
- Customizable accent color — change a single line to restyle the whole presentation
- Minimal chrome: thin accent bar on the title slide, separator under each frame title, clean footline
- Three block styles: standard (accent), alert (red), example (green)
- Bibliography support via **biblatex** — ready-to-use `bibliography.bib` for citations with `\cite{}`; default style is `verbose`

## Requirements

- XeLaTeX or LuaLaTeX (required for `fontspec`)
- Fonts installed on the system: [Roboto Slab](https://fonts.google.com/specimen/Roboto+Slab), [Fira Sans](https://fonts.google.com/specimen/Fira+Sans)

## Usage

```latex
\documentclass[aspectratio=169]{beamer}
\usetheme{AyuMirage}   % or AyuLight, AyuDark
```

`beamerthemeAyuBase.sty` holds the shared layout, fonts and templates; each variant file only defines its `ayu*` palette and loads it, so keep it next to the variant you use.

Compile with:

```
lualatex main.tex
```

## Accent Color

The accent color drives titles, frame title text, the separator line, bullet points, and `\alert{}`. By default it is the ayu signature accent (`ayuAccent`). It can be changed anywhere in the preamble after `\usetheme`:

```latex
\usetheme{AyuDark}
\colorlet{ayuAccentColor}{ayuBlue}  % switch to blue
```

The rule under each frame title follows the accent by default; restyle it alone with `\setbeamercolor{frametitle rule}{bg=ayuCyan}`.

## Palette

| Name | Ayu source | Light | Mirage | Dark |
|---|---|---|---|---|
| `ayuAccent` | `common.accent.tint` | `#F29718` | `#FFD56A` | `#FDB900` |
| `ayuYellow` | `syntax.func` | `#EBA400` | `#FFD66A` | `#FFB02E` |
| `ayuOrange` | `syntax.keyword` | `#FA8532` | `#FFA244` | `#FF8A2A` |
| `ayuRed` | `syntax.markup` | `#F07171` | `#FF8B7B` | `#FF717B` |
| `ayuPink` | `syntax.operator` | `#F2A191` | `#FFA370` | `#FF9A64` |
| `ayuPeach` | `syntax.special` | `#E59645` | `#F5C379` | `#FEC572` |
| `ayuGreen` | `syntax.string` | `#86B300` | `#CBFF23` | `#ACE700` |
| `ayuTeal` | `syntax.regexp` | `#4CBF99` | `#67FAD0` | `#67FAD0` |
| `ayuCyan` | `syntax.tag` | `#55B4D4` | `#00DEFE` | `#00C6FB` |
| `ayuBlue` | `syntax.entity` | `#22A4E6` | `#63D1FF` | `#4AC3FF` |
| `ayuPurple` | `syntax.constant` | `#A37ACC` | `#E1BDFF` | `#D4A3FF` |
| `ayuError` | `common.error` | `#E65050` | `#FF6666` | `#D95757` |

Neutrals: `ayuBg` (`editor.bg`), `ayuFg` (`editor.fg`), `ayuBg4` (`ui.fg`), `ayuFg4` (`syntax.comment`); `ayuBg1`–`ayuBg3` and `ayuFg2`–`ayuFg3` are blends of these, used for the frame title bar, block bodies and secondary text. `ayuAccentOn` (`common.accent.on`) is a dark tone meant for text on top of the accent.
