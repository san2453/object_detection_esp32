# object_detection_esp32

https://pjreddie.com/darknet/yolo/
So this repository consists of an esp32cam that can detect any object given in yolov3 listed under coco.names in coco dataset. To make your own set of objects it can detect, please create a custom dataset which is properly anontated and then train yolov3 respectively using that. The code for doing the same can be found on youtube https://youtu.be/m9fH9OWn8YM?feature=shared. 

The file has two primary codes, one arduino setup for esp32cam connected to FTDI using the circuit diagram given and one object detection file running yolov3 on coco dataset. 
The arduino setup file is programmed keeping servo connection in mind, if you are not using a servo to mount your esp, please remove that code block. Once all the libraries mentioned in the cam_mod_servo are downloaded, run the file and extract the ip address of the camera and set resolution by doing /hi.jpg or /lo.jpg etc.
to run the specificobject.py, you require the ip address with the resolution along with coco.names (file containing label of classes of objects in coco dataset) as well as yolov3.cfg and yolov3.weights file. These files can be downloaded from the link given on top of this document or just refer to a video on how to download  config and weights files of yolo trained on custom dataset. 

After all appropriate settings, i created dummy classes for cat and bird so that the program detect only cats and birds, replace that with the class label you wish to detect (you can make a simple input variable by saying detect=input("enter class") and feed it into the code). Once that is done, the code should detect the required class only whilst the servo spins to increase the range of camera of esp32
