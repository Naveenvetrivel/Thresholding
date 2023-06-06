## Thresholding of Images
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

### Software Required
Anaconda - Python 3.7
OpenCV
### Algorithm
## Step 1:
Load the necessary packages.

## Step 2:
Read the Image and convert to grayscale.

## Step 3:
Use Global thresholding to segment the image.

## Step 4:
Use Adaptive thresholding to segment the image.

## Step 5:
Use Otsu's method to segment the image.

## Step 6:
Display the results.

Program
Developed by: NAVEENKUMAR V
Register Number: 212221230068
# Load the necessary packages
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt
~~~

# Read the Image and convert to grayscale
~~~
image = cv2.imread("picture (1).jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("picture (1).jpg",0)
~~~
# Use Global thresholding to segment the image
~~~
ret,thresh_img1 = cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
~~~
# Use Adaptive thresholding to segment the image
~~~
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
~~~
# Use Otsu's method to segment the image 
~~~
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
~~~
# Display the results
~~~
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
    plt.subplot(1,2,1)
    plt.title("Original Image")    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
    ~~~
## Output

### Original Image
![image](https://github.com/Naveenvetrivel/Thresholding/assets/94165322/f78c686f-9c21-4bf5-898f-75a4ca6a6946)


### Global Thresholding
![image](https://github.com/Naveenvetrivel/Thresholding/assets/94165322/4652e939-058d-4698-900b-57ad906ca556)
![image](https://github.com/Naveenvetrivel/Thresholding/assets/94165322/21b78712-c9be-47b5-80d2-b2357f4356cb)

### Adaptive Thresholding
![image](https://github.com/Naveenvetrivel/Thresholding/assets/94165322/07de74ed-6cbb-47f0-a4a1-1b5bcd11cd88)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Naveenvetrivel/Thresholding/assets/94165322/cee290fb-a7e7-43e2-97af-ee6597156e7c)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

