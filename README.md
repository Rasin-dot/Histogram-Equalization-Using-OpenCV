# Histogram Equalization Using OpenCV (Grayscale & Color Images)

### Developed By:
### Name : Rasindhan R

### Register No : 212224230222



## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image.
- Plot histogram of the grayscale image.
- Apply histogram equalization on the grayscale image.
- Read and display a color image.
- Convert the image to HSV color space.
- Apply histogram equalization on the Value (V) channel.
- Convert the enhanced image back to BGR format.
- Display original and enhanced images along with their histograms.

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
Read the  image deer.jpg in grayscale mode.

### Step 3:
Display the grayscale image.

### Step 4:
Plot the histogram of the grayscale image.

### Step 5:
Apply histogram equalization using `cv2.equalizeHist()`.

### Step 6:
Display the equalized histogram and enhanced grayscale image.

### Step 7:
Read the same image in color mode.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization to the V (Value) channel.

### Step 10:
Convert the enhanced HSV image back to BGR format.

### Step 11:
Display the original color image, equalized image, and their histograms.

---

# Program


## 1. Import the required libraries and read the grayscale image.

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```

---

## 2. Plot the histogram of the grayscale image.

```python
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()
```

---

## 3. Apply histogram equalization.

```python
img_eq = cv2.equalizeHist(img)
```

---

## 4. Display the histogram of the equalized image.

```python
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```

---

## 5. Display the equalized grayscale image.

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```

---

## 6. Read the image in color mode and convert to HSV.

```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```

---

## 7. Apply histogram equalization to the V channel.

```python
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```

---

## 8. Convert the enhanced HSV image back to BGR.

```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```

---

## 9. Display the original and equalized color images.

```python
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```

---

## 10. Display the original and equalized images along with their histograms.

```python
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

---

## Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed.
- <img width="487" height="471" alt="image" src="https://github.com/user-attachments/assets/debf0c86-b073-4dc6-9f44-96e3e6728e53" />

- Histogram of the original grayscale image is plotted.
- <img width="655" height="482" alt="image" src="https://github.com/user-attachments/assets/07ee8a83-457e-4662-8c7c-b3f834d2cc33" />

- Equalized grayscale image is displayed.
- <img width="641" height="481" alt="image" src="https://github.com/user-attachments/assets/7ee7aaf5-2785-4e1f-91d4-0acb99631cb6" />

- Histogram of the equalized image shows improved contrast.

- <img width="497" height="467" alt="image" src="https://github.com/user-attachments/assets/afe0b1bb-4e67-4b3b-bdcf-c34d3bc68daa" />
  
- <img width="632" height="315" alt="image" src="https://github.com/user-attachments/assets/122c6cbc-9e65-41f4-b3dd-7413fa6f0899" />

### Color Image Histogram Equalization

<img width="482" height="777" alt="image" src="https://github.com/user-attachments/assets/fec45b35-6db4-4519-b059-661254f29bce" />


<img width="473" height="778" alt="image" src="https://github.com/user-attachments/assets/c47e82db-8202-4ef9-8a66-b73c22a1256a" />


## Result

Thus, histogram equalization was successfully performed on both grayscale and color images using OpenCV. The contrast of the images was enhanced, improving the overall visual quality.
