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
