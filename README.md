
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
### Developed By:SANTHANA LEKSHMI K
### Register No: 212222240091

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)

ret,frame=viedoCaptureObject.read()
cv2.imwrite("webcam_img.jpg",frame)

viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import numpy as np
import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()

cv2.imshow('captured_frame', frame)

cv2.waitKey(10000)


cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame

cv2.imshow('webcam_img.jpg',image)

cv2.waitKey(5000)  

image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)

cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame

cv2.imshow('captured_image1.jpg',image)

cv2.waitKey(5000) 

image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)

cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![DIP IMG )!](https://github.com/user-attachments/assets/2f6d8440-6029-45c1-bd8a-877262836038)


### ii) Display the video
![DIP IMG )!](https://github.com/user-attachments/assets/c0d650b6-bbc3-4327-81fd-0a592eb75d89)

### iii) Display the video by resizing the window
![2024-09-24](https://github.com/user-attachments/assets/433db15d-e0c8-45e4-a11e-57cbd6b5cec9)


### iv) Rotate and display the video
![2024-09-24 (1)](https://github.com/user-attachments/assets/e2bd1eed-40a5-4a44-ac4b-baa13d6ba063)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
