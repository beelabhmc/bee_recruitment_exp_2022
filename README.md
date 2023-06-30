# bee_recruitment_exp_2022

# Project description

This repository contains files and scripts to analyze them from an experiment on honey bee recruitment behavior conducted in the summer of 2022. The purpose of that experiment was to determine how the:

* density (spacing) and
* total number of flowers

in discrete patches that bees visits will affect the:

* probability that those bees will choose to advertise the patch with a waggle dance and
* how many repeated waggle runs they will perform per dance.

We tested this using arrays of 3D-printed artificial flowers which had cotton wicks in essential-oil-scented sugar syrup that bees could drink from. 

The experiment involved two trials, one from June 15, 2022 to June 17, 2022 and the other from July 18, 2022 to July 20, 2022.


# File organization description

## data

The data folder contains the original data spreadsheets in csv format for each of the artificial flower arrays and the observation hive on all six days of the experiment. The prefix of each file indicates the date in MMDD format. "Peppermint" and "Clove" indicate the scent used in the syrup at a flower array. "FeederVisits" and "VideoAnalysis" indicate array data and hive data, respectively.

## cleaned_data

This folder contains processed data from the first two scripts:

* all_array_visits.csv: output of 01_clean_array_data.Rmd. This contains one row for each time we recorded that a given bee was drinking at an artificial flower in one of the arrays
* all_dances.csv: output of 02)clean_hive_data.Rmd. This contains one row for every return to the hive we noted by a bee in which we counted at least one waggle run
* all_hive_visits.csv: output of 02_clean_hive_data.Rmd. This contains one row for every return to the hive we noted, including hive visits where the bee performed no waggle runs
* combined_flower_array_data.csv: output of 01_clean_array_data.Rmd. This file contains the array visit data summarized by bee and date, including the first time we noted that bee at that array and the total time she would have during the trial to potentially dance to advertize the array
* per_bee_summary.csv: output of 02_clean_hive_data.Rmd. This file contains one row per bee with both the dance information (did she dance and if so, how many waggle runs?) and array information (when did we first note her visiting the array and how long did she have to potentially dance during the trial)

Getting started- a list of steps indicating how a user can:
clone your repository, 
access the data that you used, 
set up the data folders, and 
run the script to generate model results and maps.
Full citations for data sources
Full citations for any code sources that you used/modified
