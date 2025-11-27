# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages


### Step2:
Give the input text using cv2.putText()

### Step3:
Perform opening operation and display the result

### Step4:
Similarly, perform closing operation and display the result


 
## Program:

``` Python
import numpy as np
import cv2
import matplotlib.pyplot as plt
blank=np.zeros((600,600))
import numpy as np
import matplotlib.pyplot as plt

image = np.zeros((600, 600, 3), dtype=np.uint8)

plt.imshow(image)
plt.axis('on')
plt.show()

def load_image():
    blank_image = np.zeros((600,600))
    font = cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(blank_image,text='Jeevan',org=(50,300),fontFace=font,fontScale = 5,color=(255,255,255),thickness=25,lineType=cv2.LINE_AA)
    return blank_image
def display_img(img):
    fig = plt.figure(figsize=(12,10))
    ax=fig.add_subplot(111)
    ax.imshow(img,cmap='gray')
    plt.show()
img=load_image()
kernel=np.ones((5,5),dtype=np.uint8)
white_noise=np.random.randint(low=0,high=2,size=(600,600))
white_noise = white_noise*255
noise_img = white_noise+img
display_img(noise_img)
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernel)
display_img(opening)
black_noise = np.random.randint(low=0,high=2,size=(600,600))
black_noise= black_noise * -255
black_noise_img = img + black_noise
black_noise_img[black_noise_img==-255] = 0
display_img(black_noise_img)
closing = cv2.morphologyEx(black_noise_img, cv2.MORPH_CLOSE, kernel)
display_img(closing)
display_img(img)
gradient = cv2.morphologyEx(img,cv2.MORPH_GRADIENT,kernel)
display_img(gradient)

```
## Output:

### Display the input Image
<img width="581" height="550" alt="image" src="https://github.com/user-attachments/assets/5ec988e4-5b15-414b-8999-37b8341778cb" />

### Noise img:
<img width="575" height="539" alt="image" src="https://github.com/user-attachments/assets/ea3f8bfd-e0a2-4f1f-87ed-1d8e799c19f6" />

### Display the result of Opening
<img width="557" height="557" alt="image" src="https://github.com/user-attachments/assets/7b629e68-2000-4088-8352-925d64de6539" />

### Black noise img:
<img width="603" height="572" alt="image" src="https://github.com/user-attachments/assets/bfcc5ab6-1558-4b0f-8272-896d18cd1283" />

### Display the result of Closing
<img width="583" height="562" alt="image" src="https://github.com/user-attachments/assets/7b47ca75-ecb9-4048-89b2-91eef5b77453" />

### Gradient img:
<img width="582" height="562" alt="image" src="https://github.com/user-attachments/assets/aee6781a-779f-4be0-989b-6a046a884ed0" />


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
