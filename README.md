# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step 1:

Import necessary libraries, including OpenCV (cv2) and Matplotlib (plt), to load, manipulate, and display images.
### Step 2:

Use cv2.putText() to add text to the image at a specific location with chosen font, size, color, and thickness.
### Step 3:

Define a structuring element using cv2.getStructuringElement() to specify the shape and size for morphological transformations.
### Step 4:

Apply erosion to the image using cv2.erode() with the structuring element to shrink white regions and reduce noise.
### Step 5:

Dilate the eroded image using cv2.dilate() with the structuring element to expand white regions and enhance features.
### Step 6:

Display the original and processed images using plt.imshow() with proper axis configuration and titles for comparison.
### Step 7:

Finalize by calling plt.show() to display all images in a single figure for easy visualization and comparison.
 
## Program:
### Import the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = np.zeros((300, 600, 3), dtype="uint8")
```


### Create the Text using cv2.putText
```
text = "Thiyagarajan"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```
![Screenshot 2024-11-14 153444](https://github.com/user-attachments/assets/cb85a1a2-cfc7-4789-8905-288cd54e7bf2)

### Create the structuring element

```
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

```


### Original image
```

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
```
![Screenshot 2024-11-14 153453](https://github.com/user-attachments/assets/604c2973-32bc-48e4-8756-c32f17d291fd)


### Erode the image
```
eroded_image = cv2.erode(image, kernel, iterations=1)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")
```


![Screenshot 2024-11-14 153456](https://github.com/user-attachments/assets/c0d59e91-6e5c-4858-836c-1f5fdee49df7)

### Dilate the image
```
dilated_image = cv2.dilate(image, kernel, iterations=1)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")
```
![Screenshot 2024-11-14 153500](https://github.com/user-attachments/assets/bb847a20-5f9c-4b17-aa05-5efccf22bb8d)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
