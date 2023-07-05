# bee_recruitment_exp_2022

## Project description

This repository scripts to analyze data from an experiment on honey bee recruitment behavior conducted in the summer of 2022. The purpose of that experiment was to determine how the:

* density (spacing) and
* total number of flowers

in discrete patches that bees visits will affect the:

* probability that those bees will choose to advertise the patch with a waggle dance and
* how many repeated waggle runs they will perform per dance.

We tested this using arrays of 3D-printed artificial flowers which had cotton wicks in essential-oil-scented sugar syrup that bees could drink from. 

The experiment involved two trials, one from June 15, 2022 to June 17, 2022 and the other from July 18, 2022 to July 20, 2022.


## File organization description

### scripts

* 01_clean_array_data.Rmd:

  + input: "FeederVisits" csv files from data folder
  + output: cleaned_data/all_array_visits.csv, cleaned_data/combined_flower_array_data.csv

* 02_clean_hive_data.Rmd:

  + input: "VideoAnalysis" csv files from data folder, cleaned_data/combined_flower_array_data.csv
  + output: cleaned_data/all_dances.csv, cleaned_data/all_hive_visits.csv, cleaned_data/per_bee_summary.csv

* 03_regression_analyses.Rmd:

  + input: cleaned_data/all_dances.csv, cleaned_data/per_bee_summary.csv
  + output: none currently, in future it will create files with model results

* 04_boxplots.Rmd:

  + input: cleaned_data/all_dances.csv, cleaned_data/per_bee_summary.csv
  + output: all "Boxplot" jpg files in figures folder

* 05_cumulative_figures.Rmd:

  + input: cleaned_data/all_dances.csv, cleaned_data/all_hive_visits.csv
  + output: all "Lineplot" jpg files in figures folder

### data (you will need to download this separately from: TBA)

The data folder contains the original data spreadsheets in csv format for each of the artificial flower arrays and the observation hive on all six days of the experiment. The prefix of each file indicates the date in MMDD format. "Peppermint" and "Clove" indicate the scent used in the syrup at a flower array. "FeederVisits" and "VideoAnalysis" indicate array data and hive data, respectively.

### cleaned_data (this will be created by the scripts)

This folder contains processed data from the first two scripts:

* 01_all_array_visits.csv

  + output of 01_clean_array_data.Rmd
  + This contains one row for each time we recorded that a given bee was drinking at an artificial flower in one of the arrays

* 01_combined_flower_array_data.csv: 

  + output of 01_clean_array_data.Rmd
  + This file contains the array visit data summarized by bee and date, including the first time we noted that bee at that array and the total time she would have during the trial to potentially dance to advertize the array
    
* 02_all_dances.csv: 

  + output of 02_clean_hive_data.Rmd
  + This contains one row for every return to the hive we noted by a bee in which we counted at least one waggle run
  
* 02_all_hive_visits.csv: 

  + output of 02_clean_hive_data.Rmd
  + This contains one row for every return to the hive we noted, including hive visits where the bee performed no waggle runs
  
* 02_per_bee_summary.csv: 

  + output of 02_clean_hive_data.Rmd 
  + This file contains one row per bee with both the dance information (did she dance and, if so, how many waggle runs?) and array information (when did we first note her visiting the array and how long did she have to potentially dance during the trial)

### figures (this will be created by the scripts)

This folder contains all figures made using ggplot in scripts 04 and 05.


## Getting started

If you clone this repository, it will not include the data folder. You will need to download that from: TBA online repository

You will need to install several packages before running the R notebook scripts:

* DHARMa 0.4.6
* tidyverse 2.0.0
* nlme 3.1-160
* lme4 1.1-31

I recommend opening and running the R notebooks in R Studio. If you run them in the order indicated by the file prefixes ("01_" to "05_"), they will create the other necessary files and folders.
