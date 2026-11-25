# Software Engineering Department microsite

Coursework microsite for the Software Engineering Department, Faculty of Computers and Informatics, Suez Canal University (Ismailia, Egypt). Plain HTML and one stylesheet. No build step, no JavaScript, no `style` attributes.

Live: https://omarhisham101.github.io/scu-fci-se-microsite/

## Pages
- `index.html`: news cards and one wide timetable
- `programs.html`: four photographs (`srcset` + `sizes`) and one embedded video (16:9 `aspect-ratio` box)
- `contact.html`: demo form (labels tied to inputs, no submission backend) and a map link to the campus
- `styleguide.html`: palette, type scale (base 1rem, ratio 1.25), spacing, measured contrast

## Structure
- `css/site.css`: the only stylesheet. Palette, type scale, spacing, layout widths and z-index layers are custom properties on `:root`. Change `--c-brand` and the whole site follows (checked, see the PDF section 7).
- `img/`: each photo at 480, 800 and 1200 px wide, plus `credits.json`
- `docs/grids/`: grid drawings (SVG) for the four pages, committed before `css/site.css`
- `docs/evidence.pdf`: style guide, drawings, box and spacing audit, measurements, screenshots, keyboard pass, network record, brand-colour check, superseded-rules table, reflection
- `docs/box-audit.md`: the box and spacing audit on its own
- `docs/evidence/`: screenshots at 320, 768, 1400 and the 400% zoom emulation, for all four pages

## CSS approach
Mobile-first. Two breakpoints only (`40rem` and `64rem`), each with a comment giving its reason. Headings use `clamp()`. Page skeleton uses named `grid-template-areas`; the news cards and photo gallery use an auto-sizing Grid (`auto-fit`/`minmax`). Flexbox is used in the header/navigation, in card content, and in form rows. No fixed page width.

## Accessibility
Skip link, one visible focus ring on every control (amber ring, 5.12:1 on the brand header; the ink ring there is only 1.96:1 and is not relied on), labelled form fields, alt text on images, `prefers-reduced-motion` respected, text and non-text contrast measured for 15 pairs.

## Testing and evidence limits
Measurements were taken in headless Chrome through the DevTools protocol on the final files. The "400% zoom" shots are emulated (320 CSS px wide at device pixel ratio 4), not the browser's own zoom control. Not tested: real Firefox/Safari, a screen reader, a physical phone, W3C HTML validator. The wide timetable scrolls sideways inside its own box at 320px (a known, documented limit). Tab passes through 7 stops inside the YouTube iframe at 1400px, where the site's focus ring cannot render.

## Open
Open `index.html` in a browser, or use the live link. Resize to 320, 768 and 1400 px, and press Tab to test the keyboard.

Content note: news items, timetable and programme text are illustrative placeholders for the coursework, not official announcements. The contact form is a demo.

## Photo credits (Wikimedia Commons)
- Social Distancing in a Computer Lab.jpg by Mbrickn, licence CC BY 4.0: https://commons.wikimedia.org/wiki/File:Social_Distancing_in_a_Computer_Lab.jpg
- COMPUTER LAB IMUV.jpg by RitwickSingh, licence CC BY-SA 4.0: https://commons.wikimedia.org/wiki/File:COMPUTER_LAB_IMUV.jpg
- Kefalonia Wild Flora project students in computer lab.jpg by Saintfevrier, licence CC BY-SA 4.0: https://commons.wikimedia.org/wiki/File:Kefalonia_Wild_Flora_project_students_in_computer_lab.jpg
- L Nicosia's YAL laptop students jeh.jpg by Jim.henderson, licence CC0: https://commons.wikimedia.org/wiki/File:L_Nicosia's_YAL_laptop_students_jeh.jpg

Video: "What is Software Engineering? | College Majors" by Study Hall, https://www.youtube.com/watch?v=WtxWuvxsO8M
