
# Image Smoothing and Sharpening Using OpenCV

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

##  Developed By

- **Name:** S.jana shravin
- **Register No:** 212224243003

---
## program

```
import cv2
import matplotlib.pyplot as plt
import numpy as np

# Step 1: Load the image
image1 = cv2.imread("shravin.jpeg")

# Step 2: Convert BGR to RGB
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

# Step 3: Average Filter
kernel = np.ones((11,11), np.float32) / 169
image3 = cv2.filter2D(image2, -1, kernel)

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

# Step 4: Weighted Average Filter
kernel1 = np.array([[1,2,1],
                    [2,4,2],
                    [1,2,1]]) / 16

image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
image3 = cv2.filter2D(image2, -1, kernel1)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

# Step 5: Gaussian Blur
gaussian_blur = cv2.GaussianBlur(image2, (33,33), 0, 0)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

# Step 6: Median Blur
median = cv2.medianBlur(image2, 13)

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

# Step 7: Laplacian Kernel
kernel2 = np.array([[-1,-1,-1],
                    [2,-2,1],
                    [2,1,-1]])

image3 = cv2.filter2D(image2, -1, kernel2)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

# Step 8: Laplacian Operator
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

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
<img width="516" height="266" alt="download" src="https://github.com/user-attachments/assets/a5b41c2e-9791-4ab5-a2c2-c1d29621995b" />
<img width="717" height="358" alt="download" src="https://github.com/user-attachments/assets/fc49fbb9-eb09-4fa2-9465-d4b9ecc954e9" />
<img width="516" height="266" alt="download" src="https://github.com/user-attachments/assets/a24f7a50-e78f-4b0c-95f9-5222cb3598a0" />
<img width="717" height="358" alt="download" src="https://github.com/user-attachments/assets/5a758a1d-1da2-468b-b159-18af28ad2379" />
<img width="533" height="266" alt="download" src="https://github.com/user-attachments/assets/1e0082d6-b382-4889-92c5-2912322ae818" />
<img width="516" height="266" alt="download" src="https://github.com/user-attachments/assets/7b5a6137-0016-478b-9a64-bb044894f07a" />

### Smoothing Filters

- Averaging filter produces blurred image  
- Weighted averaging provides smoother result with less distortion  
- Gaussian filter preserves edges better while reducing noise  
- Median filter removes salt-and-pepper noise effectively  

###  Sharpening Filters

- Laplacian kernel enhances edges and fine details  
- Laplacian operator detects edges clearly in grayscale  

---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
