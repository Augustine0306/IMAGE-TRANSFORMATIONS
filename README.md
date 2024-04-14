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
Developed By: AUGUSTINE J

Register Number:212222240015

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
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/f1888623-73ef-4f20-8df1-75f62494193f)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/23f9c58e-d4a2-4b20-ab5b-585552287016)


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
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/f9e68e81-0477-4b4c-93f4-36e48c7a6862)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/4d084bdc-6052-4634-99a1-caedc35542df)

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
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/f876e2bc-604c-4431-b911-f3efe9de397a)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/09a075b3-dfb1-4a14-9ea3-fdd9b2bffd93)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/ebd00688-8b10-425e-8ecd-0dc6273d0678)


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
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/bc7df2f8-f647-450c-b108-4db650aa84bb)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/524a5751-e5bb-494f-b8b5-39d144503c50)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/5843c46d-7d8a-4165-b503-0f4b3562dcf3)

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
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/01c06f38-0c6f-4a21-bb28-56b18de65492)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/76aeb8b1-f0e7-43b3-938f-745525de8f43)


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
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/09606066-11cc-4c5c-b470-fe0959e2560e)
![image](https://github.com/Augustine0306/IMAGE-TRANSFORMATIONS/assets/119404460/9250aa03-6e6a-4d9c-a65e-cb7211daefa5)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

