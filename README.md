# Image_Acqusition-_using_Web_Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG

ii) Display the video

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
Step 1:
Use cv2.VideoCapture(0) to access web camera

Step 2:
Use cv2.imread to read the video or image

Step 3:
Use cv2.imwrite to save the image

Step 4:
Use cv2.imshow to show the video

Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
### Developed By: SABJAY S
### Register No: 212222230132
```
i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("sanjay.jpg", frame)
videoCaptureObject.release()
cv2.destroyAllWindows()
ii) Display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Harish',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
iii) Display the video by resizing the window
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
    cv2.imshow('212222230045-Harish',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
iv) Rotate and display the video
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
    cv2.imshow('212222230045-Harish',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output
i) Write the frame as JPG image
<br>
![WhatsApp Image 2024-11-23 at 11 37 36_dc1f0a17](https://github.com/user-attachments/assets/184c4b60-b49b-4a4c-8310-5f32e34019a6)
<br>

ii) Display the video
<br>
![WhatsApp Image 2024-11-23 at 11 37 45_a263cdab](https://github.com/user-attachments/assets/253bfca7-549c-4174-be33-7fff3d0730fa)
<br>

iii) Display the video by resizing the window
<br>
![image](https://github.com/user-attachments/assets/0e9cba39-81c7-4ead-8d43-2b47506ea224)
<br>

iv) Rotate and display the video
<br>
![WhatsApp Image 2024-11-23 at 11 37 35_2e68c205](https://github.com/user-attachments/assets/aea25e68-10f1-46f2-8c10-f083160ac4e8)
<br>

## Result:
Thus the image accessed from webcamera is displayed successfully using openCV.
