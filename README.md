# HawkEye - An Automated Violence Detection System for CCTVs
With the increase of surveillance cameras in modern cities, there are insufficient human resource for monitoring all the screens at one time. In our project, we use machine learning techniques to detect violent behavior so a quick alarm can be given in time. This project is mainly intended to serve as an alarm system for the police/security forces to respond quickly to occasions of violence which can be curbed before they escalte out of control. 

We have built and implemented an automated system which can be integrated with the CCTV Systems and will alarm the appropriate authorities whenever violent behavior is detected in an CCTV footage. The detection is done with the assistance of an ML Model implemented in TFLite, for lightweight and fast execution. This Model was trained on [RWF2000 Dataset](https://github.com/mchengny/RWF2000-Video-Database-for-Violence-Detection) which is a collection of nearly 2000 video clips as a new data set for real-world violent behavior detection under surveillance camera.  

### There are two parts of of this project:

#### 1) The implementation of an example System code in Python (in the `SystemCode` directory) :- 

This directory contains an implementation of the Python Script which can be easily integrated with CCTV Systems. It is a multithreaded Python Script which uses OpenCV framework to captures frames from a video stream in one thread while simultaneously running the ML model in a different thread. This ensures smooth execution of multiple prediction by the ML model as well as efficient use of computing resources. Whenever this script detects violent behavior in a footage, it signals a central Firebase server which then forwards the location of camera along with a small footage clip to all the authorities connected with the organization.

#### 2) The implementation of the Flutter App (in the `Flutter App` directory) :-

This directory contains the implementation of an Flutter App which will can be installed on the mobile devices of appropriate authorities and will serve as the receiving endpoint of any signal given off from the server. Using this app, users will be able to SignUp using a unique organization ID provided only to the people specified by organization to avoid unneccessary spread of the footage. Whenever the script in the CCTV Systems detects violent behavior a small video clip is sent to this app along with location and coordinates of the camera from which the footage was taken. Authorities can then stream this video and prepare a response force of an appropiate size. The app also features the ability to show the shortest route to point of crime from the current location of the user using Google Maps.
