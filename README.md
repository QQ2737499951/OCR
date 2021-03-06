# Optical Character Recognition

OCR for Baidu competition (level one)<br>
Environment requirements:<br>
>**tensorflow 1.1.0, python 2.7**<br>

This work is based on model from Peiwen Wang whose excellent work (https://github.com/ypwhs/baiduyun_deeplearning_competition) is carried out on keras. Thanks to him sincerely.  

# Contents
* Training dataset
* Model
* Loss & accuracy
* Features learned by different level layers
* Weights and biases 


------------------------------------------------------------------------------------------------------------------------------
# Training datａset
Training dataset has 100,000 pictures including characters from 0123456789+-*() with **different length** as pictures below show.The label format, for example, to the first training picture, is **(7+5)+4 16**. You can download dataset here https://pan.baidu.com/s/1geT4z9x , keep in mind that the label file is inside the unpacked folder.

 <img src="https://github.com/hedongya/OCR/blob/master/results/image.png" width = "600">
<br>
<br>

# Model

The neural network includes conv network,RNN(GRU) and CTC (Connectionist Temporal Classifier) as picture below shows.
There are three convnet modules,layer1,layer2,layer3, every module has two convnet layers and a max_pool layer. [3,3] kernel and [1,1] strides are used behind every convnet layers. [2,2] kernel and [2,2] strides are used by max_pool layer. What's more, **learning features** by different convnet modules are outputted by tensorboard.<br><br>
 <img src="https://github.com/hedongya/OCR/blob/master/results/Graph.png" width = "600"><br>
 <br>
 <br>
 
# Loss & accuracy
As we can see, after training about 2.5h, there is a sharp ｄrop of CTCloss, meanwhile the training and validation accuracy turn to be ｃlose to 1.

<img src="https://github.com/hedongya/OCR/blob/master/results/CTCloss.png" width = "600">
<img src="https://github.com/hedongya/OCR/blob/master/results/acc.png" width = "600" height = "50">
<img src="https://github.com/hedongya/OCR/blob/master/results/seqPredic.png" width = "600">
<br>
<br>

# Features learned by different layers
Within the same level convnet layers,only some of them have learned effective features.  
With the layers going deeper, features learned by them become more and more abstract.
<br>

Layer1<br>
<img src="https://github.com/hedongya/OCR/blob/master/results/featureLayer1.png" width = "600"><br>
Layer2<br>
<img src="https://github.com/hedongya/OCR/blob/master/results/featureLayer2.png" width = "600"><br>
Layer3<br>
<img src="https://github.com/hedongya/OCR/blob/master/results/featureLayer3.png" width = "600"><br>
Fully connected layer1<br>
<img src="https://github.com/hedongya/OCR/blob/master/results/fc1.png" width = "600">
<br>
<br>

# Weights and biases distributions

<img src="https://github.com/hedongya/OCR/blob/master/results/distributions.png" width = "600">
<img src="https://github.com/hedongya/OCR/blob/master/results/history.png" width = "600">








