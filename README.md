Purpose
=============
This is the code the challenge"Chalearn Looking at People 2014“.
******************************************************************************************************
Gist: Delief Networks (Gaussian Bernoulli RBM as first layer) + Hidden Markov Networks
******************************************************************************************************
by Di WU: stevenwudi@gmail.com, 2015/05/27


Citation
-------
If you use this toolbox as part of a research project, please cite the corresponding paper
******************************************************************************************************
```yaml
@inproceedings{wu2014leveraging,
  title={Leveraging Hierarchical Parametric Networks for Skeletal Joints Based Action Segmentation and Recognition},
  author={Wu, Di and Shao, Ling},
  booktitle={Proc. Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2014}
}
```
******************************************************************************************************


Dependency: Theano
-------
Some dependent libraries requirements:
Theano: for deep learning tasks http://deeplearning.net/software/theano/.
		Note that Wudi change some of the functionalities(Deep Belief Networks, Gaussian Bernoulli Restricted Boltzmann Machines).
		They are in the subfolder of -->TheanoDL


	
Test
-------
To reproduce the experimental result for test submission, there is a Python file:

`Step3_SK_Test_prediction.py` and there are three paths needs to be changed accordingly:

line: 60, Data folder (Test data)
data_path=os.path.join("I:\Kaggle_multimodal\Test\Test\\") 
 
line: 62, Predictions folder (output)
outPred=r'.\training\test'

line: 64, Submision folder (output)
outSubmision=r'.\training\test_submission'

It takes about ~20 second for each example file using only skeleton information. (I use Theano GPU model, but I reckon CPU model should almost of the same speed)

Train
-------
To train the network, you first need to extract the skeleton information

1)`Step1_SK_Neutral_Realtime.py`--> extract neutral frames (aka., 5 frames before and after the gesture)

2)`Step1_SK_Realtime.py`--> extract gesture frames

3)`Step1_DBN_Strucutre2.py`-->Start training the networks (`Step1_DBN.py` specifies a smaller networks, train faster, but the larger the net is always better)

Voila, here you go.

Dataset
-------
According to some reader recommendation, I supplement the links of the datasets used in the paper as follows:

1) `ChaLearn Italian Gesture Recognition` --> [http://gesture.chalearn.org/2013-multi-modal-challenge](http://gesture.chalearn.org/2013-multi-modal-challenge)

You should download from this dataset from Kaggle platform. [https://www.kaggle.com/c/multi-modal-gesture-recognition/data](https://www.kaggle.com/c/multi-modal-gesture-recognition/data)

2) `MSR Action3D` --> [http://research.microsoft.com/en-us/um/people/zliu/actionrecorsrc](http://research.microsoft.com/en-us/um/people/zliu/actionrecorsrc)

3) `MSRC12 ` --> [http://research.microsoft.com/en-us/um/cambridge/projects/msrc12](http://research.microsoft.com/en-us/um/cambridge/projects/msrc12)

(If you use the datasets, please cite the corresponding original paper. Thanks)

Contact
-------
If you read the code and find it really hard to understand, please send feedback to: stevenwudi@gmail.com
Thank you!
