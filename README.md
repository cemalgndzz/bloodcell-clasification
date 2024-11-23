# bloodcell-clasification
Artificial Neural Networks and Deep Learning [2024-2025] - Homework 1

## Overview
The goal is to create a classifier that classifies eight different blood cell classes from the given dataset with high accuracy. 
The dataset is composed of 13759 images in the shape of 96 x 96-pixel size in RGB color format.

## Dataset
Dataset published for the competition is [here](https://drive.google.com/file/d/1JV9mJkGEGjBNIGoN1gLUG2ZEn5JCOBQ2/view?usp=sharing).

## Preprocess
Initially, dataset consist of 13759 96 x 96 images. However the dataset included some outlier Shrek&Singer images as we observed. 
So first we eliminate the outliers, then we removed the duplicates from the dataset and we balanced the dataset as there is imbalance problem.

## Augmentation
As a result of our experiments, we realized that the score on the local test set did not match well with the test set on the competition platform. So our model had to be quite generalizable. 
So we used the RandAugment + RandFlip layers of keras and extended the dataset with more different blood cell photos. This really affected out performance in a good way.

## Training
In the training section we used AdamW optimizer as its convergence capability in generalized dataset observed better than Lion and standard Adam.
As a model, we started with smaller models and increased the model size and capability as we want to observe the increase in accuracy. 
So in training we used MobileNet -> EfficientNet -> Convnext pretrainined model for transferlearning and finetuning. At then end, we submitted the
ConvneXtLarge model as it outperformed others in terms of accuracy on test dataset in codabench.

