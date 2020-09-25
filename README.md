# Olsen et al. (2020, Frontiers in Human Neuroscience) Analysis script.

This script produces most of the figures in this article. The article details the case report of the first participant in this clinical trial.

This script does not contian the LFP preprocessing code. LFP preprocessing was done using [MNE Python](https://mne.tools/stable/index.html). Email (below) regarding access to that code and raw LFP recordings.

The data files contained in the Data folder are required to run the scripts. See below for details regarding those files.


## Install

Script was created and run using Anaconda installation of Jupyter Notebook.

Install required packages:
- blah
-
-
-

## Usage

 Do .... to run the code
 
 ```python
 for i = 1:10:
  function(data,etc)
 ```
 
 ## Data Format
 
 **UH3-NS100548-01_PCS01_GanttChartData.xlsx** contains the timing of study events, stimulation and recording settings changes, and clinical outcomes measures. Data are formatted to create a gantt chart of said events. 
 
 **UH3-NS100548-01_PCS01_ClinOutcomes_PowWpliFeatures.csv** Columns contain the clinical outcomes measures, and extracted power and weighted phase lag index (WPLI) features, and some recording and stimulation parameter features. See the above sited article for details of how power and WPLI features were calculated. Each row is a day one or more clinical outcomes were taken. This file is used for plotting clinical outcomes, clinical outcomes x WPLI correlations, and the random forest analyses predicting clinical outcomes from power and WPLI.   
 
 **UH3-NS100548-01_PCS01_MSIT_Full.csv** Contains the behavioral data for all runs of the multisource interference task (MSIT). Rows are single trials.
 
 **UH3-NS100548-01_PCS01_IntraoperativeWPLI.csv** Contains WPLI for the intraoperative LFP recordings. Long form DF where each row is the WPLI for a single frequency at a single timepoint, within each cortical-striatal contact pair for the left and right hemispheres. 
 
 **UH3-NS100548-01_PCS01_Saline_Power.csv and UH3-NS100548-01_PCS01_Saline_WPLI.csv** contain Power and WPLI, respectively, for the saline bath recordings. Long form DF with each row being being power at a given frequency, within a given channel (power) or hemisphere (WPLI) for a specific recording.
 
**UH3-NS100548-01_PCS01_DailyLFP_NonCorrected_Power.csv and UH3-NS100548-01_PCS01_DailyLFP_NonCorrected_WPLI.csv** contain Power and WPLI, respectively, for the patient daily LFP recordings PRIOR TO the removal of the stimulation artifact signal (see saline recordings above). Long form DF with each row being being power at a given frequency, within a given channel (power) or hemisphere (WPLI) for a specific recording.

**UH3-NS100548-01_PCS01_DailyLFP_Corrected_Power.csv and UH3-NS100548-01_PCS01_DailyLFP_Corrected_WPLI.csv** contain Power and WPLI, respectively, for the patient daily LFP recordings AFTER the removal of the stimulation artifact signal (see saline recordings above). Long form DF with each row being being power at a given frequency, within a given channel (power) or hemisphere (WPLI) for a specific recording.

Email me for data **sarah@umn.edu**
