---
layout: page
title: Pipelines
---
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">

<center><i>This page lists the various pipelines to process high-contrast images that are available to the community.</i></center>

## Pipelines for HCI surveys
The following pipelines focus on the image reduction (or pre-reduction) stages: calibration, centering, image selection, etc.
* <a href="https://sphere.osug.fr/spip.php?rubrique35&lang=en" style="text-decoration:underline;color:slateblue">HC-DC</a> (formerly SPHERE-DC): homogeneous data reduction dedicated to the VLT/SPHERE instrument. Also includes various ADI-based post-processing techniques from <a href="https://arxiv.org/pdf/1805.04854.pdf" style="text-decoration:underline;color:slateblue">SpeCal</a>. Developed by the SPHERE consortium <a href="https://arxiv.org/pdf/1712.06948.pdf" style="text-decoration:underline;color:slateblue">Delorme et al., 2017</a>.
* <a href="https://docs.planetimager.org/pipeline/" style="text-decoration:underline;color:slateblue">GPI pipeline</a> and <a href="https://arxiv.org/pdf/1801.01902.pdf" style="text-decoration:underline;color:slateblue">GPIES Data Cruncher</a>: mainly developed to process Gemini-S/GPI data, the former focuses on the pre-processing steps, while the latter on the ADI-based post-processing. Developed by the Gemini-S/GPI consortium. 
* GRAPHIC: Full high-contrast image processing pipeline, from pre-reduction to ADI-based post-processing. Developed by the Geneva Observatory: <a href="https://arxiv.org/pdf/1510.04331.pdf" style="text-decoration:underline;color:slateblue">Hagelberg et al., 2015</a>.

## Open-source pipelines for HCI
* <a href="https://github.com/vortex-exoplanet/VIP" style="text-decoration:underline;color:slateblue">VIP</a>: collaborative library of algorithms and general HCI toolkits, <a href="https://arxiv.org/pdf/1705.06184.pdf" style="text-decoration:underline;color:slateblue">Gomez Gonzalez et al., 2017</a>, <a href="https://joss.theoj.org/papers/10.21105/joss.04774" style="text-decoration:underline;color:slateblue">Christiaens et al., 2022</a>.
* <a href="https://github.com/PynPoint/PynPoint" style="text-decoration:underline;color:slateblue">PynPOINT</a>: modular reduction and post-processing pipeline allowing for large HCI data management, <a href="https://arxiv.org/pdf/1811.03336.pdf" style="text-decoration:underline;color:slateblue">Stolker et al., 2019</a>.
* <a href="https://bitbucket.org/pyKLIP/pyklip/src/main/" style="text-decoration:underline;color:slateblue">pyKLIP</a>: collaborative library of algorithms and HCI analysis tools, (Wang et al., 2015).

## Specific algorithms for HCI
* <a href="" style="text-decoration:underline;color:slateblue">RSM</a>[RSM](https://github.com/chdahlqvist/RSMmap): dedicated to point-source detection after applying various ADI-based post-processing techniques, <a href="" style="text-decoration:underline;color:slateblue"></a>[Dalqvist et al., 2019](https://arxiv.org/pdf/1912.05412.pdf).
* <a href="https://github.com/m-samland/trap" style="text-decoration:underline;color:slateblue">TRAP</a>: dedicated to point source detection from pupil tracking data set, <a href="https://arxiv.org/pdf/2011.12311.pdf" style="text-decoration:underline;color:slateblue">Samland et al., 2021</a>
* <a href="https://github.com/timothygebhard/hsr4hci" style="text-decoration:underline;color:slateblue">HSR4HCI</a>: half-sibling regression applied to high-contrast imaging, <a href="https://arxiv.org/pdf/2204.03439.pdf" style="text-decoration:underline;color:slateblue">Gebhard et al., 2022</a>
* <a href="https://github.com/hazandaglayan/likelihoodratiomap" style="text-decoration:underline;color:slateblue">LR maps</a>: computes a likelihood ratio map after a ADI-based PCA subtraction of the image cube, <a href="https://arxiv.org/pdf/2210.10609.pdf" style="text-decoration:underline;color:slateblue">Daglayan et al., 2022</a>
* <a href="https://github.com/bpairet/mayo_hci" style="text-decoration:underline;color:slateblue">MAYONNAISE</a>: dedicated to extended signal imaging from pupil tracking data set, <a href="https://arxiv.org/pdf/2008.05170.pdf" style="text-decoration:underline;color:slateblue">Pairet et al., 2020</a>
* <a href="https://github.com/Sand-jrd/mustard" style="text-decoration:underline;color:slateblue">MUSTARD</a>: dedicated to extended signal imaging from pupil tracking data set, <a href="https://arxiv.org/pdf/2211.03361.pdf" style="text-decoration:underline;color:slateblue">Juillard et al., 2023</a>.
* <a href="https://github.com/markusbonse/applefy" style="text-decoration:underline;color:slateblue">Applefy</a>: pipeline dedicated to produce unbiased detection limits for high-contrast images, <a href="https://arxiv.org/pdf/2303.12030.pdf" style="text-decoration:underline;color:slateblue">Bonse et al., 2023</a>

<br>

<p style='text-align: justify;'>The image below summarizes the three main open-source pipelines (all written in python) that are available to the HCI community, with their respective functionalities highlighted. These three pipelines are highly complementary and are the result of a collabrative work within the HCI community. Please do not hesitate to contact the moderators of the pipelines if you have any suggestion for improvements. </p>
<br>
<p align="center">
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/OpenSourcePipelines.png" />
</p>



