# Signals

This book will consider three principal signals acquired by many wearables: acceleration, electrocardiogram, and photoplethysmogram signals.

(content:signals:accel)=
## Acceleration

An accelerometer is used to measure acceleration - the rate of change in velocity. Accelerometers can be used to assess physical activity, such as exercise, posture, and sleep status. They are inexpensive and consume little power, and are widely incorporated into wearables and smartphones.

Tri-axial accelerometers measure acceleration in three orthogonal directions (often seen as the x-, y-, and z-axes on a graph). {numref}`tri-axial-accel` shows a 10-second excerpt of tri-axial accelerometer signals during walking. Note that the signal with a mean value of -9.87m/s$^2$ exhibits twice as many cycles as the other signals. The axis of this signal is approximately vertical (as shown by a mean value of approximately 1 g-force), and it captures the vertical accelerations which occur with each stride. In contrast, the other signals are dominated by the horizontal movement of the arm during walking, and therefore exhibit one peak for every two strides.

```{figure} ../images/accel_pulseon_walk_tri.png
:name: tri-axial-accel
---
width: 100%
---
**Tri-axial accelerometer signals during walking.** _Measured using a PulseOn OHR Tracker._
```

In some applications, a single accelerometer signal is calculated from the tri-axial signals as the magnitude of the resultant acceleration vector, $r_i = \sqrt{x_i^2 + y_i^2 + z_i^2}$:

```{figure} ../images/accel_pulseon_walk.png
:name: resultant-accel
---
width: 100%
---
**Resultant accelerometer signal.** _Measured using a PulseOn OHR Tracker._
```

