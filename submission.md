---
layout: page
title: Submission instructions
---

This challenge will consist of two consecutive phases (while the sub-challenges run in parallel), each one with its own type of submission and metrics. 

**Phase 1**: In the first phase, the expected output from an algorithm, i.e. the submission from a given participant, consists of a list of detection maps (nine for the first sub-challenge and ten for the second), a detection threshold (the accepted threshold at which a detection is claimed) and the [FHWM](https://en.wikipedia.org/wiki/Full_width_at_half_maximum) values used for each dataset (related to the expected size of detected blobs on the detection maps). Every file must be in FITS format, please check out the documentation of the [Astropy Python library](http://docs.astropy.org/en/stable/io/fits/) if you want to know more about saving data in FITS format. Optionally, the [VIP Python library]((https://github.com/vortex-exoplanet/VIP)) contains a wrapper (``vip_hci.fits.write_fits()``) of Astropy for saving Python numpy arrays as FITS files.

For example, for generating a submission file to the second sub-challenge (ADI+mSDI) you  must save the following files in *zip* format: 

* ``gpi_detmap_1.fits`` (2d array),
* ``gpi_detmap_2.fits`` (2d array), 
* ``gpi_detmap_3.fits`` (2d array), 
* ``gpi_detmap_4.fits`` (2d array), 
* ``gpi_detmap_5.fits`` (2d array), 
* ``gpi_fwhm_1.fits`` (scalar value), 
* ``gpi_fwhm_2.fits`` (scalar value),
* ``gpi_fwhm_3.fits`` (scalar value),
* ``gpi_fwhm_4.fits`` (scalar value),
* ``gpi_fwhm_5.fits`` (scalar value), 
* ``sphere_ifs_detmap_1.fits`` (2d array), 
* ``sphere_ifs_detmap_2.fits`` (2d array), 
* ``sphere_ifs_detmap_3.fits`` (2d array), 
* ``sphere_ifs_detmap_4.fits`` (2d array), 
* ``sphere_ifs_detmap_5.fits`` (2d array), 
* ``sphere_ifs_fwhm_1.fits`` (scalar value), 
* ``sphere_ifs_fwhm_2.fits`` (scalar value), 
* ``sphere_ifs_fwhm_3.fits`` (scalar value), 
* ``sphere_ifs_fwhm_4.fits`` (scalar value), 
* ``sphere_ifs_fwhm_5.fits`` (scalar value), 
* ``detection_threshold.fits`` (scalar value). 

{: .box-note}
**Note:** Each submission must correspond to the results of applying **a single algorithm to all the datasets**. If your algorithm works for both 3D and 4D datasets then you need to make two submissions (to have your score on each scoreboard). Please keep in mind that a partial submission for a given sub-challenge is possible, but that will penalize the metrics computations and your score. 

**Phase 2**: This expensive procedure will be performed locally, therefore the source code of the algorithm (implemented on an open source language such as Python or R), an executable file or a Docker image will be required from the participants. Additionally, the participant must submit the detection thresholds for the thresholding and blob counting procedure.

{: .box-warning}
**Important:** only the participants who agree to submit their code will be included in the second phase of this data challenge.  



