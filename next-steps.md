# Next Steps Track: Tech for Monitoring and Continued Access

**Tentative outline for next-steps breakout in afternoon**

Even though we're nowhere near done collecting data, events are pushing us to think about what we do next. We're already seeing changes to government websites and even small-scale disappearance of data from the web. We see at least three areas of concern that we hope to build on immediately:
1. [Monitoring & Filtering](#monitoring-and-filtering-websites) of website archives (work with @titaniumbones in the [pagefreezer-cli](https://github.com/edgi-govdata-archiving/pagefreezer-cli) repo)
1. [Building Machine-Learning Infrastructure](#machine-learning) for mass processing of website archive data (work with @acshn or independently in **Some new repo?**)
1. [Building Resiliency and Sustainability](#building-resiliency) in the storage, distribution, and accessibility of the datasets we harvest (work with **???**, starting with the [Guides](https://github.com/edgi-govdata-archiving/guides) repo, and perhaps building some new spec.)

## Monitoring And Filtering Websites

[Page Freezer](http://www.pagefreezer.com) has generously donated use of their tracking service for the next four years. At present they provide us with zip archive files on a weekly basis; each file contains full html files (also assets) harvested in that week's indexing run.

We're in the process of negotiating storage/bandwidth/compute time to start running the software & storing the archives on our own web-accessible nodes; until that comes together, we will be using these zipfiles as the basis for our comparisons. We have flipped back and forth but currently think **local comparison** of stored versions to each other makes the most sense (some other options are descripted in the repo linked to below).

The vast majority of web page changes are of limited interest to us, and so we need to write filters that allow us to prioritize changes. Our analysts are currently drowning in false positives. Here are some examples:

* A substantial percentage of pages on [climate.nasa.gov](http://climate.nasa.gov) include a `Latest Resources` box on the right-hand side of the main page. Every page that contains this box will be marked as a "changed page" by our version tracking software. The relevant change can be seen on `line 1305` of [this diff](https://gist.github.com/va-client/c25c6def28b760f25e3190b1e986d2e3/revisions#diff-8a777b7cd35d6141f393542135beb397R1306). A simple ad-hoc filter that discards changes from `<aside class='list_view_module'>` would cut out about [30%*](# "Made Up Number.") of our positives from `climate.nasa.gov`.
* Many domains update their "Last Updated" date at random. Again, cutting these out would help.
* The EPA recently made grammatical changes to their footer! ouch. 

Current materials:
* [WIP in the pagefreezer-cli repo](https://github.com/edgi-govdata-archiving/pagefreezer-cli/) has a number of bite-sized pieces of code that need to be refined and stitched together.
* [WIP in the differ repo](https://github.com/edgi-govdata-archiving/differ) re-implements the pagefreezer diff service (incompletely) to avoid network latencies & service caps.
* [versionista-outputter](https://github.com/edgi-govdata-archiving/versionista-outputter) implements similar goals for our current (deprecated) monitoring process using another service

### Goal

Develop a  tool that generates a human-usable output (probably CSV) useful to an analyst seeking to inspect and assess web page changes. At minimum, this tool needs to perform ad-hoc filtration of known noise sources in the noisiest domains (at best, those filters would operate on more general principles). 

### Deliverables
As many of the following as possible. See code, docs and issues in [pagefreezer-cli](https://github.com/edgi-govdata-archiving/pagefreezer-cli) for more details.

* **diff:** command-line service capable of carrying out diffs on ca. 10^4 pages at a time. Ouputs JSON file that (hopefully) matches the format of Pagefrezer's API. See [differ](https://github.com/edgi-govdata-archiving/differ) for one initial implementation.
* **filter:** filtration tool that accepts the output of **diff** and adds priority ranking (can be Boolean for now)
* **outputter:** outputs a JSON or CSV report (pref both) of changes for use by analysts
* **viewer:** certain fields in the records created by **outputter** link to diff views of the archived pages. **viewer** serves them over the web
* Documentation suggesting improvements/next steps

### Priority

**High**, Time Sensitive

## Machine Learning

The approach described above filters **out** -- showing analysts all but the lowest-ranking pages -- and is suitable for the relatively small number of pages we are manually monitoring. For the much larger set of ~10^7 web pages we hope to monitor, we will instead need to filter pages **in** -- only showing the highest ranking pages to analysists. For this we need to expand the toolkit with more sophsticated machine learning approaches.

I'm hoping someone else in the group can think about this stuff since I'm so ignorant.

### Goal
A machine-learning workflow that plugs into the tools described [above](#monitoring-and-filtering-websites).

### Deliverables
Documentation including:
* Recommendations for a tool, integrated in to the analysis workflow, that analysts will use to rate diffs as relevant or irrelevant. 
* Recommendations for/pointers to existing tools that we can use to jumpstart analysis
* Back-of-the-envelope calculation of computing resources required to process `n` web pages/week

### Priority
**Medium**, an implementation is necessary but not in the next few weeks.

## Building Resiliency

Data collection is great, but it only really matters if people can use the data; and having just replaced one single-point-of-failure system of data storage, we don't want to set up another one. We are collaborating with Stanford libraries and Protocol Labs on a major test of IPFS, and we hope to work collaboratively with Protocol and many other groups towards this future. 

Current materials:
* [discussion points from NYC](https://hackmd.io/OwIwLApgrAJgbATgLQEMDMCJLCuAzJBAJjywWAjzBgQGMEAGOADiA===?both#)
* [Action items from NYC](https://hackmd.io/MYEwRgHAhloLQHYDMAWAZnFKCs24E4kBGEOCAU3AiWCLDSQDYg==?view#)
* [Guides Repo](https://github.com/edgi-govdata-archiving/guides) is intended to warehouse documentation on best-practices for sustainability
* [Overview Issue #27 on IPFS](https://github.com/edgi-govdata-archiving/overview/issues/27)
* [datarefugephilly/ckan](https://github.com/datarefugephilly/ckan)
* [datarefugephilly/ckanext-extrafields](https://github.com/datarefugephilly/ckanext-extrafields)

### Goal

To ensure that as we develop our tools to store data for future use we are creating secure, redundant, and resilient storage

### Deliverable

* Improved documentation with 5-10 suggested best practises as well as considerations and resources as we develop our tools
* Clearer/more specific milestones for our projects to hit in the near and long term

### Priority

Medium, Less Time Sensitive


## ~~Disseminating~~

**This work has been moved to the "Storytelling" track!**

~~Our work is only relevant if people hear about it. How should we make our work public? What will it take to build public-facing tools to allow citizens to investigate the archive we have assembled?~~

### ~~Goal~~

~~To decide on the next milestones for outreach and engagement with archived materials~~

### ~~Deliverable~~

* ~~Strategy document for communications and citizen research~~

### ~~Priority~~

~~Medium, Less Time Sensitive~~

