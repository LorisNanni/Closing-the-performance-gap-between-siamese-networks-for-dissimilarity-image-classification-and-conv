# Closing-the-performance-gap-between-siamese-networks-for-dissimilarity-image-classification-and-conv
Closing the performance gap between siamese networks for dissimilarity image classification and convolutional neural networks
https://www.preprints.org/manuscript/202108.0094/v1


In the abstract we have written:
“With FULLY, the distance between a pattern and a prototype is calculated by comparing two images using the fully connected layer of the Siamese network.”

It is not entirely clear, that fully connected layer is applied when binary cross entropy loss is used, when triplet loss is used there is not that fully connected layer, see predictSiamese.m for details.
Figure 2 of the article is correct only when the chosen loss is the binary cross entropy; when the triplet loss is applied, the similarity between F1 and F2 (feature vectors describing an image and a prototype) is given by:
Y = abs(F1 - F2);
delta = 1e-6;
Y = sqrt(sum((Y.^2),1) + delta);
