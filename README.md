# Person recognition in paintings - IMA205 Computer Vision Challenge

In April 2020 I took part in a computer vision challenge at my school Télécom Paris. The goal of the challenge was to adapt computer vision alogrithms in order to classify paintings and other artworks as containing a representation of a person or not. The dataset contained 10.000 RGB images of artworks split in half between a train and test set. The performance mesure used for ranking is the Mean F1-Score. I ranked 10th out of 44 teams. 

Link to the Kaggle InClass competition : https://www.kaggle.com/c/ima205-challenge-2020

I used the VGG16 deep convoluational neural network with pre-trained weights (on ImageNet) as a starting point. I replaced the original output layer a new output layer containing two neurons and softmax activation. I fine-tuned the weights on the artwork dataset using different configurations :
- Fine-tuning all layers 
- Freezing only the first 3 convoluational layers
- Freezing all convoluational layers
- Freezing all convoluational layers and replacing VGG16 fully connected layers by one 256 dense layer with relu activation.

The best results were obtained by fine-tuning all layers. I used Stochastic gradient descent and 0.5 dropout between the fully-connected layers. 
