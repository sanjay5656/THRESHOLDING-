# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import necessary packages
<br>
### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image and display the results.
<br>

## Program
### Load the necessary packages:
```python

import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale:
```python
img = cv2.imread("300.webp",1)
img = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
img_gry = cv2.imread("300.webp",0)
```
### Use Global thresholding to segment the image:
```python
r,t_img1=cv2.threshold(img_gry,86,255,cv2.THRESH_BINARY)
r,t_img2=cv2.threshold(img_gry,86,255,cv2.THRESH_BINARY_INV)
r,t_img3=cv2.threshold(img_gry,86,255,cv2.THRESH_TOZERO)
r,t_img4=cv2.threshold(img_gry,86,255,cv2.THRESH_TOZERO_INV)
r,t_img5=cv2.threshold(img_gry,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image:
```python
t_img7=cv2.adaptiveThreshold(img_gry,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
t_img8=cv2.adaptiveThreshold(img_gry,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Use Otsu's method to segment the image:
```python
ret,t_img6=cv2.threshold(img_gry,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

### Display the results:
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
imgs=[img_gry,t_img1,t_img2,t_img3,t_img4,t_img5,t_img6,t_img7,t_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(img)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(imgs[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image:
![o1](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/67c5cf1e-67e6-42bd-ac1e-e3f4058f775a)

### Global Thresholding:
![o2](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/d4725a14-cfb2-4f3f-9a94-8db261900eac)

![o3](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/ca725f89-7250-40ce-a370-d674d2d65ee3)

![o4](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/cacf2e84-3724-4b14-8e04-7350e8129c6e)

![o5](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/15a149f7-ff34-4a2c-8cc3-1b06bbe13993)

![o6](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/ed90cdbf-631e-46ab-9465-4fcc6c75bae0)

### Adaptive Thresholding:
![o7](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/df244b09-d4ea-4010-a742-c4ac420fbf64)

![o8](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/5a92750e-176f-47a4-a3e1-6dea0f1d4a26)

### Optimum Global Thesholding using Otsu's Method:
![o9](https://github.com/sanjay5656/THRESHOLDING-/assets/115128955/fc218ffc-4227-4305-8770-db8b8f826f00)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
