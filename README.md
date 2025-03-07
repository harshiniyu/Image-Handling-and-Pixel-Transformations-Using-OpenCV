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
- **Name:** Harshini Y
- **Register Number:** 212223240050

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```
img = cv2.imread('Eagle_in_Flight.jpg')
img_gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
plt.imshow(img_gray, cmap='gray')
plt.axis("off") 
plt.title("Gray Image")
plt.show()
```
![Screenshot 2025-03-07 104537](https://github.com/user-attachments/assets/9a6edb4c-bd54-4985-9117-5ab56313579e)



#### 2. Print the image width, height & Channel.
```
img.shape
```
![Screenshot 2025-03-06 215500](https://github.com/user-attachments/assets/e88839f6-a027-4d25-856d-a707a1113f2d)

#### 3. Display the image using matplotlib imshow().
```
img_rgb = cv2.cvtColor(img_copy, cv2.COLOR_RGB2BGR)
plt.imshow(img_rgb)
plt.axis('off') 
plt.show()
```

![Screenshot 2025-03-06 213656](https://github.com/user-attachments/assets/4226ea23-87e4-46f7-ab45-26fe3b7103df)

#### 4. Save the image as a PNG file using OpenCV imwrite().
```
img2 = cv2.imwrite('Eagle.png',img)

```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```
img_copy = cv2.imread('Eagle.png')
img_BGR = cv2.cvtColor(img_copy, cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```
plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis("off")
plt.show()
img_copy.shape
```
![Screenshot 2025-03-06 213718](https://github.com/user-attachments/assets/08c9c392-a33e-4ba7-b573-8a9d9c341a8d)
#### 7. Draw the line in image.
```
cv2.line(img_rgb, (0,0),(768,600),(255, 255, 0), thickness = 3)
plt.imshow(img_rgb) 
plt.title("Image with Line")
plt.show()
```
![Screenshot 2025-03-06 213729](https://github.com/user-attachments/assets/e6f1820f-65bc-4a2a-ad36-c5ae64280741)


#### 8. Crop the image to extract any specific (Eagle alone) object from the image.
```
cr = img_rgb[0:450,200:560] 
plt.imshow(cr)
plt.title("Cropped Region")
plt.axis("off")
plt.show()

```
![Screenshot 2025-03-06 213740](https://github.com/user-attachments/assets/d9f1ffc0-267f-48ad-984f-9be4c9c67ff8)


#### 9. Resize the image up by a factor of 2x.
```
res= cv2.resize(cr,(400*2, 400*3))
plt.imshow(res)
plt.axis("off")
```


![Screenshot 2025-03-06 213757](https://github.com/user-attachments/assets/18744d85-b712-46f7-961a-f1e5bef985ff)


#### 10. Flip the cropped/resized image horizontally.
```
flip= cv2.flip(res,1)
plt.imshow(flip)
plt.title("Flipped Horizontally")
plt.axis("off")
```

![Screenshot 2025-03-06 213809](https://github.com/user-attachments/assets/5823a3c1-4d13-4233-9854-727cf812bcf4)

#### 11. Read in the image ('Apollo-11-launch.jpg').
```
img=cv2.imread('Apollo.jpg')
plt.imshow(img)
plt.axis("off")
```

![Screenshot 2025-03-06 213821](https://github.com/user-attachments/assets/cf0abadb-b3eb-4126-9c44-f08c8e3a2e02)


#### 12. Add the following text to the dark area at the bottom of the image (centered on the image):
```
text = cv2.putText(img, "Apollo 11 Saturn V Launch, July 16, 1969", (300, 700),cv2.FONT_HERSHEY_TRIPLEX, 1, (255, 255, 255), 2)  
plt.imshow(text, cmap='gray')  
plt.title("Texted image")
plt.axis("off")
plt.show()  
```

![Screenshot 2025-03-06 213849](https://github.com/user-attachments/assets/53f30a4f-4dd8-4fdb-9c01-44d0fcd21edc)


#### 13. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```
cv2.rectangle(img, (400,650),(800,50),(255,0,255), thickness = 3)
plt.imshow(img) 
plt.title("Rectangled Image")
plt.axis("off")
plt.show()
```


![Screenshot 2025-03-06 213858](https://github.com/user-attachments/assets/a28b4b82-1715-421c-a140-54f6fc9fe06c)

#### 14. Display the final annotated image.
```
plt.title("Annotated image")
plt.imshow(img)
plt.axis("off")
plt.show()
```

![Screenshot 2025-03-06 213911](https://github.com/user-attachments/assets/59cde43e-650c-43c1-a52a-ea518dfc24e5)

#### 15. Read the image ('Boy.jpg').
```
img_3 =cv2.imread('boy.jpg')
img_3_rgb= cv2.cvtColor(img_3, cv2.COLOR_BGR2RGB)
m = np.ones(img_3_rgb.shape, dtype="uint8") * 75
img_brighter = cv2.add(img_3_rgb, m)  
img_darker = cv2.subtract(img_3_rgb, m)
plt.title("Colored Image")
plt.imshow(img_3_rgb)
plt.axis("off")
```

![Screenshot 2025-03-06 213921](https://github.com/user-attachments/assets/4f715dd0-cc3f-409c-9905-6a181637387b)

#### 16. Adjust the brightness of the image.
```
plt.title("Darker Image")
plt.imshow(img_darker)
plt.axis("off")
```


![Screenshot 2025-03-06 213933](https://github.com/user-attachments/assets/12d57197-d6bd-47ab-8fb8-ad65a15d5f7e)

#### 17. Create brighter and darker images.
```
plt.title("Brighter Image")
plt.imshow(img_brighter)
plt.axis("off")
```

![Screenshot 2025-03-06 213944](https://github.com/user-attachments/assets/0c15839c-abb9-4483-85e5-d38298b51d40)


#### 18. Display the images (Original Image, Darker Image, Brighter Image).
```
matrix1 = np.ones(img_3_rgb.shape, dtype="float32") * 1.5
matrix2 = np.ones(img_3_rgb.shape, dtype="float32") * 3.0
img_higher1 = cv2.multiply(img_3_rgb.astype("float32"), matrix1).clip(0,255).astype("uint8")
img_higher2 = cv2.multiply(img_3_rgb.astype("float32"), matrix2).clip(0,255).astype("uint8")
plt.title("Original Image")
plt.imshow(img_3_rgb)
plt.axis("off")
```

![Screenshot 2025-03-06 213956](https://github.com/user-attachments/assets/a24e6bc4-fbe7-4915-8751-1416a8f1e156)

#### 19. Modify the image contrast.
```python
# Create two higher contrast images using the 'scale' option with factors of 1.1 and 1.2 (without overflow fix)
matrix1 = 
matrix2 = 
# img_higher1 = 
# img_higher2 = 
# YOUR CODE HERE
```

#### 20. Display the images (Original, Lower Contrast, Higher Contrast).
```
plt.title("Lower Contrast")
plt.imshow(img_higher1)
plt.axis("off")
plt.title("Higher Contrast")
plt.imshow(img_higher2)
plt.axis("off")
```

![Screenshot 2025-03-06 214009](https://github.com/user-attachments/assets/1cd2d970-9aa5-4236-9d10-22a024029620)

![Screenshot 2025-03-06 214020](https://github.com/user-attachments/assets/9595bec4-9446-4e2b-a234-653bd5b62f10)

#### 21. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```
b, g, r = cv2.split(img_3_rgb)
plt.title("Blue Colored Image")
plt.imshow(b)
plt.axis("off")

plt.title("Green Colored Image")
plt.imshow(g)
plt.axis("off")

plt.title("Red Colored Image")
plt.imshow(r)
plt.axis("off")

```
![Screenshot 2025-03-06 214030](https://github.com/user-attachments/assets/eba12e52-c3e5-4218-a28b-209e5e20c76d)

![Screenshot 2025-03-06 214044](https://github.com/user-attachments/assets/04aa4ac4-746f-4afa-a0e8-09dbac7c8d99)

![Screenshot 2025-03-06 214059](https://github.com/user-attachments/assets/a10e10b6-dce9-49cf-aa7a-db83437c1907)



#### 22. Merged the R, G, B , displays along with the original image
```
merged_rgb = cv2.merge([r, g, b])
plt.imshow(merged_rgb)
plt.title("Merged RGB Image")
plt.axis("off")
plt.show()
```

![Screenshot 2025-03-06 214110](https://github.com/user-attachments/assets/861a37c7-8ee0-479b-b986-1734cc62c40e)


#### 23. Split the image into the H, S, V components & Display the channels.
```
hsv_img = cv2.cvtColor(img_3_rgb, cv2.COLOR_RGB2HSV)
h, s, v = cv2.split(hsv_img)

plt.imshow(h)
plt.title("Hue Channel")
plt.axis("off")
plt.show()

plt.imshow(s)
plt.title("Saturation Channel")
plt.axis("off")
plt.show()

plt.imshow(v)
plt.title("Value Channel")
plt.axis("off")
plt.show()
```


![Screenshot 2025-03-06 214131](https://github.com/user-attachments/assets/fc8f982e-9a89-4e79-bfe5-dc7f66b2f25a)

![Screenshot 2025-03-06 214141](https://github.com/user-attachments/assets/4bcb318c-8a24-468b-9893-b5e2328eee04)


![Screenshot 2025-03-06 214152](https://github.com/user-attachments/assets/4ff4b70a-adb0-4537-a855-c789e34c01cc)


#### 24. Merged the H, S, V, displays along with original image.
```
merged_hsv = cv2.merge([h, s, v])
plt.imshow(merged_rgb)
plt.title("Merged HSV Image")
plt.axis("off")
plt.show()
```


## Output:
- **i)** Read and Display an Image.

![Screenshot 2025-03-07 105433](https://github.com/user-attachments/assets/74c74039-938b-486e-b4b1-816d01af5a0a)

 
- **ii)** Adjust Image Brightness.

- ![Screenshot 2025-03-06 213933](https://github.com/user-attachments/assets/0140ac4f-5394-427d-914c-6bc2d4645db6)

- ![Screenshot 2025-03-06 213944](https://github.com/user-attachments/assets/6c78a5e4-6098-43e5-8b26-ca0f3a8ddefe)

 
- **iii)** Modify Image Contrast.

- ![Screenshot 2025-03-06 214009](https://github.com/user-attachments/assets/037e4a71-ac4b-4da5-b34f-8d06d1ec5009)


 ![Screenshot 2025-03-06 214020](https://github.com/user-attachments/assets/7d01ff01-dcc6-4f20-9869-a5aa1dab4957)

- **iv)** Generate Third Image Using Bitwise Operations.

- ![Screenshot 2025-03-06 214131](https://github.com/user-attachments/assets/30d9b6a3-8e35-474d-bad0-559cefa9d6b7)


![Screenshot 2025-03-06 214141](https://github.com/user-attachments/assets/922eed6b-4ac5-4167-8c5e-512f2ca09d55)


![Screenshot 2025-03-06 214152](https://github.com/user-attachments/assets/b04e7aff-e735-418b-8c1a-c731d55296a9)

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

