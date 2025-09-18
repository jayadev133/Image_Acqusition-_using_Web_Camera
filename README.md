# EX-02 : Image Acquisition using Web Camera

### NAME: JAYADEV PALLINTI
### REG NO: 212223240058

## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.
<br>

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.
<br>

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.
<br>

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.
<br>

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image.
<br>

### Step 6:
End Program with 'q'. Allow the program to be terminated by pressing the 'q' key.
<br>

## Program:

## i) Write the frame as JPG file
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("img.jpg", frame)
    print("Image saved as img.jpg")
else:
    print("Failed to capture image")
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## ii) Display the video
``` Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while True:
    ret, frame = videoCaptureObject.read()
    cv2.imshow('myimage', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## iii) Display the video by resizing the window
``` Python

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video
``` Python

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
<img width="930" height="840" alt="image" src="https://github.com/user-attachments/assets/a14ee5e0-bd7b-47e3-b738-c3fafab55c43" />


</br>
</br>


### ii) Display the video
<img width="816" height="649" alt="image" src="https://github.com/user-attachments/assets/f6f4c235-19f0-492f-bc28-79db8ea0eed7" />


</br>
</br>


### iii) Display the video by resizing the window
<img width="820" height="664" alt="image" src="https://github.com/user-attachments/assets/9ddcc06a-296d-411f-991f-04a86ce7dc72" />


</br>
</br>



### iv) Rotate and display the video
<img width="811" height="651" alt="image" src="https://github.com/user-attachments/assets/473c434f-cb49-4a18-85db-a5e222b27d97" />


</br>
</br>



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
