# Image Histogram Matching and Blending

This project demonstrates how to perform histogram matching between two grayscale images using OpenCV and `skimage`, and blend the matched image with the source image. It also displays the source, matched, and blended images along with their respective histograms.

## Prerequisites

To run this code, you need to have the following Python libraries installed:

- `opencv-python`
- `numpy`
- `matplotlib`
- `scikit-image`

You can install the required libraries using the following pip command:

```bash
pip install opencv-python numpy matplotlib scikit-image
```

<h1><u>How it Works</u></h1>
<h3>Source Image: The image for which you want to match the histogram.

Reference Image: The image whose histogram will be used as the reference.

Histogram Matching: This is done using skimage.exposure.match_histograms, which transforms the source image's histogram to match the reference image.

Blending: The source image and the matched image are blended together using cv2.addWeighted with a 50-50 blending ratio.

Display: The source image, matched image, and the final blended image, along with their histograms, are displayed using Matplotlib.</h3>

<h1><u>Code Explanation</u>u</h1>

<h2>Image Loading</h2>
<h3>The source and reference images are loaded as grayscale images using OpenCV:</h3>
```bash
source_image = cv2.imread('/content/22.png', cv2.IMREAD_GRAYSCALE)
reference_image = cv2.imread('/content/pics11.jpg', cv2.IMREAD_GRAYSCALE)
```
<h2>Histogram Matching</h2>
<h3>The match_histograms function from skimage.exposure is used to match the histogram of the source image to that of the reference image:</h3>
```bash
matched_image = match_histograms(source_image, reference_image).astype(np.float32)
```
<h2>Image Blending</h2>
<h3>The source image and matched image are blended using a weighted sum:</h3>
```bash
mix_image = cv2.addWeighted(source_image_float, 0.5, matched_image, 0.5, 0)
```

<h2>Display Image and Histograms</h2>
<h3>A function display_images_and_histograms is used to display the images and their corresponding histograms:</h3>
```bash
def display_images_and_histograms(source, reference, mix):
    # Code to display images and histograms
```

<h2>Example of The Output</h2>

<h3>The program will display three images:

1. Source Image: The original input image.

2. Matched Image: The source image after its histogram is matched to the reference image.

3. Mix Image: The result of blending the source image with the matched image.

Each image will have its corresponding histogram shown alongside it.</h3>

<h2>How to Run The Code</h2>

<h3>
1. Ensure that all the required dependencies are installed.
  
2. Replace the image paths in the code (/content/22.png and /content/pics11.jpg) with the paths to your source and reference images.

3.Run the script to view the results.
</h3>
```bash
python image_histogram_matching.py
```
<h2>Output</h2>
<h3>
The output will be three images displayed along with their histograms:

1. Source Image

2. Matched Image

3. Mix Image
</h3>

<h2>License</h2>

<h3>This project is licensed under the MIT License.</h3>
```bash
Make sure to adapt the image paths in the code to match the actual locations on your system when running the code.
```



<H1>Happy Coding</H1>
