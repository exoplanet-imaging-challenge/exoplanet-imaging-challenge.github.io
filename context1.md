---
layout: page
title: Objectives of the Phase 1 
---

# Objectives:
## point source detection

In the first phase of the <i> Exoplanet Imaging Data Challenge </i>, the focus is exclusively on the detection of point-like sources (exoplanets) within high-contrast images taken with ground-based telescopes. 

A multitude of high-contrast imaging post-processing algorithms and pipelines have been developed in the past fifteen years to detect faint planetary signals within astronomical images. [Pueyo (2018)](https://link.springer.com/referenceworkentry/10.1007/978-3-319-30648-3_10-1) offers an ample discussion on the exoplanet detection algorithms proposed in the literature. You may refer to the ``Bibliography`` tab for more reference about the latest image processing techniques dedicated to HCI.

# Two sub-challenges:
## Rotating field and multispectral images

This competition is composed of two sub-challenges focusing on the two most widely used observing techniques:<br> 
- Pupil tracking observations (angular differential imaging, **ADI**), <br> 
- Multi-spectral imaging, combined with pupil tracking (multi-channel spectral differential imaging, **ADI+mSDI**). 

### ADI
In pupil-stabilized or pupil-tracking observations the telescope pupil is stabilized on the detector and the field of view rotates in step with a given angle (the parallactic angle). This generates a fake movement of the companions in a circular trajectory around the center of the image, the place where the star is located. This generated diversity makes it possible to disentangles the exoplanet signal (rotating) from the speckle field (quasi-static). ADI-based post-processing techniques exploit this diverstity to unveil the faint planetary signals. 

The so-called "ADI datasets" are composed of:<br> 
(i) a cube of images (x,y,t) acquired during a 1h to 3h observing sequence (see Fig. 1);<br>
(ii) the corresponding parallactic angles variation during the observing sequence;<br>
(iii) the point-spread function (PSF) of the instrument (a non-saturated or non-coronagraphic image of the target star) acquired around the observing sequence. 

The following video explains the ADI observation technique:

<center> 
<iframe src="https://player.vimeo.com/video/125547220" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
<p><a href="https://vimeo.com/125547220">90 Seconds of Astronomy - Angular Differential Imaging</a> from <a href="https://vimeo.com/user5671143">nadara</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
</center> 

### ADI+mSDI
In the case of multi-spectral imaging, an integral field spectrograph (IFS) disperses the light, providing simultaneously, for each exposure, several monochromatic images. The resolution and wavelength coverage varies depending on the instrument used. The speckle distributions (and more generally the starlight residuals) vary with the wavelength (see Fig. 1), while the planetary signal's centroid remains static. This diversity also makes it possible to disentangles the exoplanet signal (static) from the speckle field (moving radially). SDI-based post-processing techniques exploit this diverstity to unveil the faint planetary signals. 

| ![IFS_frame](https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/ifs_frame.gif){:width="400px"} |
| --- |
| Figure 1. *A single IFS frame showing the behaviour of the speckles as a function of the wavelength (the label on the animation corresponds to an index instead of the wavelength itself)*. |

Multi-spectral imaging is usually combined with ADI. In this case, the so-called "ADI+mSDI datasets" are composed of:<br>  
(i) a 4D cube of images (see Fig. 2);<br>
(ii) the corresponding parallactic angles variation along the temporal dimension;<br>
(iii) the corresponding vector of wavelenghts along the spectral dimension;<br>
(iv) the point-spread function (PSF) of the instrument.


| ![ADI_SDI](https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/challenge_fig1.001.png){:width="700px"} |
| --- |
| Figure 2. *Dimensionality of the cubes used in this challenge, depending on the observing technique: the left panel shows a single ADI data cube and the right panel shows an ADI + multi-channel SDI data cube*. |


{: .box-note}
**Note on RDI:** Although Referential Differential Imaging (**RDI**) does not constitute a separate sub-challenge, we welcome submissions that make use of reference datasets or libraries (whether it is the cubes provided within the challenge or external ones). We only require the participant to **make clear if RDI is used** instead of pure ADI or ADI+mSDI post-processing (this is explained on the "metrics" sub-section on the top navigation bar).

Figure 3 shows an schematic representation of an HCI point source detection pipeline. 
In this phase of the data challenge, we do not use datasets with known (real) companions. Instead, we injected synthetic planetary signals in the data in order to measure the detection capability of different algorithms. Each challenge cube contains from *none to five synthetic point-sources*, injected using a standard process (without accounting for smearing or any source of variable photometry). For spectrally dispersed data we additionnaly use three empirical field brown dwarf template spectra for the injection of the synthetic planetary signals in the different spectral channels.

| ![data](https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/challenge_fig2.001.png){:width="700px" align="center"}|
|---|
| Figure 3. *Schematic representation of the high-contrast imaging data processing pipeline, for the case of a LBTI/LMIRCam HR8799 data cube. Notice how from a data cube (or image sequence) we obtain one view of the star's vicinity and an associated detection map where we could detect potential point-like sources*.  |
