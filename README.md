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


### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
