# Active Zone Segmenter

This ImageJ macro was specifically written to automate the segmentation of mature and immature active zone (AZ) nanostructures. It was developed for the paper by Lützkendorf et al., 2024. [DOI: https://doi.org/#####](https://doi.org/#####). Radial intensity profiles around AZs and many other measurements are exported after segmentation. 

![Fig.1: Example of Detected Active Zones]([https://github.com/ngimber/BruchpilotSegmentation/blob/main/detected_active_zones.PNG](https://github.com/ngimber/BruchpilotSegmentation/blob/main/detected_active_zones.png))
---

## Overview

This macro allows for the characterization of AZ shape in high-resolution images, particularly focusing on Bruchpilot (BRP) signals from gSTED images (e.g. .tif images). The segmentation method applies Fourier filtering and auto-thresholding to distinguish between mature and immature AZ nanostructures. Additional information can be found in the methods section of the original publication.

### Key Steps:
1. **Fourier Bandpass Filtering**:
   - Medium-to-large structures (0.1–2 μm) were isolated by applying a Fourier bandpass filter to the images.
   
2. **Thresholding and Segmentation**:
   - The filtered images were processed using ImageJ’s built-in **MaxEntropy** auto-thresholding algorithm and **watershed** algorithm to segment the AZs.
   
3. **Exclusion of Small Clusters**:
   - Small clusters, potentially representing immature AZs, were identified separately by applying a Fourier bandpass filter for small structures (0–0.06 μm) and the **Minimal** threshold algorithm in ImageJ.

---

## User Interface Parameters

### 1. Selected Area
- **Checkbox**: Limits the segmentation process to the currently selected area in the image.

---

### 2. Reference Channel
- **Field**: Specify the channel number containing the AZ data.

---

### 3. FFT Bandpass Filter *(Image-based size exclusion)*
- **Active Zone min/max size (pixels)**:
   - Select upper and lower limit of AZs for Furier Filtering
- **Intermediates min/max size (pixels)**:
    - Select upper and lower limit of  AZ intermediates for Furier Filtering
---

### 4. Enlarge ROIs
- **Enlarge Active Zone ROIs (pixels)**:
  - Add Multiplier
- **Enlarge Intermediates ROIs (pixels)**:
  - Add Multiplier

---

### 5. Object Parameter Filters
- **Min Circularity**:
- **Min Area**:

---

### 6. Radial Profile Parameters
- **Radial Profile Radius (units)**:

- **Randomization Shift (pixels)**:
  - Introduce a toroidal shift between the image channels as in silico control for 'random' distribution.

---

## How to Use
1. **Load Image**: Open your gSTED or high-resolution microscopy image in ImageJ.
2. **Select Folder**: Select Folder for Batch Processing.
3. **Select Filetype**: Select the filetype of your images (e.g. .tif).
4. **Set Parameters**: Adjust the parameters in the GUI according to your experiment.
5. **Run Segmentation**: Press `OK` to execute the segmentation algorithm.

For further details, please refer to the [original publication](https://doi.org/#####).

![Alt Text for the Image](https://github.com/ngimber/BruchpilotSegmentation/blob/main/GUI.PNG)
