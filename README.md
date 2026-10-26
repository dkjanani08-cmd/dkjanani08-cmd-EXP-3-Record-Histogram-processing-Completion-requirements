# Histogram-of-an-images

## *Name:* SHRIVARSHAN P G  
## *Register Number:* 212225240146


## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

**Developed By:** SHRIVARSHAN P G

**Register Number:** 212225240146

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

## Output

### Input Grayscale Image

<img width="330" height="530" alt="image" src="https://github.com/user-attachments/assets/2a81ce4b-3ca6-47cd-a895-05d4027b83a9" />


### Input Grayscale Image Range

<img width="732" height="525" alt="image" src="https://github.com/user-attachments/assets/99a485d9-eb13-4859-80b3-69a8d6b0928d" />


### Input Grayscale Image Equalized Histogram

<img width="752" height="533" alt="image" src="https://github.com/user-attachments/assets/210543ff-d744-420e-96cc-9dec30fb9bc1" />


### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="355" height="542" alt="image" src="https://github.com/user-attachments/assets/a7184c45-db5f-48a1-835e-8e82019c247d" />


### Equalized Image

<img width="376" height="535" alt="image" src="https://github.com/user-attachments/assets/816419ec-58b2-47c6-8c89-aad7992ecee8" />


### Equalized Histogram

<img width="752" height="538" alt="image" src="https://github.com/user-attachments/assets/e37eddf1-134e-4837-8c95-157c064608b5" />


### Final Output of Original Image and Equalized 

<img width="1368" height="517" alt="image" src="https://github.com/user-attachments/assets/6d71da8b-17ad-4a01-a0b7-03a918ee9b15" />


### Final Output of Original Image and its Histogram Equalized

<img width="1392" height="402" alt="image" src="https://github.com/user-attachments/assets/fc9cb4ec-0988-4543-8bc8-fd17f41fd322" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
