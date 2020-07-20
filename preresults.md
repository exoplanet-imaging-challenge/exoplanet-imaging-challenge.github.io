---
layout: page
title: Preliminary results
---

**On this page, we present the results obtained during the test phase of the data challenge (deadline January 2020).** 
The feedbacks of this test phase were useful to improve the data challenge as a whole before settling the new deadline for the phase 1 (30th of September 2020). 
We warmly thanks the participants who have submitted their results for this first test phase (note that the results submitted during the test phase are valid for the final phase 1).

Among the 51 participants who registered on CodaLab, we received *9 submissions*. 
We publish here the results from the ADI sub-challenge (*subchallenge_1*) on the VLT/SPHERE-IRDIS data in K1 narrow-band (*SPHERE_IRDIS_3*). 

## Data VLT/SPHERE-IRDIS narrow-band
We chose this dataset among the data for the data challenge ([presented on this page] (https://exoplanet-imaging-challenge.github.io/datasets/)) because this is the most used SPHERE mode for exoplanet detection (e.g. SHINE large survey, [Chauvin et al., 2017](https://ui.adsabs.harvard.edu/abs/2017sf2a.conf..331C/abstract)). 

The observing conditions were not stable so the image cube shows large temporal speckle variation.

| ![DataSPHEREirdis3](){:width="600px"} |
|---|
| Figure 1. *First frame of the provided data cube (left), temporal median of the data cube (middle) and normalised off-axis PSF (right) *. |

## Baseline result

In order to define the detection limit around which the synthetic companions are injected, we ran a classic annular PCA from the VIP toolbox (https://vip.readthedocs.io/en/latest/#). The obtained detection map is shown on Fig.2 below. The F1-score obtained for this widely used speckle-subtraction technique is *0.45*. 

| ![BaslineSPHEREirdis3](link){:width="600px"} |
|---|
| Figure 2. *Post-processed image using annular PCA as implemented in VIP*. |


## Results from participants

From the submission, 6 are valid and the results are shown below. 

The six detection maps are displayed from their minimum value to the participant provided threshold: every resel above this threshold is considered as a detection. The true positifs are encircled in blue. 

From these detection map, we extracted the true positive fraction (TPF, see definitions [here](https://exoplanet-imaging-challenge.github.io/metrics/)) and the false positive fraction (FPF). For this we first apply the same binary mask to all the detection maps (between a radius of 15 to 70 pixels, the detection maps being 159x159 pixels). We then varied the threshold from 0.1 to 10 and counted the detections per resels, compared to the injected signals. The FPF (in red) and the TPF (green) as a function of the threshold are shown below the detection maps. *The goal is to minimize the area under the red curve (the FPF must be as close as possible to zero whatever the threshold) and to maximize the area under the green curve (the TPF must be as close as possible to one, whatever the threshold)*.

More information about each algorithm used can be find at the end of this page.

The global F1-score ([defined here](https://exoplanet-imaging-challenge.github.io/metrics/)) is also shwown below each algorithm.

| ![ResultSPHEREirdis3](img/DataChallenge_sphere3.pdf){:width="600px"} |
|---|
| Figure 3. *Detection maps submitted (the colorbar is given from the minimal value to the given threshold): at the participant-provided threshold, true detections are encircled in blue. For each image we plotted the corresponding FPF and TPF as a function of threshold (vertical line is the participant-provided threshold) and the F1-score is indicated below*. |


## Discussions

### Visual inspection

* First, we can notice that similar concept show a very similar structure in the detection map. For instance speckle subtraction techinques (baseline, PCA_padova and PCA_mpia) show similar residual maps whereas inverse problems based technique (FMMF and ANDROMEDA) show also similar structures due to correlation with the planetary model. The RSM map and STIM-ca map both use the temporal axis and while the first looks for a noise-planet regime switch, the second combines the PCA subtracted data by taking into account the noise temporal statistics. 

* Second, some algorithm process the whole field of view (FMMF and marginally PCA_padova), while the other ones are working in inscribed circles.

* Third, similarly, some algorithm process the data as close as possible to the star (STIM-ca), whereas others are starting at larger angular separation (FMMF), depending on the concept behind (angular subtraction etc.)


### True Positive Fraction

In terms of TPF (green curve), the STIM-ca map stands beyond other methods, by always revealing the 5 injected companions even at very high thresholds. 
FMMF provides a threshold (dashed vertical line) that enables the detection of the 5 injected companions, but all the other detections fail at revealing all of the 5 detections.

### False Positive Fraction

In terms of FPF (red curve), the RSM map stands also beyond with no false positives, whatever the threshold. 
On the contrary the speckle subtraction technique PCA_padova shows a high number of false positives all over the field of view. 
Notably, FMMF and ANDROMEDA, based on a very similar approach (modeling and tracking the planetary signal after a speckle subtraction), have a very similar trend of false positive fraction as a function of threshold.

*In terms of trade-off, FMMF is the most powerful technique to minimize the FPF while maximizing the TPF in order to detect the 5 injected signals above the participant-provided threshold (hence the larger F1-score).*

### Running time 

TBC


## Additional information about the algorithm used

* Forward Modeling Matched Filter [FMMF](https://ui.adsabs.harvard.edu/abs/2017ApJ...842...14R/abstract): available in the [pyKLIP](https://pyklip.readthedocs.io/en/latest/) package.
* ANDROMEDA [ANDRO](https://ui.adsabs.harvard.edu/abs/2015A%26A...582A..89C/abstract): available in the [VIP](https://pyklip.readthedocs.io/en/latest/) package. 
* Regime Switching Model [RSM](https://ui.adsabs.harvard.edu/abs/2020A%26A...633A..95D/abstract): available in the [VIP](https://pyklip.readthedocs.io/en/latest/) package.
* Standardized Trajectory Intensity Mean [STIM](https://ui.adsabs.harvard.edu/abs/2019MNRAS.487.2262P/abstract): available in the [VIP](https://pyklip.readthedocs.io/en/latest/) package.
* Principal Component Analysis [PCA](https://ui.adsabs.harvard.edu/abs/2012MNRAS.427..948A/abstract),[KLIP](https://ui.adsabs.harvard.edu/abs/2012ApJ...755L..28S/abstract)


**We hope this page motivates you to participate too !**

