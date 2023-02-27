# Workshop

## Welcome

Welcome to this workshop, which will provide an introduction to the fundamentals of biomedical signal processing and learning for wearable signals of multiple modalities.

### Organisers

This workshop is co-organised by:
- The [Department of Public Health and Primary Care](https://www.phpc.cam.ac.uk/) at the University of Cambridge
- [Turing's meta-learning for multimodal data interest group](https://www.turing.ac.uk/research/interest-groups/meta-learning-multimodal-data)

The workshop was designed and run by researchers from several universities across Europe. You can find details of the individuals who have contributed [here](https://github.com/peterhcharlton/bsp-book#contributors-).

### Outline

This is an interactive, online workshop providing an introduction to the fundamentals of biomedical signal processing and learning for wearable signals of multiple modalities.

The workshop will consist of three parts:
- Participants will be introduced to the signals measured by wearables, including photoplethysmogram and electrocardiogram signals.
- Participants will learn fundamental techniques for processing wearable signals through interactive tutorials.
- Participants will gain hands-on experience of signal processing and machine learning with wearable data through a group exercise, applying data analysis to real-world problems.

The workshop will use pre-prepared teaching materials consisting of online Jupyter notebooks running Python code on the cloud, so no installation is required on participants' computers. The teaching materials are designed to be highly accessible to the non-specialist, while also providing opportunity for people with experience in the field to explore the topic more deeply.

Follow the links on the left for further details of the workshop.


### Old content ...

![PPG signals at rest and during exercise](https://upload.wikimedia.org/wikipedia/commons/8/8a/Photoplethysmogram_signals_at_rest_and_during_exercise.svg)

Source: _Charlton PH, [Photoplethysmogram signals at rest and during exercise](https://commons.wikimedia.org/wiki/File:Photoplethysmogram_signals_at_rest_and_during_exercise.svg), Wikimedia Commons (CC BY 4.0)._

**Cuffless blood pressure estimation:** Estimating blood pressure from physiological signals which can be acquired unobtrusively without the use of a blood pressure cuff. Broadly, there are three approaches for cuffless blood pressure estimation. These are based on the observation that the speed with which the pulse wave propagates increases with blood pressure:
   - measuring the pulse transit time (PTT) between two arterial pulse waves (one closer to the heart and one further away).
   - measuring the pulse arrival time (PAT) between a marker of ventricular contraction, and the arrival of a pulse wave (preferably at a peripheral site)
   - estimating BP from the shape of a pulse wave (such as a photoplethysmography, PPG, pulse wave), since changes in pulse wave velocity and BP influence the shapes of pulse waves.
 
![Deriving indicators of BP](https://journals.physiology.org/cms/10.1152/ajpheart.00392.2021/asset/images/large/ajpheart.00392.2021_f003.jpeg)

Source: _Charlton PH et al., [Assessing hemodynamics from the photoplethysmogram to gain insights into vascular age: a review from VascAgeNet](https://doi.org/10.1152/ajpheart.00392.2021), AJP Heart Circ, 2022 (CC BY 4.0)._
