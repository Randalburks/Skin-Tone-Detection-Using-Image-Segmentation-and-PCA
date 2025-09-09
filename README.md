# Skin-Tone Detection Using Image Segmentation and PCA
# Skin Tone Detection Using Image Segmentation and PCA

This project demonstrates **color-based image segmentation** using **Principal Component Analysis (PCA)**.  
The goal is to separate skin tones from background colors in images by projecting pixel values into a PCA-derived color space.

## Project Overview
- Uses the [UCI Skin Segmentation Dataset](https://archive.ics.uci.edu/ml/datasets/skin+segmentation).
- Extracts RGB values of skin pixels and learns a transformation matrix using PCA.
- Transforms image pixels into a new “skin tone colorspace”.
- Segments skin regions by thresholding distances in PCA space.

## Workflow
1. **Load Dataset**
   - Download `Skin_NonSkin.txt` from UCI repository.
   - Keep only rows labeled as skin (label = 1).
   - Reorder BGR to RGB format.

2. **Preprocessing**
   - Compute mean RGB values.
   - Mean-center the dataset.
   - Build the Gram matrix and compute eigenvalues/eigenvectors.
   - Verify orthogonality of eigenvectors.

3. **Transform an Example Image**
   - Reshape the image into pixel vectors.
   - Subtract the mean RGB vector.
   - Project pixels into PCA space.

4. **Segmentation**
   - Compute distance of pixels to the first principal axis.
   - Threshold distances to classify “skin-like” pixels.
   - Visualize segmentation mask vs original image.

