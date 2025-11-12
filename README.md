# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('imgme.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 13, 130)

plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)


plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')

```
## Output

### Input image and grayscale image

<img width="514" height="508" alt="image" src="https://github.com/user-attachments/assets/d0179628-a017-406a-afb3-e59373ec271a" />
<img width="546" height="518" alt="image" src="https://github.com/user-attachments/assets/dbf93d04-a701-41a7-9970-0cae41feb5a2" />




### Canny Edge detector output

<img width="519" height="510" alt="image" src="https://github.com/user-attachments/assets/b27316e2-600f-45ed-ab72-63387e446a5d" />



### Display the result of Hough transform
<img width="536" height="520" alt="image" src="https://github.com/user-attachments/assets/8e947162-71e3-4da4-9654-9d38cfad0f3d" />


## Result:
Thus the code to perform Edge detection using Hough Transform was written and executed successfully.
