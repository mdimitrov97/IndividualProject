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
The motivation for building a model which utilizes feedback connections is that they are transmitting information to the early visual cortex not available via feedforward connections.

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

## Week 4
A prototype dissertation - status report
Always do simple thing first, then go to more complicated things

Subtractive feedback process
Encoding loss
Take a matrix of coefficients multiplied by input_image, subtract that from output
Class separation
Hypothesis - weight matrix will generate a mask covering the object
Leave stuff that is of interest
Linear predictive encoding networks
LSTM doing feedback between layers
Take the input, reconstruct it, multiply by -1
Take the input, multiply by 1

Joint loss - between the output and classification
2,3 fully connected layers
LSTMs/Recurrent units
Explicitly training a segmentation mask and a class - then using that in the feedback loop

Try and learn object class and segmentation mask at the same time through feedback

## Week 5
Questions to ask
End goal - what would the network do as a task - image captioning, visual question answering
Search terms for papers

Motivation should talk about particular object - This project is about ..., doing.., done by..., this is why the idea is important
.. and .. did this - comparison between my project and what has been done before, explain how it helped you solve your problem
Summarise the gap between what's done and what you're doing
Approach
Risk, mitigation of what you do
Reasons for doing things
Timeline from now until Christmas
Pixels 
2-3 fully connected#

Each individual loss
Plot the loss graphs
Focus the attention
1D tensor - input to the classifier
Infer the pixels itself
what feedback do we currently implement
Gated recurrent unit - previous inputs mixed with currently
Deep predictive coding - feedback between layers, output feeding back into the input
Attention-GAN!!!!!!!!!
Mix previous outputs with current inputs - what i want
Mix previous inputs with current inputs - what is done
Remember events that happened
Latent space
Match size of fully connected layer the output bottleneck layer
Take the encoded images and then flatten them to 1D, then take that and process through 3 FC
Adversarial autoencoder
rasbt/deeplearning models - look up this repo
Attention Guided CycleGAN
Conv LSTM takes the output of the autoencoder
Terms by which to search papers - recurrents, attention, predictive coding, feedback networks, extended surround

Cortical mapping

## Week 6
We discussed that the combined model should be compared with the baselines.
Actions for me to do are plot the graphs and look at the ranges of the different losses as well as split the training set into training and validation.

## Week 7
We looked at the way the models are performing. We found out that the architectures are not exactly the same.
Actions for me to do are to make sure architectures are identical and look at how they're performing.
I shall include a loss switch for the mixed model which uses only one type of loss and look at whether there is a difference between that and the original individual model.

## Week 8
Question - which optimizer to use
Autoencoders use Adam so how is that going to translate in the model?
We looked at the performance of the scaled model on the FashionMNIST dataset.

## Week 9
Progress - all models using Adam, scaling losses improves performance
How does all of this relate to feedback
Output buffer is initialized to 0
Image minus reconstructed image and that goes into the network
Minibatch
NARX architecture
Background - Gated recurrent unit, the LSTM, Deep Predictive Coding Network, Class Activation Mapping, NARX architecture
Taking backpropagations and using them directly
Inverted heatmap both subtractions and multiplicative
Learning rate alpha (1-alpha)

## Week 10
No meeting due to sickness

## Week 11
I have subtracted the reconstructed image from the original.
I have also started looking at code implementations of different papers.
Six channels of input - output goes into one channel, input into the other

### Week 12
Question - does evaluating loss and accuracy count as evaluation
Feedback in terms of LSTM, previous layers are taken into account
Feedback in predictive coding - feedback between
NARX - output is generated and fed back into the entire system and fed back into the loop
Networks which incorporate feedback have the possibility of converging a solution
Feedback is a potential mechanism to improve obtained results in visual processing tasks using deep nets. One particular task is automatic segmentation as it requires labeled data.
Objective - examine existing feedback architectures for their potential to improve classification results and particular automatic segmentation
Formulate new architectures
Minibatch
Issue - bootstrap training, joint model
Explore feedback archtitecutres with a view to attempt to build a feedback arch that automatically segments what it classifies/enhance classification by suppressing irrelevant or enhacing parts of an image that contribute to classification process
Requires hands-segmented data
Automatically segment information background
Explore potential feedback architecture for this task
Approach - examine standard architectures - LSTM Deep Predictive Coding NARX
Classifiers
FashionMNIST pretrained weights
Explain joint loss function
Explored implementing a joint loss function - both types of loss
Risk - not discovering an architecture
Focus on NARX
Pretrain the autoencoder
Wednesday - 14:00

### Week 13
Doesn't the input get obscured by subtracting
Improvement on classification
Plan for break - write as much as possible on introduction and background, experiment with LSTM and Deep Predictive Coding

Pretrain the classifier
Initialize output layer to zero
Freeze the classifier and then train the generator to subtract the background
Set threshold
Joint model using classifier loss

Loss function and how to train 
Multiplicative
I would expect to see background and a mask of the image
