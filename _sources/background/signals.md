# Signals

This book will consider three principal signals acquired by many wearables: acceleration, electrocardiogram, and photoplethysmogram signals.

## Acceleration

An accelerometer is used to measure acceleration - the rate of change in velocity.

Tri-axial accelerometers measure acceleration in three orthogonal directions (often seen as the x-, y-, and z-axes on a graph). {numref}`tri-axial-accel` shows a 10-second excerpt of tri-axial accelerometer signals during walking. Note that the signal with a mean value of -9.87m/s$^2$: exhibits twice as many cycles as the other signals. The axis of this signal is approximately vertical (as shown by a mean value of approximately 1 g-force), and it captures the vertical accelerations which occur with each stride.

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

For instance, in the example above the MAD is 1.93m/s$^2$, which corresponds to approximately 197mg$_0$ (milligravitational units). Using the look-up table below, we can see that this corresponds to normal walking:

| MAD (mg$_0$)    | Activity    |
| :--- | ---: |
| 0 - 16.7    | Sedentary    |
| 16.7 - 157.4    | Slow walking    |
| 157.4 - 331.2    | Normal walking    |
| 331.2 - 599.3    | Brisk walking    |
| > 599.3    | Jogging and running    |

## Electrocardiogram

## Photoplethysmogram

![PPG signals at rest and during exercise](https://upload.wikimedia.org/wikipedia/commons/8/8a/Photoplethysmogram_signals_at_rest_and_during_exercise.svg)

Source: _Charlton PH, [Photoplethysmogram signals at rest and during exercise](https://commons.wikimedia.org/wiki/File:Photoplethysmogram_signals_at_rest_and_during_exercise.svg), Wikimedia Commons (CC BY 4.0)._
