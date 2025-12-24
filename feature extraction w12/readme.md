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

Statistical Measures - First Order

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

