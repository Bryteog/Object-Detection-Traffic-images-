#### Overview

Built a model to detect real world object in images collected by a self driving car moving through traffic.

#### Model

The YOLO algorithm is used. The algorithm passes through the network once, make predictions and display the output along with bounding boxes. 

The images are reshaped to a size acceptable by the model (608, 608, 3). The algorithm computes a probability that an object exists in the image and the probability that the object belongs to a certain class. The product of the two becomes the score. The bounding boxes enclose the detected objects and display the object class and score. 
Non-max suppression is implemented to remove boxes with low probabilities of an object or a class. A probability threshold is set and any box below this threshold is removed. This process is repeated until there are no such boxes. 
The output of the YOLO model is converted to box corners coordinates, this serves as the input for the yolo_filter_boxes function to compute the box scores.