# Notebooks

This repository contains a collection of interactive and educational Python notebooks designed for teaching and demonstrating key concepts in 
- remote sensing, with a focus on image registration, signal processing,
- speckle analysis, dynamic speckle

The notebooks are designed for execution in [Google Colab](https://colab.research.google.com) and include reproducible examples based on Sentinel-1 and Sentinel-2 data from [Google Earth Engine](https://earthengine.google.com/).

## 📘 Notebooks

- Sentinel_2_Cube.ipynb:  
  Demonstrates how to extract a Sentinel-2 time series using Earth Engine, perform subpixel image registration using phase correlation in the Fourier domain, and visualize geometric misalignments and corrections.

- Generation_Video_Speckle_Funny.ipynb:  
  Simulates a dynamic speckle sequence based on a synthetic binary text mask, where speckle decorrelation is spatially modulated. The notebook demonstrates how to extract an activity map based on decorrelation rate.

- S1_burst_ASF_to_numpy_VV_VH.ipynb:

  provides a lightweight way to explore Sentinel-1 SLC bursts without downloading the entire SAFE package. Thanks to the Alaska Satellite Facility (ASF) API, we can directly request and load burst-level data into Python/Colab, and quickly check what phase information brings to the analysis, by using the color composition: Saturation → Degree of Polarization, Hue → Orientation of the polarization ellipse, Intensity → SPAN (total backscattered power). This notebook does not perform full polarimetry (Sentinel-1 IW is dual-pol only), but these principles are useful to understand what VV/VH combinations can reveal.

## 🚀 Getting Started

You can open each notebook directly in Colab using the badge links below each file, or clone the repository locally.

### Running in Colab

Click the badge below to open the repo in Google Colab:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/remote-sensing-notebooks)


