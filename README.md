# Unsupervised Shadow Removal using Target-Consistency Generative Adversarial Network


by [Chao Tan](https://这里放置作者的主页), Xin Feng        

This repository contains the source code and pretrained model for our TC-GAN, provided by [Chao Tan](https://这里放置作者个人主页).  
The paper is avaliable for download [here](https://这里放置论文的arxiv下载链接).
Click [here](https://这里放置论文的主页链接) for more details.
***

## Dataset

The USR dataset can be download from [MaskShadowGAN](https://github.com/xw-hu/Mask-ShadowGAN).  
The ISTD dataset can be download from [ST-CGAN](https://github.com/DeepInsight-PCALab/ST-CGAN).


        
## Prerequisites
* Python 3.7
* PyTorch >= 1.2.0
* opencv 0.4
* PyQt 4
* numpy
* visdom


  
## Traing & Testing
1. Please download and unzip [USR](https://github.com/xw-hu/Mask-ShadowGAN) dataset and place it in ```/datasets/data``` folder.
Then modify the dataset to the structure of ```TRAIN_A,TRAIN_B,TEST_A and TEST_B```.
 
2. Training
    - Run ```python -m visdom.server"``` to activate visdom server.
    - Run ```python run.py``` to start training from scratch.
    - You can easily monitor training process at any time by visiting ```http://localhost:8097``` in your browser.
3. Testing
    - After the training is over, you can test the performance of the model on the test dataset.
    First, you need to modify the ```configs/tcgan_usr256.yaml``` file and change the status option from train to test.
    - You need to pretrain a classification network offline for testing. 
    The structure of the classification network can be obtained in ```net.py``` script. 
    After obtaining the model, please name the pretrained classifier ```classifier.pkl``` and place it in the root directory.
    - Run ```python run.py``` for testing, and the test result will be saved in ```checkpoints/tcgan_usr256/testing```.
   
## Testing with Pretrained Model
 - You can download the pretrained model ([TianYiCloud](https://这里放置USR数据集下的天翼云预训练模型) or [BaiduCloud](https://这里放置USR数据集下的百度云预训练模型)) of TC-GAN under USR dataset. 
 And put the ```tcgan_usr256``` and ```classifier.pkl``` under the ```checkpoints\``` folder and root directory respectively.
 - You need to modify the ```configs/tcgan_usr256.yaml``` file and change the status option from train to test.
 - Run ```python run.py``` for testing, and the test result will be saved in ```checkpoints/tcgan_usr256/testing```.


## Citation

Update soon...