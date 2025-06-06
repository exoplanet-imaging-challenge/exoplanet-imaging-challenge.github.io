---
layout: page
title: Bibliography HCI post-processing 
---
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">

<i><center>In this section, you will find the most relevant scientific publications related to post-processing techniques for high-contrast imaging with ground-based instruments. Please note that the following list is not exhaustive. If you would like your publication to be added to the list, please do not hesitate to contact us.</center></i>

<br>

<p style='text-align: justify;'> Nowadays, most post-processing techniques are based on <i>differential imaging</i> (DI). It consists in estimating the residual starlight (ideally without any circumstellar signal) and subtracting this estimate from the scientific image. This operation is repeated for every available image of the target star. The subtracted images are then combined to increase the signal-to-noise ratio of the potential circumstellar signals (planets and/or disks). A so-called <i>detection map</i> is then built (usually a signal-to-noise ratio map with a threshold), providing a confidence level for any detection in the field of view.</p>

<p> In order to estimate the starlight residuals, <i>diversity</i> is required: the circumstellar signals of interest must have different behavior or properties from those of the residual starlight noise, so that they can be disentangled. This diversity is usually achieved through specific <i>observing strategies</i> (e.g. polarization imaging, pupil tracking imaging, reference imaging etc.). </p>
<br>
<p>The image below summarizes the four steps of differential imaging towards the detection of exoplanet (or disk) signals:</p>
<p align="center"> 
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/DIprocessing.png" />
</p>
<center><small><i> The images above were acquired with the VLT/SPHERE-IRDIS high-contrast instrument. The target star is HR 8799 hosting a multiple planetary system (four detected). </i></small></center>

### High-contrast imaging general reviews ###

* <i> High-Contrast Imaging: Hide and Seek with Exoplanets</i>: <a href="https://arxiv.org/pdf/2501.07976" style="text-decoration:underline;color:slateblue">Claudi & Mesa, 2025</a>
* <i> Direct imaging of exoplanets</i>: <a href="https://arxiv.org/pdf/2404.05797" style="text-decoration:underline;color:slateblue">Zurlo, 2024</a>
* <i> Direct Imaging and Spectroscopy of Extrasolar Planets</i>: <a href="https://arxiv.org/pdf/2205.05696.pdf" style="text-decoration:underline;color:slateblue">Currie et al., 2023</a>
* <i> An Introduction to High Contrast Differential Imaging of Exoplanets and Disks</i>: <a href="https://iopscience.iop.org/article/10.1088/1538-3873/aceb31/pdf" style="text-decoration:underline;color:slateblue">Follette, 2023</a>
* <i> Imaging exoplanets with coronagraphic instruments</i>: <a href="https://comptes-rendus.academie-sciences.fr/physique/item/10.5802/crphys.133.pdf" style="text-decoration:underline;color:slateblue">Galicher & Mazoyer, 2023</a>
* <i> Peering through SPHERE Images: A Glance at Contrast Limitations</i>: <a href="https://www.eso.org/sci/publications/messenger/archive/no.176-jun19/messenger-no176-25-31.pdf" style="text-decoration:underline;color:slateblue">Cantalloube et al., 2019</a>


### Post-processing techniques dedicated to high-contrast imaging ###
<p style='text-align: justify;'>The paper presented below correspond to data processing based on Angular Differential Imaging (ADI). The concept of ADI applied to high-contrast imaging has been introduced by <a href='https://iopscience.iop.org/article/10.1086/500401/pdf' style="text-decoration:underline;color:slateblue">Marois et al., 2006</a>.</p>
<p style='text-align: justify;'>In order to use ADI-based techniques, the images are taken in <em>pupil tracking mode</em> during the observation sequence (usually about an hour of observation, with exposure times ranging from milliseconds to minutes). This observing strategy introduces angular diversity: during the whole observation sequence <strong>(1)</strong> the astrophysical scene rotates around the optical axis (centred on the target star) following the <a href='https://en.wikipedia.org/wiki/Parallactic_angle' style="text-decoration:underline;color:slateblue">parallactic angle</a>, while <strong>(2)</strong> the telescope pupil (entrance aperture) remains fixed, meaning that the optical aberrations are kept in the same direction in the field of view during the observation sequence.</p> 
<br>
<p>The image below summarizes how a typical so-called <em>ADI data set</em> is acquired:</p>
<p align="center"> 
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/HCI_ADIconcept.jpeg" />
</p>
<center><small><i> From left to right: Pupil-tracking imaging is possible with a telescope equipped with an alt-az mount. The pupil (telescope entrance aperture) remains fixed, i.e. the optical wavefront propagates in the same direction until it is focused in the detector's field of view. Meanwhile, the astrophysical scene rotates in the detector's field of view, following the parallactic angles (dotted white curve). The end result is a temporal image cube in which the residual starlight remains more or less fixed, while the planetary/disk signals have a different position in each temporal image, depending on the parallactic angle. </i></small></center>

<br>

#### 1/ Classical Speckle Subtraction techniques ####
* LOCI: <a href="https://arxiv.org/pdf/astro-ph/0702697.pdf" style="text-decoration:underline;color:slateblue">Lafrenière et al., 2007</a>
* KLIP (PCA): <a href="https://iopscience.iop.org/article/10.1088/2041-8205/755/2/L28/pdf" style="text-decoration:underline;color:slateblue">Soummer et al., 2012</a>
* SVD (PCA): <a href="https://arxiv.org/pdf/1207.6637.pdf" style="text-decoration:underline;color:slateblue">Amara & Quanz, 2012</a>
* NMF: <a href="https://iopscience.iop.org/article/10.3847/1538-4357/aaa1f2/pdf" style="text-decoration:underline;color:slateblue">Ren et al., 2018</a>

