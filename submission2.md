---
layout: page
title: Submission instructions (phase 2)
---

To submit your result(s), the competition is held on [EvalAI](https://eval.ai/web/challenges/challenge-page/1717/)

The second phase of the Exoplanet Imaging Data Challenge consists in performing *two* tasks, each one will have its own type of submission and metrics.


## Deadline: 25th of June 2022
For each submission (one submission per algorithm), the participants must provide one zip file per task. <br>
In each zip file, one [MEF](https://docs.astropy.org/en/stable/generated/examples/io/create-mef.html) (multi-extension *.fits* file) file per data set (so a total of 8 MEF fils must be included in the zip file).

### Task 1 (astrometry)
The participants must provide one `.mef` file containing per target: <br>
(i) the estimated position from the star (in other words, the star is located at the coordinates [0,0]), in pixels;
(ii) [optional] the 1-sigma uncertainties on the estimated position;
(iii) [optional] the corresponding posterior distribution used to estimate the position and its uncertainties.

If the posterior distribution (iii) is not provided, we will assume that the posterior follows a normal distribution. 

One .mef file contains the information of all the injections (2 to 3) of a given data set.

{: .box-note}
**Task 1: filename:** Please call all your files following this naming convention **astrometry_instID.mef**, with **inst** the instrument in lower case (e.g. `sphere` or `gpi`) and **ID** the dataset index (e.g. `1`, `2`, `3` or `4`).



### Task 2 (spectrophotometry)
The participants must provide one `.mef` file containing per target: <br>
(i) the estimated contrast wrt the star;
(ii) [optional] the 1-sigma uncertainties on the estimated contrast;
(iii) [optional] the corresponding posterior distribution used to estimate the contrast and its uncertainties.

If the posterior distribution (iii) is not provided, we will assume that the posterior follows a normal distribution. 

One .mef file contains the information of all the injections (2 to 3) of a given data set.

{: .box-note}
**Task 2: filename:** Please call all your files following this naming convention **photometry_instID.mef**, with **inst** the instrument in lower case (e.g. `sphere` or `gpi`) and **ID** the dataset index (e.g. `1`, `2`, `3` or `4`).


### Example of submission files

#### Task 1:
For example, for submitting your results of the 1st task (astrometry), you must gather the following eight files in *.zip* format (any name can be used for the *.zip* file - please do not use any subfolder!): 
* ``astrometry_gpi1.mef``,
* ``astrometry_gpi2.mef``,
* ``astrometry_gpi3.mef``, 
* ``astrometry_gpi4.mef``, 
* ``astrometry_sphere1.mef``,
* ``astrometry_sphere2.mef``,
* ``astrometry_sphere3.mef``,
* ``astrometry_sphere4.mef``.<br>
Each file must *at least* contain the 1st dimension with the position values in x and y of each candidate, following the order given by the `first_guess_astrometry_instID.fits` file provided with the data sets. 

#### Task 2:
For example, for submitting your results of the 2nd task (photometry), you must gather the following eight files in *.zip* format (any name can be used for the *.zip* file - please do not use any subfolder!): 
* ``photometry_gpi1.mef``,
* ``photometry_gpi2.mef``,
* ``photometry_gpi3.mef``, 
* ``photometry_gpi4.mef``, 
* ``photometry_sphere1.mef``,
* ``photometry_sphere2.mef``,
* ``photometry_sphere3.mef``,
* ``photometry_sphere4.mef``.<br>
Each file must *at least* contain the 1st dimension with the contrast estimates along each spectral channel, for each candidate, following the order given by the `first_guess_astrometry_instID.fits` file provided with the data sets. 

{: .box-note}
**File format:** Every file must be in **.mef** format. In the [EIDC2 Github repository](https://github.com/exoplanet-imaging-challenge/phase2/tree/main/eidc2), you will find functions and a dedicated jupyter notebook to put your results into a .mef file.

{: .box-note}
**Submission into a .zip file:** All of the 8 .mef files must be submitted within **a single .zip file**, with a flat structure (without subfolder structure, e.g. using the command on Mac > ``zip -r -X -j archive_name.zip folder_to_compress``).
One .zip file must be submitted for each task (one for **astrometry** and one for **spectrophotometry**).

{: .box-note}
**Note:** Each submission must correspond to the results of applying **a single algorithm to all the datasets**. You can therefore make several submissions, even if only one will show up on the competition webpage leaderboard, all of the submissions will be processed off-line.

*** 

### Potential error message

{: .box-warning}
**Other error message:** Please contact us if you encounter any issue when submitting your results <exoimg.datachallenge@gmail.com>.

*** 
