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
- Jupyter Notebook / VS Code  
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

## Program


### Developed By:
**Name:** Venkata Mohan N

### Register No:
212224230298

```
# Import required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image in grayscale format.


img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

# Display the images.
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Plot the histogram of the grayscale image
assert np.array_equal(img ,cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE))
# Display the images
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

# Perform histogram equalization
img_eq = cv2.equalizeHist(img)

# Display [1] the Original Image (Gray Image) and its Histogram, and [2] the Enhanced Image and its Histogram using a 2×2 layout in Matplotlib.


plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

# Import required libraries
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()


#  Histogramm Equalization for color Image

# Read the color image.
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

# Convert to HSV.
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Perform histogram equalization only on the V channel, for value intensity.
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert back to BGR format.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

# Perform histogram equalization

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

# Convert back to BGR format

# Display the images.
#plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

# Display the histograms.
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```

---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed

- <img width="841" height="541" alt="image" src="https://github.com/user-attachments/assets/7096ad97-5d48-429f-a59e-ed5327eca80d" />

- Histogram of original grayscale image is plotted

- <img width="871" height="566" alt="image" src="https://github.com/user-attachments/assets/4eec4589-9fe6-4452-b254-b68312fbbec1" />

- Enhanced image after histogram equalization is displayed

- <img width="790" height="549" alt="image" src="https://github.com/user-attachments/assets/a0199496-3623-4b21-86b6-e5ea63cbcc4a" />

- Histogram of enhanced grayscale image shows improved contrast

- <img width="800" height="532" alt="image" src="https://github.com/user-attachments/assets/9657b1a6-d8a9-4b45-8c77-b4047c2432ee" />


### Color Image Histogram Equalization

- Original color image is displayed

- <img width="829" height="520" alt="image" src="https://github.com/user-attachments/assets/b840fdd1-c511-40d5-b49a-e047dd2a7a41" />

- Histogram of B, G, R channels is plotted

- <img width="859" height="575" alt="image" src="https://github.com/user-attachments/assets/b2b28a9b-c730-44e8-876f-0d4a9bfdbeaa" />

- Enhanced image after HSV-based equalization is displayed

<img width="875" height="577" alt="image" src="https://github.com/user-attachments/assets/196b5d62-8c72-48fb-8ae2-64811810c336" />

- Histogram of enhanced image shows better intensity distribution  


<img width="1529" height="538" alt="image" src="https://github.com/user-attachments/assets/05e9778a-12a1-4a68-9600-c305fc72b059" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
