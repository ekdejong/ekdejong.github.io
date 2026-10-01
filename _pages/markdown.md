---
permalink: /markdown/
title: "Research"
author_profile: true
redirect_from: 
  - /md/
  - /markdown.html
---
I study cloud microphysics and its representation in weather and climate models, working across high-fidelity simulation, machine learning, and observational inference to connect micron-scale particle physics to global-scale climate predictions.

# Ongoing Work

## 1. High-fidelity modeling
In more expensive simulations of a single cloud or small region, an approach known as the "Superdroplet Method" is becoming more and more popular. This Lagrangian particle-based method tracks individual tracers ("superdroplets"), each of which correspond to many individual particles with identical properties, and updates their properties as they interact and evolve using Monte Carlo steps. I contributed [a scalable representation of collisional breakup](https://doi.org/10.5194/gmd-16-4193-2023) in an [open source implementation of the SDM](https://github.com/open-atmos/PySDM) to enable studies of how breakup of raindrops might impact precipitation and cloud properties, and I continue to use these high-fidelity simulations as training data and ground truth for the data-driven methods below.

## 2. Reduced-order & surrogate modeling
A single cloud contains upwards of 10^10 individual particles -- droplets, aerosols, or ice -- constantly changing size, shape, and other properties as they interact with each other and the air around them. Operational models typically distill all of this complexity into a handful of tracked quantities, introducing uncertain parameterizations in the process. My current work builds machine-learned reduced-order models that track the evolving particle size distribution directly from high-fidelity simulation data, using autoencoders to discover a compact latent representation and comparing several ways of evolving that latent state in time (a polynomial SINDy framework, a neural-network-predicted time derivative, and a direct autoregressive predictor). [Our comparison of these approaches](https://doi.org/10.1029/2025JH001103) found that the simplest model generalizes best -- a result that was also [featured as an Eos Research Spotlight](https://eos.org/research-spotlights/comparing-machine-learning-models-of-raindrop-formation). I'm now working on integrating these latent-space emulators directly into operational microphysics schemes (via the PyTorch-Fortran interface FTorch) to replace, rather than just approximate, existing parameterizations.

## 3. Observational inference
Observations of clouds from space are one of the most complete datasets that climate scientists have available to validate models, but satellite imagery is fundamentally two-dimensional while clouds are not. My work develops probabilistic deep learning methods to infer vertically-resolved cloud structure from 2D satellite fields: [CERBERUS](https://arxiv.org/abs/2604.08772) is a three-headed encoder-decoder that predicts vertical radar reflectivity profiles -- along with calibrated uncertainty -- from GOES satellite brightness temperatures, trained and validated against ground-based Ka-band radar. The goal is to generate model-relevant synthetic observations of cloud vertical structure at the scale that only satellites can provide.

## 4. AI emulators
At the other end of the scale spectrum, I work with fully data-driven emulators of entire coupled climate models. Using SamudrACE-E3SMv3, a coupled atmosphere-ocean AI emulator trained to reproduce E3SM, I investigate questions of seasonal predictability in coupled AI weather and climate emulators -- how well these fast, learned models capture the slower, coupled dynamics (like ENSO) that govern predictability beyond the weather timescale.

![Sc clouds over the ocean in Santa Barbara, CA](../images/clouds.jpeg)

# Previous Research

**Aerosol-cloud-lightning interactions.** After shipping regulations led to a sharp reduction in ship-emitted aerosols in 2020, I looked for signals of aerosol-cloud interactions in deeply convective clouds using lightning frequency as a metric, leveraging the abrupt 2020 IMO fuel sulfur regulation as a natural experiment over two of the world's busiest shipping lanes.

**Low-level jets in the coastal environment.** In my research at NREL, I investigated the atmospheric mechanisms behind low-level jets -- a low-level maximum in wind speed -- which have been found off the coast of New Jersey and New York at altitudes relevant to future offshore wind energy. Using floating lidar buoy data, I found these coastal jets arise from a combination of synoptic-scale temperature gradients and inertial oscillations triggered by fronts or the land-sea breeze ([published in the Journal of the Atmospheric Sciences](https://doi.org/10.1175/JAS-D-23-0079.1)), and in a follow-on study used this understanding to examine how these wind phenomena might impact offshore wind turbine structural design.

**Numerical methods for droplet size distributions.** During my PhD, I developed [a novel spectral method](https://doi.org/10.1029/2022MS003186) for directly tracking a cloud droplet size distribution under collisional coalescence, aiming to balance accuracy against computational cost between traditional "bulk" and "bin" microphysics schemes. I also contributed to [Cloudy.jl](https://github.com/CliMA/Cloudy.jl), including an efficient Bayesian approach for learning droplet collision kernel parameters.
