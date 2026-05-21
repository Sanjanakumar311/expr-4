# expr-4
# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```python
Developed By : SANJANA K L
Register Number:2122224230241
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('flower.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

# 6.Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot the original and transformed images
plt.figure(figsize=(12, 8))
```
```
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
# Output:

<img width="313" height="538" alt="image" src="https://github.com/user-attachments/assets/849ae411-19c1-48d0-9260-23f1dbd2df78" />

# 1. Translation
```
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
### Output:

<img width="317" height="543" alt="image" src="https://github.com/user-attachments/assets/d9d1883c-f557-454f-88d8-c7b001a10217" />



# 2. Scaling
```
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
### Output:

<img width="665" height="521" alt="image" src="https://github.com/user-attachments/assets/02bec7bf-b373-4e75-963a-99681551babf" />



# 3. Shearing
```
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
### Output:

<img width="317" height="533" alt="image" src="https://github.com/user-attachments/assets/942ea109-f4e1-4698-a56d-d6c40dd87c49" />


# 4. Reflection (Flip)
```
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
### Output:


<img width="298" height="562" alt="image" src="https://github.com/user-attachments/assets/e330d1ad-cb50-410c-ad4d-afc6eed5c144" />


# 5. Rotation
```
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
### Output:

<img width="300" height="535" alt="image" src="https://github.com/user-attachments/assets/b912a4b2-e781-4318-815a-7f8260075e95" />


# 6.Cropping
```
plt.tight_layout()
plt.show()

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
### Output:

<img width="540" height="533" alt="image" src="https://github.com/user-attachments/assets/3212f57d-29f3-4717-ae8d-362de669360d" />


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
