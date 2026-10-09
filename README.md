# Sharjeel Syed - Portfolio (INFR3120 Assignment 1)

Live site: https://jeel2005.github.io/Portfolio-Web-Programing/
Repository: https://github.com/jeel2005/Portfolio-Web-Programing

This README file explains how my code works and the thought process I had while coding my portfolio.

## Pages
Four separate HTML5 files, all linked from the same `<nav>` menu:

| File | Content |
|------|---------|
| index.html | Home page: welcome text and 3 boxes about my skills |
| about.html | Photo, short introduction, and an HTML5 `<video>` with `controls` and a `poster` |
| projects.html | 5 projects, each in its own `<article>` with an `<h3>` heading and a 2-3 line explanation |
| contact.html | Contact form (Name, Email, Cell No., Comments, 2+2 robot check, Reset/Submit) |

Every page has a footer with my contact email and copyright.

Semantic tags used: `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<figure>`/`<figcaption>`, `<footer>`.
The nav link for the page being viewed also has the class `current`, which highlights it in orange.

Font: Poppins from Google Fonts, loaded with `<link>` tags the same way as in the lectures.

### Form validation (contact.html)
All rules are built-in HTML5 validation, no JavaScript:
- **Name**: `required`, `pattern` allows only letters, spaces, hyphens and apostrophes, 2-50 characters
- **Email**: `type="email"` checks for a valid address format, `required`
- **Cell No.**: `type="tel"`, `pattern` forces the format `905-555-1234`, `required`
- **Comments**: `required`, `minlength="10"`
- **2+2 check**: `pattern="4"` so only the answer 4 is accepted. Taken from the example in the assignment.

## View ports (fluid design + media queries, no Flexbox)
Each HTML page links three style sheets. The browser only applies the one whose `media` query matches the screen width.
Each file is complete on its own. All layout uses percentage widths and `float`, with no Flexbox and no Grid. Floats are cleared with `<div class="clear"></div>`.

| File | Width range | Why |
|------|-------------|-----|
### CSS Files and Responsive Layout

| CSS File             | Screen Size  | Description                                                                                                                                                                                                                                                             
| `css/full.css`       | 960px and up | Used for laptops and desktops. The wrapper takes up 85% of the screen, leaving some of the gradient background visible. Navigation buttons appear in one row. Home boxes appear 3 per row, project boxes appear 2 per row, and the About Me photo sits beside the text. |
| `css/tablet.css`     | 481px–959px  | Used for tablets and smaller browser windows. The wrapper takes up 95% of the screen to give more space to the content. The layout is similar to the desktop version, but the photo is wider, the boxes are taller, and the font size is 15px.                          |
| `css/smartphone.css` | Up to 480px  | Used for smartphones. The wrapper takes up the full screen width. Navigation buttons appear in a 2-by-2 grid, while the home and project boxes stack vertically. The About Me photo appears above the text, and the font size is 14px.                                  |


The `<meta name="viewport" content="width=device-width, initial-scale=1.0">` tag in every page is required. Without it, phones would render the desktop layout zoomed out and the media queries would never match.

## Gradients
Both gradients are in all three CSS files, so they show at every screen size.
- **Angled linear gradient**: `body` background, `linear-gradient(135deg, #2A9D8F 0%, #E9C46A 100%)`. It runs diagonally from teal (top-left) to yellow (bottom-right) and is visible on all 4 pages around the white `#wrapper`.
- **Linear gradient**: `header` background, `linear-gradient(to bottom, #264653 0%, #2A9D8F 100%)`. It runs top to bottom from dark teal to teal behind my name and the nav on all 4 pages.

## Colour scheme
I entered the palette into Adobe Color (https://color.adobe.com/create) using the Custom harmony setting and saved it as a library: https://www.adobe.com/files/libraries/urn:aaid:sc:US:0949e578-c942-4e1c-af64-bd0b03d2b9d6. The colours were suggested by Claude and I chose them because I liked how they look together.

| Colour | Hex | Where it is used |
|--------|-----|------------------|
| Dark teal | #264653 | All text, footer background, header gradient start, button and wrapper shadows |
| Teal | #2A9D8F | Header gradient end, page background gradient start, home box top border, form field borders |
| Yellow | #E9C46A | Nav buttons, Reset button, footer links, page background gradient end |
| Orange | #F4A261 | Current page and hover nav button, project boxes |
| Red-orange | #E76F51 | Submit button |


## Testing
| Test | Tool | Result |
|------|------|--------|
| HTML | W3C Markup Validation Service (https://validator.w3.org/) | about.html has no errors. contact.html has no errors. index.html has no errors. projects.html has no errors|
| CSS | W3C CSS Validation Service (https://jigsaw.w3.org/css-validator/), CSS level 3 + SVG |full.css has no errors. smartphone.css has no errors. tablet.css has no errors.  |
| Links | W3C Link Checker (https://validator.w3.org/checklink) | I had 1 issue with the link. It could not check my mailto link.|
| Spelling | Grammarly | spelling mistakes were there when intially making the code but fixed before the first push. |
| Accessibility | WAVE (https://wave.webaim.org/) | WAVE had no issues with my website and gave it a 10/10  |
This was all checked when the wesbite was near completion and functioned as purpose.

## Citations
- Font: Poppins from Google Fonts (https://fonts.google.com), loaded with the `<link>` tags Google provides.
Claude helped with formatting code and helped make comments. It also helped with deciding the colour scheme and helped with the README.