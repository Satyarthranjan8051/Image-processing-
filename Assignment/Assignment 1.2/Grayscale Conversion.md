# Image Grayscale Conversion Using Python and PIL

This project demonstrates how to load an image, convert it to grayscale using the luminance method, save the grayscale image, and display both the original and grayscale images using Python, PIL (Python Imaging Library), and Matplotlib.

## Prerequisites

To run this code, you need the following Python libraries installed:

- `Pillow` (PIL Fork)
- `matplotlib`
- `numpy`

You can install the required libraries using the following command:

```bash
pip install Pillow matplotlib numpy
```
# How It Works

1. mage Loading: The image is loaded using the Pillow library.

2. Grayscale Conversion: The RGB image is converted to grayscale using the luminance formula:

```bash Grayscale = 0.299 × 𝑅 + 0.587 × 𝐺 + 0.114 × 𝐵
        Grayscale= 0.299 × R + 0.587 × G + 0.114 × B
```
## This method ensures that the luminance of each pixel is preserved while converting to grayscale.

Image Saving: The grayscale image is saved to a specified output path.
Image Display: Both the original image and the grayscale image are displayed side-by-side using Matplotlib.

# Code Explanation
##Loading the Image

The image is loaded using the Pillow library's Image.open() method:
```bash
def load_image(image_path):
    return Image.open(image_path)
```
## Grayscale Conversion
The RGB image is converted to grayscale using the luminance formula:
```
def convert_to_grayscale(image):
    np_image = np.array(image)
    grayscale_array = 0.299 * np_image[:, :, 0] + 0.587 * np_image[:, :, 1] + 0.114 * np_image[:, :, 2]
    return Image.fromarray(grayscale_array.astype('uint8'))

```
## Saving the Grayscale Image
The grayscale image is saved to the output path using the save_image() function:

```
def save_image(image, output_path):
    image.save(output_path)

```
## Displaying the Images
The original and grayscale images are displayed side-by-side using Matplotlib:
```
def display_images(original, grayscale):
    fig, axs = plt.subplots(1, 2, figsize=(10, 5))
    axs[0].imshow(original)
    axs[0].set_title('Original Image')
    axs[0].axis('off')
    axs[1].imshow(grayscale, cmap='gray')
    axs[1].set_title('Grayscale Image')
    axs[1].axis('off')
    plt.show()
```

## Running the Program
The main() function orchestrates the execution:

```
def main():
    image_path = "/content/sample image4.jpeg"
    grayscale_output_path = "/content/grayscale_image.jpg"
    original_image = load_image(image_path)
    grayscale_image = convert_to_grayscale(original_image)
    save_image(grayscale_image, grayscale_output_path)
    display_images(original_image, grayscale_image)

```

## How to Use
1. Make sure the required dependencies are installed.

2. Replace the image_path and grayscale_output_path with your input and output image file paths.

3. Run the script using Python.

```
python grayscale_conversion.py

```
## Expected Output
The output will display the original image and the grayscale image side by side. Additionally, the grayscale image will be saved at the specified path.

## License
This project is licensed under the MIT License.

```

Ensure to update the image paths to match the actual locations when running the code.

```

# <i>Happy Coding </i>

![wow-world-of-warcraft](https://github.com/user-attachments/assets/fbb128f8-5408-4a35-afee-a8937d59b24c)
