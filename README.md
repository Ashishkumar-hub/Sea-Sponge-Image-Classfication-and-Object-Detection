# sea_sponge_transfer_learning

Aim: This is my end to end project submisson for problem statement by DroneBase.

#### Problem Statement:

Build and train a system to perform object detection of Sea Sponges

#### About Sea Sponge:
    
    Sponges may look like plant life, but they are actually animals. These sea-bottom dwellers are very simple multi-cellular creatures. 
    There are various types of sea sponges found on reefs and deep-sea bottoms. 
    Some are loners, while others grow in colonies. They have a very wide range of sizes, shapes and colors.
    
    Tube Sponge
    The tube sponge (Callyspongia vaginalis) attaches itself to a reef, which is where it makes its home. 
    This type of sponge is one of the most recognized of all sea sponges because of its tubular shape. 
    It can be very colorful with hues of purple, green, gray or blue. 
    The tube acts like a filter, taking in water from one end and ejecting it out the other. 
    It extracts nutriments out of the water that it filters.
    
    Vase Sponge
    The vase sponge (Ircinia campana) resembles a bell in shape. 
    This type of sponge makes its home in the waters of the Caribbean and off the eastern coast of Florida. 
    It attaches to rocks on the sandy bottom of the ocean. The vase sponge can grow to 3 feet high and be as wide as 2 feet. 
    The colors of this sponge are hues of red, brown and purple.
    
    Yellow Sponge
    The yellow sponge (Cleona celata) makes its home in the Pacific coastal waters of the United States. 
    This type of sponge is not a loner and usually grows in small colonies. 
    It gets its name from its appearance of bright yellow as a predominate feature. 
    It also has hues of orange throughout. This sea sponge is tiny and can be found on a reef encrusting the rocks.
    
    Bright Red Tree Sponge
    The bright red tree sponge (Haliclona compressa) lives in the Caribbean. 
    This type of sponge makes a good pet for your home aquarium. 
    It is relatively small and does not grow much bigger than 8 inches in height. 
    Its color is generally in hues of red. This species will require a moderate flow of water and dim lighting if it is going to live out of its natural habitat.
    
    Painted Tunicate Sponge
    The painted tunicate (Clavelina picta) is a type of sponge that gets its nutriments from the water that it takes in then ejects. 
    Painted tunicates are another type of sponge that grows in colonies. They are very small, growing to only about ¾ inch long. 
    They are translucent in color with red, yellow and purple hues.
    
    Sea Squirt Sponge
    The common sea squirt (Didemnum molle) is another type of sea sponge that is a reef dweller. 
    It makes its home on rocks forming a crust around them. 
    It is usually found in deeper water and grows in large colonies. 
    This type of sponge has a leather look to it. It is bag-shaped and has a spotted exterior and is bright green inside. 
    You will sometimes see these growing on rocks in an aquarium.

#### Dataset Description 
    
    The dataset was collected from google images using Image Scrapper from my GitHub Repository for downloading 
    the 6 different types of sea sponges.
    
    Drive link to data set: https://drive.google.com/drive/folders/1JfFf2CY7k3dbPjXxSHkP47U6afs-EcRm?usp=sharing
    
    I have used 60 Images for training the model and 58 images for testing it. All the images belong to 6 different 
    classes of sea sponge as mentioned in description.
    
The Dataset for object detection is present at RoboFlow:

