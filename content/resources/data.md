# Datasets

There are several publicly available datasets containing ECG, PPG and accelerometry signals. The following are helpful starting points for finding such datasets:

- [PhysioNet](https://physionet.org/) hosts [many datasets](https://physionet.org/about/database/) of physiological signals.
- [List of PPG datasets](https://peterhcharlton.github.io/post/ppg_datasets) is a list of several datasets containing PPG signals, some of which are on PhysioNet, and some of which are hosted elsewhere.

In this book we'll use two datasets, both of which are hosted on PhysioNet and are now described.

## MIMIC Database

The [MIMIC Database](https://mimic.mit.edu/) is a publicly accessible critical care database. It is widely used in biomedical signal processing research because it contains a variety of physiological signals collected from many thousands of patients. The relevant signals for this book are the ECG and PPG signals (as shown in {numref}`mimic-signals`). Note that this database does not contain accelerometry signals.

```{figure} https://cloud.githubusercontent.com/assets/9865941/13321748/ce4d0ce2-dbc8-11e5-91d0-c480bad98555.png
:name: mimic-signals
---
width: 100%
---
**Signals from a patient in the MIMIC Database.**
```

The latest version of the MIMIC Database is [MIMIC-IV](https://mimic.mit.edu/docs/iv/), which currently includes an initial release of 200 signal recordings from 198 patients ([here](https://physionet.org/content/mimic4wdb/0.1.0/)). The previous version of MIMIC, [MIMIC-III](https://mimic.mit.edu/docs/iii/) contains signals recorded from 10,000s of patients, alongside clinical data for many of these patients. {numref}`mimic-pt` shows an example of the additional clinical data for an individual patient.

```{figure} ../images/examplepatient.jpg
:name: mimic-pt
---
width: 100%
---
**Clinical data from a patient in the MIMIC Database.** _Reproduced under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) from: Johnson AEW et al. MIMIC-III, a freely accessible critical care database. Sci Data 2016; 3: 160035. https://doi.org/10.1038/sdata.2016.35_
```

There are several advantages to using the MIMIC Database to develop algorithms for wearable data analysis:

- The dataset is large: it contains signals from 10,000s of patients mostly lasting hours or days.
- The dataset is publicly available, facilitating open research in both academic and commercial settings.
- The dataset contains a wide range of physiological signals from which reference physiological parameters can be derived. For instance, the dataset includes blood pressure and respiratory signals from which reference blood pressure and respiratory parameters can be derived. These can be used as reference values with which to assess the performance of PPG and ECG signal processing algorithms. See the impedance signal in {numref}`mimic-signals` for an example of a reference signal alongside ECG and PPG signals.

However, the data are acquired from critically-ill patients in hospital using bedside monitors, meaning they may not be representative of real-world wearable data:
- The physiology of critically-ill patients may differ from that of healthy subjects
- The signals are not necessarily measured in the same way as with wearable sensors. For instance, the PPG signal is mostly measured using infrared light at the finger, rather than the other colours and measurement sites used by wearables. ECG signals are measured using chest electrodes rather than at the wrist.
- The artifact contained within the signals is not necessarily representative of that which would be encountered in wearable data. For instance, critically-ill patients are often bed-bound and do not undertake many of the activities of daily living which healthy subjects perform.

## Pulse Transit Time PPG Dataset

The [Pulse Transit Time PPG Dataset](https://doi.org/10.13026/jpan-6n92) is a publicly accessible dataset containing ECG, PPG, accelerometry, and other signals. Signals were acquired from 22 healthy subjects during a few activities (sitting, walking, and running). It also contains some reference physiological parameters such as blood pressure. This dataset is particularly helpful because the signals are broadly representative of those acquired by wearable devices. For instance, the PPG signals include red, infrared, and green wavelength signals, and the dataset includes accelerometry signals.
