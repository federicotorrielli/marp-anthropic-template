# Marp Anthropic-Style Template

A clean, accessible [Marp](https://marp.app) deck theme inspired by the
warm cream-and-coral aesthetic of Anthropic's public materials. One
markdown file, one CSS block in the frontmatter, no build pipeline.

![A Marp slide titled "Marp Anthropic-Style Template" with the subtitle "A clean, accessible deck theme for talks and lectures" set in Fraunces and Inter on a cream background with a soft coral glow in the upper right.](assets/preview-title.png)

## Why this template

- **Single-file** — the theme lives in the YAML frontmatter, so the
  deck stays portable. Copy `slides.md`, edit the content, present.
- **Readable** — Fraunces for headings, Inter for body, JetBrains Mono
  for code; generous line height; high-contrast ink on cream.
- **Two slide classes** — `<!-- _class: title -->` for opening and
  closing slides, `<!-- _class: divider -->` for chapter breaks.
- **Math built in** — KaTeX is enabled by default; flip the
  frontmatter to `math: mathjax` if you need it.
- **Showcase deck** — every styled element (lists, tables, code,
  blockquotes, math, figures, utility classes) is demonstrated in
  `slides.md` so you can see what you have before you start writing.
- **Outputs** — HTML, PDF, PPTX, and PNG/JPEG image sequences via the
  Marp CLI.

## Quickstart

```bash
git clone https://github.com/federicotorrielli/marp-anthropic-template.git my-talk
cd my-talk
# edit slides.md
marp slides.md --pdf            # → slides.pdf
```

That is the whole workflow. Open `slides.md` in any editor, replace
the example slides with your own content, and run `marp` to build.

## Prerequisites

You need one of the following:

- **Marp CLI** (recommended) — `npm install -g @marp-team/marp-cli`,
  then `marp slides.md`. See [installation
  options](https://github.com/marp-team/marp-cli#install) including
  Homebrew, Docker, and standalone binaries.
- **VS Code** — install the [Marp for VS
  Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)
  extension and use the live preview pane. No CLI needed for editing;
  exports run from the command palette.

PDF and PPTX export require a Chromium-based browser on your system.
Marp picks one up automatically on most platforms.

## Project layout

```
.
├── slides.md          # the deck and the theme — edit this
├── assets/
│   ├── placeholder.svg    # example figure used by slides.md
│   └── preview-*.png      # README screenshots
├── README.md
├── LICENSE            # EUPL-1.2
└── .gitignore         # excludes built HTML/PDF/PPTX output
```

## Customisation

### Colour palette

The palette is defined as CSS custom properties at the top of the
`<style>` block in `slides.md`. Change one variable and every slide
follows:

| Token            | Default     | Used for                              |
|------------------|-------------|---------------------------------------|
| `--cream`        | `#F0EEE6`   | Slide background                      |
| `--cream-soft`   | `#FAF9F5`   | Code blocks, blockquote, table head   |
| `--ink`          | `#1F1B16`   | Body text                             |
| `--ink-soft`     | `#3D3929`   | `h2`, secondary text, blockquote text |
| `--muted`        | `#6B6557`   | Captions, page numbers                |
| `--rule`         | `#DAD5C5`   | Hairline borders, table rows          |
| `--coral`        | `#CC785C`   | List markers, quote rule, table accent|
| `--coral-deep`   | `#BD5D3A`   | Links, `h3`, `strong`                 |
| `--coral-soft`   | `#E8C4B0`   | Title-slide glow, divider highlight   |

### Typography

Three Google Fonts are imported at the top of the style block:

- **Fraunces** (serif, 300–700) — headings
- **Inter** (sans-serif, 300–700) — body
- **JetBrains Mono** (400–500) — code

Swap any of them by editing the `@import` URL and the corresponding
`font-family` rule. The fallbacks (`Georgia`, `system-ui`,
`ui-monospace`) keep the deck readable offline if Google Fonts is
unreachable.

### Slide classes

Apply per-slide classes with Marp's HTML comment directives:

```markdown
<!-- _class: title -->
<!-- _paginate: false -->

# Title slide
## Subtitle
```

```markdown
<!-- _class: divider -->

# Section heading
```

Add your own by writing a new `section.<name> { … }` rule in the
style block.

### Utility classes

Two inline helpers ship with the template:

- `<span class="small">` — 18 px muted text for asides and footnotes.
- `<span class="cite">` — 16 px italic muted text for citations.

You can also use `<p class="small">…</p>` under a figure for a
caption-like annotation.

## Building

| Command                              | Output                       |
|--------------------------------------|------------------------------|
| `marp slides.md`                     | `slides.html` (with speaker notes via `--bespoke`) |
| `marp slides.md --pdf`               | `slides.pdf`                 |
| `marp slides.md --pptx`              | `slides.pptx` (editable)     |
| `marp slides.md --images png`        | One PNG per slide            |
| `marp slides.md --server`            | Live-reloading preview at `http://localhost:8080` |

If your slides reference local images (anything under `assets/`),
add `--allow-local-files` for PDF and PPTX export.

## Accessibility

Accessibility is in scope for this template, not an afterthought.
What is in place:

- **Contrast.** The default ink-on-cream pairing (`#1F1B16` on
  `#F0EEE6`) clears WCAG **AAA** at all body sizes. Coral accents
  (`#BD5D3A` on `#F0EEE6`) clear WCAG **AA** against the cream
  background at the default 24 px body size and at every heading
  size. If you change colours, run a contrast check before
  presenting — try [WebAIM's contrast
  checker](https://webaim.org/resources/contrastchecker/).
- **Type scale.** Body text is 24 px and headings are 22–56 px, well
  above WCAG's "large text" threshold. Avoid dropping body text below
  20 px on a slide.
- **Alt text.** The image example in `slides.md` includes descriptive
  alt text. Always write one — it is read aloud by screen readers
  during accessible HTML exports and indexed by search.
- **Heading hierarchy.** The theme styles `h1`/`h2`/`h3` distinctly so
  screen-reader users can navigate by heading. Use them in order; do
  not skip levels for visual reasons.
- **Page numbers.** `paginate: true` is on by default, with muted
  numbers via `section::after`.

What the template **cannot** do for you:

- Read your figures — write meaningful alt text, not "diagram" or
  "screenshot".
- Caption your video — if you embed media, provide captions and a
  transcript.
- Replace a screen reader test — if your audience may include screen
  reader users, export to HTML and try it with VoiceOver, NVDA, or
  Orca before the talk.

## Gallery

| Section divider | Code slide | Tables |
|---|---|---|
| ![Section-divider slide on a near-black background with the heading "Section divider" in cream and a coral underline rule.](assets/preview-divider.png) | ![Slide titled "Code" showing a Python snippet inside a soft cream code block with a hairline border.](assets/preview-code.png) | ![Slide titled "Tables" showing a five-row reference table with coral-underlined headers and soft row separators.](assets/preview-table.png) |

## Credits

- Theme inspiration: the typography and palette of Anthropic's public
  materials. **This project is not affiliated with, endorsed by, or
  sponsored by Anthropic PBC.** "Claude" and "Anthropic" are
  trademarks of Anthropic PBC.
- Built on [Marp](https://marp.app) and [Marpit](https://marpit.marp.app).
- Fonts: [Fraunces](https://fonts.google.com/specimen/Fraunces),
  [Inter](https://fonts.google.com/specimen/Inter),
  [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)
  — all under the SIL Open Font License.

## License

This template is released under the
[European Union Public Licence v1.2](https://eupl.eu/1.2/en/). See
[`LICENSE`](LICENSE) for the full text. The EUPL is a copyleft
licence that keeps the template — and any modifications you
distribute — free and reusable, while remaining compatible with GPL,
LGPL, MPL, and several other open-source licences.

Slides you write *using* this template are your own work and not
covered by the EUPL.