![image](https://user-images.githubusercontent.com/55132850/154831265-25ffd394-e236-442a-ac92-75ca8eb1ef51.png)

[Link to dataset - Click Here](https://app.roboflow.com/ashish-kumar-zqc1g/sea-sponge-yt6q6/1)

#### Model Training 
    
    For Image Classiification:
    The platfom I initially used for creating the model was Google Colab as it provides free GPU usage.
    For training the model Resnet50 using imagenet weights was used.
    
    I have compared it with VGG19 the results of VGG19 were not satisftory so went ahead with saving the Resnet50 model.
    
    For Object Detection:
    I have tried with Tensorflow Object Detection API and YoloV5 the results were much better in case of YOLOv5.
    - the porcess for gatherig the dataset was same as for image classiification then labelling was done using labelimg tool later i exported the dataset to roboflow if you don't want to download the labelimg tool you can use roboflow for labelling the images and gerate the API key then use that in colab for mmodel training.
    
#### For Running the Project:
    
    For Image Classification: 
    
    Below I have mentioned the Deployed link of the sample application that can be used for prediction purposes right away.
    
    Download the zip file extract it it already has a h5 file for Resnet50 trained model
    
    > Open the project in Pychram or VS code 
    
    > Create a new Conda environemnt 
        - File > Settings > Python Interpretor > Add > Clreate new conda environment
        
    > Activate the enviironment in terminal conda activate "ENV_NAME" 
    
    > Run : pip install - requirements.txt
    
    > Run the project find it on http://127.0.0.1:5000/
    
    > Kindly use some of the images in uploads folder for testing it or you can see the SS below.
    
    For Object Detection:
    
    > Gather the dataset of images and label our dataset (Just like image classification use the image scrapper for it or you can use the images used for image classification task)
    
    > we will label the imgges for differen type of sea sponge using labelimg tool or you can use roboflow for that task it gives you free aceess if you keep the dataset public
    
    > Export our dataset to YOLOv5 (we will put our dataset in roboflow and generate the API key from there and use that for training the model)
    
    > Train YOLOv5 to recognize the objects in our dataset
    
    > Train the yolov5 model for our dataset we kept on roboflow
    
    > Evaluate our YOLOv5 model's performance
    
    > Run test inference to view our model at work
        
#### Results
   
    For Image Classification: 
    With only 60 traning and 58 test images I got an accuracy of 80% with a validation accuracy of 45%. 
    It can be improved just for submission purposes i have used the model that i have created initially.
    
    Reset50 is a powerful model we just need to increaase the number of traning and test images in the dataset 
    to increse the model peformence.
    
    I made a sample application using flask for the client or the end users to make predictions easily with just one click
    I was configuring the CI CD pipelines for the project using docker and circle CI and deploying it on Heroku 
    but the space issue was there for submission purpose I have deployed the model on Azure Cloud without the CI CD configuration
    Kindly find the other projects in my Github repo for seeinga demo of that.
    
    For Object Detection:
    I have ran yolov5 for 500 epochs this is for testing purpose only ideally it should be trained for 20000 for testing and aqround 100000 for production grade.
    The results were atmost satisfactory seeing I ran it for 500 epochs only.
    
 
Web App Link: http://seasponge.azurewebsites.net/

***Some Results SS for the IMAGE CLASSIFICATION ***

![Screenshot (239)](https://user-images.githubusercontent.com/55132850/154292845-147b186a-3097-4869-8cda-34a95bf0a205.png)

![Screenshot (240)](https://user-images.githubusercontent.com/55132850/154292851-ffd697fc-8d39-4dda-b4e8-35e6b854bfa7.png)

![Screenshot (241)](https://user-images.githubusercontent.com/55132850/154292863-c4fd422f-494b-4570-b6f4-8af2800d9827.png)

![Screenshot (242)](https://user-images.githubusercontent.com/55132850/154292889-8cafc48b-6e88-4990-9813-6ea033459c1a.png)

![Screenshot (243)](https://user-images.githubusercontent.com/55132850/154292896-555f4452-35f9-4658-8510-8c46a4530c42.png)

![Screenshot (244)](https://user-images.githubusercontent.com/55132850/154292910-e3cd0a9e-665c-4641-ac5f-c6f89ed4b48f.png)

***Some Results SS for the OBJECT DETECTION USING YOLOv5***

The result for object detection wo't be much great because i ran it for 500 epochs only we need to make it atleast 10000-20000 epochs still with just 500 epochjs it was able to detec the sea spongs it is pretty amazing in case of Tensorflow Object Detection API it failed to do so.

![download](https://user-images.githubusercontent.com/55132850/154830997-dd853ab5-ed60-4245-9d04-856f583c3856.jpg)

![download (1)](https://user-images.githubusercontent.com/55132850/154830999-bb5469af-a660-4f63-811f-767f1693b843.jpg)

![download (2)](https://user-images.githubusercontent.com/55132850/154831000-ae0d083c-da99-4fdc-9554-c9a1ebf8d36e.jpg)

![download (3)](https://user-images.githubusercontent.com/55132850/154831001-0d3a763b-0b43-46de-b127-dfab10f95b42.jpg)

![download (4)](https://user-images.githubusercontent.com/55132850/154831002-74d89b16-0621-46c7-a114-85e62119d740.jpg)
