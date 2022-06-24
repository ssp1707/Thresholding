# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results

## Program

```python
Developed By: S. Sanjna Priya
Registration Number: 212220230043
```

# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
# Read the Image and convert to grayscale
 ```
image=cv2.imread("simp.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("simp.jpg",0)
```

# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```

## Output

### Original Image

![9 1](https://user-images.githubusercontent.com/75234965/169637883-815d3b10-781d-4097-ae22-108be0dd8e38.PNG)

### Global Thresholding

![9 2](https://user-images.githubusercontent.com/75234965/169637950-8b58f0e2-7ba8-4287-bc6d-ab4751a8f031.PNG)

![9 3](https://user-images.githubusercontent.com/75234965/169637954-cbfa1108-dacb-464b-866c-2ca7eb4b9414.PNG)

![9 4](https://user-images.githubusercontent.com/75234965/169637959-6912c0ea-dd6a-4d28-bfcf-9b083115d04d.PNG)

![9 5](https://user-images.githubusercontent.com/75234965/169637962-8db88786-1b2c-414b-8410-e0781669b394.PNG)

![9 6](https://user-images.githubusercontent.com/75234965/169637966-c10cc043-12a8-4289-8cb4-61bad226f90b.PNG)

### Adaptive Thresholding

![9 8](https://user-images.githubusercontent.com/75234965/169638015-c1603c2e-fa5b-4342-a1cc-42c2af7d159b.PNG)

![9 9](https://user-images.githubusercontent.com/75234965/169638039-363d29f7-d906-46ca-ba16-732009cb57b1.PNG)

### Optimum Global Thesholding using Otsu's Method

![9 7](https://user-images.githubusercontent.com/75234965/169638010-f32740a0-bce7-4523-b757-3604c7dde1e4.PNG)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

