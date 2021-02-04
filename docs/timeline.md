# Using timelinejs-template 

The basic steps to using timelinejs-template are: 

1. create repository from the template
2. add timeline data
3. add timeline to a page

There are two builtin options for adding TimelineJS timelines to the pages of your site: Basic Timeline (using a spreadsheet) or JSON Timeline (using JSON file). 
How the timeline is embedded in the page can be controlled using the `layout` value.
These options are described below.
See docs/customize.md for builtin options to customize the website nav and look. 

## Set up repository

- Visit timelinejs-template: <https://github.com/thecdil/timelinejs-template>
- Make your own copy of the repository by clicking the green "Use this template" button (alternatively, use Import or manually copy files to a new repo).
- Edit `_config.yml` with your site information.
    - `title` will appear in the navbar with link to home page.
    - `year` and `author` appear in footer.
    - site urls (`url` and `baseurl`) are optional if using GitHub Pages, but should be filed in if hosting else where.
- Activate GitHub Pages. 
    - On your repository visit "Settings", scroll down to "GitHub Pages" section, select Branch "main" from the drop down, and click Save. 
    - Once activated, it will provide your new URL, following the pattern `https://username.github.io/repository_name`

## Create a Basic Timeline

### 1. Create Timeline Spreadsheet 

Create a [TimelineJS spreadsheet](https://timeline.knightlab.com/docs/using-spreadsheets.html) following the template--or use an one from your existing timeline embed. 
You can start from the file "timelinejs3-template.csv" in this repository or make a copy of the [TimelineJS template](https://drive.google.com/previewtemplate?id=1pHBvXN7nmGkiG8uQSUB82eNlnL8xHu6kydzH_-eguHQ&mode=public) in Google Sheets. 
Do not change any of the default column names! 

Timelinejs-template supports these extra features:

- You can use Markdown or HTML formatting in the cells
- You can include media files in the repository
    - If you want to host media files (jpg, png, mp3, pdf) in the repository, put the files in the "media" folder. 
    - Use web-safe filenames, all lowercase with no spaces or odd characters. 
    - In the spreadsheet, put the filename in the "Media" column.

### 2. Add spreadsheet to repository 

Download or save your spreadsheet as a CSV (it must be a CSV! Google Sheets works well). 
Rename to use a filename with no spaces or special characters (other than dash `-` or underscore `_`), e.g. don't use "Example timeline -- Sheet 1.csv", rename to `example-timeline.csv`.

Copy your spreadsheet into the "_data" folder in your repository.

### 3. Add timeline to a page

Add the timeline to any page in the repository using the front matter option `timeline:` with the name of your CSV file (minus the `.csv` extension).
Optionally choose a `layout:` value depending on how you want to display the timeline.
For example, your front matter might look like:

```
---
title: A Great Timeline
layout: page-full-width
# add TimelineJS
timeline: demo-timeline
---
```

## Layout options

The page `layout` set in the front matter controls how the timeline will be displayed in the template.
These options are available:

- `page` timeline will be inside a container, with navbar, title in h1, and any content above.
- `page-full-width` timeline will be inside a container-fluid, with navbar, title in h1, and any content above.
- `default` timeline will be 100% width with no x margins, with navbar above.
- `embed` timeline will be the only content inside html element, so that it can be used as src in an iframe embed on another site.

Content can be written on the page and will appear above the timeline. 
If the `timeline` option is not added to the front matter, the stub will act as a normal content page.

## Create a Timeline from JSON File

You may have a [TimelineJS formatted JSON file](https://timeline.knightlab.com/docs/json-format.html), for example downloaded from a [CollectionBuilder](https://collectionbuilder.github.io/) data export, and want a place to host it.

1. Add your TimelineJS JSON file to the repository's "media" folder, e.g. `media/example-timeline.json`
2. Add the timeline to any page in the repository using the front matter option `timeline-json` with the name of your json file (including the extension). Optionally choose a `layout` value depending on how you want to display the timeline.

For example, your front matter might look like:

```
---
title: A JSON based Timeline
layout: default
# add TimelineJS
timeline-json: example-timeline.json
---
```

## Advanced Options

TimelineJS supports some [additional init options](https://timeline.knightlab.com/docs/options.html) (in general, they aren't necessary).
These options can be passed to the js using `timeline-options` in the page front matter when adding a timeline to a page.
Add the desired option variables (following the [option docs](https://timeline.knightlab.com/docs/options.html)) nested below `timeline-options` (yml uses two spaces indent to nest).

For example:

```
timeline: demo-timeline
timeline-options: 
  start_at_end: true
  hash_bookmark: true
  timenav_position: top
```

*Note:* many of the options won't make sense for this context and some of them have inconsistent behavior so you may have to experiment with the order to get them to work.
The most useful option is probably `hash_bookmark: true`.

## Embed on Another Site

To embed a timeline on another site (similar to how TimelineJS "authoring tool" versions are used), use the `embed` layout then add the page URL as the src for an iframe. 
See "pages/embed.md" for example.
Using the `embed` layout the timeline "page" will be generated without any nav or template elements, it is just the timeline itself.

For example, your front matter might look like: 

```
---
title: Example Timeline Embed
layout: embed
# add TimelineJS
timeline: demo-timeline
---
```

Then on the other site where you want to embed it, add an iframe with src being the link to the page, like:

`<iframe src="https://thecdil.github.io/timelinejs-template/embed.html" width='100%' height='600' frameborder='0'></iframe>`

*Note:* you will probably not want an `embed` style timeline page in your nav, so leave out the `nav` option in the front matter.

# Reference

- [TimelineJS js docs](https://timeline.knightlab.com/docs/instantiate-a-timeline.html)
- [Spreadsheet docs](https://timeline.knightlab.com/docs/using-spreadsheets.html)
- [TimelineJS json docs](https://timeline.knightlab.com/docs/json-format.html)
- [json example](https://github.com/NUKnightLab/TimelineJS3/blob/master/website/templates/examples/houston/timeline3.json)
