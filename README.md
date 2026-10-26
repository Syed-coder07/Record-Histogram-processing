## Record-Histogram-processing

## Aim:

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

* Read and display a grayscale image
* Plot histogram of the grayscale image
* Apply histogram equalization on grayscale image
* Read and display a color image
* Plot histogram of B, G, R channels
* Convert image to HSV color space
* Apply histogram equalization on the Value (V) channel
* Convert the enhanced image back to BGR format
* Display original and enhanced images with histograms

## Software Used:

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

## Algorithm:

Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the image parrot.jpg in grayscale format.

Step 3:
Display the grayscale image and plot its histogram.

Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6:
Read the same image in color format.

Step 7:
Split the image into B, G, R channels and plot their histograms.

Step 8:
Convert the image from BGR to HSV color space.

Step 9:
Apply histogram equalization on the V (Value) channel.

Step 10:
Merge the channels and convert the image back to BGR format.

Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

## Program:

Developed By: Syed Shamsheer Ali .B

Register No: 212225220114

1. Import the required libraries and read the grayscale image.


       import cv2
       import matplotlib.pyplot as plt

2. Display the Original Image:

       img = cv2.imread('Syed1.jpg', cv2.IMREAD_GRAYSCALE)
       img = cv2.imread(r"C:\Users\syedf\OneDrive\Documents\Personal\Syed1.png")
       if img is not None:
       img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
       plt.imshow(img, cmap='gray')
       plt.title('Original Image')
       plt.axis('off')

3. Display Original Image:
   
       plt.hist(img.ravel(),256,range = [0, 256]);
       plt.title('Original Image')
       plt.show()

4. Display Equalized Histogram:

       img = cv2.imread(r"C:\Users\syedf\OneDrive\Documents\Personal\Syed1.png", 0)
       img_eq = cv2.equalizeHist(img)
       plt.hist(img_eq.ravel(), 256, range=[0, 256])
       plt.title('Equalized Histogram')

5. Display the equalized grayscale image:

       plt.imshow(img_eq, cmap='gray')
       plt.title('Original Image')
       plt.show()

6. Display the Equalized Image:

       img = cv2.imread(r"C:\Users\syedf\OneDrive\Documents\Personal\Syed1.png")
       if img is None:
       print("Image not found! Check the file path.")
       else:
          img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
          img_hsv = cv2.cvtColor(img, cv2.COLOR_RGB2HSV)
          img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
          img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2RGB)
          plt.imshow(img_eq)
          plt.title("Equalized Image")
          plt.axis("off")
          plt.show()

7. Display the Histogram Equalized Image:
     
       plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()

8. Display the Original Color Image and Equalized image:

         plt.figure(figsize = (12,8))
         plt.subplot(121); plt.imshow(img[:, :, ::+1]); plt.title('Original Color Image')
         plt.subplot(122); plt.imshow(img_eq[:, :, ::+1]); plt.title('Equalized Image')
         plt.show()

9. Display the Original Image and Histogram Equalized Image:

       plt.figure(figsize = [15,4])
       plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
       plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
  
## Output:

Display the Original Image:

<img width="364" height="509" alt="image" src="https://github.com/user-attachments/assets/7371596e-1533-4235-8849-5727af1f282e" />

Display Original Image:

<img width="699" height="546" alt="image" src="https://github.com/user-attachments/assets/657536c7-0997-4491-97b8-9793850a482c" />

 Display Equalized Histogram:

 <img width="742" height="568" alt="image" src="https://github.com/user-attachments/assets/6cdab496-55da-4451-86e8-08f0abcff3ad" />

 Display the equalized grayscale image:

<img width="482" height="556" alt="image" src="https://github.com/user-attachments/assets/967312a7-a5cd-4f4c-a662-0c5977f5e468" />

Display the Equalized Image:

<img width="372" height="502" alt="image" src="https://github.com/user-attachments/assets/b3da1b15-2d4c-4309-8df2-fd084160d17b" />

Display the Histogram Equalized Image:

<img width="730" height="559" alt="image" src="https://github.com/user-attachments/assets/acfebbce-df1f-489e-b24a-31af1096f7ee" />

Display the Original Color Image and Equalized Image:

<img width="1333" height="764" alt="image" src="https://github.com/user-attachments/assets/8f4099bd-132c-4110-8b54-bf18eb88ef0d" />

Display the Original Image and Histogram Equalized Image:

<img width="1375" height="417" alt="image" src="https://github.com/user-attachments/assets/dd3a1eed-7ae0-4fc8-9d5b-b2fd193c3f8b" />

## Grayscale Histogram Equalization:

* Original grayscale image is displayed.
* Histogram of original grayscale image is plotted.
* Enhanced image after histogram equalization is displayed.
* Histogram of enhanced grayscale image shows improved contrast.

  
## Color Image Histogram Equalization;

* Original color image is displayed.
* Histogram of B, G, R channels is plotted..
* Enhanced image after HSV-based equalization is displayed.
* Histogram of enhanced image shows better intensity distribution.

## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.






