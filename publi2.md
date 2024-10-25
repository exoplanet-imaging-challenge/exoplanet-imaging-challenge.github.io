---
layout: page
title: Results Phase 2 Characterization
---

<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">


## Results of PCA-NEGFC (baseline) on the training set

<p>The images below show the baseline results on the <em>sphere0</em> training data set:</p>

<p align="center"> 
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/Phase2_data.jpeg" width="800" />
</p>
<center><small><i> Left: Residual map obtained after a PCA subtraction, using 10 principal components to build the reference image. Two injections, dubbed 'planet b' and 'planet c' are highlighted in orange and green respectively. Right: Corresponding 5-sigma detection limits for every spectral channel of SPHERE-IFS and spectral median of these detection limits (thick line). The position of both planets is shown in the plot. </i></small></center>

<br>

<p align="center"> 
<img src="https://raw.githubusercontent.com/exoplanet-imaging-challenge/exoplanet-imaging-challenge.github.io/master/img/Phase2_results.jpeg" />
</p>
<center><small><i> Left: Results in terms of astronmetry retrieval using PCA-NEGFC. The position of each data point shows the relative position to the ground truth standing in the middle and the shaded areas correspond to the
1-sigma uncertainty. Middle and Right:  Results in terms of spectro-photometry estimation using PCA-NEGFC. The top panel shows the extracted spectrum and the corresponding 3-sigma uncertainties. The bottom panel shows the residuals wrt the ground-truth with the 3-sigma uncertainties (shaded area).</i></small></center>

## Current results of the Phase 2 (leaderboard)

The table below shows the current algorithms submitted on the <a href="https://eval.ai/web/challenges/challenge-page/1717/" style="text-decoration:underline;color:slateblue">EvalAI</a> platform, with the corresponding distance, used as a metric for comparison.

<link rel="stylesheet" href="https://www.w3schools.com/lib/w3-colors-2021.css">
<div class="w3-container">
  <table class="w3-table-all">
    <thead>
      <tr class="w3-2021-cerulean">
        <th>Algorithm Name ID</th>
        <th class="w3-center">Astrometry</th>
        <th class="w3-center">Spectrophotometry</th>
      </tr>
    </thead>
    <tr>
      <td>VIP-PCA</td>
      <td>0.126</td>
      <td>24.97</td>
    </tr>
    <tr>
      <td>ANDROMEDA</td>
      <td>3.944</td>
      <td>304.88</td>
    </tr>
    <tr>
      <td>RSM</td>
      <td>0.396</td>
      <td>52.18</td>
    </tr>
    <tr>
      <td>MC</td>
      <td>0.223</td>
      <td>37.73</td>
    </tr>
  </table>
</div>

<div class="w3-text-grey"><small>Last update on February 7th 2024</small></div>


## Publication of the metrics used for the Phase 2 

<p  style='text-align: justify;'>After setting the second phase of the <em>Exoplanet Imaging Data Challenge</em>, we gathered the description of the second phase, the challenge design, the data set available and metrics used to make the comparison in an SPIE conference proceeding. This proceeding is the result of an oral contribution presented at  
<a href="https://spie.org/conferences-and-exhibitions/astronomical-telescopes-and-instrumentation" style="text-decoration:underline;color:slateblue">SPIE Astronomical Telescope + Instrumentation</a> taking place from the 17h to the 22th of July 2022 in Montréal (Canada). </p>

**You can find the SPIE 2022 publication <a href="https://arxiv.org/pdf/2209.08120.pdf" style="text-decoration:underline;color:slateblue">here</a>** (arXiv version). 

All members of the Exoplanet Imaging Data Challenge Phase 2 working group are co-authors.
<br>

## Publication of the comparison of the Phase 2 

<p  style='text-align: justify;'> After the deadline set on <b>31/05/2024</b>, we compiled the results and published the comparision in an SPIE conference proceeding is the result of an invited oral contribution presented at  
<a href="https://spie.org/conferences-and-exhibitions/astronomical-telescopes-and-instrumentation" style="text-decoration:underline;color:slateblue">SPIE Astronomical Telescope + Instrumentation</a> taking place from the 16th to the 21st of June 2024 in Yokohama (Japan). </p>

**You can find the SPIE 2024 publication <a href="[https://arxiv.org/pdf/2209.08120.pdf](https://arxiv.org/pdf/2410.17636)" style="text-decoration:underline;color:slateblue">here</a>** (arXiv version).

All participants to the Exoplanet Imaging Data Challenge Phase 2 are co-authors.
<br>

