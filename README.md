# Notebooks

This repository contains a collection of interactive and educational Python notebooks designed for teaching and demonstrating key concepts in 
- remote sensing, with a focus on image registration, signal processing,
- speckle analysis, dynamic speckle

The notebooks are designed for execution in [Google Colab](https://colab.research.google.com) and include reproducible examples based on Sentinel-1 and Sentinel-2 data from [Google Earth Engine](https://earthengine.google.com/).

## 📘 Notebooks


### `BIOMASS_Georeferencing.ipynb`

Demonstrates how to search for and download ESA BIOMASS Level-1A full-polarimetric SLC products through the MAAP STAC catalogue. The notebook reconstructs the complex HH, HV, VH, and VV channels from separate amplitude and phase rasters, generates a Pauli RGB composite, and preserves the ground-control-point information supplied with the product. It then determines a suitable projected coordinate reference system and georeferences the original radar-coordinate image using Rasterio.

### `Generation_Video_Speckle_Funny.ipynb`

Generates a synthetic dynamic speckle sequence driven by a user-defined binary text mask. The mask spatially modulates the temporal decorrelation of the speckle field, allowing different regions of the image to exhibit different levels of activity. The notebook renders the simulated sequence as an animation and estimates an activity map from the temporal fluctuations. It is intended as a pedagogical illustration of dynamic speckle rather than as a complete physical model of a coherent imaging system.

### `Impulsion_Compression.ipynb`

Provides an intuitive introduction to radar pulse compression by comparing a finite-duration monochromatic pulse with a linear frequency-modulated chirp. The notebook applies matched filtering through FFT-based convolution and visualizes the resulting compressed responses. It also simulates a noisy radar signal containing several delayed and attenuated target echoes, showing how pulse compression improves range discrimination. Audio playback is used to make the effects of modulation, bandwidth, delay, and matched filtering perceptually accessible.

### `S1_burst_ASF_to_numpy_VV_VH.ipynb`

Provides a lightweight workflow for exploring Sentinel-1 IW SLC bursts without downloading complete SAFE archives. Using the Alaska Satellite Facility Burst Extractor and Earthdata authentication, the notebook retrieves matching VV and VH burst-level GeoTIFFs and loads the complex-valued channels directly into NumPy. It visualizes their amplitudes and phases, derives dual-polarization descriptors such as total backscattered power, polarization-ellipse orientation, ellipticity, and degree of polarization, and combines them into HSV/RGB representations. The analysis is exploratory rather than a complete polarimetric decomposition, since Sentinel-1 IW provides only dual-polarization measurements.

### `Sentinel_2_Cube.ipynb`

Builds a small Sentinel-2 surface-reflectance time-series cube from Google Earth Engine and converts selected acquisitions into local NumPy arrays. The notebook illustrates the residual geometric inconsistencies that can remain between nominally orthorectified optical images. Red–cyan complementary composites are used to reveal spatial misregistration, while Fourier-domain phase correlation provides subpixel estimates of the relative translations. The estimated shifts are then applied using the Fourier shift theorem, allowing the alignment to be compared before and after correction.

### `SimulationSAR_RMA_3D.ipynb`

Simulates a stripmap SAR acquisition using a three-dimensional radar geometry and a planar ground scene populated by point scatterers. The notebook derives the exact range histories and viewing angles, synthesizes the corresponding complex raw radar echoes, and illustrates the variation of incidence and azimuth-aspect angles along the synthetic aperture. Image formation is performed with an omega–k, or Range Migration, algorithm using phase compensation and Stolt interpolation. The reconstructed complex image is finally remapped from cross-track slant coordinates onto a uniform ground-range and azimuth grid.

### `Tree3D.ipynb`

Constructs a synthetic three-dimensional tree as a recursively generated collection of finite, oriented dielectric cylinders. A coherent polarimetric scattering model inspired by finite-cylinder formulations is applied to each branch segment: the local scattering matrix is projected into the radar horizontal–vertical basis and the segment contributions are coherently summed, including their propagation phases, to obtain the tree-level Sinclair matrix. The notebook compares geometric and electromagnetic orientation angles and investigates the sensitivity of the response to viewing geometry, frequency, dielectric permittivity, and moisture content. It also produces angular maps, polarimetric RGB representations, and animated parameter sweeps.

### `swot_slc_exploration.ipynb`

Introduces SWOT KaRIn Level-1B high-resolution SLC products as a source of near-nadir, Ka-band, single-pass interferometric observations. The notebook searches for acquisitions intersecting a user-defined area, downloads the corresponding products, and reads the two precisely co-registered complex images acquired by the KaRIn antennas. It computes the mean amplitude, wrapped interferometric phase, and local coherence, and resamples the strongly anisotropic radar grid for easier visualization. An HSV composite combines interferometric phase, coherence, and amplitude, while comparison with the embedded ground-range digital elevation model illustrates how DEM structures or artefacts may propagate into apparent phase discontinuities.


## 🚀 Getting Started

You can open each notebook directly in Colab using the badge links below each file, or clone the repository locally.

### Running in Colab

Click the badge below to open the repo in Google Colab:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/your-username/remote-sensing-notebooks)


