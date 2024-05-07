# EX-07 EDGE LINKING HOUGH TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.

## Program:
 ### NAME: Karthick P
 ### REG NO: 212222100021

### Read image and convert it to grayscale image
```PYTHON
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("7 d.png",0)
img_c=cv2.imread("7 d.png",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Find the edges in the image using canny detector and display
```PYTHON
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```PYTHON
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```PYTHON
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```PYTHON
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output:

### Input image and grayscale image
![7 dip ](https://github.com/KRISHNARAJ-D/Edge-Linking-using-Hough-Transformm/assets/119559695/04761f8b-68ad-4588-9be7-b4d94df3bdd0)


<br>

### Canny Edge detector output
![7 dip 2](https://github.com/KRISHNARAJ-D/Edge-Linking-using-Hough-Transformm/assets/119559695/2a73cca1-9db6-4701-a119-1dd987d11961)



<br>

### Display the result of Hough transform
![7 dip 3](https://github.com/KRISHNARAJ-D/Edge-Linking-using-Hough-Transformm/assets/119559695/05f02611-f354-40e0-9332-b836af92d281)



<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
