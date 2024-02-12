---
layout: page
title: Submission instructions
---
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">

<center><div class="w3-text-red"><h2>Deadline for the <em>Exoplanet Imaging Data Challenge</em> Phase 1: <br> 30th of September 2020</h2></div></center>


{: .box-note}
**CodaLab platform:** The results of the Phase 1 (detection) of the <em>Exoplanet Imaging Data Challenge</em> must be submitted on <a href="https://competitions.codalab.org/competitions/20693" style="text-decoration:underline;color:slateblue">CodaLab</a>. 


The first phase of the <em>Exoplanet Imaging Data Challenge</em> is focused on the detection of point source.<br>
For each algorithm, the participants must submit:<br>
* All the detection maps for each data set (9 for the ADI sub-challenge and 10 for the ADI+mSDI sub-challenge).
* One detection threshold for all the maps, which is the threshold from which a detection is claimed (1 value per sub-challenge).
* Optionally, the <a href="https://en.wikipedia.org/wiki/Full_width_at_half_maximum" style="text-decoration:underline;color:slateblue">FHWM</a> values used for each dataset can be submitted -the FWHM is related to the expected size of a candidate detection - or resolution element - in the detection maps- (9 values for the ADI sub-challenge and 10 values for the ADI+mSDI sub-challenge).

{: .box-note}
**File format:** Every file must be in **.fits** format.

{: .box-note}
**Threshold:** The detection threshold is **one single value for all of the detection maps** submitted. Also the threshold must be a 1x1 array containing the chosen scalar value. If needed, the detection maps can be streched to a common threshold value. We remind that any signal above the threshold value will be considered as a detection.

{: .box-note}
**Submission into a .zip file:** All of the .fits files must be submitted within **a single .zip file**, with a flat structure (e.g. using the command on Mac > ``zip -r -X -j archive_name.zip folder_to_compress``).
One .zip file must be submitted for each sub-challenge (one for ADI and one for ADI+mSDI).

{: .box-note}
**Note:** Each submission must correspond to the results of applying **a single algorithm to all the datasets**. If your algorithm works for both 3D and 4D datasets then you need to make two submissions (to have your score on each scoreboard). Please keep in mind that a partial submission for a given sub-challenge is possible, but that will penalize the metrics computations and your score. You can make several submissions, even if only one will show up on the competition webpage leaderboard, all of the submissions will be processed off-line.

*** 

### Potential error message

**Zipping the file:** The zip file must be flat (i.e. without subfolder structure), please consider checking this aspect.

**Space left on device:** This error occurs when a compute worker is full, usually because it has too many docker images. If this happens, we have to contact CodaLab and clean the repository. Please notify us if you encounter such error <a href="mailto:exoimg.datachallenge@gmail.com" style="text-decoration:underline;color:slateblue">exoimg.datachallenge@gmail.com</a>.

{: .box-warning}
**Other error message:** Please contact us if you encounter any issue when submitting your results <a href="mailto:exoimg.datachallenge@gmail.com" style="text-decoration:underline;color:slateblue">exoimg.datachallenge@gmail.com</a>.

{: .box-note}
**Note:** *Please check out the documentation of the <a href="http://docs.astropy.org/en/stable/io/fits/" style="text-decoration:underline;color:slateblue">Astropy Python library</a> if you want to know more about saving data in '.fits' file format. Optionally, the  <a href="https://github.com/vortex-exoplanet/VIP" style="text-decoration:underline;color:slateblue">VIP Python library</a> contains a wrapper (``vip_hci.fits.write_fits()``) of Astropy for saving Python numpy arrays as FITS files.*

*** 

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
