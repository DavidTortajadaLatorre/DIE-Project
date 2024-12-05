<p align="justify">
The second challenge consists of trying to beat a pre-existing model while keeping the network complexity and computing resources as close as possible to the original.

In first place we need to know what is the structure of the existing model (blocks), as well as its hyperparameters and internal settings.

**Original:** 

_Learning Block: Transfer Learning_

_Tuning Hyperparameters: Training Cycles = 20, LR = 0.0005_

_Model: MobileNetV2 96x96 0.35 (final layer: 16 neurons, 0.1 dropout)_ 

Initial Scheme:

Initial Results: 

**First Idea: ADAPTATIVE LEARNING RATE!**

This technique is one of the basic pillars of ML, as it allow us to seriously improve the converge of the loss function. However, this option can only be used in Edge Impulse under paid license (there is a 14 day free trial though). That is why the following results will be done with the basic option.

**Second attempt: Modify the blocks and general scheme.** 

As proposed in the cited webpage [1], reducing the size of the images might improve this model.

![image](https://github.com/user-attachments/assets/0805c8cc-075c-42d2-b606-030fe1726ca3)

For the block structure, Edge Impulse offers, by default (in this type of problem), a pre-trained model. If we use the “classical” Classification block, we would be able to manually design the complexity and depth of the network. However, as it may be expected, after a couples of tries we couldn’t get any better results.



**Third approach: From grayscale to colour + Data Augmentation**

We expect a sligth enhancement 

**Fourth Idea: Dropout rate.**

Now, we are proposing a grid search experiment with dropout rates (0.1, 0.2, 0.5) to determine the optimal setting for our dataset.

Original/Default dropout: 0.1 --- Accuracy: 82%


**Fifth Aim: More training cycles** 

This might not be the best approach since we would be breaking the rules: trying to beat the model in efficiency not size/computer resources. However, I think that just augmenting the number of training cycles



 </p>

**Last but not least: How to interpret results?**

 [1] https://docs.arduino.cc/tutorials/nicla-vision/image-classification/

