# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step-1:
Create a black image of size 100x600 pixels.
### Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.
### Step-3:
Show the image containing the text without axis labels.
### Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).
### Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.
### Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.
 
## Program:
```
Developed By: HARI PRASATH S
Reg.No: 212222240034
```
``` Python
# Import the necessary packages
import numpy as np
import cv2
import matplotlib.pyplot as plt

# Create the Text using cv2.putText
img = np.zeros((100, 600, 3), dtype='uint8')  # Black background (RGB: 0, 0, 0)
font = cv2.FONT_HERSHEY_COMPLEX
text_color = (255, 255, 255)  # White text (RGB: 255, 255, 255)
cv2.putText(img, 'HARI PRASATH', (60, 70), font, 2, text_color, 5, cv2.LINE_AA)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/d89b74c4-0547-4633-883d-9a048f0f0143)


```
# Create the structuring element
kernel = np.ones((5,5),np.uint8)
kernel1 = cv2.getStructuringElement(cv2.MORPH_CROSS,(5,5))
cv2.erode(img,kernel)
```
```
# Erode the image

img_erode = cv2.erode(img,kernel1)
plt.imshow(img_erode)
plt.axis('off')
```
### Display the Eroded Image
![image](https://github.com/user-attachments/assets/a1896880-dd15-44cb-9ca2-f1bb46b33110)

```
# Dilate the image
img_dilate = cv2.dilate(img,kernel1)
plt.imshow(img_dilate)
plt.axis('off')

```
### Display the Dilated Image
![image](https://github.com/user-attachments/assets/4dd5927c-ce34-4eac-973b-88b48a9fc0ec)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
