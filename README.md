# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---



### Developed By:
**Name:** SABEESHWARAN. P

**Register Number:** 212225230234

**Date:** 26.07.2026

## Program
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)
```
```python
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)
```
```python
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
```
```python
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
```python
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
```python
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.ashow()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed



<img width="825" height="500" alt="image" src="https://github.com/user-attachments/assets/2ad0ba95-f37d-4883-a798-9b18d9723cf4" />

 
- Histogram of original grayscale image is plotted

 <img width="841" height="557" alt="image" src="https://github.com/user-attachments/assets/56984687-2695-4550-8340-24687052f7cd" />


- Enhanced image after histogram equalization is displayed

<img width="807" height="495" alt="image" src="https://github.com/user-attachments/assets/beacf85b-056a-4af0-a8de-1322b72ed48b" />



- Histogram of enhanced grayscale image shows improved contrast  

<img width="861" height="556" alt="image" src="https://github.com/user-attachments/assets/639bef5e-e97d-4ade-b5f9-4c17a39f8d7f" />



### Color Image Histogram Equalization

- Original color image is displayed

<img width="606" height="401" alt="image" src="https://github.com/user-attachments/assets/0a46a40f-a785-4d69-ab41-b0d4a191128b" />

 
- Enhanced image after HSV-based equalization is displayed

<img width="756" height="507" alt="image" src="https://github.com/user-attachments/assets/fb461eae-4d25-4f23-910b-aed7cb501863" />


- Histogram of enhanced image shows better intensity distribution

<img width="790" height="556" alt="image" src="https://github.com/user-attachments/assets/4ae617ca-fbb9-4e4f-a160-1cde51ff5e59" />



---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
