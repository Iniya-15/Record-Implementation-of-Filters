# Record-Implementation-of-Filters

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---
## Program: 
### Developed By
- **Name:** Iniya E
- **Register No:** 212224230096

---
### 1. Smoothing Filters
i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("mk.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

##  Output

### Smoothing Filters

- Averaging filter produces blurred image
  <img width="756" height="528" alt="image" src="https://github.com/user-attachments/assets/6ad9d70c-3924-44f3-8f5d-d4959d244b8b" />

- Weighted averaging provides smoother result with less distortion
 <img width="692" height="466" alt="image" src="https://github.com/user-attachments/assets/89b90988-0c4d-4cf8-a99a-ff73ed0132c8" />

- Gaussian filter preserves edges better while reducing noise
 <img width="676" height="475" alt="image" src="https://github.com/user-attachments/assets/cb8f69ab-ed01-4180-8c34-ae13f91c2d48" />
 
 
- Median filter removes salt-and-pepper noise effectively  
<img width="757" height="530" alt="image" src="https://github.com/user-attachments/assets/67a3ddda-0913-465c-afb0-02bcbfd24493" />


###  Sharpening Filters

- Laplacian kernel enhances edges and fine details
 <img width="676" height="481" alt="image" src="https://github.com/user-attachments/assets/86cc649f-c6fa-4b16-87df-98a80fedfae6" />


  
- Laplacian operator detects edges clearly in grayscale  

<img width="668" height="466" alt="image" src="https://github.com/user-attachments/assets/bed5cce0-3e40-476a-821e-7cd95805b432" />

---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
