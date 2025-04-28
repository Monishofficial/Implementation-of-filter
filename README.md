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

img_path = r"C:\Users\admin\Downloads\eif.jpeg"  # Change this to your correct path

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

![Screenshot 2025-04-23 142842](https://github.com/user-attachments/assets/4d87c117-34d1-46ef-a0ed-3665ee2176a8)
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

![Screenshot 2025-04-23 142937](https://github.com/user-attachments/assets/d0434972-cbfb-4dec-b59f-73fe1bda88ce)
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
![Screenshot 2025-04-23 143027](https://github.com/user-attachments/assets/5f77a941-9436-49b3-ae6e-5ecab433e502)
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
![Screenshot 2025-04-23 143104](https://github.com/user-attachments/assets/88dd1d59-a205-4f03-9cdb-3074e2cc91bb)
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
![Screenshot 2025-04-23 143144](https://github.com/user-attachments/assets/943ff1da-ce99-4ab8-8832-1515ea50b54e)
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
![Screenshot 2025-04-23 143216](https://github.com/user-attachments/assets/bb1d2a85-afed-41fa-8312-fe5538e23664)
</br>
## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
