# Implementation-of-Erosion-and-Dilation
## Aim :
To implement Erosion and Dilation using Python and OpenCV.
## Software Required :
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step 1:
Apply the dilation operation on the image using cv2.dilate() with the same structuring element. Dilation will increase the size of the white regions (text) in the image, effectively reversing the effect of erosion

### Step 2:
Initialize a blank image (100 pixels high and 340 pixels wide) using NumPy. The image should be a single-channel (grayscale) array filled with zeros (black)

### Step 3:
Use OpenCV's cv2.putText() function to overlay the text "HYCINTH" on the blank image. Define the font style, position, font scale, color, and thickness for rendering the text.

### Step 4:
Specify the size of the structuring element (e.g., 5x5 pixels) and create a rectangular structuring element using cv2.getStructuringElement(). This element will be used for the morphological operations.

### Step 5:
Apply the erosion operation on the image using cv2.erode() with the defined structuring element. Erosion will reduce the size of the white regions (text) in the image.
 
## Program:
``` 
Name : Gopika R
Reg No: 212222240031
```
```
import cv2
import matplotlib.pyplot as plt

# Create a blank image (100 pixels high and 400 pixels wide)
img = np.zeros((100, 340), dtype='uint8')
# Put some text on the image for demonstration
cv2.putText(img, 'Gopika', (60, 70), cv2.FONT_HERSHEY_SIMPLEX, 2, (255), 5)
# Create a rectangular structuring element
kernel_size = (5, 5)  # Width and height of the kernel
structuring_element = cv2.getStructuringElement(cv2.MORPH_RECT, kernel_size)

# Perform Erosion
eroded_image = cv2.erode(img, structuring_element, iterations=1)

# Perform Dilation
dilated_image = cv2.dilate(img, structuring_element, iterations=1)

# Display the original, eroded, and dilated images
plt.figure(figsize=(6, 4))

# Original Image

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.show()
plt.figure(figsize=(6,4))
# Eroded Image
plt.imshow(eroded_image, cmap='gray')
plt.title('Eroded Image')
plt.axis('off')
plt.figure(figsize=(6, 5))
# Dilated Image
plt.imshow(dilated_image, cmap='gray')
plt.title('Dilated Image')
plt.axis('off')
```

## Output:

### Display the input Image :

![Screenshot 2024-11-10 181535](https://github.com/user-attachments/assets/712599ce-975a-4426-b8b1-b3bbf23b95b1)


### Display the Eroded Image :

![Screenshot 2024-11-10 181547](https://github.com/user-attachments/assets/dec4637b-3ab6-457d-b466-3b01cd93c51f)

### Display the Dilated Image :
![Screenshot 2024-11-10 181600](https://github.com/user-attachments/assets/7f2d913b-6744-44c6-a920-e1774bf92790)
## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
