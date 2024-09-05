# Image Transformations Using OpenCV and Matplotlib

This project demonstrates various image transformation techniques such as negative transformation, logarithmic transformation, gamma correction, and histogram equalization. The transformations are applied to a grayscale image using Python, OpenCV, and NumPy, and the results are visualized using Matplotlib.

## Prerequisites

To run this code, the following Python libraries must be installed:

- `opencv-python`
- `numpy`
- `matplotlib`

You can install the required dependencies by running the following command:

```bash
pip install opencv-python numpy matplotlib
```
# How It Works
## Transformations Applied

### Negative Transformation:
 
![image](https://github.com/user-attachments/assets/9e41bb58-3605-4ffb-891a-2d556534016f)

This operation inverts the pixel values of the image to create its negative.

### Logarithmic Transformation:

![image](https://github.com/user-attachments/assets/7f1a5799-22e6-4912-825c-6c3b231a5661)

The log transformation is used to enhance details in darker regions of the image. The constant c is calculated based on the maximum pixel intensity.

### Gamma Transformation:

![image](https://github.com/user-attachments/assets/3112164d-0dd0-4d78-8086-5c65c9c3818d)
Gamma correction adjusts the brightness of the image by using a gamma value of 2.0.

### Histogram Equalization: 

Histogram equalization enhances the contrast of the image by redistributing the pixel intensity values across the entire range of intensity values.

# Code Explanation
## Load the Image
### The grayscale image is loaded using OpenCV:
```code
image = cv2.imread('/content/sample image4.jpeg', cv2.IMREAD_GRAYSCALE)
if image is None:
    raise ValueError("Image not found. Check the path and try again.")
```
### Apply Transformations
  Negative Transformation:
```code
negative_image = 255 - image

```
 Logarithmic Transformation:
```code
c = 255 / np.log(1 + np.max(image))
log_image = c * (np.log(1 + image)).astype(np.uint8)

```
Gamma Transformation:
```code
gamma_image = np.array(255 * (image / 255) ** 2.0, dtype='uint8')
```
Histogram Equalization:
```code
hist_eq_image = cv2.equalizeHist(image)
```
## Display the Images
### The original and transformed images are displayed using Matplotlib:
```code
plt.figure(figsize=(15, 10))
titles = ['Original Image', 'Negative Transformation', 'Log Transformation', 'Gamma Transformation', 'Histogram Equalization']
images = [image, negative_image, log_image, gamma_image, hist_eq_image]

for i in range(5):
    plt.subplot(2, 3, i + 1)
    plt.title(titles[i])
    plt.imshow(images[i], cmap='gray')
    plt.axis('off')
```
# How to Run the Code
1. Ensure the necessary dependencies are installed.

2. Replace the image path in the code (/content/sample image4.jpeg) with your desired image file path.

3.Run the script to apply the transformations and display the results.

```bash
python image_transformations.py
```
# Expected Output
## The script will display the following images side by side:

1. Original Image
2. Negative Image
3. Log Transformation Image
4. Gamma Transformation Image
5. Histogram Equalized Image

# License
## This project is licensed under the MIT License.

```aurdino
Make sure to adjust the image path to match the actual location of your image when running the code.
```
# <i>Happy Coding </i>
![code-lyoko-aelita](https://github.com/user-attachments/assets/0c665cb0-4967-497b-b3e1-5796f4f3e2e1)
