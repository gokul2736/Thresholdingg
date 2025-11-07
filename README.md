# EX-08 THRESHOLDING
## Name: Markandeyan Gokul
## Reg no:212224240086

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
Use Otsu's method to segment the image and display the results

## Program
# Load the necessary packages
```
import cv2
import matplotlib.pyplot as plt
```
# Read the Image and convert to grayscale
```
image=cv2.imread('image01.png')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
```
# Original image: 
```
plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
# Use Global thresholding to segment the image
```
_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)
```
# Use Adaptive thresholding to segment the image
```
adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```
# Use Otsu's method to segment the image 
```
_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
# Global Thresholding:
```
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```
# Adaptive Thresholding:
```
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```
# Otsu's Method:
```
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```
# Show the plot:
```
plt.tight_layout()
plt.show()
```
## Output
### Original Image
<img width="669" height="276" alt="Screenshot 2025-10-10 190842" src="https://github.com/user-attachments/assets/e5e13a30-f77c-4b90-9023-69c1a8c9b2fc" />

### Global Thresholding
<img width="670" height="272" alt="Screenshot 2025-10-10 190853" src="https://github.com/user-attachments/assets/dbb83798-75ea-4460-969e-8550c7cd400f" />

### Adaptive Thresholding
<img width="668" height="270" alt="Screenshot 2025-10-10 190901" src="https://github.com/user-attachments/assets/9dd5cb46-37df-4345-93af-cede5861739f" />

### Optimum Global Thesholding using Otsu's Method
<img width="679" height="277" alt="Screenshot 2025-10-10 190908" src="https://github.com/user-attachments/assets/48fa3447-4364-48ce-a5b1-06e8aaef324b" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
