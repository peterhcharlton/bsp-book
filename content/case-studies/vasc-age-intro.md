# Vascular age - Intro

In the tutorials we have explored different steps which would commonly be encountered when developing techniques for cuffless blood pressure estimation.

## Introduction to estimating blood pressure from the PPG

Blood pressure (BP) has been estimated from the PPG using the following inputs: a single PPG; a proximal and a distal PPG to measure PPT; or a distal PPG signal and a signal indicating the time of ventricular contraction (e.g., ECG, phonocardiogram) to measure PAT. Techniques that use a single PPG signal are based on analysis of pulse wave shape using either extracted features or the whole pulse wave. Often machine learning is used to create a model relating pulse wave features to BP. Techniques that use PTT or PAT require a second signal, such as ECG at the wrist or a signal at the chest. Several models relating BP to PTT or PAT have been proposed, including models that incorporate additional variables, such as HR. Models that require a single calibration cuff measurement are convenient but potentially less accurate than those that use multiple measurements to form a patient-specific calibration curve. While frequent calibration may be necessary to accurately estimate absolute BP values from a single PPG, less frequent calibration may be required when estimating BP from certain PAT measurements. Furthermore, it may be possible to identify changes in BP from a single PPG without calibration, which could have utility in detecting clinical deteriorations, such as sepsis.

Wearables that use the PPG for BP monitoring are widely available. Most devices are not validated [163] although some have recently been certified for medical use. Studies are now assessing the accuracy and potential clinical utility of such devices. Standards have been developed for the validation of wearable, cuffless BP devices although further work is required to refine validation standards to account for the issues presented by PPG-based devices.

