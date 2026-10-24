# Sigfly Design Guide

**Style:** Retro Nordic Poster · Version 1.0 · October 2026

## Identity
A playful, bold visual language inspired by mid-century Scandinavian illustrated book and film posters: flat color, graphic contrast, strong type, warm paper, and a slightly imperfect print-like personality. Modern apps should remain accessible, responsive, and easy to use.

**Keywords:** warm, confident, playful, graphic, editorial, simple.

## Color palette

| Token | Hex | Use |
|---|---|---|
| Paper | `#F2DFB5` | Main warm background |
| Cream | `#FFF3D9` | Cards, inputs, raised surfaces |
| Mustard | `#EABF58` | Highlights, labels, secondary emphasis |
| Vermilion | `#E44D2C` | Primary accent, active states, bold headings |
| Deep blue | `#1F426A` | Supporting text, links, alternate accents |
| Ink | `#191919` | Main text, borders, outlines |
| Brick | `#B83E27` | Small uppercase eyebrow headings |

Use cream/paper as the dominant background, ink for primary text, vermilion for emphasis, deep blue for supporting copy, and mustard sparingly. Avoid gradients and neon colors; use mostly flat blocks of color.

## Typography
- Prefer bold, condensed or heavy sans-serif headings; fallback: `Arial Black`, `Impact`, `system-ui`, sans-serif.
- Use a clean system sans-serif for body copy.
- Large headings: uppercase, heavy, tight tracking, approximately `clamp(3rem, 10vw, 5.5rem)`.
- Eyebrow labels: uppercase, bold, wide letter spacing (`0.15em`).
- Body text: 16–18px minimum on mobile, line-height 1.5.
- Favor short, punchy copy. Avoid all-caps for long paragraphs.

## Layout and components
- **Mobile first.** Start at 320–390px; grow into a centered max-width layout around 1100px.
- Give the hero generous vertical breathing room.
- Use thick dark outlines (2–3px) for buttons, inputs, and prominent cards.
- Use subtle rounding (4–10px), not overly pill-shaped controls.
- Buttons should have high contrast, clear hover/focus states, and at least 44px tap height.
- Project cards: bold title, short description, optional flat-color icon, prominent 'Open app' action.
- Use 1 column on narrow screens, 2–3 columns on larger screens.
- Prefer simple borders, graphic dividers, and color blocks over shadows and glass effects.
- For interactive tools, prioritize clarity and readable data over decorative styling.

## Accessibility
- Check text contrast, especially blue/red on warm paper.
- Provide visible keyboard focus outlines and semantic HTML.
- Never rely on color alone to convey state.
- Respect reduced-motion preferences.
- Keep inputs labeled and touch targets comfortably sized.

## Reusable CSS starter

```css
:root {
  --paper: #F2DFB5;
  --cream: #FFF3D9;
  --mustard: #EABF58;
  --vermilion: #E44D2C;
  --blue: #1F426A;
  --ink: #191919;
  --brick: #B83E27;
  --border: 3px solid var(--ink);
  --radius: 6px;
}
* { box-sizing: border-box; }
body {
  margin: 0;
  background: var(--paper);
  color: var(--ink);
  font: 400 17px/1.5 system-ui, sans-serif;
}
.container { width: min(100% - 40px, 1100px); margin-inline: auto; }
.eyebrow {
  color: var(--brick);
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: .15em;
}
.display {
  font-family: Impact, 'Arial Black', system-ui, sans-serif;
  font-size: clamp(3rem, 10vw, 5.5rem);
  line-height: .98;
  text-transform: uppercase;
  letter-spacing: -.025em;
}
.accent { color: var(--vermilion); }
.supporting { color: var(--blue); }
.card, .input, .button {
  background: var(--cream);
  border: var(--border);
  border-radius: var(--radius);
}
.card { padding: 24px; }
.input { width: 100%; padding: 14px 18px; font: inherit; }
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 48px;
  padding: 10px 22px;
  color: var(--ink);
  font: 800 16px/1.2 system-ui, sans-serif;
  text-decoration: none;
  cursor: pointer;
}
.button:hover { background: var(--mustard); }
.button:focus-visible, .input:focus-visible {
  outline: 3px solid var(--blue);
  outline-offset: 3px;
}
.projects { display: grid; grid-template-columns: 1fr; gap: 20px; }
@media (min-width: 700px) {
  .projects { grid-template-columns: repeat(2, minmax(0, 1fr)); }
}
@media (min-width: 1050px) {
  .projects { grid-template-columns: repeat(3, minmax(0, 1fr)); }
}
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after { scroll-behavior: auto !important; transition: none !important; }
}
```

## Signature homepage copy (reference, not mandatory for every app)

**BUCKETS OF RAIN**  
**IDEAS.**  
**APPS.**  
Little red wagon  
Little red bike  
I ain't no monkey but I know what I like

## Applying the guide to new apps
1. Keep the shared colors, headline weight, paper background, and graphic borders.
2. Give each app its own distinctive icon or hero illustration.
3. Adapt density to the task: dashboards may use more compact cards and tables than the homepage.
4. Keep functionality, responsiveness, and accessibility more important than decorative fidelity.
5. Add a link back to `https://sigfly.github.io/` where appropriate.

## Reference
Inspired by the user's three vintage illustrated poster references and the live Sigfly App Hub screenshot. This is a design interpretation, not a reproduction of poster artwork.
