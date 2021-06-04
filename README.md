# Face Mask Detection and Alert System
## Abstract
The rapid worldwide spread of COVID-19 has resulted in a global pandemic. Correct facemask 
wearing is valuable for infectious disease control, but the effectiveness of facemasks has been 
diminished, mostly due to improper wearing/not wearing of masks at all. The model is accurate, 
and since we used the MobileNetV2 architecture, it’s also computationally efficient and thus 
making it easier to deploy the model to embedded systems (Raspberry Pi, Google Coral, etc.). 
This system can therefore be used in real-time applications which require face-mask detection 
for safety purposes due to the outbreak of Covid-19 and alert the authorities if someone is seen 
without a mask/ restrict the entries of people in public place without a mask. This project can be 
integrated with embedded systems for application in airports, railway stations, offices, schools,
and public places to ensure that public safety guidelines are followed. Our method was trained 
and evaluated on the public dataset Medical Masks Dataset containing 1376 images with 690 
images of with facemask and 686 images without facemasks.
## Flow of the Project
1. Configure Working Directory and Mount Google Drive to make use of Google Colab.
2. Data Pre-prepressing to convert images to Grayscale and separate out labels and images.
3. Build a Convolutional Neural Network using Sequential API of Keras.
4. Train The Face Mask Detection Classifier on Image Data using Keras and Tensor as 
Backend.
5. Evaluate the model to see the Loss and Accuracy in Graphical Form.
6. Save or Serialize the Face Detection Classifier Model.
7. Download the model on the Local System and Load it in the program.
8. Use the live Web Cam Video Stream to Detect the Face.
9. Extract the Region of Interest of the Face.
10. Engage trained Face Mask Detection Model to the face identified and determine if the 
person is Wearing a mask or not.
11. Throw a Warning Message in terms of Pop-Up Window to highlight that Access Denied 
if the person is not wearing a Mask.12. Trigger an Email to the Concerned person/ Authorities alerting them if the Person is now 
wearing a mask
## Getting Started
I) Tech/framework/Libraries used:

• Keras Framework and TensorFlow as Backend: Since our model is neural Network based Deep Learning model, we are using Keras Framework to train our model.

• Hardware Accelerator: so, our model is trained on GPU Machine.

• Keras Packages: these packages are used to convert text and labels into 
oneHotencoded() form converting the data into Training and Test Dataset.

• Numpy and cv Packages: to access the live Web Cam Footage.<br/>
II) Building Convolution Neural Network (CNN) Classification Model<br/>
A. Different Convolutional Layers<br/>
• Convolution Layer: The convolution layer is the core building block of the CNN. It carries 
the main portion of the network’s computational load.<br/>
• Pooling Layer: The pooling layer replaces the output of the network at certain locations 
by deriving a summary statistic of the nearby outputs. This helps in reducing the spatial 
size of the representation, which decreases the required amount of computation and 
weights. The pooling operation is processed on every slice of the representation 
individually.<br/>
• Fully Connected Layer: Neurons in this layer have full connectivity with all neurons in 
the preceding and succeeding layer as seen in regular FCNN. This is why it can be 
computed as usual by a matrix multiplication followed by a bias effect.<br/>
B. Flatten: This Function Converts the input into a 1-D array to make connections final 
layer.<br/>
C. Dropout : This Function is used to overcome the Overfitting problem in neural Networks<br/>
D. Soft_Max Activation Function: Used for multi class Classification Problem. It reports the 
Classification Score for each class<br/>
III) PLOTS OF THE ACCURACY OF TRAINED MODE<br/>
![snap1](https://user-images.githubusercontent.com/69399113/120862319-5e2a3700-c5a6-11eb-8b11-e5ee5971c2e1.JPG)

IV) Dataset <br/>
The dataset used is present in the zip file submitted as Project Code.<br/>
This dataset consists of 3835 images belonging to two classes:<br/>
• with mask: 1916 images<br/>
• without mask: 1919 images<br/>
The images used were real images of faces wearing masks. The images were collected from the 
following sources:<br/>
• Kaggle datasets<br/>
• RMFD dataset<br/>
• MyDrive dataset<br/>
## Mask Detection
To detect whether someone is wearing their mask, we follow those steps:<br/>1. Detect if there is a person’s face in the current footage (MobileNet v2)<br/>
2. If so, crop the image to that face bounding box.<br/>
3. Apply a mask / no mask binary classifier on the cropped face. <br/>
4. Create an event if no mask is detected and store it on local storage.<br/>
The logic is detailed in the main () function of our detect.py file.<br/>
## MASK ALERT SYSTEM
1. The next step id notification services for sending email to an administrator with a 
summary of the event, to be sent (alert for someone not wearing their mask).<br/>
2. The libraries used are smtplib library is used to an alert email to the authorities/ violator 
to alert if someone is not wearing a mask.<br/>
3. tinker function is used to create the frame window which needs to be removed after 
detection. This is done using the withdraw function.<br/>
4. The variable subject and message define the Subject and the message that has to be sent 
via email.<br/>![Capture](https://user-images.githubusercontent.com/69399113/120863358-07256180-c5a8-11eb-8519-7b613ec21aa8.JPG)</br>
## Conclusion
Our model gave 93% accuracy for Face Mask Detection after training via tensorflow-gpu==2.0.0 </br>
![s1](https://user-images.githubusercontent.com/69399113/120863549-5ec3cd00-c5a8-11eb-9973-41ac74f834e4.JPG)




