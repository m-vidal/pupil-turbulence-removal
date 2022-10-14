## Removal of turbulent flows in the pupil signal

This repository contains a set of routines for pupilometry artifact removal written in R. The main algorithm, described in [1], detects slow and high-frequency turbulences produced by changes in retinal luminance (e.g. due to blinks) and removes them without affecting pupil activity related to cognitive processes. We call this turbulent behavior “responses to ocular events” (ROEs). The algorithm is unsupervised, meaning that it does not rely on any artifact benchmark. To optimize the procedure, the user has to select a dispersion hyperparameter. We model this parameter as a negative exponential that depends on the blink rate, although by default it is set to 3. The algorithm was specifically designed to enhance the estimation of cognitive-related pupil activity during complex motor tasks.

To show the performance of our methods, we recorded a participant who was asked to blink four times synchronised with an auditory beat (2 s) in two different time frames separated by pauses. The beat also appeared 4 times with a different sound during the pauses to alert the participant of the beginning of the blinking task. Blinks were intentionally performed longer to see their effect on the signal. During the pauses, eventual (faster) blinks also occurred. We recorded the participant in a dark environment where, a time before the beginning of the task, a white cross was projected to the scene: this produced a slow ROE not related to blinking activity. 

![alt text here](path-to-image-here)

Please, install  the following packages:

```R
install.packages("imputeFin")
install.packages("imputeTS")
```
--

[1] M. Vidal, K. E. Onderdijk, A. M. Aguilera, J. Six, P-J. Maes and T. H. Fritz, M. Leman. "Cholinergic-related pupil activity reflects level of emotionality during motor performance", 2022.

[2] R. Zhou, J. Liu, S. Kumar and D. P. Palomar, "Student's  t  VAR Modeling With Missing Data Via Stochastic EM and Gibbs Sampling," in IEEE Transactions on Signal Processing, vol. 68, pp. 6198-6211, 2020, doi: 10.1109/TSP.2020.3033378.
