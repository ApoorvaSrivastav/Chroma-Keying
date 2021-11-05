# Chroma-Keying
What is Chroma Keying:

Chroma key compositing, or chroma keying, is a visual effects/post-production technique for compositing (layering) two images or video streams together based on color hues (chroma range).Here I am using Video shot against green screen to perform the Chroma Keying. The technique has been used in many fields to remove a background from the subject of a photo or video – particularly the news-casting, motion picture, and video game industries.
Chroma Keying is a type of mating problem of separating non-rectangular foreground from a rectangular background for allowing a substitution of different background. There are several approaches to solve a matting problem but Chroma keying uses the technique of using a constant backing(background) color.

Matte: Classically, matte is used as an opaque stripped mask to a transparent color film so that when light is projected on it, the light passes only through the transparent region of the matte and rest is blocked. A holdout matte is the complement of a matte having opaque region for the area of interest.

Alpha Channel: It is Digital Equivalent of holdout matte. It is a grayscale channel having full pixel value for the region to be seen and 0 pixel value for the region not to be seen. The values lie between 0 to 1 representing the transparency of the particular pixel.

Formal Presentation of Matting Problem:
Any image can be considered as f(Cf,Cb)=α * Cf + (1-α)*Cb ;
where Cf=Colour vector of foreground object , Cb= Colour vector of background image, α=Value of the transparency
In other words, an image can be understood as the combination of foreground and the background image in proportion to the α i.e. transparency.
In Case of an Image shot against a constant colour background: Cb is known and is equal to Ck, hence such an image can be represented as f(Cf, Ck)= α * Cf + (1-α)*Ck ;
Now if we know α and Cf for this image we can get exactly those pixels locations for which the foreground object is present and then replacing Ck with some other background Vector Cb exactly. That is, New Image formed is f(Cf, Ck, α)= α * Cf + (1-α)*Cb. Its an interesting concept but there is an intrinsic problem associated with the solution discussed in next section.

In the Blue Screen Matting Paper(https://github.com/ApoorvaSrivastav/Chroma-Keying/blob/main/BlueMatt-Smith-Blinn.pdf), 
the solution to the problem has been stated by 3 methods and one previous work of:

1) Petro Vlahos Method
2)No Blue
3)Gray or Flesh
4)Triangualtion

My Implementation: I obtained 4 solutions by experimenting 4 methods.
-----------------
1) Thresholding the Image(Intuitive Way)
2) No Blue method but customized as per the image background requirements
3) Hybrid of first 2 methods
4) Vlahos Formula
The best results are obtained by the Thresholding Method


Foreground GIF
-------------------------
![Foreground Video](https://github.com/ApoorvaSrivastav/Chroma-Keying/blob/main/GreenScreen_foreground.gif)

Background GIF 
--------------------------
![Background Video](https://github.com/ApoorvaSrivastav/Chroma-Keying/blob/main/Background.gif)

Thresholding GIF
--------------------
![Thresholding Video](https://github.com/ApoorvaSrivastav/Chroma-Keying/blob/main/Chroma_Threshold.gif)

NoGreen GIF 
-------------------
![NoGreen Video](https://github.com/ApoorvaSrivastav/Chroma-Keying/blob/main/Chroma_NoGreen.gif)

Hybrid GIF 
--------------------------
![Hybrid Video](https://github.com/ApoorvaSrivastav/Chroma-Keying/blob/main/Chroma_Hybrid.gif)

Vlahos GIF 
--------------------
![Vlahos Video](https://github.com/ApoorvaSrivastav/Chroma-Keying/blob/main/Chroma_Vlahos.gif)


