---
layout: page
title: Datasets phase 1
---

{: .box-note}
**Zenodo repository:** The Zenodo repository containing the challenge datasets can be found [here](https://zenodo.org/record/3361544). 
Make sure you get the latest version (v2.0). 

### Instruments
The datasets used in this data challenge were kindly provided by scientists from several high-contrast imaging instruments (see [Team](https://exoplanet-imaging-challenge.github.io/team/)), and are the result of many years of work from different teams around the globe.

*Subchallenge 1:*

* VLT/SPHERE-IRDIS, [Beuzit et al., 2019](https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...631A.155B/PUB_PDF)
* Keck/NIRC2, [NIRC2 webpage](https://www2.keck.hawaii.edu/inst/nirc2/)
* LBT/LMIRCam, [Wilson et al., 2008](https://ui.adsabs.harvard.edu/abs/2008SPIE.7013E..3AW/abstract)

*Subchallenge 2:*

* VLT/SPHERE-IFS, [Beuzit et al., 2019](https://ui.adsabs.harvard.edu/link_gateway/2019A%26A...631A.155B/PUB_PDF)
* Gemini-S/GPI, [Macintosh et al., 2008](https://www.spiedigitallibrary.org/conference-proceedings-of-spie/7015/1/The-Gemini-Planet-Imager--from-science-to-design-to/10.1117/12.788083.full) 

The datasets used in this competition are diverse: from H-band (1.6 mum) to L-band (3.8 mum), broadband/narrowband filters, total range of field rotation, with or without a coronagraph, observing conditions etc. 

### Pre-processing steps
The datasets were calibrated/pre-processed using the standard pipelines of each instrument. We then applied a few pre-processing procedures on each cube to make sure that the library is homogeneous (centering, cropping etc.). The cubes have been cropped to focus on the innermost 20 lambda/D region.

The data are saved in [FITS](https://en.wikipedia.org/wiki/FITS) files format. A convenient software for quick visualization is [SAOImageDS9](http://ds9.si.edu/site/Download.html). If you use Python and Jupyterlab, you can use the [HCIplot](https://github.com/carlgogo/hciplot/) open-source library for visualizing the cubes. 

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
It is mandatory that the submitted datasets remain *secret* for the duration of the challenge. After the data challenge is finished, the contributed datasets (without injected companions) will constitute the **HCI benchmark library** that will be made available for the community. This benchmark library will be stored on Zenodo, ensuring the long term preservation of data, and will serve the next generation of researchers who will be able to re-use the benchmark datasets for quick validation of novel algorithms and for publication.


