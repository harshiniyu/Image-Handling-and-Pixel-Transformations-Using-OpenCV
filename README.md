# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:**Harshini Y  
- **Register Number:**212223240050

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
img = cv2.imread('Eagle_in_Flight.jpg')
img_gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
plt.imshow(img_gray, cmap='gray')
plt.axis("off") 
plt.title("Gray Image")
plt.show()
```
![alt text](image-1.png)
#### 2. Print the image width, height & Channel.
```python
img_gray.shape
```
![alt text](image-2.png)

#### 3. Display the image using matplotlib imshow().
```python
img = cv2.imread('Eagle_in_Flight.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis("off")
```
![alt text](image-3.png)
#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
img2 = cv2.imwrite('Eagle.png',img)

```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img_copy = cv2.imread('Eagle.png')
img_BGR = cv2.cvtColor(img_copy, cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
plt.imshow(img_BGR)
plt.title("Original Image")
plt.axis("off")
plt.show()
img_copy.shape
```
![alt text](image-4.png)
#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
cr = img_BGR[0:450,200:600] 
plt.imshow(cr)
plt.title("Cropped Region")
plt.axis("off")
plt.show()
cr.shape
```
![alt text](image-5.png)
#### 8. Resize the image up by a factor of 2x.
```python
res = cv2.resize(cr, (800, 900))
plt.imshow(res)
plt.title("Resized image")
plt.axis("off")
res.shape
```
![alt text](image-6.png)

#### 9. Flip the cropped/resized image horizontally.
```python
flip= cv2.flip(res,1)
plt.imshow(flip)
plt.title("Flipped Horizontally")
plt.axis("off")
```
![alt text](image-7.png)
#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
img=cv2.imread('Apollo-11-launch.jpg')
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
```
![alt text](image-8.png)
#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = cv2.putText(img, "Apollo 11 Saturn V Launch, July 16, 1969", (300, 700),cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)  
plt.imshow(text, cmap='gray')  
plt.title("New image")
plt.axis("off")
plt.show()  
```
![alt text](image-9.png)
#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
cv2.rectangle(img, (400,650),(800,100),(255,0,255), thickness = 3)
plt.imshow(img) 
plt.title("Image with rectangle")
plt.axis("off")
plt.show()
```
![alt text](image-10.png)
#### 13. Display the final annotated image.
```python
plt.title("Annotated image")
plt.imshow(img)
plt.axis("off")
plt.show()
```

#### 14. Read the image ('Boy.jpg').
```python
img_3 =cv2.imread('boy.jpg')
img_3_rgb= cv2.cvtColor(img_3, cv2.COLOR_BGR2RGB) 

```

#### 15. Adjust the brightness of the image.
```python
m = np.ones(img_3_rgb.shape, dtype="uint8") * 75
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img_3_rgb, m)  
img_darker = cv2.subtract(img_3_rgb, m)  
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
#### Original Image
```python
plt.title("Original Image")
plt.imshow(img_3_rgb)
plt.axis("off")
```
![alt text](image-11.png)
#### Darker Image
```python
plt.title("Brighter Image")
plt.imshow(img_darker)
plt.axis("off")
```
![alt text](image-12.png)
#### Brighter Image
```python
plt.title("Brighter Image")
plt.imshow(img_brighter)
plt.axis("off")
```
![alt text](image-13.png)

#### 18. Modify the image contrast.
```python
matrix1 = np.ones(img_3_rgb.shape, dtype="float32") * 1.5
matrix2 = np.ones(img_3_rgb.shape, dtype="float32") * 3.0
img_higher1 = cv2.multiply(img_3_rgb.astype("float32"), matrix1).clip(0,255).astype("uint8")
img_higher2 = cv2.multiply(img_3_rgb.astype("float32"), matrix2).clip(0,255).astype("uint8")
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
#### Original Image
```python
plt.title("Original Image")
plt.imshow(img_3_rgb)
plt.axis("off")
```
![alt text](image-14.png)
#### Lower Contrast Image
```python
plt.title("Lower Contrast")
plt.imshow(img_higher1)
plt.axis("off")
```
![alt text](image-15.png)
#### Higher Contrast Image
```python
plt.title("Higher Contrast")
plt.imshow(img_higher2)
plt.axis("off")
```
![alt text](image-16.png)
#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
b, g, r = cv2.split(img_3_rgb)
```
#### Blue Channel
```python
plt.title("Blue Color")
plt.imshow(b)
plt.axis("off")
```
![alt text](image-17.png)
#### Green Channel
```python
plt.title("Green Color")
plt.imshow(g)
plt.axis("off")
```
![alt text](image-18.png)
#### Red Channel
```python
plt.title("Red Color")
plt.imshow(r)
plt.axis("off")
```
![alt text](image-19.png)

#### 21. Merged the R, G, B , displays along with the original image

#### Original Image
```python
plt.imshow(img_3_rgb)
plt.title("Original Image")
plt.axis("off")
plt.show()
```
![alt text](image-20.png)
#### Merged Image
```python
merged_rgb = cv2.merge([r, g, b])
plt.imshow(merged_rgb)
plt.title("Merged RGB Image")
plt.axis("off")
plt.show()
```
![alt text](image-21.png)
#### 22. Split the image into the H, S, V components & Display the channels.
```python
hsv_img = cv2.cvtColor(img_3_rgb, cv2.COLOR_RGB2HSV)
h, s, v = cv2.split(hsv_img)
```
#### Hue Channel
```python
plt.imshow(h)
plt.title("Hue Channel")
plt.axis("off")
plt.show()
```
![alt text](image-22.png)
#### Saturation Channel
```python
plt.imshow(s)
plt.title("Saturation Channel")
plt.axis("off")
plt.show()
```
![alt text](image-23.png)
#### Value Channel
```python
plt.imshow(v)
plt.title("Value Channel")
plt.axis("off")
plt.show()
```
![alt text](image-24.png)
#### 23. Merged the H, S, V, displays along with original image.
```python
merged_hsv = cv2.merge([h, s, v])
plt.imshow(merged_rgb)
plt.title("Merged HSV Image")
plt.axis("off")
plt.show()
```
![alt text](image-25.png)

## Output:
- **i)** Read and Display an Image.  
![alt text](image-4.png)
- **ii)** Adjust Image Brightness. 
![alt text](image-12.png) ![alt text](image-13.png) 
- **iii)** Modify Image Contrast. 
![alt text](image-15.png) ![alt text](image-16.png)
- **iv)** Generate Third Image Using Bitwise Operations.
![alt text](image-22.png) ![alt text](image-23.png) ![alt text](image-24.png)
## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

