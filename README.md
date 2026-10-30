# Exp-5--Record-Implementation-of-Filters
## NAME : KAVINAYA V
## REGISTER NO : 212225230133


## Aim

To implement filters for smoothing and sharpening images in the spatial domain.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import the required libraries.

### Step 2
Read the image and convert it from BGR to RGB.

### Step 3
Apply the required smoothing and sharpening filters to the image separately.

### Step 4
Plot and display the original and filtered images using `matplotlib.pyplot`.

### Step 5
End the program.

## Program

## 1. Smoothing Filters

### i) Using Averaging Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("ex1 image.jpeg")
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

### ii) Using Weighted Averaging Filter

```python
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
plt.show())
```

### iii) Using Gaussian Filter

```python
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

### iv) Using Median Filter

```python
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

## 2. Sharpening Filters

### i) Using Laplacian Linear Kernel

```python
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

### ii) Using Laplacian Operator

```python
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

## Output

### 1. Smoothing Filters
#### i) Using Averaging Filter
<img width="1072" height="417" alt="Screenshot 2026-10-30 144021" src="https://github.com/user-attachments/assets/5974273c-f5e7-4c2e-972d-dca274b5c26a" />


#### ii) Using Weighted Averaging Filter
<img width="792" height="310" alt="Screenshot 2026-10-30 144044" src="https://github.com/user-attachments/assets/24acd2d8-85bc-40c2-8fc3-3352c18a1e22" />


#### iii) Using Gaussian Filter
<img width="768" height="312" alt="Screenshot 2026-10-30 144052" src="https://github.com/user-attachments/assets/2a0f0dae-d49c-403d-bf42-6d70529d3e87" />


#### iv) Using Median Filter
<img width="1071" height="412" alt="Screenshot 2026-10-30 144059" src="https://github.com/user-attachments/assets/176fdc44-0f3e-4c6a-b776-7cbcaf1ce979" />


### 2. Sharpening Filters

#### i) Using Laplacian Kernel
<img width="767" height="311" alt="Screenshot 2026-10-30 144129" src="https://github.com/user-attachments/assets/cf3379b2-f8a1-49fa-9f2a-0b752d792291" />


#### ii) Using Laplacian Operator
![Uploading Screenshot 2026-10-30 144137.png…]()


## Result

Thus, filters were implemented for smoothing and sharpening images in the spatial domain using OpenCV and Python.
