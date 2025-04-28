# Exp-5 Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

1.Import the required libraries.

2.Convert the image from BGR to RGB.

3.Apply the required filters for the image separately.

4.Plot the original and filtered image by using matplotlib.pyplot.

5.End of Program

## Program:
### Developed By   : MONISH N
### Register Number: 212223240097
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
import os

img_path = r"C:\Users\admin\Desktop\butterfly.png"  # Change this to your correct path

if not os.path.exists(img_path):
    print(" Image not found. Check the file path.")
else:
    image1 = cv2.imread(img_path)
    if image1 is None:
        print(" Image could not be loaded (possibly corrupted or unsupported format).")
    else:
        image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
        kernel = np.ones((11, 11), np.float32) / 169
        image3 = cv2.filter2D(image2, -1, kernel)

        plt.figure(figsize=(9, 9))
        plt.subplot(1, 2, 1)
        plt.imshow(image2)
        plt.title("Original Image")
        plt.axis("off")

        plt.subplot(1, 2, 2)
        plt.imshow(image3)
        plt.title("Average Filter Image")
        plt.axis("off")
        plt.show()


```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 211655](https://github.com/user-attachments/assets/854a9536-1be3-4f46-9e05-7f845b10f9b0)

ii) Using Weighted Averaging Filter
```Python
# Developed By: MONISH N
# Register Number: 212223240097
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 211804](https://github.com/user-attachments/assets/62c1886b-7093-4cbc-8616-2f87d437494a)

iii) Using Gaussian Filter
```Python
# Developed By: MONISH N
# Register Number: 212223240097
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 211826](https://github.com/user-attachments/assets/6ad41f38-97f0-483b-a788-043ac6085ce9)

iv)Using Median Filter
```Python
# Developed By: MONISH N
# Register Number: 212223240097
median = cv2.medianBlur(image2, 13)
plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct color display
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 211851](https://github.com/user-attachments/assets/3d557005-1c25-40a4-b24c-c9ade29f27f1)
### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
# Developed By: HAREESH R
# Register Number: 212223230068

kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 211937](https://github.com/user-attachments/assets/56154de9-c084-4bf1-883f-cba2eb24a222)

ii) Using Laplacian Operator
```Python
# Developed By: MONISH N
# Register Number: 212223240097
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```
<h2>OUTPUT</h2>

![Screenshot 2025-04-28 212007](https://github.com/user-attachments/assets/fc64b78f-67cd-43e7-89f1-6dffc7596492)

</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
