# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br> Load the necessary packages.

### Step2:
<br> Read the Image and convert to grayscale

### Step3:
<br> Use Global thresholding to segment the image.

### Step4:
<br> Use Adaptive thresholding to segment the image.

### Step5:
<br> Use Otsu's method to segment the image and display the results.

## Developed By 
```
Name: KEERTHANA C
Register Number : 212224220047
```
## Program

# Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
# Read the Image and convert to grayscale
```
image = cv2.imread('zebra.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('zebra.jpg',0)
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

<img width="498" height="183" alt="image" src="https://github.com/user-attachments/assets/90b93a12-f365-41cf-9272-5e1ec6693729" />

### Global Thresholding

<img width="306" height="567" alt="image" src="https://github.com/user-attachments/assets/5e5de447-c610-4fcd-aeca-c73f3ab3cf71" />

### Adaptive Thresholding
<img width="531" height="406" alt="image" src="https://github.com/user-attachments/assets/21dd29e0-b156-47e8-bd50-ee4751f2c828" />


### Optimum Global Thesholding using Otsu's Method
<img width="535" height="200" alt="image" src="https://github.com/user-attachments/assets/b7ea1669-858a-429e-b809-05428463b327" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
