# Yale Crime Statistics: Beyond the 2018 Clery Report

This repository contains supporting files for a Yale Daily News analysis of crime data for Yale's campus. The associated story, titled *Analysis: New Haven sees drop in crime*, can be found [here](https://yaledailynews.com/blog/2019/10/22/analysis-new-haven-sees-drop-in-crime/).

Maggie Nolan and Daniel Zhao, data analytics editors with the News, analyzed the data, extracted key data insights, and prepared the story for publication. John Besche, a beat reporter with the University desk, sourced students and administrators, and wrote a majority of the story.

A background and context on the story can be found in the beginning of the story.

## Data and processing

We downloaded data using the data download tool from the Department of Education's [Campus Safety and Security database](https://ope.ed.gov/campussafety/). This database contains campus safety information for all campuses nationwide, and is populated with mandatory annual filings by individual universities. We used the "Download custom data" option in the link above, searched for *Yale University*, selected all years, and selected all categories except for fire statistics. Note that we restricted our analysis to main campus and chose to exclude West Campus because it is a significantly different campus environment, and note that we excluded fire statistics because these data are reported at a by-incident level, while all other measures were reported as aggregate data.

Because the database has not yet been populated with the most recent 2018 data, we had to combine this data with raw data found in Yale's recent 2018 Clery Report.

`OPE CSS Custom Data 2019-10-04 011737.zip` is the raw downloaded data archive, and its contents have been extracted into `/data`. `01_merge.R` was the script we used to merge these separate files into one large dataset that was fit for visualization. We manually entered 2018 values into this file, and then used `02_reshape.R` to 1) remove some duplicate categories, and to 2) turn measures of *on-campus student housing* and *all on-campus* into *on-campus student housing* and *on-campus non-student housing*. Finally, `03_exploration.Rmd` (and the associated PDF) contains initial exloratory graphs.

`yale_crimed_merged.csv` is the final merged dataset, which you are free to use for your own exploration.

## Visualization

We used Google Data Studio to create visualizations for our data because it is free, web-based, and easy to embed on the Yale Daily News website. We uploaded `yale_crime_merged.csv` as a data source in Google Data Studio and produced two visualizations, which you can find in the story linked above.

Please contact Daniel Zhao (daniel.zhao@yale.edu) or Maggie Nolan (maggie.nolan@yale.edu) with any questions about this project.