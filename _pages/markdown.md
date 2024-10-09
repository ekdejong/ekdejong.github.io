---
permalink: /markdown/
title: "Research"
author_profile: true
redirect_from: 
  - /md/
  - /markdown.html
---
# Modeling & Understanding Cloud Microphysics
My PhD research aims to improve our understanding of microscale cloud processes in the atmosphere and climate system, primarily through improving the way we represent and model these physics.

## 1. Reduced-order modeling
A single cloud contains upwards of 10^10 individual particles -- droplets, aerosols, or ice -- which are constantly changing their size, shape, and other properties by interacting with each other and the air around them. Representations of microphysics in climate and weather models typically distill all of this complexity into about 3 to 6 tracked quantities, making many assumptions and introducing uncertain parameterizations in the process. My research aims to eliminate some of the structural uncertainty of these models by developing smarter mathematical tools to directly track the particle size distribution, or other less obvious latent properties discovered by ML. Check out my [paper on a novel spectral method](https://doi.org/10.1029/2022MS003186) and stay tuned for future work to improve this approach even further, ongoing in contributions to [Cloudy.jl](https://github.com/CliMA/Cloudy.jl) and [CloudyMicrophysics.jl](https://github.com/CliMA/CloudMicrophysics.jl). 

## 2. High-fidelity modeling
In more expensive simulations of a single cloud or small region, an approach known as the "Superdroplet Method" is becoming more and more popular. This Lagrangian particle-based method tracks individual tracers ("superdroplets"), each of which correspond to many individual particles with identical properties, and updates their properties as they interact and evolve using Monte Carlo steps. I contributed [a scalable representation collisional breakup](https://doi.org/10.5194/gmd-16-4193-2023) in an [open source implementation of the SDM](https://github.com/open-atmos/PySDM) to enable studies of how breakup of raindrops might impact precipitation and cloud properties. In summer 2023, I also mentored an undergraduate researcher in implementing a "memory" of droplet fallspeed to investigate whether our assumptions about terminal velocity might be flawed.

## 3. Insights from remote sensing
Observations of clouds from space are one of the most complete datasets that climate scientists have available to validate models. But what we can we actually learn from these data about aerosol-cloud interactions and microphysics process rates? After shipping regulations led to a sharp reduction in ship-emitted aerosols in 2020, I began looking for signals of aerosol-cloud interactions in deeply convective clouds using lighting as a metric. More recently, I am investigating whether ML upscaling tools can help us gain insights and information from satellite observations about cloud properties -- vertical structure and size distributions -- that are not directly measured.

# Low-Level Jets in the Coastal Environment
In my research at NREL, I investigated the atmospheric mechanisms behind low-level jets, which are a low-level maximum in the windspeed. These jets occur most frequently over the Southern Great Plains of the U.S. at high altitudes, but they have also been found off the coast of New Jersey and New York at low altitudes that would be relevant to future offshore wind energy. I investigated the possible causes of these coastal jets in floating lidar buoy data, revealing that they arise from a combination of synoptic scale temperature gradients and inertial oscillations triggered by fronts or the land-sea breeze. [(Check out my recent publication, now in press!)](http://edejong-caltech.github.io/files/2023-lljs.pdf). In a later follow-on study, I used this new understanding of coastal jets to study how these wind phenomena might impact the structure of offshore wind turbines.