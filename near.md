---
layout: page
title: NEAR campaign data
---

TEST

The NEAR campaign aims to search for low-mass planets around both components of the binary a Centauri, the closest stellar system to Earth. 
As such, 100-hour of observations were conducted using a dedicated upgrade of the VLT mid-infrared imager VISIR. 
The NEAR campaign is a collaboration between ESO and the Break-through Initiatives. 
Here, through the data challenge initiative, we propose to offer access to the NEAR campaign data. 
As such, anyone has the possibility of applying the best algorithm on these data and therefore taking part in this fascinating adventure: attempting to image the closest planet to Earth.

A short article published in the ESO Messenger summarizes the NEAR campaign: <https://www.eso.org/sci/publications/messenger/archive/no.178-dec19/messenger-no178-5-9.pdf>

The campaign data can be found [here](<ftp://ftp.eso.org/projects/aosimul/NEAR_Campaign_data/>)

These data are gathered in a serie of .fits files, each consisting of 401x401 images (Primary HDU), and parallactic angle as an ImageHDU. 

Compared to the raw data: 
* the chopping subtraction has already been done, 
* outliers and bad frames were removed, 
* frames are aligned, 
* 500x0.12s frames were combined to 60s time resolution.

For more enquiry about the data or to discuss your results, please contact P. Pathak (<Prashant.Pathak@eso.org>) and M. Kasper (kasper@eso.org)
