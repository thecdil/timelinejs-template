---
title: About timelinejs-template
nav: About
nav_order: 2
layout: page-narrow
---

[timelinejs-template](https://github.com/thecdil/timelinejs-template) is basic Jekyll template for creating self-hosted [TimelineJS](https://timeline.knightlab.com/) on GitHub Pages.
It is compatible with existing timelines created in Google Sheets following the TimelineJS template or can be used with TimelineJS formatted JSON files.

{% include button.html text="Get Started" link="https://github.com/thecdil/timelinejs-template/blob/main/docs/timeline.md" color="success" %}

*Note:* since the template implements self hosted TimelineJS3, please explore [TimelineJS](https://timeline.knightlab.com/) for more examples, data format documentation, and advanced features.

## Why timelinejs-template?

[TimelineJS](https://timeline.knightlab.com/) is a very popular open-source project to create visual timelines that can be embedded on a webpage.
Their "authoring tool" provides an easy way to create and publish a timeline embed using Google Sheets.
This is great for getting started with minimal setup and no overhead.

However, relying on Google Sheets can be problematic:

- API outages and changes unexpectedly break the TimelineJS service
- you may not have a convenient location to host your media files or a website to embed your timelines
- Google platform exposes your users to unnecessary privacy tradeoffs

To avoid these issues you can [self-host your TimelineJS projects](https://timeline.knightlab.com/docs/instantiate-a-timeline.html) and use the standalone javascript to create timelines without relying on any 3rd party services.

The `timelinejs-template` implements the basics of TimelineJS in a simple Jekyll project template to make self-hosting easy on [GitHub Pages](https://pages.github.com/).
This approach is more sustainable, keeping the library assets, metadata, and media together in a self-contained package (rather than multiple 3rd party platforms).
