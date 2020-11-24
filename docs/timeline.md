# Using timelinejs-template 

There are two builtin options for adding TimelineJS timelines to the pages of your site: Basic Timeline (using a spreadsheet) or JSON Timeline (using JSON file). 
How the timeline is set in the page can be controlled using the `layout` option.
These options are described below.
See docs/customize.md for builtin options to customize the website nav and look. 

## Create a Basic Timeline

### 1. Set up repository 

- Make your own copy of the [timelinejs-template](https://github.com/thecdil/timelinejs-template) repository by clicking the green "Use this template" button (alternatively, use Import or manually copy files to a new repo).
- Edit `_config.yml` with your site and repository information
- In your new repository visit "Settings" to activate GitHub Pages

### 2. Create Timeline Spreadsheet 

Create a [TimelineJS spreadsheet](https://timeline.knightlab.com/docs/using-spreadsheets.html) following the template--or use an one from your existing timeline embed. 
You can start from the file "timelinejs3-template.csv" in this repository or make a copy of the [TimelineJS template](https://drive.google.com/previewtemplate?id=1pHBvXN7nmGkiG8uQSUB82eNlnL8xHu6kydzH_-eguHQ&mode=public) in Google Sheets. 
Do not change any of the default column names! 

Timelinejs-template supports these extra features:

- You can use Markdown or HTML formatting in the cells
- You can include media files in the repository
    - If you want to host media files (jpg, png, mp3, pdf) in the repository, put the files in the "media" folder. 
    - Use web-safe filenames, all lowercase with no spaces or odd characters. 
    - In the spreadsheet, put the filename in the "Media" column.

These limitations:

- "Time" column is not implemented
- "Eras" are not implemented

### 3. Add spreadsheet to repository 

Download or save your spreadsheet as a CSV (it must be a CSV!). 
Rename to use a filename with no spaces or special characters (other than dash `-` or underscore `_`), e.g. `example-timeline.csv`.

Copy your spreadsheet into the "_data" folder in your repository.

### 4. Add timeline to a page

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

### Layout options

The page `layout` set in the front matter controls how the timeline will be displayed in the template.
These options are available:

- `page` timeline will be inside a container, with navbar, title in h1, and any content above.
- `page-full-width` timeline will be inside a container-fluid, with navbar, title in h1, and any content above.
- `default` timeline will be 100% width with no x margins, with navbar above.
- `embed` timeline will be the only content inside html element, so that it can be used as src in an iframe embed on another site.

Content can be written on the page and will appear above the timeline. 
If the `timeline` option is not added to the front matter, the stub will act as a normal content page.

## Create a Timeline from JSON File

You may have a TimelineJS formatted JSON file, for example downloaded from a [CollectionBuilder](https://collectionbuilder.github.io/) data export, and want a place to host it.

1. Set up your project repository as in the Basic example above.
2. Add your TimelineJS JSON file to the repository's "media" folder, e.g. `media/example-timeline.json`
3. Add the timeline to any page in the repository using the front matter option `timeline-json` with the name of your json file (including the extension). Optionally choose a `layout` value depending on how you want to display the timeline.

For example, your front matter might look like:

```
---
title: A JSON based Timeline
layout: default
# add TimelineJS
timeline-json: example-timeline.json
---
```

# Reference

- [TimelineJS json docs](https://timeline.knightlab.com/docs/json-format.html)
- [json example](https://github.com/NUKnightLab/TimelineJS3/blob/master/website/templates/examples/houston/timeline3.json)
- [TimelineJS js docs](https://timeline.knightlab.com/docs/instantiate-a-timeline.html)
- [Spreadsheet docs](https://timeline.knightlab.com/docs/using-spreadsheets.html)
