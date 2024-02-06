---
layout: page
title: Bibliography HCI post-processing 
---

<i>In this section, you will find the most relevant scientific publications related to post-processing techniques for high-contrast imaging with ground-based instruments. <em>Please note that the following list is non-exhaustive, if you want your publication to join the list, feel free to contact us.</em></i>

<br>

<p> Nowadays, most post-processing is based on <i>differential imaging</i>. This technique consists in estimating the residual starlight (ideally without any circumstellar signal) and subtracting this estimated image from the scientific image. This operation is repeated for all the available high-contrast scientific images of the target. The subtracted images are then combined to increase the signal-to-noise ratio of the circumstellar signals (planets and/or disks). In order to estimate the starlight residuals, <i>diversity</i> is required: the circumstellar signals of interest must have a different behavior or properties from those of the starlight noise residuals, so that they can be disentangled. This diversity is usually achieved through specific <i>observing strategies* (e.g. polarization imaging, pupil tracking imaging, reference imaging etc.). </p>

<p>The image below summarizes the four steps of differential imaging towards the detection of exoplanets (or disks) signals.</p>
<br>
<p align="center"> 
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/DIprocessing.png" />
</p>
<center><small><i> The images above were acquired with the SPHERE-IRDIS high-contrast instrument installed at the Very Large Telescope (ESO, Chile). The target star is HR 8799 hosting a multiple planetary system. </i></small></center>

### High-contrast imaging general reviews ###

* <i> Direct Imaging and Spectroscopy of Extrasolar Planets</i>: [Currie et al., 2023](https://arxiv.org/pdf/2205.05696.pdf)
* <i> An Introduction to High Contrast Differential Imaging of Exoplanets and Disks</i>: [Follette et al., 2023](https://iopscience.iop.org/article/10.1088/1538-3873/aceb31/pdf)
 

### Post-processing techniques dedicated to high-contrast imaging ###
The paper presented below correspond to data processing based on Angular Differential Imaging (ADI). The concept of ADI applied to high-contrast imaging has been introduced by [Marois et al., 2006](https://iopscience.iop.org/article/10.1086/500401/pdf).<br>
In order to use ADI-based techniques, the images are taken in <em>pupil tracking mode</em> during the observation sequence (usually about an hour of observation, with exposure times ranging from milliseconds to minutes). This observing strategy introduces angular diversity: during the whole observation sequence (1) the astrophysical scene rotates around the optical axis (centred on the star) following the parallactic angle, while (2) the pupil (entrance apperture) of the telescope remains fixed, which means that the optical aberrations are kepts in the same direction in the field of view.
<br>
<p>The image below summarizes how typical so-called 'ADI data set' (temporal cube of high-contrast images) are taken.</p>
<br>
<p align="center"> 
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/HCI_ADIconcept.jpeg" />
</p>
<center><small><i> From left to right: Pupil-tracking imaging is possible with a telescope equipped with an alt-az mount. The pupil (telescope entrance aperture) remains fixed, i.e. the optical wavefront propagates in the same direction until it is focused in the detector's field of view. Meanwhile, the astrophysical scene rotates in the detector's field of view, following the parallactic angles (dotted white curve). The end result is a temporal image cube in which the residual starlight remains more or less fixed, while the planetary/disk signals have a different position in each temporal image, depending on the parallactic angle. </i></small></center>

<br>

#### 1/ Classical Speckle Subtraction techniques ####
* LOCI: [Lafrenière et al., 2007](https://browse.arxiv.org/pdf/astro-ph/0702697.pdf)
* KLIP (PCA): [Soummer et al., 2012](https://iopscience.iop.org/article/10.1088/2041-8205/755/2/L28/pdf)
* SVD (PCA): [Amara & Quanz, 2012](https://browse.arxiv.org/pdf/1207.6637.pdf)
* NMF: [Ren et al., 2018](https://iopscience.iop.org/article/10.3847/1538-4357/aaa1f2/pdf)

#### 2/ Advanced Subtraction techniques ####
* RSM: [Dahlqvist et al., 2020](https://browse.arxiv.org/pdf/1912.05412.pdf)
* STIM-map: [Pairet et al., 2019](https://browse.arxiv.org/pdf/1810.06895.pdf)
* LR-map: [Daglayan et al., 2022](https://arxiv.org/pdf/2210.10609.pdf)

#### 3/ Inverse Problem approaches ####
* ANDROMEDA: [Cantalloube et al., 2015](https://browse.arxiv.org/pdf/1508.06406.pdf) (after [Mugnier et al., 2009](http://laurent.mugnier.free.fr/publis/Mugnier-JOSAA-09.pdf))
* FMMF: [Ruffio et al., 2017](https://browse.arxiv.org/pdf/1705.05477.pdf) (after [Pueyo et al., 2016](https://iopscience.iop.org/article/10.3847/0004-637X/824/2/117/pdf))
* PACO: [Flasseur et al., 2018](https://www.aanda.org/articles/aa/pdf/2018/10/aa32745-18.pdf)
* TRAP: [Samland et al., 2021](https://browse.arxiv.org/pdf/2011.12311.pdf)

#### 4/ Supervised Machine learning ####
* SODDIN: [Gomez-Gonzalez et al., 2017](https://arxiv.org/pdf/1712.02841.pdf)
* NA-SODDIN: [Cantero et al., 2023](https://arxiv.org/pdf/2302.02854.pdf)
* HSR: [Gebhard et al., 2022](https://arxiv.org/pdf/2204.03439.pdf)
* Deep-PACO: [Flasseur et al., 2023](https://arxiv.org/pdf/2303.02461.pdf)

#### 5/ Dedicated to extended structure imaging ####
* NMF: [Ren et al., 2018](https://iopscience.iop.org/article/10.3847/1538-4357/aaa1f2/pdf)
* DISK-FM: [Mazoyer et al., 2020](https://arxiv.org/pdf/2012.06790.pdf)
* MAYONNAISE: [Pairet et al., 2021](https://browse.arxiv.org/pdf/2008.05170.pdf)
* REXPACO: [Flasseur et al., 2021](https://arxiv.org/pdf/2104.09672.pdf)
* MUSTARD: [Juillard et al., 2023](https://browse.arxiv.org/pdf/2309.14827.pdf)


### Detection limits & performance assessement ###
* <i>Confidence level and Sensitivity limits in HCI</i>: [Marois et al., 2007](https://browse.arxiv.org/pdf/0709.3548.pdf)
* <i>Fundamental limitations of HCI set by small sample statistics</i>: [Mawet et al., 2014](https://browse.arxiv.org/pdf/1407.2247.pdf)
* <i>A New Standard for assessing the performance of HCI</i>: [Jensen-Clem et al., 2017](https://arxiv.org/pdf/1711.01215.pdf)
* <i>Robust Detection Limits for HCI in the presence of non-Gaussian noise</i>: [Bonse et al., 2023](https://arxiv.org/pdf/1711.01215.pdf)



