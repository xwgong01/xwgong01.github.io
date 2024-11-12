---
layout: page
title: Enhance LHAASO Resolution with Machine Learning
description: De-convolution with neural networks!
img: assets/img/1849.jpg
importance: 3
category: work
related_publications: false
---

Every instrument suffers from systematic error --- As a result, imaging power is limited by point spread function (PSF). It has been proven impossible to recover the original sky map from PSF blurring using mathematical methods. Will machine learning make a difference? 

Super Resolution techniques have been widely applied in microscopy. They could go beyond the instrumental limit, help resolving the small structures of tiny structures like fibers. Inspired by this, we want to explore whether similar models could be applied in astronomical research. the Large High Altitude Air Shower Observatory (LHAASO) has measured extreme high energy gamma-ray photons, but its angular resolution is poor, many sources are unresolved. If machine learning can enhance the resolution, it could at least give some hints on the source morphology, which help researcher identify the cosmic ray acceleration site. 

#### Training Data


<!-- <div class="row"> -->
<div class="d-flex justify-content-center">
    <div class="col-12 col-md-6">
        {% include figure.liquid loading="eager" path="assets/img/fermibkg.jpg" title="Fermi Diffuse Gamma-Ray Emission Model" class="img-fluid rounded z-depth-1" %}
    </div> 
</div>
We start from a rather simple case. We first train the model to reconstruct PSF-blurred sky map with certain energy and declination, which means the PSF of LHAASO is accurately measured. Since the LHAASO data are not well studied, we choose dataset from Fermi LAT, an earlier gamma-ray observatory, as the intrinsic intensity map. The sky map is then convolved with the LHAASO PSF. On this dataset, we tested the ability of machine learning model to reconstruct sky maps blurred with certain PSF. 


We then perform a 2d-convolution with the PSF function to the sky map, so that it looks smoothed and the small scale structure seems not distinguishable any more. 




<div class="row">
    <div class="col-3 col-md-3">
        {% include figure.liquid loading="eager" path="assets/img/origbkg.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-3 col-md-3">
        {% include figure.liquid loading="eager" path="assets/img/blurbkg.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-6 col-md-6">
        {% include figure.liquid loading="eager" path="assets/img/poiselect.jpg" title="Fermi Diffuse Gamma-Ray Emission Model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The sky map is cropped into many small areas (\(6.4 \times 6.4^\circ \)) (left), blurred with PSF (mid). The sky regions are selected with fibonacci laticce (right).
</div>

We have trained on different models, such as variational auto-encoder (VAE), convolutional neural network (CNN) and generative adversial network (GAN). It turns out that the simplest CNN has the best performance, which is due to the convolutional nature of CNN. We have applied the trained model to five LHAASO KM2A observations at 25 to 40 TeV. It turns out that the machine learning model can recover the strong poisson noise. Also, along the manually selected directions, the peak reconstructed by our model is narrower than the TS Map resulted from the traditional likelihood test. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/recon_lhaaso.png" title="reconstructed LHAASO observations" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    First row from left: counts map from observation (should be affected by PSF); Second row: TS map using 0.29 degree as smooth radius; Third Row: machine learning reconstructed intensity map; Rightmost: intensity curve along manually selected direction.
</div>

### Problems and The Future

 In the real observation, PSF varies with energy and declination, which is a challenge for training a unified model for reconstructing the all sky map. Our treatment to the PSF blurring is also too ideal. 

 We gave a poster presentation recently at the Second LHAASO Collaboration Conference recently in Chengdu, Sichuan. Now we are collaborating with researchers from IHEP. They will offer guidance of simulating LHAASO observation, and make sure our training data is close to the real observation. 
