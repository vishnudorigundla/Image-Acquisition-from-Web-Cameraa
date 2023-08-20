# Image-Acquisition-from-Web-Camera
## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG <br>
ii) Display the video <br>
iii) Display the video by resizing the window<br>
iv) Rotate and display the video<br>

## Software Used
Anaconda - Python 3.7
## Algorithm
Step 1:
Import Opencv Package.<br>

Step 2:
Capture the Video from the WebCamera.<br>

Step 3:
Write the image to a file.<br>

Step 4:
Show the image or the live camera.<br>

Step 5:
End the program.<br>

## Program:
## i) Write the frame as JPG file
``` Python
### Developed By: D. Vishnu vardhan reddy
### Register No: 212221230023


```python
import cv2
video = cv2.VideoCapture(0)
while(True):
    t,frame = video.read()
    cv2.imwrite("krishna.jpg",frame)
    result=False
    if cv2.waitKey(1) == ord('b'):
        break
video.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```python
import cv2
pic = cv2.VideoCapture(0)
while True:
    t,frame = pic.read()
    cv2.imshow('krishna',frame)
    if cv2.waitKey(1) == ord('b'):
        break
pic.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = smallerFrame
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = smallerFrame
    cv2.imshow('krishna',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('krishna',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image

![image](https://github.com/vishnudorigundla/Image-Acquisition-from-Web-Cameraa/assets/94175324/a1889248-7a02-4c14-b064-e5e76dde3375)

### ii) Display the video

![image](https://github.com/vishnudorigundla/Image-Acquisition-from-Web-Cameraa/assets/94175324/9e20d34c-7592-4c28-952c-c6b6d730e947)

### iii) Display the video by resizing the window

![image](https://github.com/vishnudorigundla/Image-Acquisition-from-Web-Cameraa/assets/94175324/14b6320a-126e-48f7-8507-579f07f382c4)

### iv) Rotate and display the video
![image](https://github.com/vishnudorigundla/Image-Acquisition-from-Web-Cameraa/assets/94175324/d2092539-5bb9-46e1-a22e-c14891a47f2a)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
