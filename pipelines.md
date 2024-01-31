---
layout: page
title: Pipelines
---

<i>This page lists the various pipelines to process high-contrast images that are available to the community.</i>

## Pipelines for HCI surveys
The following pipelines are focused on the basic reduction steps (or pre-reduction) of the images.: calibration, centering, frame selection etc. 
* [HC-DC](https://sphere.osug.fr/spip.php?rubrique35&lang=en) (formerly SPHERE-DC): homogeneous data reduction for VLT/SPHERE data. Also includes various ADI-based post-processing [SpeCal](https://arxiv.org/pdf/1805.04854.pdf). Developed by the SPHERE consortium [Delorme et al., 2017](https://arxiv.org/pdf/1712.06948.pdf).
* [GPI pipeline](https://docs.planetimager.org/pipeline/) and [GPIES Data Cruncher]([GPIES Data Cruncher ](https://arxiv.org/pdf/1801.01902.pdf): mainly developd to process Gemini-S/GPI data, the former focuses on the pre-processing steps, while the latter the ADI-based post-processing. Developed by the Gemini-S/GPI consortium. 
* GRAPHIC: Full high-contrast image processing pipeline, from pre-reduction to ADI-based post-processing. Developed by the Geneva Observatory: [Hagelberg et al., 2015](https://arxiv.org/pdf/1510.04331.pdf)

## General pipelines for HCI
* [VIP](https://github.com/vortex-exoplanet/VIP): library of various post-processing techniques including many tools and tutorials, [Gomez Gonzalez et al., 2017](https://github.com/vortex-exoplanet/VIP), [Christiaens et al., 2022](https://joss.theoj.org/papers/10.21105/joss.04774) and references therein.
* [PynPOINT](https://github.com/PynPoint/PynPoint): modular reduction and post-processing pipeline for large HCI data managements, [Stolker et al., 2019](https://arxiv.org/pdf/1811.03336.pdf).
* [pyKLIP](https://bitbucket.org/pyKLIP/pyklip/src/main/): collaborative library of pipeline, including various forward modeling techniques, (Wang et al., 2025)[Wang, J. J., Ruffio, J.-B., De Rosa, R. J., et al. 2015, Astrophysics Source Code Library, ascl:1506.001]

## Specific algorithms for HCI
* [RSM](https://github.com/chdahlqvist/RSMmap): dedicated to point-source detection after applying various ADi-based post-processing techniques, [Dalqvist et al., 2019](https://arxiv.org/pdf/1912.05412.pdf).
* [TRAP](https://github.com/m-samland/trap): dedicated to point source detection from pupil tracking data set, [Samland et al., 2021](https://arxiv.org/pdf/2011.12311.pdf)
* [HSR4HCI](https://github.com/timothygebhard/hsr4hci): half-sibling regretion applied to high-contrast imaging, [Gebhard et al., 2022](https://arxiv.org/pdf/2204.03439.pdf)
* [LR maps](https://github.com/hazandaglayan/likelihoodratiomap): computes a likelihood ratio map after a ADI-based PCA subtraction of the image cube, [Daglayan et al., 2022](https://arxiv.org/pdf/2210.10609.pdf)
* [MAYONNAISE](https://github.com/bpairet/mayo_hci): dedicated to extended signal imaging from pupil tracking data set, [Pairet et al., 2020](https://arxiv.org/pdf/2008.05170.pdf)
* [MUSTARD](https://github.com/Sand-jrd/mustard): dedicated to extended signal imaging from pupil tracking data set, [Juillard et al., 2023](https://arxiv.org/pdf/2211.03361.pdf).
* [Applefy](https://github.com/markusbonse/applefy): pipeline dedicated to produce unbiased detection limits for high-contrast images, [Bonse et al., 2023](https://arxiv.org/pdf/2303.12030.pdf)
