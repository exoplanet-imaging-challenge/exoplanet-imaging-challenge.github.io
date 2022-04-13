---
layout: page
title: Objectives of the Phase 1 
---

# Objectives 

A multitude of HCI post-processing algorithms and pipelines have been developed in the past thirteen years. [Pueyo (2018)](https://link.springer.com/referenceworkentry/10.1007/978-3-319-30648-3_10-1) offers an ample discussion on the exoplanet detection algorithms proposed in the literature. **The goal of this challenge is not only to compare, in a fair and robust way, existing post-processing algorithms, but also to spur the design of new techniques, spark new collaborations and ideas, and share knowledge.** 

With the aim of creating a manageable competition, we will focus exclusively on the detection of point-like sources (exoplanets). Other tasks, such as the characterization of companions, the detection of extended sources, reference star differential imaging and the usage of metadata/telemetry, will be the subject of future editions of the challenge. 

Computer science and machine learning fields have a long tradition conducting data challenges and competitions. Repositories of benchmark (curated) datasets are an integral part of the field of machine learning. We want to integrate these practices to the field of high-contrast imaging. In the future, the process of testing new algorithms will be much straightforward and robust, once the community adopts the standard metrics (with their open-source implementations) and the benchmark library resulting from this challenge.  

# Two sub-challenges

This competition is composed of two sub-challenges focusing on the two most widely used observing techniques: pupil tracking (angular differential imaging, ADI) and multi-spectral imaging combined with pupil tracking (multi-channel spectral differential imaging, ADI+mSDI). 

**ADI**: In pupil-stabilized or pupil-tracking observations the telescope pupil is stabilized on the detector and the field of view rotates in step with a given angle (the parallactic angle). This generates a fake movement of the companions in a circular trajectory around the center of the image, the place where the star is located. This process disentangles the exoplanet signal from the speckle field, an effect that is enhanced by the post-processing techniques. ADI datasets are composed of a 3d cube of images taken during an observing run (see Fig. 1) and their corresponding parallactic angles and non-saturated point-spread function (PSF). The following video explains the ADI observation technique:

<center> 
<iframe src="https://player.vimeo.com/video/125547220" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
<p><a href="https://vimeo.com/125547220">90 Seconds of Astronomy - Angular Differential Imaging</a> from <a href="https://vimeo.com/user5671143">nadara</a> on <a href="https://vimeo.com">Vimeo</a>.</p>
</center> 

**ADI+mSDI**: In the case of multi-spectral imaging, an integral field spectrograph (IFS) is used to disperse the light, providing a data cube of several monochromatic images. The resolution and band coverage varies depending on the instrument used. Since the speckles are a function of wavelength, as shown in Fig. 1, we can rescale the images to align them and create a fake movement of the companions in a radial direction. This diversity is also exploited by the post-processing algorithms. 

| ![IFS_frame](https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/ifs_frame.gif){:width="400px"} |
| --- |
| Figure 1. *A single IFS frame showing the behaviour of the speckles as a function of the wavelength (the label on the animation corresponds to an index instead of the wavelength itself)*. |

Multi-spectral imaging is usually combined with ADI in modern instruments. In this case, the datasets are composed of a 4d cube of images (see Fig. 2), a vector of parallactic angles, a vector of wavelenghts and a PSF (this is detailed in the ``datasets`` section of this website). 


| ![ADI_SDI](https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/challenge_fig1.001.png){:width="700px"} |
| --- |
| Figure 2. *Dimensionality of the cubes used in this challenge, depending on the observing technique: the left panel shows a single ADI data cube and the right panel shows an ADI + multi-channel SDI data cube*. |


{: .box-note}
**Note on RDI:** Although Referential Differential Imaging (**RDI**) does not constitute a separate sub-challenge, we welcome submissions that make use of reference datasets or libraries (whether it is the cubes provided within the challenge or external ones). We only require the participant to **make clear if RDI is used** instead of pure ADI or ADI+mSDI post-processing (this is explained on the "metrics" sub-section on the top navigation bar).

In Fig. 3 we show an schematic representation of a HCI blob/planet detection pipeline. In the context of this data challenge, we will not use datasets with known (real) companions. Instead, we will inject synthetic planets or companions in order to measure the detection capability of different algorithms. Each challenge cube contains from *none to five synthetic point-sources*, injected using a standard process without accounting for smearing or variable photometry). For spectrally dispersed data we will use three template spectra when injecting the fake companions. 

| ![data](https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/challenge_fig2.001.png){:width="700px"} |
|---|
| Figure 3. *Schematic representation of the high-contrast imaging data processing pipeline, for the case of a LBTI/LMIRCam HR8799 data cube. Notice how from a data cube (or image sequence) we obtain one view of the star's vicinity and an associated detection map where we could detect potential point-like sources*.  |
