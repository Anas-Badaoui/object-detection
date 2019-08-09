# People detection and tracking in the OCP sites.

This repository assembles the necessary code for people detection, tracking and counting. The object detection has been done with the SSD Mobilenet model from the [Tensorflow Detection Model Zoo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md).

The main code is in the file **people_counter.py**. The algorithm used combines both object detection and object tracking.
This hybrid approach will allow us to significantly reduce the computational burden of the detection.

The SSD Mobilenet model files are stored in the **inference_graph_ssd_mobilenet_v2/** folder. 
The Centroid Tracking algorithm is stored in the **pyimagesearch/** folder.



### Prerequisites

To run this code, you'll need to install some python libraries : Numpy, OpenCv, dlib, imutils, intervals.

To install dlib use this guide : 
* [dlib](https://www.pyimagesearch.com/2018/01/22/install-dlib-easy-complete-guide/) - Installation guide
To install the other libraries, simply use a pip install command
