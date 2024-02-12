---
layout: page
title: Datasets phase 1
---

<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">

{: .box-note}
**Zenodo repository:** The Zenodo repository containing the challenge datasets can be found [here](https://zenodo.org/record/3361544).<br>
Make sure you get the latest version (v2.0). 

### Instruments
The datasets used in this data challenge were kindly provided by scientists from several high-contrast imaging instruments (see [Team](https://exoplanet-imaging-challenge.github.io/team/)), and are the result of many years of work from different teams around the globe.

*Subchallenge 1:*

* VLT/SPHERE-IRDIS, <a href="https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...631A.155B/PUB_PDF" style="text-decoration:underline;color:slateblue">Beuzit et al., 2019</a>
* Keck/NIRC2, <a href="https://www2.keck.hawaii.edu/inst/nirc2/" style="text-decoration:underline;color:slateblue">NIRC2 webpage</a>
* LBT/LMIRCam, <a href="https://ui.adsabs.harvard.edu/abs/2008SPIE.7013E..3AW/abstract" style="text-decoration:underline;color:slateblue">Wilson et al., 2008</a>

*Subchallenge 2:*

* VLT/SPHERE-IFS, <a href="https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...631A.155B/PUB_PDF" style="text-decoration:underline;color:slateblue">Beuzit et al., 2019</a>
* Gemini-S/GPI, <a href="https://www.spiedigitallibrary.org/conference-proceedings-of-spie/7015/1/The-Gemini-Planet-Imager--from-science-to-design-to/10.1117/12.788083.full" style="text-decoration:underline;color:slateblue">Macintosh et al., 2008</a>

<p style='text-align: justify;'>The datasets used in this competition are diverse: from H-band (1.6 mum) to L-band (3.8 mum), broadband/narrowband filters, total range of field rotation, with or without a coronagraph, observing conditions etc. </p>

### Pre-processing steps
<p style='text-align: justify;'>The datasets were pre-reduced (calibrated) using the standard pipeline of each instrument. We then applied a few pre-processing procedures on each cube to make sure that the offered data cubes are homogeneous (centering, cropping etc.). All the image of the cubes have been cropped to focus on the innermost 20 lambda/D region.</p>

The data are saved in <a href="https://en.wikipedia.org/wiki/FITS" style="text-decoration:underline;color:slateblue"><em>.fits</em></a> files format. 
A convenient software for quick visualization is <a href="http://ds9.si.edu/site/Download.html" style="text-decoration:underline;color:slateblue">SAOImageDS9</a>. 
If you use Python and Jupyterlab, you can use the <a href="https://github.com/carlgogo/hciplot/" style="text-decoration:underline;color:slateblue">HCIplot</a> open-source library for visualizing the cubes. 

No additional sorting or temporal binning have been applied. **Users can sort-out the images if they wish**

### Injections
Using the center defined in the table below and [here](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0fDpZD4LAoawUkITgWj_6Nx7XIKB4JAeOVS9CUIsTITI4X-MTI_rsqzC6e5MvQ2j9ivkoxZzI-XKB/pubhtml?gid=39220023&single=true), we injected 0 to 5 synthetic planetary signals in each dataset, with contrast and separation randomly picked around the detection limit (5-sigma contrast curve) computed from the baseline post-processing technique (a full frame PCA). To inject the synthetic planetary signals, we made use of the VIP pipeline.

### Provided data content
For the sub-challenge on ADI post-processing, each dataset is composed of:
 * ``instrument_cube_id.fits`` (3d array, containing the images temporal cube),
 * ``instrument_pa_id.fits`` (1d array, vector of parallactic angles),
 * ``instrument_pxscale_id.fits`` (float value, the pixel scale value in arc/px),
 * ``instrument_psf_id.fits`` (2d array, the associated non-coronagraphic or non-centered instrumental PSF), 
 where **instrument** is one of the following: ``nirc2``, ``lmircam`` or ``sphere_irdis``, and **id** is a positive integer to describe each data set. 

For the second sub-challenge on ADI+mSDI post-processing, each dataset is composed of:
 * ``instrument_cube_id.fits`` (4d array, containing the images temporal and spectral dimension),
 * ``instrument_pa_id.fits`` (1d array, vector of parallactic angles),
 * ``instrument_pxscale_id.fits`` (float value, the pixel scale value in arc/px),
 * ``instrument_psf_id.fits`` (2d array, the associated non-coronagraphic or non-centered instrumental PSF), 
 * ``instrument_wls_id.fits``(1d array, vector of wavelengths),
 where **instrument** is one of the following: ``sphere_ifs`` or ``gpi``, and **id** is a positive integer to describe each data set. 

### Data parameters
The information about the datasets can be find in the table below:

<iframe 
src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0fDpZD4LAoawUkITgWj_6Nx7XIKB4JAeOVS9CUIsTITI4X-MTI_rsqzC6e5MvQ2j9ivkoxZzI-XKB/pubhtml?gid=39220023&amp;single=true&amp;widget=true&amp;headers=false"
style="width:100%; height:535px;"></iframe>

{: .box-note}
**Note LMIRCam images:** The image cube of LMIRCam being quite long, feel free to bin temporally the images to process it faster. 

***

<p style='text-align: justify;'>It is mandatory that the submitted datasets remain *secret* for the duration of the challenge. After the data challenge is finished, the contributed datasets (without injected companions) will constitute the <strong>HCI benchmark library</strong> that will be made available for the community. This benchmark library will be stored on Zenodo, ensuring the long term preservation of data, and will serve the next generation of researchers who will be able to re-use the benchmark datasets for quick validation of novel algorithms and for publication.</p>


***

### Data and pre-reduction team:
* David Mouillet (IPAG, France): VLT/SPHERE data
* Dimitri Mawet (Caltech, USA): Keck/NIRC2 data
* Jordan Stone (LBT observatory, USA): LBT/LMIRCam data
* J.-B. Ruffio (Caltech, USA), on behalf of *GPIES collaboration*: Gemini-S/GPI data

### Injection of planetary signals, homoegenization and test team:
* Faustine Cantalloube (LAM, France)
* Carlos Gomez-Gonzalez (ULiege, Belgium & BCS, Spain)
* Rebecca Jensen-Clem (UCSC, USA)
* Tiffany Meshkat (IPAC/CalTech, USA)


