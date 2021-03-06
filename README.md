# Olsen et al. (2020, Frontiers in Human Neuroscience) Analysis.

This script produces most of the figures in this article. The article details the case report of the first participant [in this clinical trial](https://clinicaltrials.gov/ct2/show/NCT03184454).

This script does not contain the LFP preprocessing code. LFP preprocessing was done using [MNE Python](https://mne.tools/stable/index.html). Email (below) regarding access to that code and raw LFP recordings.

## Install
Script was created and run using Anaconda installation of Jupyter Notebook. 

Download the Jupyter Notebook and Data.zip. The script should be contained in a directory, with a Data sub-directory. The data files contained in Data.zip in this repository are required to run the scripts. See below for details regarding those files. 

Required packages:
- os
- re
- numpy
- matplotlib
- seaborn
- pandas
- collections 
- datetime
- scipy
- sklearn
- altair
- statsmodels

## Usage
With the exception of the initial cells (importing packages, and setting the data and figure directories), each major section (denoted by level one headings) is designed to be able to be run individually to produce a corresponding figure or analysis.

You will need to update the objects: data_dir and figure_dir with the paths to the data and figure sub-directories, respectively (will create the figure directory for you). This should be done by editing and running the cell containing the following code:

```data_dir = "C:\\Users\\TNEL - Human 2\\Desktop\\UH3-NS100548-01_PCS01_Analysis\\Data\\"``` 

```figure_dir = "C:\\Users\\TNEL - Human 2\\Desktop\\UH3-NS100548-01_PCS01_Analysis\\Figures\\"```
 
 ## Data Format
 
 - **UH3-NS100548-01_PCS01_GanttChartData.xlsx** contains the timing of study events, stimulation and recording settings changes, and clinical outcomes measures. Data are formatted to create a Gantt chart of said events. 
 
 - **UH3-NS100548-01_PCS01_ClinOutcomes_PowWpliFeatures.csv** Columns contain the clinical outcomes measures, and extracted power and weighted phase lag index (WPLI) features, and some recording and stimulation parameter features. See the above sited article for details of how power and WPLI features were calculated. Each row is a day one or more clinical outcomes were taken. This file is used for plotting clinical outcomes, clinical outcomes x WPLI correlations, and the random forest analyses predicting clinical outcomes from power and WPLI.   
 
 - **UH3-NS100548-01_PCS01_MSIT_Full.csv** Contains the behavioral data for all runs of the multisource interference task (MSIT). Rows are single trials.
 
 - **UH3-NS100548-01_PCS01_IntraoperativeWPLI.csv** Contains WPLI for the intraoperative LFP recordings. Long form DF where each row is the WPLI for a single frequency at a single timepoint, within each cortical-striatal contact pair for the left and right hemispheres. 
 
 - **UH3-NS100548-01_PCS01_Saline_Power.csv and UH3-NS100548-01_PCS01_Saline_WPLI.csv** contain Power and WPLI, respectively, for the saline bath recordings. Long form DF with each row being power at a given frequency, within a given channel (power) or hemisphere (WPLI) for a specific recording.
 
- **UH3-NS100548-01_PCS01_DailyLFP_NonCorrected_Power.csv and UH3-NS100548-01_PCS01_DailyLFP_NonCorrected_WPLI.csv** contain Power and WPLI, respectively, for the patient daily LFP recordings PRIOR TO the removal of the stimulation artifact signal (see saline recordings above). Long form DF with each row being power at a given frequency, within a given channel (power) or hemisphere (WPLI) for a specific recording.

- **UH3-NS100548-01_PCS01_DailyLFP_Corrected_Power.csv and UH3-NS100548-01_PCS01_DailyLFP_Corrected_WPLI.csv** contain Power and WPLI, respectively, for the patient daily LFP recordings AFTER the removal of the stimulation artifact signal (see saline recordings above). Long form DF with each row being power at a given frequency, within a given channel (power) or hemisphere (WPLI) for a specific recording.

- **UH3-NS100548-01_PCS01_Power_WPLI_ByDay.npy** is a dictionary (saved as a numpy array, so need to access elements differently-done in script) Key/value pairs are as follows:
  - *Frequencies*- (32,) numpy array containing the frequencies used in the decomposition. 
  - *power_days_list*- list containing the day numbers for power recordings.
  - *all_power*- list of four numpy arrays. Each array is (n_frequencies, n_daysOfRecording) with the power values for:
    - all_power[0] = VC/VS left
    - all_power[1] = VC/VS right
    - all_power[2] = cortical left
    - all_power[3] = cortical right
  - *coh_days_list*- list containing the day numbers for the WPLI data      
  - *all_coh* list of four numpy arrays. Each array is (n_frequencies, n_daysOfRecording) with the cortical-VC/VS WPLI values for:
    - all_coh[0] = left hemisphere WPLI
    - all_coh[1] = right hemisphere WPLI
    - all_coh[2] = average ipsi WPLI

## Info
Contact **olsen378@umn.edu** for more info.
