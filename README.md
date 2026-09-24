# Using Grid: The Easy Method

A page skeleton (header, navigation, main content, sidebar, ad slot and footer) laid out with CSS `grid-template-areas` and rearranged for tablets and phones by two media queries.

**Live site:** <https://shayan-abrar.github.io/Using-Grid-Easy-method-/>

<p align="center">
  <a href="screenshots/preview.png"><img src="screenshots/preview.png" width="800" alt="The same page at three widths: a four-column desktop layout with navigation, main content, sidebar and ad slot, a three-column tablet layout and a single-column phone layout"></a>
</p>

Placing every element with line numbers gets hard to read once a layout has several regions. With `grid-template-areas`, each element gets a name and the container draws the layout as a text map, so a new screen size only needs a new map. The HTML stays the same, and each layout is a few readable lines of CSS.

## Quick Start

```bash
git clone https://github.com/SHAYAN-ABRAR/Using-Grid-Easy-method-.git
cd Using-Grid-Easy-method-
python3 -m http.server 8000
```

Open <http://localhost:8000> and make the browser window narrower, or use your browser's responsive design mode, to watch the regions move. On Windows, use `python` instead of `python3`. Opening `index.html` directly in a browser works too, and nothing is loaded from the internet.

## Features

- **Named areas:** each region has a `grid-area` name (`header`, `nav`, `main`, `sidebar`, `advertise` and `footer`), and the `.container` rules place them.
- **Three layouts from one HTML file:**

  | Screen width | Layout |
  | --- | --- |
  | 993px and wider | Header on top, navigation on the left, main content in the middle, sidebar and ad slot stacked on the right, footer at the bottom |
  | 576px to 992px | Header, then navigation across the full width, then sidebar beside the main content, then the ad slot beside the footer |
  | 575px and narrower | One column, in the order header, navigation, main, sidebar, ad slot, footer |

- **Separate stylesheet:** the layout lives in `style.css`, apart from the markup in `index.html`.

## Usage Example

This is the desktop map in `style.css`. Each quoted string is a row, and each word names the area that fills that cell:

```css
.container{
    gap: 20px;
    display: grid;
    grid-template-areas: 
    "header  header  header  header"
    "nav     main    main    sidebar"
    "nav      main   main     advertise"
    "footer   footer  footer  footer";
}
```

To show the ad slot above the sidebar on desktop, swap the words `sidebar` and `advertise` in the second and third rows. Neither the HTML nor the other rules need to change. Each named area must still form a rectangle, or the browser ignores the whole map.

## Limitations

- At exactly 576px wide, both media queries match. The tablet query comes later in the file, so that width uses the tablet layout.
- No column sizes are set, so the columns are sized by their content: the navigation, sidebar and ad slot stay narrow and the main content takes the rest.
- The regions hold placeholder text and links, in the browser's default font.

## Tech Stack

- HTML5
- CSS3 Grid (`grid-template-areas`) and media queries in `style.css`
- Hosted on GitHub Pages

## Contributing

This is a small practice exercise, but suggestions and bug reports are welcome. Please [open an issue](https://github.com/SHAYAN-ABRAR/Using-Grid-Easy-method-/issues). The code isn't licensed for reuse, so please ask before copying it.

## License

Copyright © 2024 Shayan Abrar. All rights reserved. See [LICENSE](LICENSE). This isn't an open-source license.

---

Built by **Shayan Abrar** · [GitHub](https://github.com/SHAYAN-ABRAR) · [LinkedIn](https://www.linkedin.com/in/shayan-abrar/)
