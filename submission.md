---
layout: page
title: Submission instructions
---

The exoplanet imaging data challenge will consist of several stages, each one with its own type of submission and metrics. 

## Stage 1: Deadline 30st of September 2020

For each algorithm, the participants must submit:
* All the detection maps for each data set (9 for the ADI sub-challenge and 10 for the ADI+mSDI sub-challenge).
* One detection threshold for all the maps, which is the threshold from which a detection is claimed (1 value per sub-challenge).
* Optionally, the [FHWM](https://en.wikipedia.org/wiki/Full_width_at_half_maximum) values used for each dataset can be submitted -the FWHM is related to the expected size of a candidate detection - or resolution element - in the detection maps- (9 values for the ADI sub-challenge and 10 values for the ADI+mSDI sub-challenge).

{: .box-note}
**File format:** Every file must be in **.fits** format.

{: .box-note}
**Threshold:** The detection threshold is **one single value for all of the detection maps** submitted. Also the threshold must be a 1x1 array containing the chosen scalar value. If needed, the detection maps can be streched to a common threshold value. We remind that any signal above the threshold value will be considered as a detection.

{: .box-note}
**Submission into a .zip file:** All of the .fits files must be submitted within **a single .zip file**, with a flat structure (e.g. using the command on Mac > ``zip -r -X -j archive_name.zip folder_to_compress``).
One .zip file must be submitted for each sub-challenge (one for ADI and one for ADI+mSDI).

{: .box-note}
**Note:** Each submission must correspond to the results of applying **a single algorithm to all the datasets**. If your algorithm works for both 3D and 4D datasets then you need to make two submissions (to have your score on each scoreboard). Please keep in mind that a partial submission for a given sub-challenge is possible, but that will penalize the metrics computations and your score. 

### Potential error message

**Zipping the file:** The zip file must be flat (i.e. without subfolder structure), please consider checking this aspect.

**Space left on device:** This error occurs when a compute worker is full, usually because it has too many docker images. If this happens, we have to contact CodaLab and clean the repository. Please notify us if you encounter such error (<exoimg.datachallenge@gmail.com>).

{: .box-warning}
**Other error message:** Please contact us if you encounter any issue when submitting your results <exoimg.datachallenge@gmail.com>.

{: .box-note}
**Note:** *Please check out the documentation of the [Astropy Python library](http://docs.astropy.org/en/stable/io/fits/) if you want to know more about saving data in FITS format. Optionally, the [VIP Python library]((https://github.com/vortex-exoplanet/VIP)) contains a wrapper (``vip_hci.fits.write_fits()``) of Astropy for saving Python numpy arrays as FITS files.*


### Example, ADI
For example, for submitting your results of the 1st sub-challenge (ADI), you must gather the following files in *.zip* format (any name can be used): 
* ``detection_threshold.fits`` (scalar value, enclosed in a 1x1 vector-array),
* ``sphere_irdis_detmap_1.fits`` (2d array),
* ``sphere_irdis_detmap_2.fits`` (2d array), 
* ``sphere_irdis_detmap_3.fits`` (2d array), 
* ``nirc2_detmap_1.fits`` (2d array), 
* ``nirc2_detmap_2.fits`` (2d array), 
* ``nirc2_detmap_3.fits`` (2d array), 
* ``lmircam_detmap_1.fits`` (2d array), 
* ``lmircam_detmap_2.fits`` (2d array), 
* ``lmircam_detmap_3.fits`` (2d array), 

Optionally, you can include:
* ``sphere_irdis_fwhm_1.fits`` (scalar value), 
* ``sphere_irdis_fwhm_2.fits`` (scalar value),
* ``sphere_irdis_fwhm_3.fits`` (scalar value),
* ``nirc2_fwhm_1.fits`` (scalar value),
* ``nirc2_fwhm_2.fits`` (scalar value), 
* ``nirc2_fwhm_3.fits`` (scalar value), 
* ``lmircam_fwhm_1.fits`` (scalar value), 
* ``lmircam_fwhm_2.fits`` (scalar value), 
* ``lmircam_fwhm_3.fits`` (scalar value), 


### Example, ADI+mSDI
For example, for submitting your results of the 2nd sub-challenge (ADI+mSDI), you must gather the following files in *.zip* format (any name can be used):

* ``detection_threshold.fits`` (scalar value, enclosed in a 1x1 vector-array),
* ``gpi_detmap_1.fits`` (2d array),
* ``gpi_detmap_2.fits`` (2d array), 
* ``gpi_detmap_3.fits`` (2d array), 
* ``gpi_detmap_4.fits`` (2d array), 
* ``gpi_detmap_5.fits`` (2d array), 
* ``sphere_ifs_detmap_1.fits`` (2d array), 
* ``sphere_ifs_detmap_2.fits`` (2d array), 
* ``sphere_ifs_detmap_3.fits`` (2d array), 
* ``sphere_ifs_detmap_4.fits`` (2d array), 
* ``sphere_ifs_detmap_5.fits`` (2d array). 
And optionally the corresponding FWHM values (similarly to above).


*** 

## Stage 2

This expensive procedure will be performed locally, therefore the source code of the algorithm (implemented on an open source language such as Python or R), an executable file or a Docker image will be required from the participants. Additionally, each participant must submit a single detection threshold (per sub-challenge) to be used during the thresholding and blob counting procedures.

{: .box-warning}
**Important:** this stage of the data challenge will only be conducted if enough participants demonstrate their interest in submitting/sharing their code. 
