## Week 1
The meeting began with me reporting my summer progress and the work done before prior the meeting - I have read a few tutorials on PyTorch, have looked at how to run code on the GPU,
prepared a project template, set a repo and reference managers. We have discussed that we will mainly do group meetings so that everyone can benefit from this and get some experience
from their peers. We discussed what I should look at in the following week - Deep Predictive Coding, LSTMs, autoencoders, R-CNN, Mask R-CNN, heatmap to show which bits are relevant and which are not
as well as a PhD thesis on Cortical Feedback. We agreed that the framework used will be PyTorch. 

## Week 2
The meeting began with general guidance which is relevant for everyone's projects. We discussed the following questions
* Which pixels in the input contribute to output classification
* Does suppressing irrelevant information improve classification
We reiterated that by using feedback the layers could enhance relevant information and suppress irrelevant information.
Paul also suggested that I look into backpropagation to indicate which pixels contribute to the output. Another suggested point was to combine predictive coding and LSTMs
We also talked about semantic segmentation - looking at which pixels contribute to classification. investigate whether it can be done using feedback.
Concepts that I should continue to be looking at are LSTMs, autencoders, Semantic Segmentation Networks, ResNet, learning from annotated images.
Another topic discussed was the ensemble loss function which could minimize the difference between classification of pixels - find parameters which will best separate classes and minimize
the entropy between them.
We have discussed the main goals of the project
1) Understand different feedback mechanisms
2) Utilize them in the context of attention - highlighting relevant information
3) Segmentation - segment out the pixels and classify objects - look into whether can this be done with feedback
4) Build a model that looks at feedback mechanisms and make conclusions
Goals for incoming are for me to
1) Write a short description of the project
2) Look at what code there is in the field and how it works
3) Continue looking at background literature
4) See what modifications can be made to existing techniques

We also discussed the dissertation. Paul advised us that we should never start from a piece of blank paper - instead write down ideas and then expand them.
A possible structure of the dissertation is
1) What it has been discovered
2) Motivation
3) Background, literature review
4) Approach, results
5) Conclusion and further work

## Week 3
Description
The aim of this project is to investigate different feedback mechanisms using deep artifical neural networks. 
These will be then used to analyse which pixels in the input image contribute to object classification.
The motivation for building a model which utilizes feedback connections is that they are transmitting information to the early visual cortex not available via feedback connections.

Feedback allows expectation to be compared to reality. Feedforward makes a hypothesis what an image looks like.Feedback can compare what was hypothesised to the actual input image - measure error.
Topics discussed include Degree of feedback,Forward gain, feedback gain, gain face margin. As you increase the gain of the system, the negative feedback occurs more accurately.
Feedback connections in primary visual cortex.
We talked about the difference between early and primary visual cortexes - Early visual cortex - right of the back of the brain, Primary visual cortex - dominant visual cortex - V1 to V6 - consciously perceive visual stimulus
I was advised to look up a Neuroatanomy tutorial page - step by step anatomy of the visual cortex.
Tasks for next week are for me to write an autoencoder and a classifier for the CIFAR10 and combine their losses.
Also look up heatmaps with Pytorch. The heatmap will show which pixels are contibuting to the classification
Tools that I should look up are TensorBoard and TorchSnooper.
Hypothesis - with spatial feedback in a clutter feedback, you would expect the system to optimize to reduce the pixels which do not contribute to the classification process
We agreed that the approach should be small experiments on each type of architecture and then incrementally try on bigger datasets.


Buffer the output layers
Multiplies input with output or a learnable set of coefficients
Output image can be used to modulate the input image
Subtraction of output and input image - keep the relevant stuff
Binary mask: 0 for irrelevant, 1 for relevant
The mask will highlight diagnostic pixels
Backprojected pixels
Can you use the heatmap to modulate (multiply) the input image
Multiply input image by heatmap to reduce gain
Blend: alpha*heatmap*input_image + (1-alpha)*input image
Either all input image or the input image modulated by the heatmap
Reduce the contrast
Last idea - Recurrent architecture, use LSTMs and then train it temporal data

Further work
Semantic segmentation over an ensemble of different input images
Network trained on semantic segmentation and feed that back - bootstrapping

