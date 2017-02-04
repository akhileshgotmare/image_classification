# image_classification
Image Classification using Deep Learning and WTA Hashing


Given a set of labeled images, the idea is to store 4096 descriptors obtained by a pre-trained convolutional neural network (Places CNN) and use these descriptors instead of the entire image for classification. This results in considerable storage efficiencey (since we're storing only the descriptors that occupy 4096 x 4 bytes as opposed to a 256 x 256 pixels image for our classification task). 

This can be further improved if we hash these descriptors to a binary code of k-length, where k is a hyper-parameter and store only these binary codes. This hashing is done by WTA (winner take all) which essentially represents a set of inequalities on the input vector (4096 descriptor in this case). 

Project Presentation at IITGN (APR 2016):
https://drive.google.com/file/d/0B6uAJSfesxBXM2o0Wl9ocC1pQVk/view

WTA paper:
Yagnik, Jay, et al. "The power of comparative reasoning." Computer Vision (ICCV), 2011 IEEE International Conference on. IEEE, 2011.

Related:
Dean, Thomas, et al. "Fast, accurate detection of 100,000 object classes on a single machine." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2013.

Useful presentation:
http://www.cs.cmu.edu/~wcohen/10-605/2015-guest-lecture/ishan.pdf
