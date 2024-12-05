Bogdan 
What dataset is used in 




1 Creating a Basic Model:

For the first attempt at creating the model, 2 groups called “apples” and “bananas” were used, each with 100 photographers for training and 50 for testing on YOLOv5
the transfer learning model based on Ultralytics YOLOv5 using yolov5n.pt weights, accepts RGB input at any resolution (only square images), but with the increase in the number of photographers 425 for training and 122 for testing this model due to limited time and the large number of samples, it cannot complete the task started.





The second attempt was made on the same number of samples, but with another model, YOLOv5 for the Renesas DRP-AI Community, the learning model using the YOLOv5 v5 branch with weights yolov5s.pt. This block is only compatible with Renesas DRP-AI.
This time the model obtained notable results with more training rounds and with a similar time compared to the previous model.

 




For the third attempt, a more rudimentary model, FOMO (Faster Objects, More Objects) MobileNetV2 0.35 was used A MobileNetV2 based object detection model (alpha 0.35) designed to coarsely segment an image into a grid of background vs. objects of interest. These models are designed to be <100KB in size and accept grayscale or RGB input at any resolution.
This model did not perform very well given the limited time given by the program in the standard training plan, its run and test version.




In conclusion, a machine learning model needs time, resources and strength - many samples passed through countless training cycles - to reach the necessary maturity and maximize the precision and accuracy of an image detection and classification program.
