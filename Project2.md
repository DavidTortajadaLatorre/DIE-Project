The second challenge consists of trying to beat a pre-existing model while keeping the network complexity and computing resources as close as possible to the original.

In first place we need to know what is the structure of the existing model (blocks), as well as its hyperparameters and internal settings.

**Original:** 

_Learning Block: Transfer Learning_

_Tuning Hyperparameters: Training Cycles = 20, LR = 0.0005_

_Model: MobileNetV2 96x96 0.35 (final layer: 16 neurons, 0.1 dropout)_ 

Initial Scheme:

Initial Results: 

**First Idea:**

ADAPTATIVE LEARNING RATE! This technique is one of the basic pillars of ML, as it allow us to seriously improve the converge of the loss function. However, this option can only be used in Edge Impulse under paid license (there is a 14 day free trial though). That is why the following results will be done with the basic option.

**Second attempt: Modify the blocks and general scheme.** 

As proposed in the next webpage, reducing the size of the images might improve this model.

For the block structure, Edge Impulse offers, by default (in this type of problem), a pre-trained model. If we use the “classical” Classification block, we would be able to manually design the complexity and depth of the network. However, as it may be expected, after a couples of tries we couldn’t get any better results.


