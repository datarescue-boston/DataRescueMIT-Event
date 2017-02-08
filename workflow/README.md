# DataRescue SF Bay Workflow

This document explains the process that a url/dataset goes through from the time it has been nominated by a [web archiver (seeder)](seednsort.md), until it is _either_ made available as a record in a [CKAN data catalog](https://ckan.org/), or sent to the [Internet Archive](https://www.archive.org) as a seed for their [End of Term Crawl](http://freegovinfo.info/node/11477). The process involves several distinct stages, and is designed to maximize smooth hand-offs so that each phase is handled by someone with distinct expertise in the area they're tackling, while the data is always being tracked for security.

## Before you begin
We are so glad that you are participating in this project! Please make sure you've already read the [Event Guide](../README.md) and picked a track to participate in.

## Tools and Docs Overview

Data Rescue events make use of two main tools:
- Web Archiving: [The Data Rescue Chrome Extension](https://chrome.google.com/webstore/detail/nominationtool/abjpihafglmijnkkoppbookfkkanklok) to start the ball rolling, identifying URL's and datasets that should be preserved
- Data Archiving: [The Data Rescue Archiving App](http://www.archivers.space/) to track progress through all subsequent stages

We also rely heavily on the [EDGI Agency & Sub-agency Primers](https://envirodatagov.org/agency-forecasts/) as guides to where to look for important data and web pages.

We use lots of other docs and tools too; we link to some of them in this document, but you can also explore the [EDGI Github organization](https://github.com/edgi-govdata-archiving/) and especially the [Overview](https://github.com/edgi-govdata-archiving/overview) repository. 

## Plan Overview

### 1. Web Archiving (Done by [Seeders)](seednsort.md))
Seeders canvass the resources of a given government agency, identifying important URLs. They identify whether those URLs can be crawled by the Internet Archive's webcrawler. They use the [Nomination Tool Chrome Extension](https://chrome.google.com/webstore/detail/nominationtool/abjpihafglmijnkkoppbookfkkanklok?hl=en) as well as the [agency primers](https://envirodatagov.org/agency-forecasts/) for this work.

### 2. Data Archiving (Done by [Researchers](research.md) & [Harvesters](harvesting.md))
From this stage on, progress is tracked exclusively through the [Data Rescue Archiving app](http://archivers.space).

[Researchers](research.md) inspect individual URL's/datasets and make a more granular assessment of them, including a preliminary assessment of the type of data, the kinds of tools that might be useful for harvesters, and the importance of the data.

[Harvesters](harvesting.md) capture the actual data. This is a complex task which can require substantial technical expertise, and which requires different techniques for different tasks. The [harvesting tools](https://github.com/edgi-govdata-archiving/harvesting-tools) repo has a number of starting points, but harvesters should use the scraping tools most familiar to them.

## Storytelling & Next Steps (e.g. the "Long Tail")

Data Rescue is a coalition and a movement. When the event is over, and exhaustion is setting in over a couple of rounds...there is still work to do. If you are willing to keep participating in this important work, please join our Storytelling & Next Step tracks and make sure you are connected with our partner organizations before you leave.

## Partners
Data Rescue is a broad, grassroots effort with support from numerous local and nationwide networks. Thanks particularly to [EDGI](https://envirodatagov.org/) and [Data Refuge](http://www.ppehlab.org/datarefuge/) for their leadershp, and to our numerous supporters for their hard work.
