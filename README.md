# EXPERIMENT NO : 3
# Histogram-of-an-images

### NAME : AVINASH T
### REG NO : 212223230026
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1:
Read the gray and color image using imread()

Step2:
Print the image using imshow().

Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

Step5:
The Histogram of gray scale image and color image is shown.

## Program:
# Developed By AVINASH T
# Register Number: 212223230026

```c
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```

#### Display the images

```c
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```

#### Equalize histogram
```c
img_eq = cv2.equalizeHist(img)
Display the images.
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
#### Display the images.
```c
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

#### Read the color image.
```c
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
Convert to HSV.
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
#### Perform histogram equalization only on the V channel, for value intensity.
```c
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
Convert back to BGR format.
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```

#### Display the Equalized Image.
```c
plt.imshow(img_eq[:,:,::-1]) 
plt.title('Equalized Image')
plt.show()
```
#### Histogram Equalized
```c
plt.hist(img_eq.ravel(),256,range = [0, 256])
plt.title('Histogram Equalized')
plt.show()
```

#### Display the images.
```c
plt.figure(figsize = (20,10))
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')
plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.subplot(223)
plt.hist(img.ravel(),256,range = [0, 256])
plt.title('Original Image')
plt.subplot(224)
plt.hist(img_eq.ravel(),256,range = [0, 256])
plt.title('Histogram Equalized');plt.show()
```

#### Display the histograms.
```c
plt.figure(figsize = [15,4])
plt.subplot(121)
plt.hist(img.ravel(),256,range = [0, 256])
plt.title('Original Image')
plt.subplot(122)
plt.hist(img_eq.ravel(),256,range = [0, 256])
plt.title('Histogram Equalized')
```
## Output:
### Histogram Equalized


<img width="1090" height="486" alt="image" src="https://github.com/user-attachments/assets/4a7a3ebc-d167-4215-9e09-898169538640" />

## Result:
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
