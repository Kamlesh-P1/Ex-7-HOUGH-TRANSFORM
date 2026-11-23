# HOUGH-TRANSFORM

# Developed By
# Name : KAMLESH P
# Reg No : 212225240067

## Aim
To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

## Learning Objective

- Understand each stage of image processing

- Learn how to build a complete computer vision pipeline

- Practice writing code in guided sections


## Software Used

- Anaconda – Python 3.7

- Jupyter Notebook / VS Code

- OpenCV (cv2)

- NumPy

- Matplotlib

## Algorithm & Explanation

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt


image = cv2.imread('srii.jpg')



gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)



plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Input Image")
plt.axis('off')



plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)


plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')


lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)


for line in lines:
    x1, y1, x2, y2 = line.reshape(-1) 
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2) 


plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```

## output

Original Image

<img width="323" height="457" alt="image" src="https://github.com/user-attachments/assets/715b9de1-427c-4df3-9706-76d98ae7128c" />


Grayscale Image

<img width="318" height="457" alt="Screenshot 2026-11-23 192130" src="https://github.com/user-attachments/assets/ffc325db-87cc-43a0-a485-f4023566bf2d" />



Canny Edge Detector

<img width="345" height="463" alt="image" src="https://github.com/user-attachments/assets/890684c3-ee90-4056-9cde-dd90a98c9e59" />


Result Of Hough Transform

<img width="333" height="457" alt="image" src="https://github.com/user-attachments/assets/51149363-8586-49a1-a695-4ec8745ec068" />



## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively







