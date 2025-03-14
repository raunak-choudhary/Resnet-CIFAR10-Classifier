CIFAR-10 Image Classification with Modified ResNet

Team Information

Team Name: Decoders


Team Members:

Raunak Choudhary (raunak.choudhary@nyu.edu, NetID: rc5553)
Debika Dharma Lingam (dd3873@nyu.edu, NetID: dd3873)
Yashavika Singh (ys6668@nyu.edu, NetID: ys6668)



Project Overview:
This project implements a modified ResNet architecture for CIFAR-10 image classification, optimized to achieve high accuracy while keeping the parameter count under 5 million parameters. We achieved 94.80% validation accuracy while using only 4,969,600 parameters.
Model Architecture
We have designed an improved Pre-Activation ResNet architecture with several enhancements:

Pre-activation Residual Blocks: Unlike the original ResNet, we use batch normalization and activation before convolutions, which improves gradient flow during training.
Mish Activation Function: Replacing ReLU with Mish activation (x * tanh(softplus(x))) provides better gradient propagation and performance.
Attention Mechanisms: We implemented CBAM (Convolutional Block Attention Module) to help the network focus on the most important features both channel-wise and spatially.
Strategic Channel Progression: Careful tuning of channel dimensions (30→60→120→240) helps control parameter count while maintaining high representational capacity.
Optimized Residual Block Structure: [2, 2, 5, 3] block structure across the network layers, providing deep representation without excessive parameters.

Training Approach:
Our training methodology includes several advanced techniques:

One-cycle Learning Rate Schedule: Faster convergence with controlled learning rate changes
Label Smoothing: Prevents overconfidence and improves generalization
CutMix Data Augmentation: Mixing images together for better robustness
Comprehensive Data Augmentation: Random crops, flips, color jittering, and random erasing
AdamW Optimizer: Better weight decay implementation for regularization

Results:

Model Size: 4,969,600 parameters (under 5M limit)
Best Validation Accuracy: 95.60%
Training Time: Approximately 75 minutes

Installation & Requirements:
To run the code, you need the following dependencies:
numpy>=1.19.5
pandas>=1.3.0
torch>=1.9.0
torchvision>=0.10.0
matplotlib>=3.4.2
Pillow>=8.2.0
scikit-learn>=0.24.2

License:
This project is submitted as part of the Deep Learning course at NYU.
