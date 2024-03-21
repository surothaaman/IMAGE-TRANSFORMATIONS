# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import numpy module as np and pandas as pd.

### Step2:
Assign the values to variables in the program.

### Step3:
Get the values from the user appropriately.

### Step4:
Continue the program by implementing the codes of required topics.

### Step5:
Thus the program is executed in google colab.

## Program:
```
Developed By: R.Surothaman
Register Number: 212222103003
```
### i)Image Translation
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'lotus.jpg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```
### ii) Image Scaling
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'cat.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis

# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("cat.jpg:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)
```
### iii)Image shearing
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'butterfly.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)
```
### iv)Image Reflection
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'red.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

# Display original and reflected images
print("Original Image:")
show_image(image)
print("Reflected Horizontally:")
show_image(reflected_image_horizontal)
print("Reflected Vertically:")
show_image(reflected_image_vertical)
print("Reflected Both:")
show_image(reflected_image_both)
```

### v)Image Rotation
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'mixed.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)
```
### vi)Image Cropping
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'green.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)
```
## Output:
### i)Image Translation
![Screenshot 2024-03-22 004532](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/002a7a61-a825-4d76-8c27-2c64e617c9b2)

### ii) Image Scaling

![iger](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/c7f61528-c2cd-4b81-a458-67e571cafaa4)
![Screenshot 2024-03-22 005101](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/02ff36af-4061-46c8-ba24-6556e4b2701f)


### iii)Image shearing
![Screenshot 2024-03-22 005546](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/2907b882-ef76-4bad-9955-812379934059)

### iv)Image Reflection
![Screenshot 2024-03-22 005741](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/11bc11f4-20e8-4d6c-ab61-239ab0e57e28)
![Screenshot 2024-03-22 005754](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/b5939c00-4048-470f-aed0-3437721b42db)

### v)Image Rotation
![Screenshot 2024-03-22 010002](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/705cd1fa-8a84-4c08-a2ea-f173e82bfa64)

### vi)Image Cropping
![Screenshot 2024-03-22 010225](https://github.com/surothaaman/IMAGE-TRANSFORMATIONS/assets/133313653/fe6cffa2-0a6c-44c9-a74e-f3cb6bfbe2f7)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
