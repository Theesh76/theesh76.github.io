---
title:  How many Megapixel do you need?
image:  /assets/img/blog/cam.jpg
---
Digital cameras have become the third eye of every individual. When we buy a DSLR or an expensive smartphone, the first criteria that most individuals consider are the number of pixels present in the camera. As computer vision engineers, we consider several factors in choosing a digital camera for an application. However, this article will only guide the basic science behind choosing the right number of pixels for your application.

**What is a pixel?**

It is the smallest unit on the camera. The image is constructed as the amount of light falling on each pixel of the camera sensor. Generally, the width of a pixel would be in the order of micrometres for the cameras. and in the order of millimetres for laptops. Hence the size variations.	 

<img src="/assets/img/blog/how.jpg" class="center" width="500" height="333">

How much is the right number of pixels for your camera?
The resolution of the camera depends on the two main factors,

1.	The maximum area to be photographed, which is termed as Field of View (FOV).
2.	Smallest feature to be visible in the camera without pixelation.

Let say, James is a fashion photographer. His criteria would be

1.	FOV - The maximum area to be photographed will be lesser than 3m*3m (tallest man being 2.72m). 
2.	Smallest Feature - James sets the smallest feature to be the pupil of a man's eye. Hence, the smallest feature ranges from 2mm to 4mm, which is the diameter of the pupil.

For the smallest feature to be recognizable, James should assign at least 2 pixels for the smallest feature. This thumb rule is called the Nyquist theorem and interested readers can search to get more information. If he assigns 2 pixels for every 2mm, he needs a minimum of 3000 pixels for 3m FOV.

<pre>
<code> 
						2 Pixels ----> 2 mm
						X        ----> 3000 mm
						X = (300x2)/2 = 3000 pixels
						Camera = 3000x3000 = 9x10^6 = 9 Mega Pixel 
</code></pre>
                              
So, he needs 3000 pixels in both the vertical and horizontal direction of the camera. Technically a 9MP (3000 x 3000) camera would be sufficient. Unfortunately, we don't have cameras in this resolution format. Therefore, a 12 Megapixel camera with resolution 4080 x 3072 will be more than sufficient for James. So, next time when you decide to buy a camera, consider the aforementioned basic two factors.

**Trivia 1:**
James is demoted as a passport size photographer. Now, he would have a small FOV as compared to the former. Let's say, it is reduced to 750x750 mm and he captures the image with his same 12 MP camera. Then, he would acquire an image resolution of

<pre>
<code>			
						<b>Image Resolution:</b>

						FOV    - 750 mm
						Pixels - 4080 Pixels

						750/4080 = 0.18 mm/pixel
						0.18 mm/pixel. 
</code></pre>

It means that the image has 0.18mm of the object for every one pixel in the camera.
Nowadays, Modern laptop display comes in 2k and 4k resolutions. They have an important specification named pixels per inch (PPI). Assuming, James has a laptop screen with 100 pixels per inch and its conversion to a simple metric can be given as follows,

<pre>
<code>	
						<b>Laptop Screen Resolution:</b>

						100 pixels per inch
						1 inch = 25.4 mm
						100/25.4 pixels per mm

						= 25.4/100 mm/pixel = 0.254 mm/pixel.

						<b>Image Resolution > Laptop Resolution</b>
</code></pre>
If James decided to display the photographed 12MP image on his laptop to his customers WITHOUT ZOOMING IN the picture. He would be screening his image under lower resolution. Then, he won't be needing a 12MP camera. Something to think about!!!

**Trivia 2:**

Now, James decided not to display his photographed image on the laptop. But he decided to print the picture and make an album to show his customers. Again, James should consider the printer's pixel per inch (PPI). Assuming, James's printer operates at 200 PPI and his photographed image has a size of 4080 x 3072 pixels. His maximum frame size of the photo should be
Frame Size of the Photo:

<pre><code>
						Image Size    = 4080x3072 Pixels

						Printer's PPI = 200 Pixels/inch


						Width Frame Size    = 4080/200 = 20.4 inches

						Height Frame Size   = 3072/200 = 15.36 inches
</code></pre>
20.4 x 15.36 inches. If he exceeds this size for his frame, it would lead to pixelation and the quality of the picture would drop.
