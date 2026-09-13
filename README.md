# Research Touying template

This Typst/Touying template reproduces the visual system of `[Template] Research.pptx`: a white 16:9 canvas, Arial-style typography, 36 pt slide titles, restrained HKUST blue and gold accents, alternating pale-blue tables, cover branding, and small slide numbers.

## Use it

1. Upload this whole folder to the Typst web app, or open it locally in a Typst project.
2. Compile `main.typ`.
3. Replace the sample text and `assets/demo-hardware.png` with your own content.

The template targets **Touying 0.7.4**:

```typst
#import "@preview/touying:0.7.4": config-info
#import "research-theme.typ": *

#show: research-theme.with(
  config-info(
    title: [Presentation title],
    subtitle: [Presenter: Your Name],
    date: [9 September 2026],
  ),
)

#research-title-slide()

== First slide

Your content here.
```

## Main components

- `research-title-slide()` reproduces the title page and its two brand lockups.
- Level-two headings (`== Slide title`) create standard slides automatically.
- Level-one headings (`= Section`) create a minimal section divider.
- `research-columns(left, right)` creates a two-column layout.
- `research-table(header, rows)` creates the pale-blue table style.
- `research-callout[...]` creates the yellow formula/callout box.
- `research-process(...)` creates the blue phase sequence.
- `research-caption[...]`, `research-source[...]`, `research-highlight[...]` provide the recurring text treatments.

## Fonts

The PowerPoint uses Arial. The theme requests Arial first and then falls back to Liberation Sans, Carlito, Noto Sans, or common Chinese sans-serif fonts. For the closest match, compile in an environment with Arial installed. Chinese text will use the first available CJK fallback.

## Colors

| Token | Hex | Typical use |
|---|---:|---|
| `research-blue` | `#004B8E` | Labels, captions, primary blocks |
| `research-navy` | `#003366` | Dark brand text |
| `research-gold` | `#CE9310` | Accent lines and emphasis |
| `research-pale-blue` | `#D9E4EE` | Alternating table rows |
| `research-paler-blue` | `#F2F6F9` | Light panels and table rows |
| `research-red` | `#C00000` | Warnings or critical emphasis |

The template keeps layout values in inches so its positions map directly to the original 13.333 × 7.5 inch PowerPoint canvas.
