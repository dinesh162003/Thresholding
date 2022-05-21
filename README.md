# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

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
Display the results.

## PROGRAM:
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("Dhoni.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("Dhoni.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_d1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_d2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_d3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_d4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_d5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_d7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_d8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_d6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_d1,thresh_d2,thresh_d3,thresh_d4,thresh_d5,thresh_d6,thresh_d7,thresh_d8]
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
## OUTPUT:

### Original Image and Grayscale Image

![image](https://user-images.githubusercontent.com/75235159/169637681-100c3c13-8dd3-41c1-bdbd-5137d050a5ae.png)


### Global Thresholding

![image](https://user-images.githubusercontent.com/75235159/169637695-25c6ae2a-3306-469e-a7ad-22b15833607c.png)

![image](https://user-images.githubusercontent.com/75235159/169637713-c1423fab-b499-4994-8cbe-ff11e53ec62b.png)


### Adaptive Thresholding

![image](https://user-images.githubusercontent.com/75235159/169637733-aaac73e9-9d22-49f4-85c3-a86cbea3e249.png)


### Optimum Global Thesholding using Otsu's Method

![image](https://user-images.githubusercontent.com/75235159/169637740-a9282be8-cb11-4132-92ba-34bb33825ee5.png)


## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
