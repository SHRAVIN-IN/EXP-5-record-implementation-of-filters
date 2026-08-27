
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

```import cv2
import matplotlib.pyplot as plt
import numpy as np

# Load Image
image1 = cv2.imread("saveetha.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

# 1. Averaging Filter
kernel = np.ones((11,11), np.float32) / 169
average = cv2.filter2D(image2, -1, kernel)

# 2. Weighted Averaging Filter
kernel1 = np.array([[1,2,1],
                    [2,4,2],
                    [1,2,1]]) / 16
weighted = cv2.filter2D(image2, -1, kernel1)

# 3. Gaussian Filter
gaussian = cv2.GaussianBlur(image2, (33,33), 0)

# 4. Median Filter
median = cv2.medianBlur(image2, 13)

# 5. Laplacian Linear Kernel
kernel2 = np.array([[-1,-1,-1],
                    [2,-2,1],
                    [2,1,-1]])
laplacian_kernel = cv2.filter2D(image2, -1, kernel2)

# 6. Laplacian Operator
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

# Display All Results
plt.figure(figsize=(12,10))

plt.subplot(2,4,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(2,4,2)
plt.imshow(average)
plt.title("Average Filter")
plt.axis("off")

plt.subplot(2,4,3)
plt.imshow(weighted)
plt.title("Weighted Average")
plt.axis("off")

plt.subplot(2,4,4)
plt.imshow(gaussian)
plt.title("Gaussian Blur")
plt.axis("off")

plt.subplot(2,4,5)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")

plt.subplot(2,4,6)
plt.imshow(laplacian_kernel)
plt.title("Laplacian Kernel")
plt.axis("off")

plt.subplot(2,4,7)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")

plt.tight_layout()
plt.show()
```

##  Output
<img width="515" height="370" alt="dipexx5" src="https://github.com/user-attachments/assets/c83cd2ab-f175-49b1-a1bd-d2163024a0d0" />
<img width="515" height="370" alt="dipexx4" src="https://github.com/user-attachments/assets/02fab5d0-72ad-4c6a-b582-144e1e4fd4fc" />
<img width="515" height="370" alt="dipexx3" src="https://github.com/user-attachments/assets/e72f1240-7059-42f8-aec3-1e9485ff5715" />
<img width="717" height="251" alt="dipexx" src="https://github.com/user-attachments/assets/ed398271-c923-42ec-80a6-94ae52828274" />
<img width="515" height="370" alt="dipexx1" src="https://github.com/user-attachments/assets/279ad5fb-e71a-46df-a1e0-af236f5d82f7" />
<img width="515" height="370" alt="dipexx2" src="https://github.com/user-attachments/assets/150c42e0-e874-4a58-a3bc-63e95cccf71f" />

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
