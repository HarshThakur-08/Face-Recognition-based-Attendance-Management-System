# Face-Recognition-based-Attendance-Management-System

# Problem Statement
The main problem with the traditional attendance system is that it is subject to manipulation and thre remains chance of human error during data entry. Though it is easier to implement and saves technology expenses, the organization cannot benefit from the innovations of data analysis which has huge implications. In addition to this, contemporary attendance method at classroom requires human intervention and cooperation from students which contribute towards wastage of precious class time.

# Proposed Methodology 
The proposed automated attendance management system isbased on haar cascade for face detection and the LBPHalgorithm for face recognition. Graphical User Interface(GUI)for this system created using python moduleTkinter which is the fastest and easiest way to create a GUIapplication.This system provides functionalities such as taking images ofstudents along with their details for the database, training theimages in the database and on the camera and start trackingpeople entering the class. when students enter the classroomthis system detects the faces of students who are enteringthe classroom from the camera and pre-processed for furtherprocessing. 

<img width="394" alt="image" src="https://user-images.githubusercontent.com/70577185/178943344-995c2075-12cb-48a7-bbfe-5ced4c4c9d0e.png">

Local Binary Pattern(LBP) operation creates an imagewhich highlights the characteristics of a image in a better way.It uses the concept of the sliding window and the parameters,radius and neighbours.First, we convert the frame into matrices of 3X3 pixels. if aneighbor pixels in a matrix is greater than the median pixel ofthat matrix then set value 1 else 0 in that pixel position. nownote down the values of neighbour pixels in a line we get abinary number. convert that binary number to decimal numberand replace it with the median pixel value of the matrix asshown in above Fig.
As the image in now converted into LBP form, we extracthistograms from each grid and concatenate to form a newand larger histogram. The concatenated histogram indicatesthe characteristics of the original image. Each histogramrepresents the facial image from the database. For the newimage, it performs the above steps and gets a new histogramfor the image.
Now to recognize the person in the image it compares(by applying Euclidean distance) the new histogram with thehistograms from the training dataset and choose the histogramhaving lowest conﬁdence i.e. least distance, as lower conﬁ-dences are better and also extract the ID corresponding to thathistogram.

![image](https://user-images.githubusercontent.com/70577185/178947780-87a5fbf0-ea4a-4322-aa46-55ca1f6db7f2.png)


# Screenshots:
## Capturing Images & Training 
<img width="1267" alt="image" src="https://user-images.githubusercontent.com/70577185/178944461-7048167c-f9c1-4bfc-90ff-348e34d070cd.png">

## Entering the details:
<img width="1215" alt="image" src="https://user-images.githubusercontent.com/70577185/178944906-bb5c6866-fd53-4291-9039-c12075cae30a.png">

## Filling the Attendance 
<img width="1223" alt="image" src="https://user-images.githubusercontent.com/70577185/178945181-71a7baca-2c22-4303-9838-54dd069f409d.png">

# Result and Analysis 
We considered 3 feet as the distance of an object forrecognition. The Face recognition rate of students is 77% and its false-positive rate is 28%. This systemis recognizing students even when students are wearing glasses or grown a beard. Face Recognition of unknown persons for both existing and proposed models is 60%. This happened mostly due to detecting random objects in the background as the face of a person by face detection algorithm. Its false-positive rate is 14% and 30% for the proposed and existingmodel respectively. The threshold value only affected the false positive rate of an unknown person. In the existing system,it is observed due to when the person in the video turned his head greater slightly then conﬁdence value for that frame may get greater than favourable ﬁlter value then the person in the frame is considered as an unknown person.

In future, An effort could be made to build a better dataset, that might practically give a more accurate result.A system alert(voice and visual) can be included if an intruder is detected in the class. Also to avoid proxy, as we know students of this generation are really smart they can use an image of person to mark attendance who is not present at that time, so to tackle this situation we can add a feature in which we will be showing different handsigns that have to match by a person in order to mark attendance(like show thumbs ups, high-five).
