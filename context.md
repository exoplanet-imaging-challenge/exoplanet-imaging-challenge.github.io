---
layout: page
title: Scientific context and objectives
---

Direct imaging is the next big step in the hunt of extrasolar planets. But observing exoplanets using ground-based telescopes is a very challenging task! The main difficulties are the huge difference in brightness between the host star and its potential companions, the small angular separation between them, and the image degradation caused by the Earth's turbulent atmosphere. Therefore, ground-based high-contrast imaging (HCI) relies on the use of adaptive optics for wavefront correction and coronagraphy for the suppression of light coming from the star. The following video, prepared by the NASA Exoplanet Exploration Program, explains in simple terms the role of coronagraphy and adaptive optics with deformable mirrors in HCI. Please check it out:  

<iframe width="560" height="315" src="https://www.youtube.com/embed/SpzeS7KBGkw?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

The two remaining components of high-contrast imaging are the data acquisition techniques which focus on introducing some diversity in the data that later on can be exploited by the post-processing techniques (see the sub-challenges section below). This last step of algorithmic speckle noise subtraction is what ultimately pushes the sensitivity of the exposures, and the detection limits of HCI instruments and surveys. 

# Objectives 

A multitude of image processing algorithms and pipelines for processing high contrast imaging data have been developed in the past thirteen years. [Pueyo (2018)](https://link.springer.com/referenceworkentry/10.1007/978-3-319-30648-3_10-1) offers an ample discussion on the exoplanet detection algorithms proposed in the literature. The goal of this challenge is not only to compare, in a fair and robust way, existing post-processing algorithms but to spur the design of new techniques, spark new collaborations and ideas, and share knowledge. 

With the aim of creating a manageable competition, we will focus exclusively on the detection of point-like sources (exoplanets). Other tasks, such as the characterization of companions, the detection of extended sources, reference star differential imaging and the usage of metadata/telemetry, will be the subject of future editions of the challenge. 

{: .box-note}
**Note:** You don't need to be an astronomer or expert in high-contrast imaging to participate! We welcome the participation of non-domain experts. On this website you will find extensive documentation about the challenge and how to participate. We expect domain experts will use their tools, for outsiders we have prepared a starting kit in the resources section.

Computer science and machine learning fields have a long tradition conducting data challenges and competitions. Repositories of benchmark (curated) datasets are an integral part of the field of machine learning. We want to integrate these practices to the field of high-contrast imaging. In the future, the process of testing new algorithms will be much straightforward and robust, once the community adopts the standard metrics (with their open-source implementations) and the benchmark library resulting from this challenge.  





