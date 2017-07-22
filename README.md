# perks of the winner-take-all (WTA) hash codes 

This work studies the uses of WTA hashing applied to image datasets (WTA mappings of the images). 

Consider a simple machine learning technique: K nearest neighbors classifier! \href{https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm}{Knn }Imagine a simple machine learning classifier that takes an image as an input and predicts its' class. 
Given a dataset of labeled images, the idea is to store 4096 descriptors obtained by a pre-trained convolutional neural network (Places CNN) and then apply the WTA hashing on these descriptors (essentially vectors of length 4096) to obtain the k-bit WTA code where k is a hyper-parameter. 


# image_classification
Image Classification using Deep Learning and WTA Hashing


Given a set of labeled images, the idea is to store 4096 descriptors obtained by a pre-trained convolutional neural network (Places CNN) and use these descriptors instead of the entire image for classification. This results in considerable storage efficiencey (since we're storing only the descriptors that occupy 4096 x 4 bytes as opposed to a 256 x 256 pixels image for our classification task). 

This can be further improved if we hash these descriptors to a binary code of k-length, where k is a hyper-parameter and store only these binary codes. This hashing is done by WTA (winner take all) which essentially represents a set of inequalities on the input vector (4096 descriptor in this case). Finally we use a basic classifier like k-nn to test our performance by both the approaches - one involving k-nn trained on 4096 descriptors and other involving k-nn trained on 2000 bit WTA hashed codes. 

Project Presentation at IITGN (APR 2016):
https://drive.google.com/file/d/0B6uAJSfesxBXM2o0Wl9ocC1pQVk/view

WTA paper:
Yagnik, Jay, et al. "The power of comparative reasoning." Computer Vision (ICCV), 2011 IEEE International Conference on. IEEE, 2011.

Related:
Dean, Thomas, et al. "Fast, accurate detection of 100,000 object classes on a single machine." Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition. 2013.

Useful presentation:
http://www.cs.cmu.edu/~wcohen/10-605/2015-guest-lecture/ishan.pdf