_Source (with references): Charlton PH et al., Wearable Photoplethysmography for Cardiovascular Monitoring, Proceedings of the IEEE, 2022. DOI: [10.1109/JPROC.2022.3149785](https://doi.org/10.1109/JPROC.2022.3149785)_

### Further reading

- Overview: [1](https://doi.org/10.1146/annurev-bioeng-110220-014644), [2](https://doi.org/10.1038/s41746-019-0136-7)
- [Estimating BP from a single PPG pulse wave](https://doi.org/10.3390/jcm9030723)
- Estimating BP from pulse transit time or pulse arrival time: [1](https://doi.org/10.1109/TBME.2015.2441951), [2](https://doi.org/10.3390/jcm9041203), [3](https://doi.org/10.3390/jcm8111827)
- [Using machine learning](https://doi.org/10.1016/j.bspc.2020.101870)
- [Evaluating cuffless blood pressure devices](https://doi.org/10.1161/HYPERTENSIONAHA.121.17747)

## Example

[This notebook](../case-studies/bp-estimation-example) provides an initial example for this case study. Briefly, the code:
- Extracts data from the MIMIC database, and separates the data into training and testing datasets.
- Extracts features from PPG pulse waves for blood pressure estimation
- Extracts reference BP values from BP signals
- Trains a model to estimate blood pressure
- Assesses its performance

It is intended to provide a starting point for further work, and is by no means perfect. We would be grateful for any improvements via pull requests!

## Directions for further work

Here are some ideas for further work. You might consider working on any of these, or something of your own choosing:

### Assessing algorithm performance

The assessment of algorithm performance could be improved as follows:
- **Developing assessment methodology:** _[suitable for all, particularly clinicians and health researchers]_ There is currently much interest in the question of how the performance of cuffless blood pressure devices should be assessed. It would be interesting to design experimental methodology to assess the performance of the algorithm, in line with recent suggestions (see [this helpful article](https://doi.org/10.1161/HYPERTENSIONAHA.121.17747) and [the IEEE standard](https://doi.org/10.1109/IEEESTD.2014.6882122) which was [updated in 2019](https://doi.org/10.1109/IEEESTD.2019.8859685)).
- **Designing potential use cases:** _[suitable for all, particularly clinicians and health researchers]_ BP is widely used in routine clinical practice for diagnosis and prognosis. Several potential use cases for cuffless BP have been proposed, including (as detailed [here](https://doi.org/10.1146/annurev-bioeng-110220-014644)): (i) identifying undiagnosed hypertension; (ii) long-term hypertension control; (iii) providing greater insight into BP through continuous monitoring in day and night; (iv) hypotension surveillance. There may be other potential use cases, such as identifying early signs of pre-eclasmpsia. It might be interesting to consider what use cases cuffless BP would be most suited to, what is required of cuffless BP devices for these use cases, and how individuals would use such devices in these use cases.
- **Using a larger dataset:** _[suitable for coders]_ The current example uses data from MIMIC-IV, which is limited to a sample size of 52 recordings. It might be interesting to import data from MIMIC-III which has many more recordings available for analysis (following [this tutorial](../tutorial/notebooks/data-exploration3)).
- **Tracking changes in BP:** _[suitable for coders]_ The example currently assesses the algorithm's ability to estimate absolute BP from a PPG signal segment, with no prior knowledge of the patient. In contrast, often cuffless blood pressure devices require calibration with a reference blood pressure measurement for each patient. Therefore, it might be interesting to assess the ability of the model to track changes in BP within a recording, rather than estimating absolute BP.

## Suggested workflow

A suggested workflow is provided here - feel free to use this or ignore it!

1. Loop through ICU stays, determining whether each stay meets the inclusion criteria for the study (contains at least 10 minutes of simultaneous PPG and ABP signals). The [Data Visualisation tutorial](https://wfdb.io/mimic_wfdb_tutorials/tutorial/notebooks/data-visualisation.html) provides scripts for doing this (except that it only runs on a specified ICU stay, and doesn't loop through stays). Continue looping until 60 ICU stays have been identified which meet
2. Extract 10 minutes of simultaneous PPG and ABP signals from each ICU stay which meets the inclusion criteria.
3. Run signal processing scripts to extract a parameter from the shape of each PPG pulse wave (let's call the parameter the stiffness index - SI). This will produce a vector of values for each ICU stay (with a length of approximately 600 - i.e. one value per heart beat - which varies from one stay to the next), and a vector of corresponding time stamps.
4. Run signal processing scripts to extract systolic and diastolic blood pressure (SBP and DBP) values from each ABP pulse wave. Similarly, this will produce two vectors of values for each ICU stay, one for systolic blood pressure, and one for diastolic blood pressure, and a vector of corresponding time stamps.
5. Calculate an average (e.g. median) value of the SI for each 30 second window, and repeat for SBP and DBP, ensuring that the same timings are used for the SI, SBP and DBP windows. For each ICU stay, this will produce three vectors each of length 20 (because the 10 minute segments can be split into 20 non-overlapping 30-second windows). The three vectors will contain SI, SBP and DBP respectively.
6. Create 'overall' vectors by concatenating each of the three vectors across all ICU stays. This will generate three vectors each of length 1200 (i.e. 20 values for 60 ICU stays). In addition, create a vector of ICU stays (i.e. a vector of length 1200 which contains the ICU stay ID from which each window was obtained).
7. Split the data into training and testing data, at the ICU stay level. E.g. the first 600 values (corresponding to the first 30 ICU stays) are designated as training data, and the remaining 600 values are designated as testing data.
8. Train a linear regression model on the training data to estimate either SBP (or DBP) from SI. The default behaviour should be to use SBP, but it would be nice to include the option to change this to DBP.
9. Test the performance of the model on the testing data:
   - Use the model to estimate SBP (or DBP) from each SI value in the testing data. This should produce a vector of estimated SBP (or DBP) values of length 600.
   - Calculate the errors between the estimated and reference SBP (or DBP) values (using error = estimated - reference).
   - Calculate error statistics for the entire testing dataset. e.g. mean absolute error, bias (i.e. mean error), limits of agreement (i.e. 1.96 * standard deviation of errors).

