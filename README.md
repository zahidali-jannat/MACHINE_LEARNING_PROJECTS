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
Means woh directory keh andar jaega location per or waha iterate karega all over upr seh neech jb tak khtm nhi ho jata maal andar kah mtlb images 

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

5->Next question you may have is why we have done b , g , r not  r , g , b we merge them aslso why??
Ans: opencv be default splits image pixels into b g r format means if u have dimention like [50 , 100 , 150] means b=50 , g=100 , r=150 but most of the deep learning model accept  input as RGB that why  we  made three list b , g , r which stores number blue , green , red respectiviely than i merged them as rgb. 


health.shape (Important need ur focus here pls)
(1218, 128, 128, 3) 
health.shape[0] will give 1218 which is total number of images we have 
health.shape[1], health.shape[2] it tell images size 128 x 128 
health.shape[3] it tells there are three channel R G B  Each one of them size 128 x 128 they are like in row one is behind another and each of them size 128 x 128 and number of images is 1218 


import random which is a part of numpy 
np.random.choice(tumor.shape[0] , num , replace=False) iska matlb hai tumhare pas choice hai 1218 mai seh koi bhi num=koi bhi integer randomly select karo , replae=False means tum joh choose kroge repeated nhi hoga jaise index 1 2 3 4 5 okay if num=5 , if num=6 u can not have 1 2 2 3 4 5 replce=False means same index dubara nhi instead hoga 1 2 3 4 5 6 



I am not explaning portion of subplot it is too basic try to learn on your own i will explain other things in details later own




