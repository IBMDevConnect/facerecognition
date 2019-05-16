# FACE RECOGNITION APP

## Build a Face Recognition app using FaceNet

This Project uses OpenCV's [OpenFace](https://cmusatyalab.github.io/openface/), a pytorch implementation of [FaceNet](https://www.cv-foundation.org/openaccess/content_cvpr_2015/app/1A_089.pdf) to train a simple SVM that performs deep facial recognition with minimal number (4-5) of images per class

### Pre-requisite:

1) Python
    
    For Windows- https://www.python.org/downloads/windows/
    For MAC- https://www.python.org/downloads/

2) Anaconda Installation- https://www.anaconda.com/distribution/

Follow steps mentioned in the blog to setup the environment- https://www.pugetsystems.com/labs/hpc/The-Best-Way-to-Install-TensorFlow-with-GPU-Support-on-Windows-10-Without-Installing-CUDA-1187/

### Steps:

1) Clone/Download the Github repo- https://github.com/krishnac7/Deep_facial_recognition

    `git clone https://github.com/krishnac7/Deep_facial_recognition.git`

2) Change the directory to facerecognition

    `cd facerecognition`

3) Install all dependencies

    `pip install -r requirements.txt`

4) Run make_class.py with class name as argument to create your own class of faces

    `python make_class.py --class Bob`
    
    OR _Manual Addition:_   
 
    1) Create a new folder with class name as the directory in dataset folder eg: Bob
    2) Add images of the New Person into directory ( make sure there is only one person in the image )

NOTE: You need atleast two classes in the dataset folder to proceed with training

5) Run train.py to create corresponding embeddings and pickle files in the output folder

    `python train.py`

6) Run recognize.py to run facial recognition on an image

    `python recognize.py --image <PATH_TO_TEST_IMAGE>`

7) Execute the following to run facial recognition on webcam

    `python recognize_video.py`

Optionally you can pass in the argument --unauth <CLASS_NAME> to sound alarm when that particular person is in the frame

    `python recognize_video.py --unauth Bob`


## Build a Face Recognition app using Watson Visual Recognition service

### Pre-requisite: 

1. IBM Cloud Account- https://cloud.ibm.com

### Steps:

1. Sign in to IBM Cloud and from IBM Cloud catalog, create Watson Studio service.

2. Open the Watson Studio service by clicking on Get Started.

3. From the Projects page in Watson Studio, create a new project.

4. When prompted, select the `Visual Recognition project` type.

5. If you have no instances of the Visual Recognition service, a new instance will be created. 
   If you have existing instances, you have a choice:
        Click the Existing option to associate an existing instance with the project
        OR
        Click the New option to create another new instance


6. Prepare images by clicking your's and your colleagues 10 face photos

7. Organize 10 images in two .zip files (For eg yours.zip && your_colleagues.zip)

8. Upload your files to your project from the Assets tab of your project in Watson Studio or from within the Visual Recognition model builder in Watson Studio, upload .zip files using the data panel. (If the data panel isn't open, you can open the data panel by clicking the Find and add data icon )

9. If a Visual Recognition service instance is not already associated with your project, follow the prompts to create a new service or associate an existing service. Note: A Visual Recognition service instance can be associated with only one project at a time.

10. Enter a name for your model.
     
11. Add .zip files to your model from the data panel. (If the data panel isn't open, you can open it by clicking the Find and add data icon (The find data icon).)
     
12. Click Train Model.

Wait for the training process to finish. You can leave the Visual Recognition model builder while the process runs. You can monitor the status of the training process by looking at the status of the model on the Assets page of your project.

13. Test the model after training has been completed.

## Additional Link

### Facial Recognizer (Model Asset Exchange)

The model detects faces in an input image and then generates an embedding vector for each face. The generated embeddings can be used for downstream tasks such as classification, clustering, verification etc. The model accepts an image as input and returns the bounding box coordinates, probability and embedding vector for each face detected in the image. The model is based on the the FaceNet model. https://developer.ibm.com/exchanges/models/all/max-facial-recognizer/
