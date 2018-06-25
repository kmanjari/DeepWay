# DeepWay
This project is an aid to the blind. Till date there has been no technological advancement in the way the blind navigate. So I have used deep learning particularly convolutional neural networks so that they can navigate through the streets. Watch the <a href="https://www.youtube.com/channel/UCVu2Ie45Bh89lpdg7ezdMyg?view_as=subscriber"> video </a>
# My Approach 
## Collecting Training Data
My project is an implementation of CNN's, and we all know that they require a large amount of training data. So the first obstruction in my way was a correclty labeled dataset of images. So I went around my college and recorded a lot of videos(of all types of roads and also offroads).Then I wrote a basic python script to  save images from the video(I saved 1 image out of every 5 frames, because the consecutive frame are almost identical). I collected almost 10000 such images almost 3300 for each class(i.e. left right and center). 
<br>Left image:</br>
![274](https://user-images.githubusercontent.com/24778913/41227028-10cf6888-6d91-11e8-805a-bef4814ed1c1.jpg)
<br>Right Image:</br>
![11](https://user-images.githubusercontent.com/24778913/41227057-2e4b95bc-6d91-11e8-83ff-4744bcf49382.jpg)
<br>Center Image:</br>
![146](https://user-images.githubusercontent.com/24778913/41227081-42005b88-6d91-11e8-8de5-6ee415d8f617.jpg)




## Training the Model
I made a collection of CNN architectures and trained the model. Then I evaluated the performance of all the models and chose the one with the best accuracy. I got a training accuracy of about 97%. I got roughly same accuracy for all the trained model but I realized that the model in which implemented regularization performed better on the test set
The architecture of the best model was:


##
   ![screenshot 247](https://user-images.githubusercontent.com/24778913/41226545-6982ca30-6d8f-11e8-88d2-b771b3647e54.png)
   ##
   
## Interfacing with the Arduino
The next problem was how can I tell the blind people in which direction to move .
So I connected my python program to an Arduino. I connected the servo motors to arduino and fixed the servo motors to the sides of an spectacle.  Using Serial communication I can tell the arduino which servo motor to move which would then press to one side of the blind person's head and would indicate him in which direction to move.<br> This is how the modified spectacles looked like</br>
![imag0397](https://user-images.githubusercontent.com/24778913/41227853-ec3f52fa-6d93-11e8-9760-6dcbd931fd4f.jpg)
<br>
![screenshot 252](https://user-images.githubusercontent.com/24778913/41864405-8a17f052-78c7-11e8-9cbf-c1d20847a074.png)
## Other Features

# Detection of stop signs. ##
This is done using opencv. I load in a pretrained stop sign haar cascade and then identify the location of the stop sign so that the device can steer the blind person.
##
![screenshot 250](https://user-images.githubusercontent.com/24778913/41857100-5252bbd8-78b4-11e8-8639-db7bf9359a58.png)
##
# Face Detection
This is achieved using Dlibs face detector.(trying to implement face recognition)
##
![screenshot 249](https://user-images.githubusercontent.com/24778913/41856995-0a62bc06-78b4-11e8-812b-38d02cdfca1d.png)
##
## Requirements
0. Python 3.x
1. <a href="https://tensorflow.org">Tensorflow 1.5</a>
2. <a href="https://keras.io">Keras</a>
3. OpenCV 3.4(for loading,resizing images)
4. h5py(for saving trained model)
5. pyttsx3
6. A good grasp over convolutional neural networks. For online resources refer to standford cs231n, deeplearning.ai on coursera or cs231n by standford university
7. A good CPU (preferably with a GPU).
8. Time
9. datetime
10. Patience.... A lot of it.

## Installing the requirements
1. Start your terminal of cmd depending on your os.
  2. If you have a NVidia GPU then make sure you have the prerequisites for Tensorflow GPU installation (Refer to official site). Then use this commmand

    pip install -r requirements_gpu.txt

  3. In case you do not have a GPU then use this command

    pip install -r requirements_cpu.txt

## Train your own classifier
To train your own classifier you need to gather data for all three type(.i.e images from left side of road, right side, and center region of the road) and then run model_trainer.py(you need to change the directories of images in model_trainer.py first).I used around 10000 images, if you want to have a look at the training data you can go <a href="https://drive.google.com/drive/folders/1RVr7L4O9TFomO4gHv4XXTaAKZffk_95P?usp=sharing">here</a> or you can download the <a href="https://drive.google.com/drive/folders/1AN712GckTDCcFdISsulOSMb2zJwINwmh?usp=sharing">pretrained model</a>
It took me about 30 minutes to train each network.<br>
## My laptop Specifiactions
1) intel core i3<br>
2) 4gb ram<br>
3) nvidia 930m graphics card

## Running the complete system
To run the complete system 
<br>1)Just clone the entire repo
<br>2)Upload Arduino_blind.ino to your arduino which is connected with your two servos
<br>3)Download the pretrained model and paste it in the deepway-master directory
<br>4)Change the COM port name in blind_runner.py
<br>5)run blind_runner.py(make sure to connect the arduino before running)

## Liked it
Tell me if you liked it by giving a star. Also check out my other repositories, I always make cool stuff. I even have a youtube channel "reactor science" where I post all my work.
## Have Questions ??
You can contact me on my facebook page <a href="https://www.facebook.com/reactorscience/">"reactor science"</a>




