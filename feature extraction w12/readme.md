## Feature Extraction in Image Processing

Feature Extraction is the process of obtaining distinctive and numerical information from an image. It transform raw pixel data into more meaningful forms for analysis and decision-making, serving as the foundation for machine learning, image classification, and segmentation.

**Types of Features**

- First Order Features
  - Based on the statistical distribution of pixel intensity values, ignoring spatial relationships.
- Second Order Features
  - Consider the spatial relationships between pixels, representing the "texture" of the image.
- Higher Order Features
- Shape-Based Features
  - Define the geometric structure of an object and independent of intensity values.
- Deep Learning-Based Features
  - Automatically learned by neural network rather than being manually defined.

**Statistical Measures - First Order**

These are derived directly from the image histogram and include:

1. Mean (Average)
  - Definition: It is the arithmetic mean of all pixel intensity values in the image.
  - Meaning: Represents the average brightness level; helps distinguish between dark and bright image.
2. Variance
  - Definition: It measures how much pixel values deviate from the mean.
  - Meaning: Shows how widespread the intensity values are.
  - helping identify homogeneous vs. heterogeneous regions.
3. Standard Deviation
  - Definition: It is the squre root of the variance.
  - Meaning: Show the typical amount of deviation of pixel intensities around the mean.
4. Minimum and Maximum
  - Minimum: The lowest intensity value in the image.
  - Maximum: The highest intensity value in the image.
  - Meaning: It provides the endpoints of the intensity range.
5. Range
  - Definition: Maximum - Minimum
  - Meaning: It is the total spread range of the intensity values in the image.
6. Energy
  - Definition: It is the sum of the squares of the probabilities in the histogram
  - Meaning: It shows how orderly the intensity distribution is.
  - What does it distinguish? Pixel values are concentrated in specific ranges.
7. Entropy
  - Definition: Measures the uncertainty in the intensity distribution.
  - Meaning: Expresses the information content and complexity of the image.
8. Skewness
  - Definition: Measures how much the histogram deviates from symmetry.
  - Meaning: Shows whether the density distribution is leaned to the right or left.
9. Kurtosis
  - Definition: Measures the sharpness of the histogram's peak structure.
  - Meaning: Shows how much the densities are concentrated around the mean.
  - What does it distinguish? High kurtosis - sharp distribution, Low kurtosis - wide distribution.
10. Percentiles
  - Definition: Shows values below certain percentages of the density values.
  - Meaning: Summarizes specific points of the distribution.
11. Interquartile Range (IQR)
  - Definition: The difference between the 75% - 25% percentiles.
  - Meaning: Shows the spread of the middle 50% of the densities.
  - It is a very powerful and stable feature in Radiomics studies.

General Evaluation
- First-order features represent the general density structure of the image;
- Provides information about brightness, contrast, and heterogeneity;
- Does not contain spatial information; therefore, it is not sufficient on tits own;
- Generally used together with second order and shape-based features.

**Second Order Features**

Second order features are statistical features that consider the spatial relationships between pixel density values in the image.

Second order features calculate density and neighborhood relationship. Therefore, second order features represent the texture information in the image.

Why are second order features needed? It can disitiguis spatial information such as texture regulatiry, repeating patterns, and structural heterogeneity. While first order features give information about brightness and contrast. However, they connot explain how two pixels come together side-by-side.

**The comcept of the texture**

Texture refers to the spatial arrangement of density variations in an image.

Example texture properties: smooth - rough, regular - irregular, homogeneous — heterogeneous repeating — random. Second order features convert these concepts into numerical metrics. 

Second order features are generally calculated via the Gray Level Co-occurrence Matrix (GLCM). It count the frequency of two pixels appearing together at a specific distance and direction. In other words, the probability of a pixel with density i being a neighbor to a pixel with density j at a certain distance.

"A Gray Level Co-occurrence Matrix (GLCM) of size N_g x N_g describes the second-order joint probability function of an image region constrained by the mask and is defined as P(i, j | δ, θ). The (i,j)^th element of the matrix represent the number of times the combination of level i and j occur in two pixels in the image, that are separated by a distance of δ pixels along θ." from pyradiomics.readthedocs.io GLCM features
