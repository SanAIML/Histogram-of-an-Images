# Histogram Equalization Using OpenCV (Grayscale & Color Images)
# Name: Sanchita Sandeep
# Reg No: 212224240142
## Aim:
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

1 Read and display a grayscale image
2 Plot histogram of the grayscale image
3 Apply histogram equalization on grayscale image
4 Read and display a color image
5 Plot histogram of B, G, R channels
6 Convert image to HSV color space
7 Apply histogram equalization on the Value (V) channel
8 Convert the enhanced image back to BGR format
9 Display original and enhanced images with histograms
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm:
```

1 Import the required libraries: OpenCV, NumPy, and Matplotlib.
2 Read the image parrot.jpg in grayscale format.
3 Display the grayscale image and plot its histogram.
4 Apply histogram equalization using cv2.equalizeHist() to enhance contrast.
5 Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.
6 Read the same image in color format.
7 Split the image into B, G, R channels and plot their histograms.
8 Convert the image from BGR to HSV color space.
9 Apply histogram equalization on the V (Value) channel.
10 Merge the channels and convert the image back to BGR format.
11 Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.
```

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('3E108C11-46EF-4E1E-A24B-ECB3E19B3DCA.png', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
img = cv2.imread('3E108C11-46EF-4E1E-A24B-ECB3E19B3DCA.png', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
## Output:
1) Grayscale image
<img width="342" height="434" alt="download" src="https://github.com/user-attachments/assets/f65b76e3-ab17-47a9-9b20-db1486e817aa" />
2) Histogram
<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/75c1c786-6f59-4368-94d5-18b60c686794" />
3) Equalized Histogram
<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/84b77277-3bc9-4302-b8aa-fbeb89c400cf" />
4) Equalized histogram image
<img width="342" height="434" alt="download" src="https://github.com/user-attachments/assets/74652cc4-6268-408f-923c-988de4fa950c" />
5) Equalized histogram for coloured image
<img width="342" height="434" alt="download" src="https://github.com/user-attachments/assets/6e85ee85-05e4-47eb-a531-2caa3d85b751" />
6) Equalized Histigram
<img width="547" height="434" alt="download" src="https://github.com/user-attachments/assets/5f552d72-a889-4b03-a2a3-edd85ca25bb0" />
7) Differentiation of Original Image and equalized image
<img width="1173" height="414" alt="download" src="https://github.com/user-attachments/assets/75961f7b-615d-4f6a-aa11-16af9143a0c7" />
8)Differentiation of Original Histogram and equalized Histogram
<img width="1214" height="372" alt="download" src="https://github.com/user-attachments/assets/0ea87f82-c38a-4b59-af66-320107709763" />

## Result:
Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.


















