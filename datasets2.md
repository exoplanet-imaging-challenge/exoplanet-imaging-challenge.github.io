---
layout: page
title: Datasets phase 2
---

<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">

{: .box-note}
**Zenodo repository:** The repository containing the 8 challenge datasets and the 1 training dataset can be found [here](https://zenodo.org/record/6902628). 

### Instruments 
The provided challenge datasets come from two high-contrast spectro-imagers of the latest generation:

* VLT/SPHERE-IFS, [Beuzit et al., 2019](https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...631A.155B/PUB_PDF)
* Gemini-S/GPI, [Macintosh et al., 2008](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/7015/1/The-Gemini-Planet-Imager--from-science-to-design-to/10.1117/12.788083.full) 

There are **4** datasets from SPHERE-IFS and **4** datasets from GPI. The training dataset is from SPHERE-IFS.

<p style='text-align: justify;'>The data have been pre-reduced by the official IFS <a href="https://ui.adsabs.harvard.edu/abs/2017sf2a.conf..347D/abstract">HC-DC</a> and GPI pipelines <a href="[https://ui.adsabs.harvard.edu/abs/2017sf2a.conf..347D/abstract](https://ui.adsabs.harvard.edu/abs/2017SPIE10400E..26W/abstract)">GPIES Data Cruncher</a>. Our team homogenized the data (centering, cropping etc.) and injected between 2 and 3 synthetic planetary signals in the coronagraphic image cubes (see details below).</p>

### Provided data content
The 8 data set of the data challenge contain the following files (in *.fits* format):
 * ``image_cube_instID.fits``: Spectral temporal coronagraphic image cube (4D array);
 * ``parallactic_angles_instID.fits``: Vector of parallactic angles and airmass variation (2D vector array);
 * ``wavelength_vect_instID.fits``: Vector of the central wavelength of each channel of the spectro-imager (1D vector array);
 * ``psf_cube_instID.fits``: Spectral non-coronagraphic image cube of the star (3D array);
 * ``first_guess_astrometry_instID.fits``: First guess position of the injected signals (between 2 and 3 vectors); <br>
 where **inst** is either `sphere` or `gpi` (lower case) and **ID** the index of the data set between 0 and 4.

Note that the airmass is given as an information, it is not mandatory to take it into account within the algorithm used.
 
<p style='text-align: justify;'>
<strong>Image center:</strong> The images (coronagraphic and non-coronagraphics) are within a frame with an odd number of pixels, centered on the central pixel. If Npix is the dimension of the frame, it means that the center is located at (Npix-1)/2.</p>

<p style='text-align: justify;'>
<strong>Astrometry first guess:</strong> The first guess gives an estimation of the location of the injected planetary signal within a radius of 5 pixels (in case of low SNR). The values are given as the distance (in pixels) from the star (the center of the frame) in cartesian coordinates (x,y). This first guess is given because the task here is not to assess the detection capabilities but the astrometry estimation accuracy. Therefore, one may attempt to extract the astrometry even if their algorithm shows the signal with a very low signal-to-noise ratio.</p>


### Observing conditions
<p style='text-align: justify;'>The datasets are taken under various observing conditions, from very favorable to bad, with bright or faint targets. 
The table below summarizes the main information about the data set and the observing conditions:</p>

<iframe 
src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSAXn_qb9ul2Mt458MEUoQfPyg6qyR_ctGkOYjTo73v7YONXpWDLErtDLckinR5E6LVXvWORa0OsBcH/pubhtml?gid=1302786282&single=false"
style="width:100%; height:290px;"></iframe>


### Injection procedure
<p style='text-align: justify;'> The 8 target stars contain no known companion candidate. In order to mitigate the impact of a potential astrophysical signal (planet or disk), we performed the injection using the opposite parallactic angles. This trick preserves the temporal correlation of the starlight residuals, but any pre-existing circumstellar signal is no longer co-aligned after derotation. The opposite parallactic angles are the ones used for the injections and provided with each downloadable dataset.</p>

<p style='text-align: justify;'>In each data set we observed from 2 to 3 synthetic exoplanet (point source) signals. Within the SPHERE-IFS images we injected 11 exoplanet signals, and within the GPI data 10 exoplanet signals. 
 <strong>In total there are 21 exoplanet signals to be characterized.</strong></p>

As shown in the [injection procedure tutorial](https://github.com/exoplanet-imaging-challenge/phase2/tree/main/tutorials), based on [VIP pipeline](https://vip.readthedocs.io/en/latest/) procedures, the exoplanet signal injection relies on the following steps:

* Choosing the subpixel position of the injected planet in the 1st frame of the image cube;
* Choosing the mean contrast accross wavelengths of the injected planet `mean_contrast_planet`;
* Choosing a template spectrum shape for the injected planet `spectrum_planet` (e.g. blackbody, atmospheric model, best fit etc.);
* Fitting the stellar spectrum measured from the non-coronagraphic image `fitted_stellar_spectrum` (for the contrast normalization);
* Grabbing a stellar spectrum SED model `model_stellar_spectrum` (to estimate the transmission of the atmosphere and the instrument);
* Computing the airmass factor to be applied to the planetary signal through time `airmass_factor`;
* Injecting the planet signal, using the `inject_fcp_ifs` function of VIP. <br>

<p style='text-align: justify;'>The injection function takes as an input: the multispectral image cube in which the injection is made, the normalized non-coronagraphic PSF used as a planetary signal model, the parallactic angle variation, the chosen position, spectrum and mean contrast of the injection, the fitted stellar spectrum, the model SED stellar spectrum, the instrument spectral resolving power and the airmass variation through time.</p>

The injected signal at a given wavelength (lambda) and position then writes: <br>
`Injected_planet_lambda = PSF_lambda * spectrum_planet * mean_contrast_planet * transmission_AtmInstr * airmass_factor`, <br>
where `transmission_AtmInstr = fitted_stellar_spectrum / model_stellar_spectrum `.

<p style='text-align: justify;'>No other effect is taken into account for the injection: no other flux temporal variation (intrinsic nor instrumental), no smearing at large separation due to the exposure time, no temporal binning, no off-centering of the star behind the coronagraph during the exposure, no diffraction effect due to the coronagraph at close separation etc.</p>


{: .box-note}
**Training data set:** On the [Zenodo repository](https://zenodo.org/record/6902628) containing the data, you will find a data set annoted `sphere0`. This is the training data set (empty of exoplanetary signals). On the [Github repository](https://github.com/exoplanet-imaging-challenge/phase2/tree/main/tutorials) containing the toolkit, you will find a tutorial showing our planet injection procedure within this example SPHERE-IFS data set. This tutorial makes use of 2 planet spectra (in folder /planet_spectra/) to be injected and uses a given stellar spectra (in folder /stellar_spectra/) to compute a mean contrast. This tutorial contains a part to visualise the input data and one to process the data for a quick-look using a full frame ASDI PCA. Feel free to use this training set to refine your algorithm use.

<link rel="stylesheet" href="https://www.w3schools.com/lib/w3-colors-2021.css">
<div class="w3-panel w3-2021-cerulean w3-round-large w3-border">
  <p> More information (telescope, instrument, coronagraph type, effective telescope diameter, total field rotation, spectral resolving power, central wavelength, exposure time DIT, number of exposures NDIT, pixel scale, seeing etc.) are written in the header, when available. More information about the data, the reduction and the planet signals injection procedure is available in the SPIE proceeding 2022 (see <a href="https://exoplanet-imaging-challenge.github.io/publi2/">Results</a> Tab).</p>
</div>


*** 

### Data and pre-reduction team:
* J.-B. Ruffio (Caltech, USA), on behalf of *GPIES collaboration*: Gemini-S/GPI data
* P. Delorme (IPAG, France), on behalf of the *SPHERE Data Center team*: VLT/SPHERE-IFS data

### Injection of planetary signals, homogenization and test team:
* Faustine Cantalloube (LAM, France)
* Carles Cantero (ULiège, Belgium)
* Valentin Christiaens (ULiège, Belgium)
