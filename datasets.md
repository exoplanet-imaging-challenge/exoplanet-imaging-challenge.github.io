---
layout: page
title: Datasets
---

{: .box-note}
**Zenodo repository:** The Zenodo repository containing the challenge datasets can be found [here](https://zenodo.org/record/3361544). Make sure you get the latest version (v2.0). 

The datasets used in this data challenge were kindly provided by scientists from several high-contrast imaging instruments, and are the result of many years of work of different teams around the globe. The datasets come from these instruments: SPHERE (both IRDIS and IFS), GPI, NIRC2 and LMIRCam. With this we ensure the data used in this competition is diverse in terms of their characteristics and the observation modalities: slow/high speed cameras, broadband/filtered sequences, total range of rotation, presence of a coronagraph, etc. 

In order to reduce the need of domain knowledge (e.g. the expertize related to high-contrast imaing or to a specific instrument), the datasets were calibrated/pre-processed using the standard pipelines of each instrument. Then we applied a few pre-processing procedures on each cube to make sure that the library is homogeneous. The characteristics of each dataset and the pre-processing procedures applied to them are recorded on a public [Google spreadsheet](https://docs.google.com/spreadsheets/d/1Zx7tTGNBMhCXpAa5KIoufdvMrxtjfA3q2gX03APMkaM/edit?usp=sharing). 

Please keep in mind that we use these contributed datasets to inject synthetic companions and create the data challenge library. Once the data challenge is finished, the datasets without synthetic companions will constitute the benchmark HCI library.

<iframe width="700" height="550" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRtS1LYA97Rbv27P9T3bD3ctrS0-cxhJ9n2CT_qEIZZ-6bvwzx7u7OSaH5o9fdWIKNDnXa99b0vjalw/pubhtml?widget=true&amp;headers=false"></iframe>

For the sub-challenge on ADI post-processing, each dataset will be composed of:
 * ``instrument_cube_id.fits`` (3d array),
 * ``instrument_pa_id.fits`` (1d array, vector of parallactic angles),
 * ``instrument_pxscale_id.fits`` (float value, the pixel scale value in arc/px),
 * ``instrument_psf_id.fits`` (2d array, the associated PSF template), 
 
where ``id`` is a positive integer and instrument is one of the following: ``nirc2``, ``lmircam`` or ``sphere_irdis``. For the second sub-challenge, on spectrally dispersed data (instruments: ``sphere_ifs`` or ``gpi``), a 4D cube will be provided along with a vector of wavelengths (``instrument_wls_id.fits``). 

The cubes will be cropped to focus on the innermost 20 lambda/D. The challenge files are saved as [FITS](https://en.wikipedia.org/wiki/FITS) files, a format with long tradition in astronomy. FITS files can be easily opened in any programming language or environment (Python, Matlab, IDL, R, C, etc). The most convenient software for quick visualization of the cubes is the SAOImageDS9 viewer which can be downloaded [here](http://ds9.si.edu/site/Download.html). If you are into Python and you use Jupyterlab, then consider using the [HCIplot](https://github.com/carlgogo/hciplot/) open source library for visualizing the cubes. 

It is mandatory that the submitted datasets remain *secret* for the duration of the challenge. After the data challenge is finished, the contributed datasets (without injected companions) will constitute the **HCI benchmark library** that will be made available for the community. This benchmark library will be stored on Zenodo, ensuring the long term preservation of data, and will serve the next generation of researchers who will be able to re-use the benchmark datasets for quick validation of novel algorithms.


