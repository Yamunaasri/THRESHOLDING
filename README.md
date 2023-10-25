# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
DEVELOPED BY: T S YAMUNAASRI
REGISTER NO: 212222240117
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("disney.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("disney.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
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
![Screenshot 2023-10-25 094004](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/2e029ef4-1738-41e2-87e8-5b23c62fa188)


### Global Thresholding
![Screenshot 2023-10-25 094127](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/f849fbb3-5298-47e3-b19c-dc4c0860214d)

![Screenshot 2023-10-25 094143](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/e4c5e8cc-ca3f-4a52-b1cc-e440332fd6ad)

![Screenshot 2023-10-25 094155](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/bb2a0d67-3abd-47e1-8675-62ac76f73635)

![Screenshot 2023-10-25 094214](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/2354404b-fea9-449e-8544-7dfefe14babe)

![Screenshot 2023-10-25 094233](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/a6a5872a-7eae-4906-9ef6-68addd815d03)

### Adaptive Thresholding
![Screenshot 2023-10-25 094621](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/3d524d34-d22f-4380-b7b0-160683c4d127)

![Screenshot 2023-10-25 094632](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/8779aef7-c48d-4169-8552-8cbfda919c8d)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2023-10-25 094733](https://github.com/Yamunaasri/THRESHOLDING/assets/115707860/0eb838d1-f05a-4dd8-bba2-31c1472b16e2)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

