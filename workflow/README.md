# DataRescue Workflow -- Overview

This document describes the workflow our coalition uses for the **Data Rescue project**, both at in-person events and when people work remotely. It explains the process that a url/dataset goes through from the time it has been nominated by a [seeder](seednsort.md), until it is _either_ made available as a record in a [CKAN data catalog](https://ckan.org/), or sent to the [Internet Archive](https://www.archive.org) as a seed for their [End of Term Crawl](http://freegovinfo.info/node/11477). The process involves several distinct stages, and is designed to maximize smooth hand-offs so that each phase is handled by someone with distinct expertise in the area they're tackling, while the data is always being tracked for security.

## Before you begin
We are so glad that you are participating in this project!
- If you are an event organizer: learn about [what you need to do to prepare the event](advance-work.md), and peruse the [Overview Repo](https://github.com/edgi-govdata-archiving/overview).
- If you are an event volunteer: read the event-specific documents, familiarize yourself with the **specific goals of the event**, and come ready to get some data! 

## Tools and Docs Overview

Data Rescue events make use of two main tools:
- [The Data Rescue Chrome Extension](https://chrome.google.com/webstore/detail/nominationtool/abjpihafglmijnkkoppbookfkkanklok) to start the ball rolling, identifying URL's and datasets that should be preserved
- [The Data Rescue Archiving App](http://www.archivers.space/) to track progress through all subsequent stages

We also rely heavily on the [EDGI Agency & Sub-agency Primers](https://envirodatagov.org/agency-forecasts/) as guides to where to look for important data andweb pages.

We use lots of other docs and tools too; we link to some of them in this document, but you can also explore the [EDGI Github organization](https://github.com/edgi-govdata-archiving/) and especially the [Overview](https://github.com/edgi-govdata-archiving/overview) repository. 

## Plan Overview

### 1. [Seeders](seednsort.md) 
Seeders canvass the resources of a given government agency, identifying important URLs. They identify whether those URLs can be crawled by the Internet Archive's webcrawler. They use the [Nomination Tool Chrome Extension](https://chrome.google.com/webstore/detail/nominationtool/abjpihafglmijnkkoppbookfkkanklok?hl=en) as well as the [agency primers](https://github.com/edgi-govdata-archiving/agency-primers/blob/master/README.md) for this work.

### 2. [Researchers](research.md)
From this stage on, progress is tracked exclusively through the [Data Rescue Archiving app](http://archivers.space). Researchers inspect individual URL's/datasets and make a more granular assessment of them, including a preliminary assessment of the type of data, the kinds of tools that might be useful for harvesters, and the importance of the data. [Research](research.md) describes this process in more detail. 
*Often this step is incorporated into either "Seeding" or "Harvesting".*

### 3. [Harvesters](harvesting.md)
Harvesters capture the actual data. This is a complex task which can require substantial technical expertise, and which requires different techniques for different tasks. The [harvesting tools](https://github.com/edgi-govdata-archiving/harvesting-tools) repo has a number of starting points and [Harvesting](harvesting.md) describes the required harvesting format. 

### 4. [Checkers](checking.md)
Checkers inspect a harvested dataset and make sure that it is complete. The main question the checkers need to answer is "will the bag make sense to a scientist"? Checkers need to have an in-depth understanding of harvesting goals and potential content variations for datasets.

### 5. [Baggers](bagging.md)
Baggers do some quality assurance on the dataset to make sure the content is correct and corresponds to what was described in the spreadsheet. Then they package the data into a bagit file (or "bag"), which includes basic technical metadata and upload it to final DataRefuge destination.

### 7. [Describers](metadata.md)
Describers create a descriptive record in the destination CKAN repository for each bag. Then they links the record to the bag, and make the record public.

## After the Event!
Data Rescue is a coalition and a movement. When the event is over, and exhaustion is setting in over a couple of rounds... there is still work to do. 
- [ ] **someone MUST follow up with coalition partners** -- this mostly means EDGI & Data Refuge -- about the final disposition of the data. Are there large datasets that need to be uploaded to S3 by an authorized person? Has someone taken responsibility for handing seeds off to the Internet Archive? etc. 
- [ ] **someone MUST pass feedback about event processes** back to other Data Rescue groups, so we can all learn from your experience
- [ ] hopefully, some of you **WILL continue to be involved in the data protection movement**, and contribute your ideas, energy, and good will to building a sustainable future for knowledge.

## Partners
Data Rescue is a broad, grassroots effort with support from numerous local and nationwide networks. Thanks particularly to [EDGI](https://envirodatagov.org/) and [Date Refuge](http://www.ppehlab.org/datarefuge/) for their leadershp, and to our numerous supporters for their hard work.
