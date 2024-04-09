# EX-9 THRESHOLDING
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE:** 09.04.2024<br>
### Aim: 
To segment the image using global thresholding,adaptive thresholding and Otsu's thresholding using OpenCV. 
### Software Required:
Anaconda - Python 3.7 , OpenCV
### Algorithm:
- Step1: Load the necessary packages.
- Step2: Read the Image and convert to grayscale.
- Step3: Use Global thresholding to segment the image.
- Step4: Use Adaptive thresholding to segment the image.
- Step5: Use Otsu's method to segment the image.
```
Developed By: SHALINI K
Register No: 212222240095
```
### Program:
- Load the necessary packages.
  ```Python
  import cv2
  import numpy as np
  import matplotlib.pyplot as plt
  ```
  - Read the Image and convert to grayscale.
  ```Python
  image=cv2.imread("exp5.jpg",1)
  image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
  image_gray=cv2.imread("exp5.jpg",0)
  ```
- Use Global thresholding to segment the image.
  ```Python
  ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
  ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
  ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
  ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
  ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
  ```
- Use Otsu's method to segment the image.
  ```Python
  ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
  ```
- Use Adaptive thresholding to segment the image.
  ```Python
  thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
  thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
  ```
- Display the results.
  ```Python
  titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
        ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
  images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
  plt.title("Original Image")
  plt.imshow(image)
  plt.axis("off")
  plt.show()
  for i in range(0,9):
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
  ```
### Output:
<div align="center">
  <img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/0b03028a-7c90-4c93-9e28-1af4a44de1ea">
  <img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/c1ff92d1-6eae-421c-bc1b-934e350dab4d">
</div>
<br>
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/f6703fb7-c468-4b20-8cad-795a284a04c9">
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/3bb49d73-04c3-4389-9851-c0743a1da687">
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/74a1eed0-7a6c-4887-af12-5f84ce96e5e1">
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/4e3fb14a-5412-4220-84b4-0bfb97d62b31">
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/956dc656-f408-4f6d-a169-94b9fbb6f90a">
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/46d83fd4-76d5-4a6d-b0bc-a344a2dbd8c1">
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/337b6a75-4124-438e-a59c-60a343f26ff5">
<img height=16% width=24% src="https://github.com/shalinikannan23/THRESHOLDING-/assets/118656529/8384ce2f-a6a3-49fc-ba19-7acede2b8bc3">


### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

