---
marp: true
theme: default
paginate: true
size: 16:9
math: katex
style: |
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Fraunces:opsz,wght@9..144,300;9..144,400;9..144,500;9..144,600;9..144,700&family=JetBrains+Mono:wght@400;500&display=swap');

  /* ---------- Design tokens ---------- */
  :root {
    --cream:        #F0EEE6;  /* page background */
    --cream-soft:   #FAF9F5;  /* code, blockquote, table head */
    --ink:          #1F1B16;  /* body text */
    --ink-soft:     #3D3929;  /* secondary text, h2 */
    --muted:        #6B6557;  /* captions, page numbers */
    --rule:         #DAD5C5;  /* hairlines */
    --coral:        #CC785C;  /* primary accent */
    --coral-deep:   #BD5D3A;  /* links, h3, strong */
    --coral-soft:   #E8C4B0;  /* title-slide glow, divider accents */
  }

  /* ---------- Base slide ---------- */
  section {
    font-family: 'Inter', system-ui, sans-serif;
    font-size: 24px;
    color: var(--ink);
    background: var(--cream);
    padding: 60px 72px 56px 72px;
    line-height: 1.45;
    letter-spacing: -0.005em;
  }

  /* ---------- Headings ---------- */
  h1, h2, h3 {
    font-family: 'Fraunces', 'Source Serif Pro', Georgia, serif;
    font-weight: 500;
    color: var(--ink);
    letter-spacing: -0.015em;
    line-height: 1.15;
  }
  h1 {
    font-size: 40px;
    margin: 0 0 0.25em 0;
    padding-bottom: 0.35em;
    border-bottom: 1px solid var(--rule);
  }
  h2 { font-size: 30px; color: var(--ink-soft); margin-top: 0; }
  h3 { font-size: 22px; color: var(--coral-deep); }

  /* ---------- Inline ---------- */
  strong { color: var(--coral-deep); font-weight: 600; }
  em     { color: var(--ink-soft); }
  a      { color: var(--coral-deep); text-decoration: underline; text-underline-offset: 3px; }

  /* ---------- Blockquote ---------- */
  blockquote {
    border-left: 3px solid var(--coral);
    background: var(--cream-soft);
    padding: 14px 22px;
    margin: 18px 0;
    color: var(--ink-soft);
    font-style: normal;
  }

  /* ---------- Code ---------- */
  code, pre {
    font-family: 'JetBrains Mono', ui-monospace, monospace;
    background: var(--cream-soft);
    border: 1px solid var(--rule);
    border-radius: 4px;
    padding: 1px 6px;
    font-size: 0.9em;
  }
  pre { padding: 12px 16px; }

  /* ---------- Tables ---------- */
  table {
    font-size: 20px;
    border-collapse: collapse;
    margin: 12px 0;
    width: 100%;
  }
  th {
    background: var(--cream-soft);
    color: var(--ink-soft);
    text-align: left;
    font-weight: 600;
    border-bottom: 2px solid var(--coral);
    padding: 10px 14px;
  }
  td {
    border-bottom: 1px solid var(--rule);
    padding: 10px 14px;
  }

  /* ---------- Lists ---------- */
  ul, ol { margin: 0.4em 0 0.4em 1.1em; padding: 0; }
  li     { margin: 0.25em 0; }
  li::marker { color: var(--coral); }

  /* ---------- Figures ---------- */
  section img {
    display: block;
    margin: 8px auto;
    max-width: 92% !important;
    max-height: 380px !important;
    width: auto !important;
    height: auto !important;
    object-fit: contain;
  }
  figure     { margin: 0; text-align: center; }
  figcaption { font-size: 16px; color: var(--muted); margin-top: 6px; }

  /* ---------- Utility classes ---------- */
  .small { font-size: 18px; color: var(--muted); }
  .cite  { font-size: 16px; color: var(--muted); font-style: italic; }

  /* ---------- Page number ---------- */
  section::after {
    color: var(--muted);
    font-family: 'Inter', sans-serif;
    font-size: 14px;
    font-weight: 400;
  }

  /* ---------- Title slide:  <!-- _class: title --> ---------- */
  section.title {
    background:
      radial-gradient(circle at 88% 18%, var(--coral-soft) 0%, transparent 38%),
      var(--cream);
    padding: 96px 96px 80px 96px;
  }
  section.title h1 {
    font-size: 56px;
    border: none;
    padding: 0;
    line-height: 1.1;
  }
  section.title h2 {
    font-size: 28px;
    color: var(--coral-deep);
    font-weight: 400;
    margin-top: 0.4em;
  }
  section.title::after { content: ''; }

  /* ---------- Section divider:  <!-- _class: divider --> ---------- */
  section.divider {
    background: var(--ink);
    color: var(--cream);
    padding: 96px;
  }
  section.divider h1 {
    color: var(--cream);
    border-color: var(--coral);
    font-size: 52px;
  }
  section.divider strong { color: var(--coral-soft); }
