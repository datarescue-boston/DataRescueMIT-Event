# Harvesting

Harvesting follows directly after [research](research.md), and it is not uncommon for the same person to perform both steps. Harvesters use any one of several [techniques](https://github.com/edgi-govdata-archiving/harvesting-tools/) to acquire datasets that have been investigated by Seeders and Researchers. This is a complex task that can require substantial technical expertise, and that requires different techniques for different tasks.

You need to be logged in to the [Archivers Pipeline App](https://www.archivers.space) to follow this! If you have not yet gotten an invite to the app, DM a guide in the #data-archiving Slack channel.

## "Meaningful Datasets"

- Your role is to harvest datasets that are complete and *meaningful*. By meaningful we mean: "will the collection make sense to a scientist"? 
- For instance, if a dataset is composed of a spreadsheet without any accompanying key or explanation of what the data represents, it might be completely impossible for a scientist to use it.
  
## Claiming a Dataset to Harvest

From the main app interface, click on the "Harvesting" tab and choose any any record by clicking on the UUID field (or just continue working on the one you were researching, if you are doing both roles). Read the Research notes to get a sense of whether you have the right skills/interest to harvest this dataset. As with researching, be sure to click `Checkout this URL` so that you can edit the fields. 

## Check the Terms of Service!!!

Before you go any further, it is *always* worth confirming that the data in question is in fact open for archiving. If the terms of service explicitly prohibit archiving, *make a note of it*. Data Rescue events are purposely aimed only at publicly available data, but it is easy to follow a link away from a publicly available source onto a site that has different terms of service.

**Data acquired outside terms of service is not usable**

## Determine Scale of the Dataset

If the dataset you're looking at is quite large--say, more than 1000 documents--capturing it may require more elaborate programming than is described here, and it may be difficult to complete in the timeframe of the event. In that case, you may want to look outside the scope of this document and read the documentation of tools such as the [EIS WARC archiver](https://github.com/edgi-govdata-archiving/eis-WARC-archiver), which shows how to initiate a larger, fully automated harvest on a web-based virtual machine. Talk to a DataRescue guide to determine how to best proceed.

## Zipstarter: Generate HTML, JSON & Directory

Click `Download Zip Starter` to download a directory structured according to our specification:

	DAFD2E80-965F-4989-8A77-843DE716D899
		├── DAFD2E80-965F-4989-8A77-843DE716D899.html
		├── DAFD2E80-965F-4989-8A77-843DE716D899.json
		├── /tools
		└── /data

More colloquially:

	A directory named by the UUID
		├── a .html (or WARC, if you prefer) "web archive" file of the url for future reference, named with the UUID
		├── a .json metadata file that contains relevant metadata, named with the UUID
		├── a /tools directory to include any scripts, notes & files used to acquire the data
		└── a /data directory that contains the data in question


### [id].html file
The Zip Starter will create an HTML file in the directory. The html file gives the archive a snapshot of the page at the time of archiving which we can use to monitor for changing data in the future, and corrobrate the provenance of the archive itself. We can also use the .html in conjunction with the scripts you'll include in the tools directory to replicate the archive in the future.

### [id].json file
You'll need to inspect the .json manifest to be sure all fields are correct. This file contains vital data, including the url that was archived, and date of archiving. The manifest should contain the following fields:

	{
		"Individual source or seed URL": "",
		"UUID": "",
		"Institution facilitating the data capture creation and packaging": "",
		"Date of capture": "",
		"Federal agency data acquired from": "",
		"Name of resource": "",
		"File formats contained in package": "",
		"Type(s) of content in package": "",
		"Free text description of capture process": "",
		"Name of package creator": ""
	}

## Acquire the Data
See the [harvesting tools](https://github.com/edgi-govdata-archiving/harvesting-tools/) for a bunch of ideas, tools and code snippets to hope you complete this task!

### Tips
- If you encounter a Search bar, try entering "*" to check to see if that returns "all results".
- Leave the data unmodified. During the process you may feel inclined to clean things up, add structure to the data, etc. Avoid temptation. Your finished archive will be hashed so we can compare it later for changes, and it's important that we archive original, unmodified content.

## Upload the Data
- Zip the all the files pertaining to your dataset, so that you have a resulting zip file. Upload the Zip file using the `Upload` button.

## Finish Up
- Be sure to `Checkout` the URL.
- You're done! Move on to the next URL!
