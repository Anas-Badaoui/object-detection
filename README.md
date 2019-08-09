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

### How to run the code 

We have six command line arguments which allow us to pass information to our people counter script from the terminal at runtime :

--prototxt : The path to the frozen graph file.

--model : The path to the pbtxt file.

--input : Optional input video file path. If no path is specified, your webcam will be utilized.

--output : Optional output video path. If no path is specified, a video will not be recorded.

--confidence : With a default value of 0.4 , this is the minimum probability threshold which helps to filter out weak detections.

--skip-frames : The number of frames to skip before running our DNN detector again on the tracked object. Remember, object detection is computationally expensive, but it does help our tracker to reassess objects in the frame. By default we skip 30  frames between detecting objects with the OpenCV DNN module and our CNN single shot detector model.

For example, if we are in the object-detection folder :

```
python people_counter.py --prototxt /inference_graph_ssd_mobilenet_v2/frozen_inference_graph.pb --model /inference_graph_ssd_mobilenet_v2/graph.pbtxt --input /videos/compilation_highD_to_use.mp4 --output /output/test_output.avi --skip-frames 2
```

### How does the tracking work :

Each frame of the input video file is divided into 3 areas :

- **The top area** : The top zone of the frame; area = 1/8 of the total area of the frame.

- **The bottom area** : The bottom zone of the frame; area = 1/8 of the total area of the frame.

- **The medium area** : The zone between the **top** and **bottom** area.

![Image of Yaktocat](https://octodex.github.com/images/yaktocat.png)


