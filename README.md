# Bruchpilot Segmentation

This ImageJ macro was specifically written to automate the segmentation of active zone (AZ) nanostructures. It was developed for the paper by Lützkendorf et al., 2024. [DOI: https://doi.org/#####](https://doi.org/#####).

## Overview

This macro allows for the characterization of AZ shape in high-resolution images, particularly focusing on Bruchpilot (BRP) signals from gSTED images. The segmentation method applies Fourier filtering and auto-thresholding to distinguish between mature and imature AZ Nanostructures. Additional information can be foud in the methods section of the original publication.

1. **Fourier Bandpass Filtering**:
   - Medium-to-large structures (0.1–2 μm) were isolated by applying a Fourier bandpass filter to the images.
   
2. **Thresholding and Segmentation**:
   - The filtered images were processed using ImageJ’s built-in **MaxEntropy** auto-thresholding algorithm and **watershed** algorithm to segment the AZs.
   
3. **Exclusion of Small Clusters**:
   - Small clusters, potentially representing immature AZs were identified separately by applying a Fourier bandpass filter for small structures (0–0.06 μm) and the **Minimal** threshold algorithm in ImageJ.
