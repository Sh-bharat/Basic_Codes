# Basic_Codes
This repositry is for Providing Basic Functions, loops and Code that we need Every Time.

## 1) For Accessing Camera Frames
```
## For Live Testing
import cv2

cap = cv2.VideoCapture(0)
if not cap.isOpened():
    raise IOError("Error: Camera can not be opened. ")
while True:
    ret, frame = cap.read()
    if(not ret):
        print(f'End f Live Session')
        break

    cv2.imshow('Camera', frame)
    
    c = cv2.waitKey(1)
    if c == 27: # For Esc character
        break
cap.release()
cv2.destroyAllWindows()
```

## 2) For Check/Create Output Directory
```
## For Check/Create Output Directory
import os

Output_path=os.path.join(os.getcwd(),"Output")
if(os.path.exists(Output_path)):
    print(f'Output Directory Found')
else:
    os.mkdir(Output_path)
    print(f'Output Directory Created')
```
