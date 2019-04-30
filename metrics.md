---
layout: page
title: Metrics and scoreboard
---

On the table below, you can find a summary of the metrics used for each phase:

|           |Sub-challenge 1: ADI   |Sub-challenge 2: ADI+mSDI
|:--:       |:--:                   |:--:
|**Phase**  |*Metric*               |*Metric*                    
|**1**      |F1, TPR and FDR        |F1, TPR and FDR
|**2**      |ROC space              |ROC space   

**Phase 1**: By thresholding each detection map (using the provided ``value_threshold`` for claiming a detection) and counting the true and false positives, we define several metrics:

* the true positive rate (TPR) also known as sensitivity or recall: ``TPR = TPs / Ninj``,
* the false discovery/detection rate (FDR): ``FDR = FPs / Ndet``,
* the precision or positive predictive value (PPV): ``PPV = TPs / Ndet``,
* the F1-score or harmonic mean of TPR and the precision: ``F1 = 2 * PPV * TPR / (PPV + TPR)``.

where ``TPs`` is the number of true positives/detections, ``FPs`` is the total number of false positives or Type I error, ``Ndet`` is the total number of detections (``TPs + FPs``) and ``Ninj`` is the total number of injections (accros all the datasets of a given sub-challenge). The ``TPs``, ``FPs`` and ``Ndet`` are counted for a given participant/algorithm over all the datasets of a given sub-challenge. This blob counting procedure is implemented in the [Vortex Image Processing package](https://github.com/vortex-exoplanet/VIP), specifically in the ``compute_binary_map`` function found [here](https://github.com/vortex-exoplanet/VIP/blob/master/vip_hci/metrics/roc.py). Read below about the Data Challenge starting kit, which contains detailed explanations about the blob counting procedure. 

Two **scoreboards** will be computed, one for the sub-challenge on ADI data (3D cubes) and one for the sub-challenge on ADI+mSDI cubes (4D cubes). The F1-score serves well our goal of assessing the performance of detection algorithms as binary classifiers, therefore we will use it to rank the entries on each scoreboard.

The contrast (brightness) value for injecting each synthetic companion will be estimated wrt a baseline algorithm. First, the S/N of a population of injected companions will be measured on residual final frames (processed with the baseline algorithm). Then, the interval of fluxes as a function of the separation from the star will be defined by checking which contrast corresponds to S/Ns in given interval (e.g. 1 to 4). This procedure is implemented [here](https://github.com/carlgogo/exoimaging_challenge_extras/blob/master/flux_estimation.py).

**Phase 2**: The community is converging on the usage of receiver operating characteristic (ROC) curves for the performance assessment of high-contrast imaging post-processing algorithms (see [Jensen Clem et al. 2017](https://arxiv.org/abs/1711.01215)). In Fig. 3 is displayed a compilation of some ROC curves from the high-contrast imaging literature. 

| ![data](https://raw.githubusercontent.com/carlgogo/exoimaging_challenge/master/assets/images/challenge_fig3.001.png){:width="600px"} |
|---|
| Figure 3. *ROC curves in the high-contrast imaging literature. Top-left from [Gomez Gonzalez et al. 2016](https://arxiv.org/abs/1602.08381), top-right from [Ruffio et al. 2017](https://arxiv.org/abs/1705.05477), bottom-left from [Gomez Gonzalez et al. 2018](https://arxiv.org/abs/1712.02841) and bottom-right from [Pueyo 2018](https://link.springer.com/referenceworkentry/10.1007/978-3-319-30648-3_10-1)*. |

In this phase, we will focus on the computation of ROC curves for comparing the trade-off of TPR and number of FPs for different algorithms as a function of the detection threshold. The ROC curve computation boils down to repeating the above procedure of injecting companions in the empty challenge datasets, computing detection maps, thresholding them and counting sources, ie. the detection state and the number of false positives for different detection criteria. This expensive procedure will be performed locally using the source code of the algorithm submitted by each participant.


## Codalab

Instead of re-inventing the wheel (designing a framework for implementing the data challenge), we chose to run this challenge on [Codalab](http://codalab.org/), a framework for accelerating reproducible computational research. The participants will enter the competition by creating their own account on Codalab and following the link of the challenge. The scoreboards will be updated automatically after each submission to the Codalab interface. The challenge interface will offer the option to include a short description of the algorithm you used for a each submission, please don't forget to fill in this information (specially if the algorithm uses RDI). Participants may submit as many times as they want. The scoring routines that compute the metrics can be found on the [Data Challenge Extras repository](https://github.com/carlgogo/exoimaging_challenge_extras).



