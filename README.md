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

## 3) For Downloading Dataset from kaggle to Colab

```
## Downloading Dataset from Kaggle
!mkdir ~/.kaggle
!cp kaggle.json ~/.kaggle/

!kaggle datasets download -d username/dataset_name

import zipfile
Zipis=zipfile.ZipFile("/content/dataset_name.zip")
Zipis.extractall('/content')
Zipis.close()
```
### For
### 1) kaggle.json file <br>
go to your profile on kaggle ```->``` Accounts ```->``` API ```->``` create new API token<br>
### 2) the Dataset api command 
go to kaggle Dataset ```->``` 3 Dots ```->``` Copy Api Command

## 4) For Sorting of Files
```
import re

def sorted_alphanumeric(data):  
    convert = lambda text: int(text) if text.isdigit() else text.lower()
    alphanum_key = lambda key: [convert(c) for c in re.split('([0-9]+)',key)]
    return sorted(data,key = alphanum_key)
```


