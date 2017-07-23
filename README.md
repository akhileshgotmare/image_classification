# Perks of the winner-take-all (WTA) hash codes 

This work studies the uses of WTA hashing (first introduced in [1]) applied to image datasets (WTA mappings of the images). 

Consider a simple machine learning technique - [K nearest neighbors classfier](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm), given a dataset of labeled images, the objective is to classify a new image that is given as an input. The 4096 descriptor of an image obtained by a pre-trained convolutional neural network (Places CNN) are great representations and carry the discriminative power required to classify an image as evident by the success of deep learning in recent years [2]. 

The **goal** of this work is to show that we obtain comparable accuracy even if the knn classifier uses the WTA hash codes (which can be very small in size compared to the descriptors) of these 4096 image descriptors instead of the descriptors themselves. The fact that WTA codes carry this discriminative power can be used to build systems with lesser storage requirements since we can get away with storing just the WTA code of an image instead of the pixel data or the descriptor data. The WTA mapping essentially represents a set of inequalities between the components of the input (4096 descriptors in this case).

Note that the size of the WTA code can be decided by a hyper-parameter involved in the hashing. The greater the WTA length, the better is the performance accuracy initially until a certain threshold is reached after which the gains in accuracy by increasing the WTA code lenght are insignificant. Our experiments show that a code of 2000 bits length obtains comparable accuracy to 4096 descriptors. Also note that a 4096 descriptor would require 4096 x 4 bytes of space whereas the WTA code would require 2000 bits in this example, that's a memory requirement reduction factor of 60!

To clarify the methodology: we obtain 4096 descriptors using pre-trained Places CNN and then use the hashing scheme described in [1] to obtain the WTA code.
**image pixels data -> 4096 descriptors -> 2000 bits WTA code**

Project Presentation at IITGN (APR 2016):
https://drive.google.com/file/d/0B6uAJSfesxBXM2o0Wl9ocC1pQVk/view

[1] Yagnik, Jay, et al. "The power of comparative reasoning." Computer Vision (ICCV), 2011 IEEE International Conference on. IEEE, 2011.
[2] Krizhevsky, A., Sutskever, I., and Hinton, G. E. ImageNet classification with deep convolutional neural networks.
In NIPS, pp. 1106–1114, 2012.

Related paper:
Dean, Thomas, et al. "Fast, accurate detection of 100,000 object classes on a single machine." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2013.

Useful presentation:
http://www.cs.cmu.edu/~wcohen/10-605/2015-guest-lecture/ishan.pdf
