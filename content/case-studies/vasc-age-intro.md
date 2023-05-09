# Vascular age - Intro

In this case study we will explore a particular approach for assessing vascular age from PPG and ECG signals: pulse arrival time measurement.

The background to this task is presented in the [Background](../background/) section of this book - in particular see the [Physiology](../background/physiology) section.

For further reading, see [this article](https://doi.org/10.1152/ajpheart.00392.2021) on assessing vascular age from the PPG.

## Example

[This notebook](../case-studies/vasc-age-example) provides an initial example for this case study. Briefly, the code:
- Extracts data from the Pulse Transit Time PPG dataset.
- Extracts pulse arrival times for each subject in this dataset.
- Extracts reference ages
- Looks at the association between pulse arrival time and age

It is intended to provide a starting point for further work, and is by no means perfect. We would be grateful for any improvements via pull requests!

## Critical appraisal of the technique

When appraising the use of pulse arrival time for vascular ageing assessment, perhaps consider:
- What would influence performance, e.g.
  - the path of the pulse wave (e.g. heart to finger in this case study)
  - pulse arrival time vs. pulse transit time, considering the effect of pre-ejection period
  - the PPG acquisition equipment (e.g. wavelength of light used, transmission vs. reflectance)
- How could this experiment be improved, e.g.
  - reference parameters (how helpful is chronological age?)
  - cohort studied (consider their ages, and health status)
  - generalisability to the real-world setting
- How could the signal processing be improved, e.g.
  - filtering (how does this impact measurements?)
- How could the modelling be improved?
  - Is the assumption of a linear relationship between pulse arrival time and vascular age suitable?
  - Conversion from pulse arrival time to pulse wave velocity?