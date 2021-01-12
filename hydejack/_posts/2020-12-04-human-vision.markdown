---
layout: post
title:  Creating a Human Vision
image:  /assets/img/blog/eye.jpg
tags: ['Computer Vision']
---
Incessantly I goggle at my phone every day, I admire when I witness beautiful scenery and I see the world through my eyes. However, I have failed to acknowledge my main protagonist who helps me capture these beauties - my eyes. Further, it raises a paramount question - how powerful are my eyes and the brain that process the images?. This particular thought didn't strike me until I got interested in computer vision. The monumental growth of camera technology, its intersection with machine learning and the plausibility of recreating a human eye with the said technology ensembles my article.

The very first question that pops up regarding a human eye is why do we have two eyes ?. This question dates back to my childhood where I was taught that the reason is to get a wider angle of view and to have a binocular vision. To make this intelligible, it is the ability of each eye to see a similar scene but with a different perspective. In turn, it creates a disparity that is processed by the brain and as a result, we can judge distances. It is this depth perception that gives gravity to our eyes. The proof goes with the cliche example of closing one eye with a pen placed in front of your eyes and trying to discern the pen's location and similarly with the other eye. Thereby, leading to parallax error of the pen. So, this forms the crux of the article where it explores the basics of determining the depth of a scene.

![two camera1](/assets/img/blog/st1.png){:.lead data-width="664" data-height="454"}
Stereo Vision Setup
{:.figure}
With a given camera, we can visualize similar to our eyes do, but can we perceive depth?. In industries, the depth perception of an object is achieved through popular techniques namely Time of Flight (ToF), Laser Triangulation and stereo vision. However, the article focusses on stereo vision as it closely mimics the principle of an eye. In an industrial stereo vision setup, two cameras are placed similar to our eye with a distance apart and each camera takes the image of an object $$P$$ with a different perspective as shown in the figure. In the above figure, $$f$$ is the focal length, $$b$$ is the distance between cameras, $$u_L$$ and $$u_R$$ are the image points of a point of an object ($$P$$) with respect to left camera and right camera image plane respectively. The disparity ($$d$$) is defined as 

$$d = u_L - u_R $$

the distance between projected points on the image plane. The depth and disparity are inversely proportional, which helps in calculating the Depth and hence the relation : 

$$\begin{aligned}D = f \times \frac{b}{d} \end{aligned}$$

![two camera](/assets/img/blog/st2.png){:.lead data-width="665" data-height="379"}
Epipolar Geometry
{:.figure}
Easy right? But there is catch here. Identifying and matching similar features in an image taken from left and right camera i.e point $$u_L$$ and $$u_R$$ to identify depth can be cumbersome. The images taken might vary due to lighting conditions or different camera position/orientation and settings. But a huge bow to the methods like Scale-Invariant Feature Transform (SIFT), Cross-correlation, symbolic feature matching to tackle the stereo correspondence problem. To make this uncomplicated, we assume the optical axes of the cameras to be parallel to each other and we have images as shown in the figure. As a result, the basic stereo correspondence algorithm would look like

~~~py
for each epipolar line (White line in the above image)
    for each pixel in the left image 
        compare with every pixel on same epipolar line in right image
	pick pixel with minimum match cost
~~~

The minimum match cost mentioned above can be absolute differences or squared differences in luminance (or intensity values) between the pixel in the left image and right image. Therefore by solving the above optimization problem, one can determine the depth of an object. Problem Solved !! So far, we have seen how to perceive depth with two camera/images. Is it possible to recover depth from a single camera image?. The answer is yes.

In a decade, Machine Learning has deeply penetrated into various applications. It is this pretentious technology that gives a new meaning to computer vision and can do the unimaginable, that humans cant do. As mentioned earlier in this article, we need two eyes to perceive depth accurately. However, the depth of a scene can be determined with a single camera with a single image using deep learning. Firstly, acquiring relevant data-set for the application is crucial to do any machine learning applications. The available data sets for depth estimation of a natural scene are Make3D, NYU, SUNRGBD, KITT. These data set has multiple images of a natural scene as input and the depth map of the corresponding images as output. The depth map of the training images can be created by xbox Kinect or laser scanner or any other methods that are mentioned earlier in this article. Once, the dataset is obtained, the Convolution Neural Networks (CNN) can be trained with appropriate architecture. Therefore, the depth map of a new scene can be determined from the prediction of the trained CNN model.

Even though machine learning supersedes humans in some aspect, the level of accuracy in depth perception and the ability of the brain to achieve perfect stereo correspondence should be duly noted. With this, it all points to the very first question raised in this article - how powerful are my eyes and the brain that process the images?

**References:**

1. L.He, G.Wang and Z.Hu, "Learning Depth from Single Images with Deep Neural Network Embedding Focal", 2018, China.
2. D.Eigen, C.Puhrsch, R.Fergus, "Depth Map Prediction from a Single Image using a Multi-Scale Deep Network", 2014, New York.
3. R.A.Hamzah, H.Ibrahim, "Literature Survey on Stereo Vision Disparity Map Algorithms", Hindawi Publishing Corporation Journal of Sensors, 2015, Malaysia.
4. Image 1 Eyes Closeup - https://twistedsifter.com/2012/08/extreme-close-ups-of-the-human-eye/
5. Image 2 Stereo Vision Camera Setup - http://chriswalkertechblog.blogspot.com/2014/03/stereo-vision-basics.html
6. A.Nieder, "Stereoscopic Vision: Solving the Correspondence Problem", 2003, Germany.