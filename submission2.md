---
layout: page
title: Submission instructions 
---

<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
<center><div class="w3-text-red"><h2>Deadline for the <em>Exoplanet Imaging Data Challenge</em> Phase 2: <br> 31st of May 2024</h2></div></center>

{: .box-note}
**EvalAI platform:** The results of the Phase 2 (characterization) of the <em>Exoplanet Imaging Data Challenge</em> must be submitted on <a href="https://eval.ai/web/challenges/challenge-page/1717/" style="text-decoration:underline;color:slateblue">EvalAI</a>. 


The second phase of the <em>Exoplanet Imaging Data Challenge</em> is focused on the characterization of point source: it consists in performing *two* tasks, each one will have its own type of submission and metrics.
 * For each submission (one submission per algorithm), the participant must provide **one zip file per task**.
 * In each zip file, <strong>one [MEF](https://docs.astropy.org/en/stable/generated/examples/io/create-mef.html) (multi-extension *.fits* file) file per data set</strong>.
 * <div class="w3-text-red"> In total, the submission consists of <strong>two <em>.zip</em> files</strong>, each consisting of <strong>eight <em>MEF .fits</em> files</strong>.</div>

### Task 1 (astrometry)
For each target star, the participant must provide one MEF `.fits` file containing: <br>
(i) the estimated position from the star (in other words, the star is located at the coordinates [0,0]), in pixels;<br>
(ii) [optional] the 1-sigma uncertainties on the estimated position;<br>
(iii) [optional] the corresponding posterior distribution used to estimate the position and its uncertainties.<br>
If the posterior distribution (iii) is not provided, we will assume that the posterior follows a normal distribution. 

<strong>Note:</strong> One MEF .fits file contains the information of all the injections (2 to 3) of a given data set.

{: .box-note}
**Task 1: filename:** Please call all your files following this naming convention **astrometry_instID.fits**, with **inst** the instrument in lower case (e.g. `sphere` or `gpi`) and **ID** the dataset index (e.g. `1`, `2`, `3` or `4`).



### Task 2 (spectrophotometry)
For each target star, the participant must provide one MEF `.fits` file containing: <br>
(i) the estimated contrast wrt the star; <br>
(ii) [optional] the 1-sigma uncertainties on the estimated contrast; <br>
(iii) [optional] the corresponding posterior distribution used to estimate the contrast and its uncertainties. <br>
If the posterior distribution (iii) is not provided, we will assume that the posterior follows a normal distribution. 

<strong>Note:</strong> One MEF .fits file contains the information of all the injections (2 to 3) of a given data set.

{: .box-note}
**Task 2: filename:** Please call all your files following this naming convention **photometry_instID.fits**, with **inst** the instrument in lower case (e.g. `sphere` or `gpi`) and **ID** the dataset index (e.g. `1`, `2`, `3` or `4`).


### Example of submission files

#### Task 1:
For example, for submitting your results of the 1st task (astrometry), you must gather the following eight files in *.zip* format (any name can be used for the *.zip* file - please do not use any subfolder!): 
* ``astrometry_gpi1.fits``,
* ``astrometry_gpi2.fits``,
* ``astrometry_gpi3.fits``, 
* ``astrometry_gpi4.fits``, 
* ``astrometry_sphere1.fits``,
* ``astrometry_sphere2.fits``,
* ``astrometry_sphere3.fits``,
* ``astrometry_sphere4.fits``.

Each file must *at least* contain the 1st extension with the position values in x and y of each candidate, following the order given by the `first_guess_astrometry_instID.fits` file provided with the data sets (and same numpy array format - e.g. 3 rows (ny) of 2 columns (nx) for the xy coordinates of 3 planets). 

#### Task 2:
For example, for submitting your results of the 2nd task (photometry), you must gather the following eight files in *.zip* format (any name can be used for the *.zip* file - please do not use any subfolder!): 
* ``photometry_gpi1.fits``,
* ``photometry_gpi2.fits``,
* ``photometry_gpi3.fits``, 
* ``photometry_gpi4.fits``, 
* ``photometry_sphere1.fits``,
* ``photometry_sphere2.fits``,
* ``photometry_sphere3.fits``,
* ``photometry_sphere4.fits``.

Each file must *at least* contain the 1st dimension with the contrast estimates along each spectral channel, for each candidate, following the order given by the `first_guess_astrometry_instID.fits` file provided with the data sets (and same numpy array format - e.g. 3 rows (ny) of 39 columns (nx) for the spectra of 3 planets). 

{: .box-note}
**File format:** Every file must be in MEF **.fits** format. In the [EIDC2 Github repository](https://github.com/exoplanet-imaging-challenge/phase2/blob/main/tutorials/tutorial_creation_MEF.ipynb), you will find a short tutorial, as a jupyter notebook, to put your results into a MEF .fits file.

{: .box-note}
**Submission into a .zip file:** All of the 8 MEF .fits files must be submitted within **a single .zip file**, with a flat structure (without subfolder structure, e.g. using the command on Mac > ``zip -r -X -j archive_name.zip folder_to_compress``).
One .zip file must be submitted for each task (one for **astrometry** and one for **spectrophotometry**).

{: .box-note}
**Note:** Each submission must correspond to the results of applying **a single algorithm to all the datasets**. You can therefore make several submissions, even if only one will show up on the competition webpage leaderboard, all of the submissions will be processed off-line.

{: .box-warning}
**IMPORTANT:** If you really cannot detect the companion, despite the first guess provided, please put `-1` as an entry (for both estimated value and its uncertainties).


*** 

### Evaluation metrics

For the leaderboard display, the EIDC team has decided to use simple metrics: the metrics consist in mean normalized distances between the estimated value submitted by the participant and the ground truth used for injection. The distance is based on the L2 and L1 norms for astrometry and spectrophotometry, respectively.

**Task 1 (astrometry)**

For each injected companion, we compute the L2-norm distance (i.e. the Euclidian distance) between the estimated position value (xy_est) and the corresponding ground-truth value (xy_gt): <br>

`dist_astro = sqrt| | x_est - x_gt |^2 + | y_est - y_gt |^2 |`

We then average all the distances *dist_astro* obtained for each of the 21 exoplanet injections. 

**Task 2 (spectrophometry)**

For each injected companion, we compute the L1-norm distance between the estimated contrast value (cont_est) and the ground-truth value (cont_gt), for each wavelength (lambda), and normalize it with the ground truth contrast (to not penalize smaller true contrasts in the averaged score): <br>

`dist_photo = sum| | cont_est_lambda - cont_gt_lambda | / cont_gt_lambda |`, (sum over all the wavelength)

We then average all the distances *dist_photo* obtained for each of the 21 exoplanet injections. 

<br>
<br>

Further analysis of the results will be conducted off-line by our team. The metric used for the phase 2 of the <em>Exoplanet Imaging Data Challenge</em> are published in the proceeding accessible [here](https://arxiv.org/pdf/2209.08120.pdf). <br> 

The final comparison results will be published an [SPIE Astronomical telescopes + instrumentation](https://spie.org/conferences-and-exhibitions/astronomical-telescopes-and-instrumentation) conference proceeding in summer 2024.  


*** 

### Potential error message

{: .box-warning}
**Other error message:** Please contact us if you encounter any issue when submitting your results <exoimg.datachallenge@gmail.com>.

*** 

### EvalAI team:
* Anthony Cioppa (ULiège, Belgium): putting the challenge and EvalAI in place, tests.
* Carles Cantero (ULiège, Belgium): writing the backend for the leaderboard, tests.
* Faustine Cantalloube (LAM, France): coordination, description and tests.