A simple application of the accelerometer signal is to classify physical activities. To do so, the 'mean amplitude deviation' can be calculated, with increasing values indicating increasing intensity levels (see [here](https://doi.org/10.1111/cpf.12127) for details). The mean amplitude deviation is the mean difference between the resultant acceleration vector and its mean value, $MAD = \frac{1}{n}\sum_{i=1}^n \left| r_i - \overline{r} \right|$.

For instance, in the example above the MAD is 1.93m/s$^2$, which corresponds to approximately 197mg$_0$ (milligravitational units). Using the look-up table below (from [here](https://doi.org/10.1111/cpf.12127)), we can see that this corresponds to normal walking:

| MAD (mg$_0$)    | Activity    |
| :--- | ---: |
| 0 - 16.7    | Sedentary    |
| 16.7 - 157.4    | Slow walking    |
| 157.4 - 331.2    | Normal walking    |
| 331.2 - 599.3    | Brisk walking    |
| > 599.3    | Jogging and running    |

(content:signals:ecg)=
## Electrocardiogram

The electrocardiogram (ECG) is a measure of the heart's electrical activity. Each time the heart beats a series of electrical currents are generated, indicating the contraction or relaxation of different parts of the heart. Consequently, the ECG provides information on heart rate, heart rhythm, and heart muscle function. The ECG is measured as the voltage difference between two points on the body surface over time. Like accelerometers, ECG sensors are inexpensive and consume little power.

A traditional 12-lead ECG device used in a clinic (such as that shown in {numref}`12-lead-ecg`) provides 12 simultaneous ECG signals which correspond to different 'views' of the heart's electrical activity (see {numref}`12-lead-ecg-trace`). Consequently, 12-lead ECGs can be used not only to identify abnormal heart function, but even to identify which part of the heart is not functioning normally. In the 1960s wearable devices ('Holter' monitors) were developed which measured a reduced set of ECG signals from electrodes on the chest. These are widely used today for cardiac investigations.

```{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/d/df/12_lead_ECG.jpg/1600px-12_lead_ECG.jpg?20230502072821
---
width: 80%
name: 12-lead-ecg-trace
---
**A 12-lead ECG measurement.** _Source: Charlton PH, [12 lead ECG](https://commons.wikimedia.org/wiki/File:12_lead_ECG.jpg) ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/))_
```

Recently, single-lead ECG sensors have been incorporated into wrist-worn devices, as shown in {numref}`withings-move-ecg`. These devices typically have on electrode on the underside, and another on either the side or top of the device which the user touches with their opposite hand.

```{figure} ../images/withings_move_ecg.jpg
---
name: withings-move-ecg
width: 80%
---
**Recording a single-lead ECG at the wrist.** _A Withings Move-ECG watch._
```

A single-lead ECG (shown in {numref}`wrist-ecg` below) can be used to assess heart rhythm, and to assess some aspects of heart functionality.

```{figure} ../images/withings_ecg.png
---
name: wrist-ecg
width: 100%
---
**Single-lead ECG recorded at the wrist.** _Measured using a Withings Move-ECG watch._
```

(content:signals:ppg)=
## Photoplethysmogram

Photoplethysmography sensors measure changes in blood volume over time. A photoplethysmogram (PPG) signal is acquired by using an LED to shine light onto the skin ({numref}`ppg-sensor`), and then measuring the amount of light either reflected from the skin (in the case of a wrist-worn device) or transmitted through the tissue (in the case of a pulse oximeter).

```{figure} ../images/polar_oh1_underside.jpg
---
name: ppg-sensor
width: 50%
---
**A photoplethysmogram (PPG) sensor.** _Source: Marozas V and Charlton PH, [Wearable photoplethysmography devices](https://doi.org/10.5281/zenodo.4601547), Wikimedia Commons (CC BY 4.0)._
```

The PPG signal, shown in {numref}`ppg-signal` below, exhibits a peak for each heart beat, caused by blood volume increasing and decreasing as blood pressure increases and decreases with each heart beat. PPG sensors are more expensive and consume more power than accelerometers and ECG sensors. However, they have the advantage that they can unobtrusively measure signals, unlike wrist ECG sensors which require the user to interact with the device whilst a signal is being measured. Consequently, photoplethysmography sensors are widely used in consumer wearables to monitor heart rate, heart rate variability, and heart rhythm. 

```{figure} https://upload.wikimedia.org/wikipedia/commons/8/8a/Photoplethysmogram_signals_at_rest_and_during_exercise.svg
---
name: ppg-signal
width: 80%
---
**Photoplethysmogram (PPG) signals at rest and during exercise.** _Source: Charlton PH, [Photoplethysmogram signals at rest and during exercise](https://commons.wikimedia.org/wiki/File:Photoplethysmogram_signals_at_rest_and_during_exercise.svg), Wikimedia Commons (CC BY 4.0)._
```

Note how the PPG signal is highly susceptible to noise, as shown in the lower panel of {numref}`ppg-signal`. Here, the signal is contaminated with motion artifact caused by walking.

(content:signals:bp)=
## Blood pressure

The blood pressure signal is not widely measured by wearables. It is briefly introduced here to outline the physiology underpinning the signal, and for comparison with the PPG signal.

The pressure within the arteries varies with the pumping of blood each heart beat. When measured continuously, the blood pressure is a pulsatile signal, varying between systolic (maximum) and diastolic (minimum) pressures, as shown in {numref}`bp-signal`.

```{figure} ../images/bp_mimic.png
---
name: bp-signal
width: 100%
---
**A blood pressure signal recorded from a critically-ill patient.** _Data extracted from the [MIMIC Waveform Database (v.2)]()._
```

{numref}`compare-ppg-bp` shows a comparison of photoplethysmogram (PPG) and blood pressure signals. The two signals do share similarities, particularly in the timing of pulse waves. However, the pulse wave morphologies differ slightly between the signals, such as the different appearances of the diastolic peaks, and the differing nature of the diastolic decay shown particularly clearly in the ectopic beat (at time 2.5-3.2 s).

```{figure} ../images/compare_ppg_bp_mimic.png
---
name: compare-ppg-bp
width: 100%
---
**Comparison of photoplethysmogram (PPG) and blood pressure signals.** _Data extracted from the [MIMIC Waveform Database (v.2)]()._
```