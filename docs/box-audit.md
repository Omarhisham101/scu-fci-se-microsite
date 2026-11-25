# Box and spacing audit

Measured in headless Chrome through the DevTools protocol (`getBoundingClientRect` and computed style) on the final files; raw numbers are in `ev/box.json` in the author's working folder. Viewports 1400px and 320px. Z-index layers: skip link `--z-skip`, header `--z-header` (position relative, so it forms a stacking context), raised card on hover/focus `--z-raised`; all other components `auto`.

| Component | Declared | Rendered 1400 (w x h) | Rendered 320 (w x h) | Padding / border / margin (1400) |
|---|---|---|---|---|
| **Wrapper** | `width: min(100% - 2*var(--space-4), 72rem)`; margin-inline: auto; padding-top 1rem, bottom 2rem (on .page) | 1152.00 x 1521.03 | 288.00 x 2890.12 | pad 16/0/32/0, border 0, margin L/R 124/124 |
| **Header** | padding 0.75rem 1rem (12px, 16px); no height; brand mark width 3rem | 1152.00 x 72.00 | 288.00 x 212.41 | pad 12/16/12/16, border 0, margin L/R 0/0 |
| **News card** | padding 1rem (16px); border 1px; width from grid track `minmax(min(100%,16rem),1fr)` | 266.66 x 254.44 | 288.00 x 254.44 | pad 16/16/16/16, border 1, margin L/R 0/0 |
| **Button** | min-height 2.75rem (44px); padding 0.5rem 1.5rem; border 2px | 212.17 x 45.59 | 212.17 x 45.59 | pad 8/24/8/24, border 2, margin L/R 0/0 |
| **Video box** | width 100%; `aspect-ratio: 16 / 9`; no height | 832.00 x 468.00 | 288.00 x 162.00 | pad 0/0/0/0, border 0, margin L/R 0/0 |

- **Wrapper.** Declared 72rem (1152px) is a cap. At 1400 the cap wins: rendered 1152, side margins (1400-1152)/2 = 124px each. At 320 the 100% - 2rem branch wins: 320 - 32 = 288px, margins 16px. The height is never declared: it is the sum of the grid rows plus 16px top and 32px bottom padding.
- **Header.** Declared padding is 12/16. No height is declared, so rendered 72px = 48px brand mark (3rem) + 12 + 12. At 320 the flex row wraps (brand, then nav), so it grows to 212px: wrapping adds a row instead of squeezing.
- **News card.** Declared min track 16rem (256px). Rendered 266.66px at 1400 (832px main, 3 columns, 16px gaps: (832-32)/3). Content width = 266.66 - 32 padding - 2 border = 232.66 (clientWidth 265 includes padding, excludes border). Height 254.44 is not declared: align-items stretch gives every card in the row the tallest card height.
- **Button.** Declared min-height 44px, rendered 45.59px. Content line is 25.6px (16px x 1.6) + 16 padding + 4 border = 45.6, which is more than the 44px floor, so the content wins. min-height is a floor, not a size. Width is not declared: 212.17 = text + 48 padding + 4 border.
- **Video box.** Declared ratio, no height. Rendered 832 x 468 at 1400 (832 x 9/16 = 468) and 288 x 162 at 320 (288 x 9/16 = 162): the height follows the width, so the iframe never overflows or letterboxes.

Wrapper width at tested viewports: 1152px at 1400, 288px at 320.