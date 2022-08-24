# MTL-SegTHOR
Multi-Task Learning for the Segmentation of Organs at Risk with Label Dependence
author: Tao He

Institution: Sichuan University

email: tao_he@scu.edu.cn

Tookit need 
Python 3, pytorch 1.1.0


### Prepare SegTHOR dataset
> reading preprocessing.ipynb in details

the source data can be downloaded from the challenging official website.
Then, using preprocessing.ipynb to process the SegTHOR dataset for 4-fold cross-validation


### Network training
> See main.py parser.argument in details

A test run is  like this \
python3 main.py -b 16 --gpu 0,1,2,3 --model_name ResUNet101 --save_dir SavePath/SM --lr 0.01 --if_dependent 0 --if_closs 0

#### Important parameters:
- model_name -> indicate which encoder network is used. Please check models/model_loader.py in details.
- if_closs -> if using the classification loss (MTL). if_closs=0, MTL is not deployed.
- if_dependent -> if using the WMCE loss function. if_dependent=0, binary relevance with BCE loss functions is used.


### Network testing
> See prediction.ipynb in details
 
## Citation
```
@article{HE2020101666,
title = {Multi-task learning for the segmentation of organs at risk with label dependence},
journal = {Medical Image Analysis},
volume = {61},
pages = {101666},
year = {2020},
author = {Tao He and Junjie Hu and Ying Song and Jixiang Guo and Zhang Yi},
}

```
