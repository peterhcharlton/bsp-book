# Physiology

This section provides an overview of the physiology of ECG and PPG signals which underpins both cuffless blood pressure estimation and the assessment of vascular age.

## Arterial stiffness, pulse wave velocity, blood pressure and vascular ageing

Arterial stiffness and pulse wave velocity are strongly related. 'Arterial stiffness' (the stiffness of arterial walls) is a key determinant of pulse wave velocity (PWV, the speed at which the pulse wave travels from the heart to the periphery). PWV increases with arterial stiffness, as expressed in the Moens-Korteweg equation (see [here](https://doi.org/10.1038/s41598-017-05807-x)). Arterial stiffness and PWV increase with age (see [here](https://doi.org/10.1093/eurheartj/ehq165)): this is an aspect of vascular ageing.

Blood pressure is also related, because arterial stiffness (and consequently PWV) increase with blood pressure. This is because as blood pressure increases, the arterial walls stretch further, and stiffness of the arterial walls increases as they distend. 

Blood pressure and vascular ageing can be assessed from ECG and PPG signals based on these changes in arterial stiffness and PWV. Blood pressure can be estimated from ECG and PPG signals because blood pressure is linked to PWV, which in turn influences these signals. As blood pressure increases, the stiffness of the arteries increases, and therefore the speed at which the pulse wave travels from the heart to the periphery (the pulse wave velocity) increases. Therefore, blood pressure can be estimated from the time taken for the pulse wave to travel through the arteries. Similarly, the impact of vascular ageing on arterial stiffness can be assessed from this time delay.

## Electrocardiogram (ECG)

The electrocardiogram (ECG) (introduced in the {ref}`content:signals:ecg` Section) can be used to identify the time of the electrical impulse which initiates ventricular contraction and occurs shortly before blood is ejected from the heart into the aorta. This is indicated by the R-wave, which is the dominant feature of an ECG signal, as shown in {numref}`ecg-waves`.

```{figure} https://upload.wikimedia.org/wikipedia/commons/5/53/SinusRhythmLabels.png
---
name: ecg-waves
width: 60%
---
**ECG waves.** _Source: Agateller (Anthony Atkielski), [Sinus rhythm labels](https://en.wikipedia.org/wiki/File:SinusRhythmLabels.png), Wikimedia Commons (Public Domain)._
```

Therefore, the ECG provides a useful marker of the approximate time of the heart beating, but it has the limitation that it doesn't provide the exact time at which blood is pumped into the circulation. Instead, it provides an earlier time, which precedes the actual time of blood being pumped by a short time known as the 'pre-ejection period' (see [here](https://doi.org/10.1088/1361-6579/aada72) for further details).

## Photoplethysmogram (PPG)

The photoplethysmogram (PPG) (introduced in the {ref}`content:signals:ppg` Section) can be used to identify the time at which the arterial pulse wave arrives at the measurement site. As shown in {numref}`ppg-origins`, the PPG signal is dominated by variations in arterial blood volume which occur when the pulse wave arrives at the measurement site. The time at which the pulse wave arrives can be obtained from the onset of the PPG pulse wave (i.e. the start of the upslope).

```{figure} https://upload.wikimedia.org/wikipedia/commons/a/ad/Photoplethysmogram_signal_components.svg
---
name: ppg-origins
width: 80%
---
**The origins of the Photoplethysmogram (PPG) signal.** _Source: Charlton PH, [Photoplethysmogram signal components](https://commons.wikimedia.org/wiki/File:Photoplethysmogram_signal_components.svg), Wikimedia Commons (CC BY 4.0)._
```

## Blood pressure estimation

Broadly, there are three approaches for cuffless blood pressure estimation, as illustrated in {numref}`estimating-bp`. These are based on the observation that the speed with which the pulse wave propagates increases with blood pressure (linked via arterial stiffness):
   - measuring the pulse transit time (PTT) between two arterial pulse waves (one closer to the heart and one further away).
   - measuring the pulse arrival time (PAT) between a marker of ventricular contraction, and the arrival of a pulse wave (preferably at a peripheral site)
   - estimating BP from the shape of a pulse wave (such as a photoplethysmography, PPG, pulse wave), since changes in pulse wave velocity and BP influence the shapes of pulse waves.

```{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Estimating_blood_pressure_from_the_photoplethysmogram.pdf/page1-1024px-Estimating_blood_pressure_from_the_photoplethysmogram.pdf.jpg
---
name: estimating-bp
width: 100%
---
**Three approaches to estimate blood pressure from ECG and PPG signals.** _Source: PH Charlton, [Estimating blood pressure from the photoplethysmogram](https://commons.wikimedia.org/wiki/File:Estimating_blood_pressure_from_the_photoplethysmogram.pdf), [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)._
```

## Vascular age assessment

Similarly to blood pressure estimation, there are broadly three approaches to assessing vascular age from PPG and ECG signals, as illustrated in {numref}`assessing-vasc-age`. These are based on the observation that the speed with which the pulse wave propagates increases with blood pressure (linked via arterial stiffness):
   - measuring the pulse transit time (PTT) between two arterial pulse waves (one closer to the heart and one further away).
   - measuring the pulse arrival time (PAT) between a marker of ventricular contraction, and the arrival of a pulse wave (preferably at a peripheral site)
   - estimating BP from the shape of a pulse wave (such as a photoplethysmography, PPG, pulse wave), since changes in pulse wave velocity influence the shapes of pulse waves.

```{figure} ../images/assessing-vasc-age.jpg
:name: assessing-vasc-age
---
width: 100%
---
**Three approaches to assessing vascular age from ECG and PPG signals.** _Source: PH Charlton et al., [Assessing hemodynamics from the photoplethysmogram to gain insights into vascular age: a review from VascAgeNet](https://doi.org/10.1152/ajpheart.00392.2021), [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)._
```

## Parameters

The three approaches to estimate blood pressure or assess vascular age from ECG and PPG signals are now described.

### Pulse transit time

Blood pressure and vascular ageing can be assessed from the pulse transit time, the time delay between two PPG pulse waves, where one is measured closer to the heart, and one further away. This pulse transit time is related to pulse wave velocity:

```{math}
:label: pwv
\mathrm{pulse} \, \mathrm{wave} \, \mathrm{velocity} = \frac{\mathrm{distance} \, \mathrm{travelled}}{\mathrm{pulse} \, \mathrm{transit} \, \mathrm{time}}
```

Pulse wave velocity is in turn related to blood pressure. The distance travelled by the pulse wave between the two PPG measurement sites is often unknown, introducing additional uncertainty into the relationship between the measured pulse transit time and the true blood pressure or arterial stiffness.

### Pulse arrival time

Blood pressure and vascular ageing can be assessed from the pulse arrival time, the time delay between the ECG R-wave and the arrival of a PPG pulse wave. The pulse arrival time is related to pulse transit time by:
```{math}
:label: pat
\mathrm{pulse} \, \mathrm{arrival} \, \mathrm{time} = \mathrm{pulse} \, \mathrm{transit} \, \mathrm{time} + \mathrm{pre} \, \mathrm{ejection} \, \mathrm{period}
```

The pre-ejection period can vary both between subjects, and also over time for an individual subject. Consequently, the use of pulse arrival time introduces additional uncertainty into the assessment of blood pressure or arterial stiffness beyond that of using pulse transit time.

### Pulse wave shape

Blood pressure and vascular ageing can be assessed from the shape of a PPG pulse wave. The shape of the pulse wave changes with vascular ageing and blood pressure as demonstrated in {numref}`ppg-classes`. The higher classes are associated with older subjects and higher blood pressures.

```{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Classes_of_photoplethysmogram_%28PPG%29_pulse_wave_shape.svg/1024px-Classes_of_photoplethysmogram_%28PPG%29_pulse_wave_shape.svg.png
---
name: ppg-classes
width: 100%
---
**Classes of PPG pulse wave shape.** _Source: PH Charlton, [Classes of photoplethysmogram (PPG) pulse wave shape](https://commons.wikimedia.org/wiki/File:Classes_of_photoplethysmogram_(PPG)_pulse_wave_shape.svg), [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)._
```