#### 2/ Advanced Subtraction techniques ####
* RSM: <a href="https://arxiv.org/pdf/1912.05412.pdf" style="text-decoration:underline;color:slateblue">Dahlqvist et al., 2020</a>
* STIM-map: <a href="(https://arxiv.org/pdf/1810.06895.pdf" style="text-decoration:underline;color:slateblue">Pairet et al., 2019</a>
* LR-map: <a href="https://arxiv.org/pdf/2210.10609.pdf" style="text-decoration:underline;color:slateblue">Daglayan et al., 2022</a>
* LRPT: <a href="https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10096197&casa_token=j0vHesuirR4AAAAA:6ponWBU8HQflUzbI9WRctvl47mGC5CcR6nwWann24tVVf1St0JkcIXuDWvsu0LMLILATemOYkJI&tag=1" style="text-decoration:underline;color:slateblue">Vary et al., 2023</a>
* AMAT: <a href="https://arxiv.org/pdf/2410.06310.pdf" style="text-decoration:underline;color:slateblue">Daglayan et al., 2024</a>

#### 3/ Inverse Problem approaches ####
* ANDROMEDA: <a href="https://arxiv.org/pdf/1508.06406.pdf" style="text-decoration:underline;color:slateblue">Cantalloube et al., 2015</a> (after <a href="http://laurent.mugnier.free.fr/publis/Mugnier-JOSAA-09.pdf" style="text-decoration:underline;color:slateblue">Mugnier et al., 2009</a>)
* FMMF: <a href="https://arxiv.org/pdf/1705.05477.pdf" style="text-decoration:underline;color:slateblue">Ruffio et al., 2017</a> (after <a href="https://iopscience.iop.org/article/10.3847/0004-637X/824/2/117/pdf" style="text-decoration:underline;color:slateblue">Pueyo et al., 2016</a>)
* PACO: <a href="https://www.aanda.org/articles/aa/pdf/2018/10/aa32745-18.pdf" style="text-decoration:underline;color:slateblue">Flasseur et al., 2018</a>
* TRAP: <a href="https://arxiv.org/pdf/2011.12311.pdf" style="text-decoration:underline;color:slateblue">Samland et al., 2021</a>
* SNAP: <a href="https://iopscience.iop.org/article/10.3847/1538-3881/abee7d/pdf" style="text-decoration:underline;color:slateblue">Thompson et al., 2021</a>

#### 4/ Supervised Machine learning ####
* SODDIN: <a href="https://arxiv.org/pdf/1712.02841.pdf" style="text-decoration:underline;color:slateblue">Gomez-Gonzalez et al., 2017</a>
* NA-SODDIN: <a href="https://arxiv.org/pdf/2302.02854.pdf" style="text-decoration:underline;color:slateblue">Cantero et al., 2023</a>
* HSR: <a href="https://arxiv.org/pdf/2204.03439.pdf" style="text-decoration:underline;color:slateblue">Gebhard et al., 2022</a>  
* Deep-PACO: <a href="https://arxiv.org/pdf/2303.02461.pdf" style="text-decoration:underline;color:slateblue">Flasseur et al., 2023</a>

#### 5/ Dedicated to extended structure imaging ####
* NMF: <a href="https://iopscience.iop.org/article/10.3847/1538-4357/aaa1f2/pdf" style="text-decoration:underline;color:slateblue">Ren et al., 2018</a>
* DISK-FM: <a href="https://arxiv.org/pdf/2012.06790.pdf" style="text-decoration:underline;color:slateblue">Mazoyer et al., 2020</a>
* MAYONNAISE: <a href="https://arxiv.org/pdf/2008.05170.pdf" style="text-decoration:underline;color:slateblue">Pairet et al., 2021</a>
* REXPACO: <a href="https://arxiv.org/pdf/2104.09672.pdf" style="text-decoration:underline;color:slateblue">Flasseur et al., 2021</a>
* IADI: <a href="https://www.aanda.org/articles/aa/pdf/2022/12/aa42820-21.pdf" style="text-decoration:underline;color:slateblue">Stapper & Ginksi, 2022</a>
* MUSTARD: <a href="https://arxiv.org/pdf/2309.14827.pdf" style="text-decoration:underline;color:slateblue">Juillard et al., 2023</a>
* DIKL: <a href="https://arxiv.org/pdf/2310.08589.pdf" style="text-decoration:underline;color:slateblue" >Ren et al., 2023</a>

### Detection limits & performance assessement ###
* <i>Confidence level and Sensitivity limits in HCI</i>: <a href="https://browse.arxiv.org/pdf/0709.3548.pdf" style="text-decoration:underline;color:slateblue">Marois et al., 2007</a>
* <i>Fundamental limitations of HCI set by small sample statistics</i>: <a href="https://browse.arxiv.org/pdf/1407.2247.pdf" style="text-decoration:underline;color:slateblue">Mawet et al., 2014</a>
* <i>A New Standard for assessing the performance of HCI</i>: <a href="https://arxiv.org/pdf/1711.01215.pdf" style="text-decoration:underline;color:slateblue">Jensen-Clem et al., 2017</a>
* <i>Robust Detection Limits for HCI in the presence of non-Gaussian noise</i>: <a href="https://arxiv.org/pdf/1711.01215.pdf" style="text-decoration:underline;color:slateblue">Bonse et al., 2023</a>

