<p align="justify">

**First project: Creating a Basic Model.** 

_Data used: 2 manually labeled classes._ 
![image](https://github.com/user-attachments/assets/e031998a-d3e1-4af1-8b03-64adb1bff858)


With default settings, we would obtain these results:

**Accuracy: 55% / Pecision 17%**

For the first attempt at creating the model, 2 groups called “apples” and “bananas” were used, each with 100 photographers for training and 50 for testing on YOLOv5.
The transfer learning model is based on Ultralytics YOLOv5 using yolov5n.pt weights. It accepts RGB as input. However, with the increase in the number of photographers 425 for training and 122 for testing this model due to limited time and the large number of samples, it cannot complete the task started.

![image](https://github.com/user-attachments/assets/d20aa8c2-90b8-456e-88f0-0a3ce9b1fbdc)
![image](https://github.com/user-attachments/assets/0588efc6-f75e-42c5-97b1-1ae2b2468f30)
![image](https://github.com/user-attachments/assets/2a3e997d-0a3c-40c7-8ee2-649cbb779559)

The second attempt was made on the same number of samples, but with another model, YOLOv5 for the Renesas DRP-AI Community, the learning model using the YOLOv5 v5 branch with weights yolov5s.pt. This block is only compatible with Renesas DRP-AI.

**This time the model obtained notable results with more training rounds and with a similar time compared to the previous model.**

![image](https://github.com/user-attachments/assets/1824a7ca-80b9-4baf-b5f4-a423c38f25fb)
![image](https://github.com/user-attachments/assets/c81cebdc-9fbf-42af-a651-187a11f344ea)
![image](https://github.com/user-attachments/assets/d04c4c1f-9136-42b7-8671-d45b63d48d10)

For the third attempt, a more rudimentary model, FOMO (Faster Objects, More Objects) MobileNetV2 0.35 was used A MobileNetV2 based object detection model (alpha 0.35) designed to coarsely segment an image into a grid of background vs. objects of interest. These models are designed to be <100KB in size and accept grayscale or RGB input at any resolution.

**This model did not perform very well given the limited time given by the program in the standard training plan, its run and test version.**

In conclusion, a machine learning model needs time, resources and strength - many samples passed through countless training cycles - to reach the necessary maturity and maximize the precision and accuracy of an image detection and classification program.

 </p>