---

<!-- _class: title -->
<!-- _paginate: false -->

# Marp Anthropic-Style Template

## A clean, accessible deck theme for talks and lectures

*Your Name* — Affiliation
*Event or course* — Date

---

# About this template

This is a **Marp** deck themed in the style popularised by Anthropic's
public materials: a warm cream canvas, ink-dark body text, and coral
accents on a *Fraunces* + *Inter* typographic pairing.

Edit `slides.md` and run `marp slides.md` (or use the VS Code extension)
to produce HTML, PDF, or PowerPoint output. Everything you need is in
this one file — the CSS lives in the frontmatter so the deck travels
on its own.

See the [Marp documentation](https://marpit.marp.app/) for the full
syntax reference.

---

<!-- _class: divider -->

# Section divider

A **dark interlude** between chapters.
Use sparingly to mark major transitions.

---

# Lists and quotations

Bullet lists use coral markers:

* First idea, kept short and concrete.
* Second idea, written so it stands on its own.
* Third idea, with a *gentle* emphasis where it helps.

Numbered lists work the same way:

1. Set up the problem.
2. Describe the approach.
3. Report the result.

> Block quotes get a coral rule and a soft cream background — useful
> for pulling out a definition, a key claim, or a line from a paper.

---

# Code

Inline `code` sits on the same soft cream as block quotes, with a thin
hairline border. Fenced blocks pick up the same treatment:

```python
def relative_decoder_norm(d_a, d_b):
    """Fraction of a feature's decoder weight that lives in model A."""
    na, nb = norm(d_a), norm(d_b)
    return na / (na + nb)
```

Use code blocks for **short, readable** snippets — long listings rarely
survive the projector. If you need a wider line, drop the body font
size for that slide with a scoped directive.

---

# Mathematics

KaTeX is enabled in the frontmatter (`math: katex`). Inline math like
$\mathcal{R}_i^A = \|\mathbf{d}_i^A\| / (\|\mathbf{d}_i^A\| + \|\mathbf{d}_i^B\|)$
flows with the prose, and display math gets its own line:

$$
\mathcal{L} \;=\; \underbrace{\|\mathbf{x}_A - \hat{\mathbf{x}}_A\|_2^2}_{\text{model A reconstruction}}
        \;+\; \underbrace{\|\mathbf{x}_B - \hat{\mathbf{x}}_B\|_2^2}_{\text{model B reconstruction}}
$$

Switch to MathJax by changing `math: katex` to `math: mathjax` if you
need extensions KaTeX does not support.

---

# Tables

| Feature           | Default value | Where to change it      |
|-------------------|---------------|-------------------------|
| Page size         | 16:9          | Frontmatter `size:`     |
| Body font         | Inter         | `--cream` block in CSS  |
| Heading font      | Fraunces      | `h1, h2, h3` rule       |
| Accent colour     | `#CC785C`     | `--coral` token         |
| Code font         | JetBrains Mono| `code, pre` rule        |

Header cells use a coral underline; row separators are a soft rule so
the eye follows the data, not the grid.

---

# Figures

![A placeholder figure showing the cream canvas, coral accent rule, and ink text used by this theme.](assets/placeholder.svg)

<p class="small">Figures are centred and capped at 380px tall. Always
write descriptive alt text — it is read aloud by screen readers and
indexed by search.</p>

---

# Utility classes

The theme ships two small helpers you can apply with raw HTML:

* `<span class="small">` — 18px muted text, for footnotes and asides.
* `<span class="cite">` — 16px italic muted text, for source lines.

<span class="small">Use `.small` for caveats that should not compete
with the main point of the slide.</span>

<span class="cite">Smith et al., *On the Aesthetics of Slide Decks*, 2024.</span>

---

<!-- _class: title -->
<!-- _paginate: false -->

# Get started

## Fork, edit `slides.md`, present.

`marp slides.md --pdf` &nbsp;·&nbsp; `marp slides.md --html` &nbsp;·&nbsp; `marp slides.md --pptx`
