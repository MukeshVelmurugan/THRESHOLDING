# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
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

## Program

```
Developed by: MUKESH V
Register No: 212222230086
```

### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```python
image = cv2.imread("elephant.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("elephant.jpg",0)
```

### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

### Display the results
```python
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
![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/467e168a-409b-4573-89fd-80ae8acaa10c)



### Global Thresholding
![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/56dfe2e7-e61f-4db6-a7eb-24173541a1f8)

![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/503f5ea4-6378-4465-a25d-bddf9679fab5)

![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/073e5328-7343-4564-ad85-568357824c9f)

![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/843c2e19-c8e8-47fc-a2b5-425468f08589)

![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/4aeeb902-3731-4631-a35e-3f10cc3da477)





### Adaptive Thresholding
![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/470fdacd-e7dd-466c-8554-e2534cf7456e)
![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/bb1d358e-3444-4a1d-845f-9eea0db73771)



### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/MukeshVelmurugan/THRESHOLDING/assets/118707363/0fa858cf-88e4-401e-915d-7b6ea32b7262)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

