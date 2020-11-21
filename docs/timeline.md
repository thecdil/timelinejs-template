# TimelineJS

By default [TimelineJS](https://timeline.knightlab.com/) is set up to work with their "authoring tool" using Google Sheets, providing an easy way to set up and publish a timeline embed.
However, relying on Google Sheets can be problematic:

- API outages and changes unexpectedly break the TimelineJS service
- you may not have a convenient location to host your media files
- Google platform exposes your users to unnecessary privacy tradeoffs

To avoid these issues you can [self-host your TimelineJS projects](https://timeline.knightlab.com/docs/instantiate-a-timeline.html) and use the standalone javascript to create timelines without relying on any 3rd party services.

The timelinejs-template implements the basics of TimelineJS in a simple Jekyll project template to make self-hosting easy on GitHub Pages.
This approach is more sustainable, keeping the library assets, metadata, and media together in a self-contained package (rather than multiple 3rd party platforms).

## Create a Basic Timeline

### 1. Set up repository 

- Make your own copy of the [timelinejs-template](https://github.com/uidaholib/timelinejs-template) repository by clicking the green "Use this template" button (alternatively, use Import or manually copy files to a new repo).
- Activate GitHub Pages in your new repository's "Settings".

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

### Add spreadsheet to repository 

Download or save your spreadsheet as a CSV (it must be a CSV!). 
Rename to use a filename with no spaces or odd characters, e.g. `example-timeline.csv`.

Copy your spreadsheet into the "_data" folder in your repository.

### Add timeline to a page

Add the timeline to any page in the repository using the front matter option `timeline:` with the name of your CSV file (minus the `.csv` extension).
Choose a `layout:` value depending on how you want to display the timeline.
For example, your front matter might look like:

```
---
title: A Great Timeline
layout: page-full-width
# add TimelineJS
timeline: demo-timeline
---
```

Layout options:

- `page` timeline will be inside a container, with navbar, title in h1, and any content above.
- `page-full-width` timeline will be inside a container-fluid, with navbar, title in h1, and any content above.
- `default` timeline will be 100% width with no x margins, with navbar above.
- `embed` timeline will be the only content inside html element, so that it can be used as src in an iframe embed on another site.

Content can be written on the page and will appear above the timeline. 
If the `timeline` option is not added to the front matter, the stub will act as a normal content page.
