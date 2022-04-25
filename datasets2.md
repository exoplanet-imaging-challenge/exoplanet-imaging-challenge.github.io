---
layout: page
title: Datasets phase 2
---


{: .box-note}
**Zenodo repository:** The repository containing the 8 challenge datasets and the 1 training dataset can be found [here](https://zenodo.org/record/3361544). 


### Instruments 
Data set from two high-contrast spectro-imagers of the latest generation are used:

* VLT/SPHERE-IFS, [Beuzit et al., 2019](https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...631A.155B/PUB_PDF)
* Gemini-S/GPI, [Macintosh et al., 2008](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/7015/1/The-Gemini-Planet-Imager--from-science-to-design-to/10.1117/12.788083.full) 

There are 4 dataset from SPHERE-IFS and 4 dataset from GPI.<br> 
The training dataset is from SPHERE-IFS.

The 8 target stars contain no known companion candidate. In order to mitigate the impact of a potential astrophysical signal (planet or disk), we performed the injection using the opposite parallactic angle. This trick preserves the temporal correlation of the starlight residuals, but makes that the signals are no-longer co-aligned at the end of the process. 

Each data set of a given instrument is taken under various observing conditions, from very favorable to bad, with bright or faint targets (see details below). 

The data have been pre-reduced by the official IFS ([SPHERE-DC](https://ui.adsabs.harvard.edu/abs/2017sf2a.conf..347D/abstract)) and GPI pipelines ([GPIES Data Cruncher](https://ui.adsabs.harvard.edu/abs/2017SPIE10400E..26W/abstract)). Our team homogeneized the data (centering, cropping etc.) and injected between 2 and 3 synthetic planetary signals in the coronagraphic image cubes (see details below).


### Provided data content
The 8 data set of the data challenge contain the following files (in *.fits* format):
 * ``image_cube_instID.fits``: Spectral temporal coronagraphic image cube (4D array);
 * ``parallactic_angles_instID.fits``: Vector of parallactic angles and airmass variation (2D vector array);
 * ``psf_cube_instID.fits``: Vector of the central wavelength of each channel of the spectro-imager (1D vector array);
 * ``psf_cube_instID.fits``: Spectral non-coronagraphic image cube of the star (3D array);
 * ``first_guess_astrometry_instID.fits``: First guess position of the injected signals (between 2 and 3 vectors).
 where **inst** is either `sphere` or `gpi` (lower case) and **ID** the index of the data set between 0 and 4.

The images (coronagraphic and non-coronagraphics) are withing a frame with an odd number of pixels, centered on the central pixel. If Npix is the dimension of the frame, it means that the center is located at (Npix-1)/2.

The first guess gives an estimation of the location of the injected planetary signal within a radius of 5 FWHM (in case of low SNR). The values are given as the distance (in pixels) from the star (the center of the frame) in cartesian coordinates (x,y).

The airmass is given as an information, it is not mandatory to take it into account within the algorithm used.


### Observing conditions


### Injection procedure



No other effect is taken into account for the injection: no other flux temporal variation (intrinsic nor instrumental), no smearing at large separation due to the exposure time, no temporal binning, no off-centering of the star behind the coronagraph during the exposure, no diffraction effect due to the coronagraph at close separation etc. 

{: .box-note}
**Training data set:** . 

*** 

### Data and pre-reduction team:
* J.-B. Ruffio (Caltech, USA), on behalf of *GPIES collaboration*: Gemini-S/GPI data
* P. Delorme (IPAG, France), on behalf of the *SPHERE Data Center team*: VLT/SPHERE-IFS data

### Injection of planetary signals, homoegenization and test team:
* Faustine Cantalloube (LAM, France)
* Carles Cantero (ULiège, Belgium)
* Valentin Christiaens (ULiège, Belgium)
