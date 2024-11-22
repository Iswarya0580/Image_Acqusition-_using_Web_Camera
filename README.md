
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
## Step 1:
Use cv2.VideoCapture(0) to access web camera.

## Step 2:
Use cv2.imread to read the video or image.

## Step 3:
Use cv2.imwrite to save the image.

## Step 4:
Use cv2.imshow to show the video.

## Step 5:
End the program and close the output video window by pressing 'q'.

## Program:

## Developed By: Iswarya P
##  Register No:212223230082

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Iswarya',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Iswarya',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video

```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Iswarya',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## Output

### i) Write the frame as JPG image

![Screenshot 2024-11-22 184755](https://github.com/user-attachments/assets/a01205c0-6732-4dad-b142-17d05f0e6986)


### ii) Display the video

![Screenshot 2024-11-22 184842](https://github.com/user-attachments/assets/aeaf283c-c6f0-496f-8c0a-c8d80bdb52fe)


### iii) Display the video by resizing the window

![Screenshot 2024-11-22 184612](https://github.com/user-attachments/assets/6e063b7a-6e37-4f0d-9b8f-f8f88fd52dbf)



### iv) Rotate and display the video

![Screenshot 2024-11-22 184944](https://github.com/user-attachments/assets/d21a695b-f720-4b40-99b6-df81797c57a5)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
