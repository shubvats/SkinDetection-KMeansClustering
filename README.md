# Skin Detection using K-Means Color Clustering

## Project Overview

The goal of this project is to perform k-means color clustering on two photos of the hand with different backgrounds and detect skin regions. This involves implementing repetitive k-means clustering to generate probability maps and thresholding the probabilities to identify skin regions in the images.

## Objectives

1. Take two photos of your hand with different backgrounds to identify factors that make image processing easier.
2. Evaluate computational challenges associated with clustering methods in image region segmentation.
3. Implement repetitive k-means clustering with k = {2, 3, 5} and detect skin regions using probability maps.

## Implementation Details

### Repetitive K-Means Clustering

- Perform k-means clustering with different randomly chosen centroids/pixel {R,G,B} values multiple times.
- Generate probability maps for each pixel indicating its likelihood of belonging to each cluster.

### Skin Region Detection

- Threshold the probabilities to detect skin regions: pixels are considered as skin regions if the highest probability value corresponds to the skin color cluster(s) and is above a threshold.

## Code

The `kmeansfn` function in the provided code performs k-means clustering on the input images and displays the results, including the original images and heatmaps.

## Usage

To use the code:
1. Place your images in the `imageArray` variable.
2. Specify the values of k (number of clusters) in the `kValues` variable.
3. Set the tolerance value for convergence in the `tolerance` variable.
4. Run the `kmeansfn` function.

```matlab
% Example usage
imageArray = {'image1.jpg', 'image2.jpg'};
kValues = [2, 3, 5];
tolerance = 0.001;
kmeansfn(imageArray, kValues, tolerance);
```

## Contributing

Contributions to this project are welcome! Feel free to open issues or submit pull requests with improvements, bug fixes, or additional features.
