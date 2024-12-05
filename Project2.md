<p align="justify">
The second challenge consists of trying to beat a pre-existing model while keeping the network complexity and computing resources as close as possible to the original.

In first place we need to know what is the structure of the existing model (blocks), as well as its hyperparameters and internal settings.

**Original:** 

_Learning Block: Transfer Learning_

_Tuning Hyperparameters: Training Cycles = 20, LR = 0.0005_

_Model: MobileNetV2 96x96 0.35 (final layer: 16 neurons, 0.1 dropout)_ 

Initial Scheme:

![image](https://github.com/user-attachments/assets/719c1526-f756-49a7-9478-605f0350d2fb)

Initial Results:

![image](https://github.com/user-attachments/assets/40c332d7-91df-4b4a-9bec-2264c5a3b5a6)

**First Idea: ADAPTATIVE LEARNING RATE!**

This technique is one of the basic pillars of ML, as it allow us to seriously improve the converge of the loss function. However, this option can only be used in Edge Impulse under paid license (there is a 14 day free trial though). That is why the following results will be done with the basic option.

![image](https://github.com/user-attachments/assets/b35a8536-be5f-4d08-bbe6-8193056562f5)

**Second attempt: Modify the blocks and general scheme.** 

As proposed in the cited webpage [1], reducing the size of the images might improve this model.

![image](https://github.com/user-attachments/assets/193d4341-2f91-4489-b3a7-a5d503dec191)

For the block structure, Edge Impulse offers, by default (in this type of problem), a pre-trained model. If we use the “classical” Classification block, we would be able to manually design the complexity and depth of the network. However, as it may be expected, after a couples of tries we couldn’t get any better results.

![image](https://github.com/user-attachments/assets/f69fb871-cca6-4c81-b6b9-7bfbeaf1f886)

*****************************************************************************************

![image](https://github.com/user-attachments/assets/6b33eb1b-2ca7-4b43-ad16-fa7eb3bad862)

**Third approach: From grayscale to colour + Data Augmentation**

We are expecting an enhancement as a result of having more and better-quality data.

![image](https://github.com/user-attachments/assets/6abebf27-7077-4709-9321-6eb9ddb78881)

**Fourth Idea: Dropout rate.**

Now, we are proposing a grid search experiment with dropout rates (0.1, 0.2, 0.5) to determine the optimal setting for our dataset.

Dropout: 0.1 --- Accuracy: 82% (Original/Default)

Dropout: 0.1 --- Accuracy: 86%

Dropout: 0.1 --- Accuracy: 84%

Dropout: 0.6 --- Accuracy: 78%

**Fifth Aim: More training cycles** 

This might not be the best approach since we would be breaking the rules: trying to beat the model in efficiency not size/computer resources. However, we think that just augmenting the number of training cycles and therefore the trainig time by some minutes is an assumable option.

From 20 to 50 training cycles:

![image](https://github.com/user-attachments/assets/aea1084d-2cf5-4703-a56a-fe195b3b5b81)

 </p>

**Last but not least: How to interpret results?**

 [1] https://docs.arduino.cc/tutorials/nicla-vision/image-classification/

