### Introduction

This is the implementation of face landmark detection on 300-W dataset using caffe. 

The success of landmark detection mainly relies on two aspects: (a) Data Augmentation and (B) Network. Differing than the above implementations, I focus on the 68 point landmark annotation, which is more challenging than 5 point landmark annotation. This experiment is purely trained on the 300W dataset itself, without using any external dataset. For face detection, I use DLIB library. Please install caffe and dlib ahead before playing with this model. 

For data augmentation, I use both rotation and bounding box perturbation. After data augmentation, there is a total of 30,301 samples and 5,878 samples for training and validation sets, respectively.

For network, I choose Vanilla CNN as the building block. The input size is 40*40 and the landmark positions has been scaled to [0,1]. 


### For prediction

python predict_vanilla_fd_one.py Model_68Point/_iter_1400000.caffemodel 314.jpg


### Evaluation Results


![alt text](https://github.com/cunjian/face_alignment/blob/master/demo_result.jpg "Logo Title Text 1")

![alt text](https://github.com/cunjian/face_alignment/blob/master/demo_result_19.jpg "Logo Title Text 1")

Images are either taken from the face landmark evaluation dataset or from the Internet. Copyright belongs to the owners.

The implementation is inspired from the following projects. 

References:

1. https://github.com/luoyetx/deep-landmark

2. https://github.com/ishay2b/VanillaCNN 