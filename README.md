# Thresholding of Images
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
Use Otsu's method to segment the image.
### Step6:
Display the results.

### Program

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt




# Read the Image and convert to grayscale
ori_img=cv2.imread('Garfield.png')
ori_img=cv2.resize(ori_img,(460,250))
gray_img=cv2.cvtColor(ori_img,cv2.COLOR_BGR2GRAY)



# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)



# Use Adaptive thresholding to segment the image
thresh_img6=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img7=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)




# Use Otsu's method to segment the image 
ret,thresh_img8=cv2.threshold(gray_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)



# Display the results
cv2.imshow('original',ori_img)
cv2.imshow('gray',gray_img)
cv2.imshow('binary threshold',thresh_img1)
cv2.imshow('binary to inverse threshold',thresh_img2)
cv2.imshow('to zero threshold',thresh_img3)
cv2.imshow('to zero to inverse threshold',thresh_img4)
cv2.imshow('truncate threshold',thresh_img5)
cv2.imshow('mean adaptive threshold',thresh_img6)
cv2.imshow('gaussian adaptive threshold',thresh_img7)
cv2.imshow('otsu thresold',thresh_img8)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output

### Original Image
<br>
<br>
<br>
<br>
<br>
<img width="336" alt="1" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/4c38d051-f408-4951-85cc-fde682fbe0fb">
<img width="339" alt="2" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/e8806536-cbe9-4b32-aa43-4b1140f466c0">

### Global Thresholding
<br>
<br>
<img width="339" alt="2" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/e8806536-cbe9-4b32-aa43-4b1140f466c0">
<img width="339" alt="3" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/79af2fc9-948a-4c0f-a6d0-c3cb25a01986"> 
<img width="340" alt="4" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/03b817dc-6027-4d1a-b841-1b4c080caf4f"> 
<img width="346" alt="5" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/04bc2ffa-4ada-4c1f-b427-34672dfd8fec">
<img width="338" alt="6" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/59de3a0c-6d17-4bc1-a05e-8469b84fac29"> 
<img width="342" alt="7" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/5d6d0e7a-ad05-4480-860c-6101875c0e3b">


<br>
<br>

### Adaptive Thresholding
<br>
<br>
<img width="343" alt="8" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/5cf04b84-9e67-4222-ba04-e4bead65ac35">
<img width="342" alt="9" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/27ecc1e0-e3e2-4500-9b03-f51abf019af4">


### Optimum Global Thesholding using Otsu's Method
<br>
<br>
<br>
<br>
<br>
<img width="339" alt="2" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/4c06d1be-8197-4122-8bf6-894b2a58e368">
<img width="341" alt="10" src="https://github.com/DhivyaShri484/Thresholding/assets/94505585/6f6ddb73-db63-435d-9736-2098d727a6c3">


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

