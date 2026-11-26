# Opening and Closing Operations Using OpenCV

## Developed By

## Name: Sridharan B

## Register No: 212225230272

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.

## Program

```python

import cv2
import numpy as np
import matplotlib.pyplot as plt

#Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Sridharan B', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')

# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')

# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
```

## Output

**Input Image**

<Figure size 640x480 with 1 Axes><img width="389" height="410" alt="image" src="https://github.com/user-attachments/assets/55b02e04-2c34-44c9-9af4-7cfc6eb7a7a6" />



**Opening Operation**

<Figure size 640x480 with 1 Axes><img width="389" height="410" alt="image" src="https://github.com/user-attachments/assets/c1222348-27ca-4e88-ac82-16a136bca72d" />


**Closing Operation**

<img width="358" height="365" alt="image" src="https://github.com/user-attachments/assets/cd8fe8bc-fd8c-4e4d-a43a-c520aca3bd18" />


## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 



