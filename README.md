# Ex 04 IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
<br>Translate the image using a function warpPerpective()

### Step3:
<br>Scale the image by multiplying the rows and columns with a float value.

### Step4:
<br>Shear the image in both the rows and columns.

### Step5:
<br>Find the reflection of the image.

### Step6:
<br>Rotate the image using angle function.

## Program:
Developed By: LEANN JOBY MATHEW

Register Number:212222230074

## Image Translation

```PYTHON
import numpy as np
import cv2
import matplotlib.pyplot as plt

input_image=cv2.imread("rajani.png")
input_image=cv2.cvtColor(input_image, cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
M=np.float32([[1,0,50],  [0,1,100],  [0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()
```
![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/e7b6ccb4-5419-4b66-bc99-fcfa1593ec1d)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/a853b2c6-c4b7-4e48-97ba-bf2371a2a799)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/94798790-ada5-4701-ae75-f80cb43aa920)


## Image Scaling
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("rajani.png")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
M = np.float32([[1.5,0,0],[0,1.7,0],[0,0,1]])
scaled_img = cv2.warpPerspective(org_image,M,(cols*2,rows*2))
plt.imshow(org_image)
plt.show()
```
![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/99c5add3-6fd9-4d39-8b07-afe51204f903)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/f351e29b-acf1-405f-9870-65102d5c02ab)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/a99beaab-9470-414c-bc04-cb1ded48d8ac)

## Image shearing
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("rajani.png")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
M_X = np.float32([[1,0.5,0],[0,1,0],[0,0,1]])
M_Y = np.float32([[1,0,0],[0.5,1,0],[0,0,1]])
sheared_img_xaxis = cv2.warpPerspective(org_image,M_X,(int(cols*1.5),int(rows*1.5)))
sheared_img_yaxis = cv2.warpPerspective(org_image,M_Y,(int(cols*1.5),int(rows*1.5)))
plt.imshow(sheared_img_xaxis)
plt.show()
plt.imshow(sheared_img_yaxis)
plt.show()
```
![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/4cf3ab5c-e53a-4fda-b866-ea73345f8c70)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/05bc325e-cdb5-4253-a6a2-a5ef6b386524)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/b626dbb5-e6a3-4426-bb73-dc38ff72aed7)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/9ec9a3ee-b313-4da0-b833-5604a4b9088e)

## Image Reflection
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("rajani.png")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
M_X = np.float32([[1,0,0],[0,-1,rows],[0,0,1]])
M_Y = np.float32([[-1,0,cols],[0,1,0],[0,0,1]])
reflected_img_xaxis = cv2.warpPerspective(org_image,M_X,(int(cols),int(rows)))
reflected_img_yaxis = cv2.warpPerspective(org_image,M_Y,(int(cols),int(rows)))
plt.imshow(reflected_img_xaxis)
plt.show()
plt.imshow(reflected_img_yaxis)
plt.show()
```
![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/d08e9ac9-674b-40d9-ae0f-6155b4c9809e)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/f3e10e6d-1c2e-45cc-b317-f50dd9fb4c3f)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/3635dc65-38e2-49c8-a03c-da573b245261)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/6c85f15f-899c-45a3-9d62-27b31f485972)

## Image Rotation
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("rajani.png")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()

angle=np.radians(10)
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]])
rotated_img = cv2.warpPerspective(input_image,M,(int(cols),int(rows)))

plt.imshow(rotated_img)
plt.show()
```
![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/4678816f-8b17-4940-94a5-fc8ae199dcc9)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/ee2074a4-53cb-413b-954e-39db1f29b053)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/10c2ef10-1771-4a09-b043-04d55ba0bdec)

## Image Cropping
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("rajani.png")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
cropped_img=org_image[80:900,80:500]
plt.imshow(cropped_img)
plt.show()
```
![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/31c081cc-78be-4c5a-9aee-26e77735521f)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/f49b263e-aa4d-4b79-88a4-c622f87c4ce4)

![image](https://github.com/Leann4468/IMAGE-TRANSFORMATIONS/assets/121165979/071bb894-5f2d-4d6d-966a-22f94bf8b344)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
