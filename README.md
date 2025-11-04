# MACHINE_LEARNING_PROJECTS
Still in progress when i was creating it i have done lot of mistake because dimensionaility which is the most hectic part of the project so please learn it care fully i will explain each part here so i get stuck into the code refer here 

First of all downgrade python version if u are watching it in 2025 from latest version 3.14 to 3.9 3.8 because these version are capable of comunicating with tensorflow or pytorch 

The first package i have used is glob which is used to navigate through your directory as u can below 

tumor=[]
health=[]
for f in glob.iglob('./data/dataset/yes/*.jpg'):
    img=cv2.imread(f)
    img=cv2.resize(img , (128 , 128))
    b , g, r=cv2.split(img)
    img=cv2.merge([r, g, b])
    tumor.append(img)
for f in glob.iglob('./data/dataset/no/*.jpg'):
    img=cv2.imread(f)
    img=cv2.resize(img , (128 , 128))
    b , g, r=cv2.split(img)
    img=cv2.merge([r, g, b])
    health.append(img)

2-> Usage of glob.iglob iglobe is a function inside glob module which returns a iterator which means it provide one file path at a time as you loop through it.

3-> Use of cv2 
What is cv2 (pip install opencv-python like that might be check if it is wrong)
Ans: cv2 provides Python bindings for OpenCV, a powerful open-source library mainly used for image processing, computer         vision, and machine learning tasks . It allows you to use OpenCV’s functions and tools in your Python programs.

What is the use of cv2.imread() what we pass into it as an argument lets talk about it......
Ans: cv2.imread in Python's OpenCV (cv2) library is used to read an image file from disk and load it into memory as a NumPy array.

img = cv2.imread('path_to_image.jpg', cv2.IMREAD_COLOR)

4-> Which comes into your mind as a beignner why we resize the images why we ?
Ans: Uniform Input Size for Models: Machine learning models like neural networks (especially CNNs) require all input images to have the same dimensions. If images are of different sizes, the model cannot process them together in batches.\

Large images have more pixels, which increases memory usage and slows down processing. Resizing to a smaller, fixed size (like 128x128) makes computation faster and less resource-intensive.

Resizing ensures that all images are scaled similarly, which helps the model learn more consistently and improves accuracy.
 img=cv2.resize(img , (128 , 128)) input which image u want to resize and in tuple pass the input shape
