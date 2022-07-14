# cnn_colon-img-detection
Train a deep neural network which can take a 32x32 image with a cell nuclei and classify it into one of the following types.

	1.Normal epithelial cells (shown orange).
	2.Cancer epithelial cells (shown in red).
	3.Immune leukocyte cells (shown in green).
	4.Connective fibroblast cells (shown in blue).

Training set of nuclei images (train.zip) with images given in suitable subdirectories with the label names. 
It also contains test archive (test.zip) which has similar 32x32 images of unlabelled cell nuclei.
The classes in the training file are unbalanced with 'Normal' cells being in the minority. However, the testing file is balanced with roughly equal 
numbers of each cell type.

Develop a ConvNet that can predict the cell type of the images in the test.zip file. 
Also do unsupervised pre-training by training an autoencoder on the unlabelled test image data and then use the 'encoder' section (with trained weights) 
as a feature extractor for the first part of your ConvNet.

Steps followed:
  1. Create a simple ConvNet trained on the labelled data and see if you can get better than random accuracy.
  2. See if you can turn this simple ConvNet into an autoencoder and train it using the unlabelled test image data.
  3. Use the encoder part of the autoencoder to recreate your ConvNet and train it using the smaller quantity of labelled data and see if you can beat the 
      accuracy of your initial ConvNet.
      
Plot out loss / accuracy curves to ensure you are not overfitting the training data set.

File descriptions
	1.train.zip - zip file containing the training images in subdirectories with the relevant labels
	2.test.zip - zip file containing the test images
	3.example.csv - an example submission file in the correct format

Data fields
	Id - an anonymous id unique to a given image
	Type - the type of cell at the middle of the image
