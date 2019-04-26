---
layout: page
title: Metrics and scoreboard
---

This challenge is focusing on the task of exoplanet direct detection. In order to measure the detection capability of different algorithms, we will rely on the injection of fake companions and the computation of several relevant metrics, such as the true positive rate or the number of false positives. 

## Phases

This challenge will consist of two consecutive phases (while the sub-challenges run in parallel), each one with its own type of submission and metrics. On the table below, you can find a summary of the metrics used for each phase:

|           |Sub-challenge 1: ADI   |Sub-challenge 2: ADI+mSDI
|:--:       |:--:                   |:--:
|**Phase**  |*Metric*               |*Metric*                    
|**1**      |F1, TPR and FDR        |F1, TPR and FDR
|**2**      |ROC space              |ROC space   

**Phase 1**: In the first phase, the expected output from an algorithm, i.e. the submission from a given participant, consists of a list of detection maps (nine for the first sub-challenge and ten for the second), a detection threshold (the accepted threshold at which a detection is claimed) and the FHWM values for each dataset. For example, for generating a submission file to the second sub-challenge (ADI+mSDI) you must include the following files: gpi_detmap_1.fits, gpi_detmap_2.fits, gpi_detmap_3.fits, gpi_detmap_4.fits, gpi_detmap_5.fits, sphere_ifs_detmap_1, sphere_ifs_detmap_2, sphere_ifs_detmap_3, sphere_ifs_detmap_4, sphere_ifs_detmap_5, gpi_fwhm_1.fits, gpi_fwhm_2.fits, gpi_fwhm_3.fits, gpi_fwhm_4.fits, gpi_fwhm_5.fits, sphere_ifs_fwhm_1, sphere_ifs_fwhm_2, sphere_ifs_fwhm_3, sphere_ifs_fwhm_4, sphere_ifs_fwhm_5, detection_threshold.fits. 

By thresholding each detection map and counting the true and false positives, we define several metrics:

* the true positive rate (TPR) also known as sensitivity or recall: ``TPR = TPs / Ninj``,
* the false discovery/detection rate (FDR): ``FDR = FPs / Ndet``,
* the precision or positive predictive value (PPV): ``PPV = TPs / Ndet``,
* the F1-score or harmonic mean of TPR and the precision: ``F1 = 2 * PPV * TPR / (PPV + TPR)``.

where ``TPs`` is the number of true positives/detections, ``FPs`` is the total number of false positives or Type I error, ``Ndet`` is the total number of detections (``TPs + FPs``) and ``Ninj`` is the total number of injections (accros all the datasets of a given sub-challenge). The ``TPs``, ``FPs`` and ``Ndet`` are counted for a given participant/algorithm over all the datasets of a given sub-challenge. This blob counting procedure is implemented in the [Vortex Image Processing package](https://github.com/vortex-exoplanet/VIP), specifically in the ``compute_binary_map`` function found [here](https://github.com/vortex-exoplanet/VIP/blob/master/vip_hci/metrics/roc.py). Read below about the Data Challenge starting kit, which contains detailed explanations about the blob counting procedure. 

Two **scoreboards** will be computed, one for the sub-challenge on ADI data (3D cubes) and one for the sub-challenge on ADI+mSDI cubes (4D cubes). The F1-score serves well our goal of assessing the performance of detection algorithms as binary classifiers, therefore we will use it to rank the entries on each scoreboard.

> Note: Each submission must correspond to the results of applying the same algorithm to all the datasets. If your algorithm works for both 3D and 4D datasets then you need to make two submissions (to have your score on each scoreboard).

The contrast (brightness) value for injecting each synthetic companion will be estimated wrt a baseline algorithm. First, the S/N of a population of injected companions will be measured on residual final frames (processed with the baseline algorithm). Then, the interval of fluxes as a function of the separation from the star will be defined by checking which contrast corresponds to S/Ns in given interval (e.g. 1 to 4). This procedure is implemented [here](https://github.com/carlgogo/exoimaging_challenge_extras/blob/master/flux_estimation.py).

**Phase 2**: The community is converging on the usage of receiver operating characteristic (ROC) curves for the performance assessment of high-contrast imaging post-processing algorithms (see [Jensen Clem et al. 2017](https://arxiv.org/abs/1711.01215)). In Fig. 3 is displayed a compilation of some ROC curves from the high-contrast imaging literature. 

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig3.001.png){:width="600px"} |
|---|
| Figure 3. *ROC curves in the high-contrast imaging literature. Top-left from [Gomez Gonzalez et al. 2016](https://arxiv.org/abs/1602.08381), top-right from [Ruffio et al. 2017](https://arxiv.org/abs/1705.05477), bottom-left from [Gomez Gonzalez et al. 2018](https://arxiv.org/abs/1712.02841) and bottom-right from [Pueyo 2018](https://link.springer.com/referenceworkentry/10.1007/978-3-319-30648-3_10-1)*. |

In this phase, we will focus on the computation of ROC curves for comparing the trade-off of TPR and number of FPs for different algorithms as a function of the detection threshold. The ROC curve computation boils down to repeating the above procedure of injecting companions in the empty challenge datasets, computing detection maps, thresholding them and counting sources, ie. the detection state and the number of false positives for different detection criteria. This expensive procedure will be performed locally, therefore the source code of the algorithm (implemented on an open source language such as Python or R), an executable file or a Docker image will be required from the participants. Additionally, the participant must submit the detection thresholds for the thresholding and blob counting procedure.

> Important: only the participants who agree to submit their code will be included in the second phase of this data challenge.   

## Starting kit

The implementations of the planet injection, source counting and ROC curve generation algorithms are included in the open source [Vortex Image Processing package](https://github.com/vortex-exoplanet/VIP) for the sake of transparency and fairness. Other code related to the data challenge is available at the [Data Challenge Extras repository](https://github.com/carlgogo/exoimaging_challenge_extras). Here we also share a Python script (``DC1_codalab_starting_kit.py``) that illustrates how to create the outputs to be submitted for participating in the data challenge.
 
The extras repository also contains a data challenge starting kit, in the form of a Jupyter notebook (``DC1_starting_kit.ipynb``), which explains in detail the source counting procedure on detection maps (to get the true and false positives). The starting kit can also be executed on the cloud thanks to [Binder](https://mybinder.org/v2/gh/carlgogo/exoimaging_challenge_extras/master). This implementation shall serve as a reference for future studies on image processing algorithms for direct imaging of exoplanets.


## Codalab

Instead of re-inventing the wheel (designing a framework for implementing the data challenge), we chose to run this challenge on [Codalab](http://codalab.org/), a framework for accelerating reproducible computational research. The participants will enter the competition by creating their own account on Codalab and following the link of the challenge. The scoreboards will be updated automatically after each submission to the Codalab interface. The challenge interface will offer the option to include a short description of the algorithm you used for a each submission, please don't forget to fill in this information (specially if the algorithm uses RDI). Participants may submit as many times as they want. The scoring routines that compute the metrics can be found on the [Data Challenge Extras repository](https://github.com/carlgogo/exoimaging_challenge_extras).



