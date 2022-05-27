# Fingerprint Liveness Detection

<h2>PROBLEM STATEMENT</h2>
To develop a system that classifies the given sample of fingerprint into real or fake and also categorize the spoofing material used for fake fingerprint, using deep learning techniques.
<br>
<br>
<h2>ABSTRACT</h2>
Fingerprints are unique way of identifying an individual as no two individuals have the same fingerprint. Fingerprint doesn’t lose its pattern even under adverse conditions where the fingers might undergo burns or tearing of the skin. So, fingerprint biometric is considered more reliable compared to other biometrics. Therefore, it is widely used and will be very beneficial to us in the future if we overcome the threats that it currently has. Some of the menaces are, Fingerprint scanners can be spoofed by artificial fingers which can be made using mouldable plastic, clay, Play-Doh, gelatine, silicone, rubber and other materials. Thus, developing an efficient method to protect fingerprint systems from imposter access is urgent. Liveness detection is an anti-spoofing method which can detect physiological signs of life from fingerprints to ensure only live fingers can be used for enrolment and authentication. Other obstacle that the fingerprint system comes across is that sometimes the fingerprint scanner might also have some dust particles on it or the sensor might be moist due to humidity, therefore the images generated might have some distortion and noise, this distortion has to be removed before classification. FdeBlur-GAN removes the blurriness from the fingerprint image and this De-Blurred image is fed into deep learning models such as CNN,VGG-16 which will identify if the fingerprint image is live or fake and if the sample is found to be fake then the spoofing material is classified.
 
 ![Screenshot 2022-05-26 at 1 48 09 PM](https://user-images.githubusercontent.com/91361896/170448037-6a075240-105e-4be3-bff4-b95fc1091940.png)

 <br>
 <br>
<b>Keywords:</b> Fingerprint, GAN, CNN, VGG 16, Authentication, Spoofed, Liveness, Distortion
<br>
<br>

<h2>PREAMBLE</h2>
Fingerprints have played a major role in identification of an individual. In many real time scenarios like employment, defence security clearance, fraud detection, and so on, fingerprints play an effective role in identifying the person and validating.
Since the fingerprint biometrics is widely used these days, there are many threats to this fingerprint system. One of major threats is the usage of spoofed fingerprints. Artificial fingerprint can made of rubber, plastic, wax, and gelatin which resembles the original fingerprint.
In current scenario our proposed system can be used in various sectors like forensics, military, banks and other departments where fingerprint is used for authentication. Our system will first denoise the fingerprint image and then identify whether the fingerprint is fake or live and if it is found to be fake the material used for spoofing is also identified which in turn increases the authenticity.
<br>
<br>
<h2>OBJECTIVES</h2>
▪ To Deblur the given fingerprint sample if required.<br>
▪ To extract the features of the fingerprint.<br>
▪ To detect if the given fingerprint sample is Fake or Real.<br>
▪ To classify the spoofing material when the detected sample is fake. <br>
▪ To design graphical user interface for the model.<br>
<br>
<br>
<h2>PROPOSED SYSTEM</h2>
Fig 2.1 represents the block diagram which describes the flow/process of the entire system. FDeblur-GAN framework consists of a cGAN deblurring network and the output of the FDeblur-GAN is given as the input to the deep-learning model.These images are fed into deep learning models like CNN or VGG-16. After processing the image, it is then fed into a classifier which classifies the input image as fake or real. If the image is fake, then it is further classified based on the type of material the fake fingerprint is made from.

![Screenshot 2022-05-26 at 1 39 30 PM](https://user-images.githubusercontent.com/91361896/170446502-569f32cd-56c3-4c5c-9765-4532f6159e5c.png)

<h2>USE CASE</h2>
Fig 3.1 describes the functionality and requirements of the system.
The use cases in the figure are : Login into the system, Upload the input image, View Live/fake and Develop a GUI.
Login into the system includes: entering the user ID and the password.
View Live/Fake use case has an extend relationship with the view spoofing material for fake image use case as shown in the figure 3.1
    
![Screenshot 2022-05-26 at 1 41 29 PM](https://user-images.githubusercontent.com/91361896/170446932-2713fd55-3045-476f-be4f-c9bc29ed5813.png)

<h2>DATASET</h2>

❑ The dataset which we acquired consists of real and fake fingerprint samples with different sensors.<br>
❑ The fake fingerprint sample consists of different spoofing materials i.e Body Double , Ecoflex , Playdoh ,Gelatine , Latex , Wood glue.<br>
❑ Total training images – 8983 (4473 fake fingerprints ,4510 live fingerprints).<br>
❑ Total testing images - 6551 (2051 fake fingerprints ,4500 live fingerprints).<br>

<h2>DATA PRE-PROCESSING</h2>

• Re-scaling : Helps to get the pixel value between 0 and 1.<br>
• Shear range : image will be distorted along an axis, mostly to create or rectify the perception angles.<br>
• Zoom range :This method randomly zooms the image either by zooming in or it adds some pixels around the image to enlarge the image.<br>
• Horizontal flipping : Reversing the entire rows and columns of an image pixels horizontally.<br>
Model Used : Convolution Neural Network, VGG16 ,DeBlur-GAN
<br>
<br>

<h2>GUI developed using Django Framework</h2>

![Screenshot 2022-05-26 at 2 01 16 PM](https://user-images.githubusercontent.com/91361896/170450481-adc3192e-257a-4518-a8dc-24adedeb62e6.png)

Fig 7.3 shows the home page of the GUI developed using Django Framework. Here the user is
provided with an option to upload the input image of .jpeg or .png type. Once the user uploads the image, the user should click on the submit button to view the result.

![Screenshot 2022-05-26 at 2 01 49 PM](https://user-images.githubusercontent.com/91361896/170450584-29991067-5187-46b9-83b8-9239446e98ea.png)

Fig 7.4 displays the result when the image is uploaded successfully i.e. it predicts whether the uploaded sample/input image was live or fake. In this figure it displays the result as Live. It also displays the image uploaded by the user.

![Screenshot 2022-05-26 at 2 02 24 PM](https://user-images.githubusercontent.com/91361896/170450667-1b8e343a-64a7-4826-91bb-11c191ba47f6.png)

Fig 7.5 depicts the various results generated for different types of fake fingerprint sample when the fingerprint image uploaded was predicted fake. It displays the spoofing material as shown in the figure. The different types of spoofing materials are shown in the figure i.e. BodyDouble, Latex and Gelatine.
