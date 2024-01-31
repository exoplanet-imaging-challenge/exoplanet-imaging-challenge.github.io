---
layout: page
title: Bibliography HCI post-processing 
---

<i>In this section, you will find the most relevant scientific publications and open-source pipelines related to post-processing techniques for high-contrast imaging.</i>

<br>

<p> Nowadays, most post-processing is based on <i>differential imaging</i>. This technique consists in estimating the residual starlight (ideally without any circumstellar signal) and subtracting this estimated image from the scientific image. This operation is repeated for all the available high-contrast scientific images of the target. The subtracted images are then combined to increase the signal-to-noise ratio of the circumstellar signals (planets and/or disks). In order to estimate the starlight residuals, *diversity* is required: the circumstellar signals of interest must have a different behavior or properties from those of the starlight noise residuals, so that they can be disentangled. This diversity is usually achieved through specific *observing strategies* (e.g. polarization imaging, pupil tracking imaging, reference imaging etc.). </p>

<p>The image below summarizes the four steps of differential imaging towards the detection of exoplanets (or disks) signals.</p>
<br>
<p align="center">
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/DIprocessing.png" />
</p>
<center><small><i> The images above were acquired with the SPHERE-IRDIS high-contrast instrument installed at the Very Large Telescope (ESO, Chile). The target star is HR 8799 hosting a multiple planetary system. </i></small></center>

### High-contrast imaging general reviews ###

### Post-processing techniques dedicated to high-contrast imaging ###

### Limitations to high-contrast imaging ###

<br>

<br>

#### HR 8799 system orbit video ####

The young star HR 8799 hosts four giant gaseous planets ([Marois et al., 2010](https://www.nature.com/articles/nature09684.pdf)). The following video shows 10 different epochs of post-processed high-contrast images of the HR 8799 system observed in the near-infrared over a period of 12 years, from 2009 to 2021. Data are taken using the [NIRC2 instrument](https://www2.keck.hawaii.edu/inst/nirc2/) installed at the [Keck Telescope](https://keckobservatory.org/) (Mauna Kea observatory, Hawaii, USA). 

<br>

<p align="center" width="150" height="150">
  <img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/orbit_hr_8799.gif" alt="animated" />
</p>
<center><i>&copy; Jason Wang (Northwestern)/William Thompson (UVic)/Christian Marois (NRC Herzberg)/Quinn Konopacky (UCSD) <a href="https://jasonwang.space/orbits.html" target="_blank">Source J. Wang</a>.</i></center>

