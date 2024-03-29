# Affinity_propagation
Affinity Propagation was first published in 2007 by Brendan Frey and Delbert Dueck in Science. In contrast to other traditional clustering methods, Affinity Propagation does not require you to specify the number of clusters.Affinity propagation defines every cluster through one central data point, the cluster exemplar. 

The algorithm assigns all data points to clusters in order to minimize an energy function based on the similarity between data points and their assigned exemplars. A further advantage is that the number of desired clusters does not have to be specified in advance.

Two different types of messages are used in this algorithm: The first one is a responsibility message r(i,j), which is sent from a data point ito a potential exemplar j. This message represents the preference of data point ito choose jas its exemplar, relative to the preferences for all other potential exemplars. So r(i,j)will be high, if j has clearly emerged as the exemplar for i, but low if there are many competing candidate exemplars. The other type of message is the availability message a(i,j), which is sent in the opposite direction from the potential exemplar jto the data point i.It indicates the evidence for point jbecoming an exemplar, based on the responsibility of jfor all other data points. This message will be high if many points have chosen jas exemplar. The responsibility and availability messages depend on each other, and so an iterative update of the messages is required to compute the clustering.

Initially, all a(i,j)messages are set to zero. In every iteration the responsibilities r(i,j)are computed based on the similarities s(i,j) from S(S)and the previous a(i,j). Then the availabilities a(i,j), and self-availabilities a(i,i)are updated from the new responsibility values. The update equations, described by Frey and Dueck in are:
given on (https://www.researchgate.net/publication/233925170_Probing_real_sensory_worlds_of_receivers_with_unsupervised_clustering).

In contrast to other methods that require the exact number of desired clusters as input, this method is much easier to tune to obtain satisfactory results. The method is also insensitive to random assignments of cluster exemplars, so it is not necessary to run the clustering algorithm multiple times and choose the best clustering.

# Data 
Prepare a file named "mydata.txt" which stores the two-dimensional data points and put this file in the same directory as the source code.

In this file, there are two real numbers in each line, which is separated by a space.

The first number is the x coordinate and the second number is the y coordinate.

# Compile 
g++ affinity_propagation -o ap

Reference: "Clustering by Passing Messages between Data Points", Brendan J. Frey, Delbert Dueck, Science 2007.

This code has been taken from : https://github.com/jincheng9/AffinityPropagation
