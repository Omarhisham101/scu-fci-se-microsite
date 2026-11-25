# Software Engineering Department microsite

Coursework microsite for the Software Engineering Department, Faculty of Computers and Informatics, Suez Canal University (Ismailia, Egypt). Plain HTML and one stylesheet, no build step, no JavaScript, no `style` attributes.

- `index.html`: news cards and one wide timetable
- `programs.html`: four photographs (`srcset` + `sizes`) and one embedded video (16:9 `aspect-ratio` box)
- `contact.html`: form and map link
- `styleguide.html`: palette, type scale (base 1rem, ratio 1.25), spacing, measured contrast
- `css/site.css`: the shared stylesheet. All palette, type and spacing values are custom properties on `:root`. Change `--c-brand` and the whole site follows.
- `docs/grids/`: the page grid drawings, committed before any CSS existed
- `docs/evidence.pdf`: style guide, drawings and test evidence

Content note: news items, timetable and programme text are illustrative placeholders for the coursework, not official announcements.

## Photo credits (Wikimedia Commons)
- Social Distancing in a Computer Lab.jpg by Mbrickn, licence CC BY 4.0: https://commons.wikimedia.org/wiki/File:Social_Distancing_in_a_Computer_Lab.jpg
- COMPUTER LAB IMUV.jpg by RitwickSingh, licence CC BY-SA 4.0: https://commons.wikimedia.org/wiki/File:COMPUTER_LAB_IMUV.jpg
- Kefalonia Wild Flora project students in computer lab.jpg by Saintfevrier, licence CC BY-SA 4.0: https://commons.wikimedia.org/wiki/File:Kefalonia_Wild_Flora_project_students_in_computer_lab.jpg
- L Nicosia's YAL laptop students jeh.jpg by Jim.henderson, licence CC0: https://commons.wikimedia.org/wiki/File:L_Nicosia's_YAL_laptop_students_jeh.jpg

Video: "What is Software Engineering? | College Majors" by Study Hall, https://www.youtube.com/watch?v=WtxWuvxsO8M
