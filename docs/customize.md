# Customize timelinejs-template website

Timelinejs-template is built on top of the [bootstrap-template](https://github.com/thecdil/bootstrap-template) base, a basic template repository to create a [Bootstrap](https://getbootstrap.com/) site using Jekyll on GitHub Pages (or where every you want to host it). 
The layout is based on the [Bootstrap starter template example](https://getbootstrap.com/docs/4.5/examples/) with a navbar, search box (using lunr.js), and sticky footer.

See [bootstrap-template](https://github.com/thecdil/bootstrap-template) repository for full documentation.

## Edit Content Pages

Edit and create pages in the "pages" folder.
Generally this will be done using Markdown (files with extension `.md`) or HTML (`.html`).
To include them in the navbar, add front matter option `nav` with the text you want to be displayed, e.g. `nav: Demo`.
Alternatively, if `nav: true` page will show up in navbar using the page `title`.
Use `nav_order` to control order of pages in the navbar.

Front matter options:

- `title` will appear as h1 at top of the page content (when using `page`, `page-full-width`, or `page-narrow` layouts only).
- `nav` if this option has a value, it will appear in the navbar as link to this page. (any stub without a `nav` value will not appear in the navbar)
- `nav_order` navbar items will be sorted using this number. 
- `layout` by default is set to `page`, but can be optionally added to override the default. Built in options are `default`, `page`, `page-full-width`, or `page-narrow`.

Use `includes` to simplify adding Bootstrap features to Markdown pages, see comments in `_include/` files for instructions.

## Customize 

bootstrap-template has a few built in customization options enabling you to quickly tweak the template theme:

- Tweak base variables in `assets/css/custom.scss` (text color, link color, container size). The variables in this file work with `_sass/_template.scss` to set some default options.
- Tweak bootstrap theme colors using `_data/theme-colors.csv`. Add a css color in the color column next to the BS color-class to override, or create a new class name. This works with `_sass/_theme-colors.scss` to auto generate btn-, text-, and bg- classes based on your settings.
- Add custom CSS to `_sass/_custom.scss`. Styles in this file will override the template and bootstrap.

Once you exhaust the possibilities of these built in options, checkout the `_layouts/` and `_includes/template/` folders. 
These files provide the basic template and can be easily tweaked using Bootstrap classes.

## Template Assets

Project assets from external sources are included in assets/lib folder:

- [Bootstrap](https://getbootstrap.com/docs/4.5/getting-started/introduction/) 4.5.3
- [JQuery](https://jquery.com/) 3.5.1
- [Bootstrap Icons](https://icons.getbootstrap.com/) 1.1.0
- [lunr.js](https://lunrjs.com/) 2.3.9
- [TimelineJS](https://github.com/NUKnightLab/TimelineJS3) 3

They are included in this directory to ensure template projects can be self-contained and could be run with out connections to external dependencies or an internet connection. 
Links to these assets are contained in the `_includes/template/head.html` and `_includes/template/foot.html` files and could easily be replaced by CDN links if desired.
The JQuery version should be kept up to date in ongoing projects, and may trigger GitHub Dependabot alerts when out of date.
