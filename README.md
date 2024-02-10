# Learning to eXplain Recommendations (LXR)

LXR is a model-agnostic, post-hoc framework to explain recommender systems. LXR can work with any differentiable recommender and learns to score the importance of users' personal data with respect to a recommended item. The framework's objective employs a novel self-supervised counterfactual loss function that aims to identify the user data that best explains the item's recommendation. Additionally, we propose several counterfactual evaluation metrics for assessing explanations in recommender systems. Using these metrics, our results demonstrate LXR's capability to provide counterfactual explanations for various recommendation algorithms across different datasets.

## A general overview 
![LXR_diagram](https://github.com/ExplainingRecommendations/LXR/assets/130644098/e4f6c4b3-d5de-48eb-a3b8-9f0e43dcecb1)

## Repository

This repository contains code for a Learning to eXplain Recommendations (LXR) framework that was evaluated on three publicly available benchmarks, MovieLens1M, a subset of Yahoo!Music dataset and a subset of Pinterest dataset, using two different recommenders, Matrix Factorization (MF) and Variational Auto Encoder (VAE). Hyperparameters optimization was done using optuna.

## Folders

* **Data**: contains the raw files for both datasets.
* **Data_preprocessing**: contains code related to the preprocessing step for preparing data to run with our models.
* **MF**: contains code related to model evaluation on MF.
* **VAE**: contains code related to model evaluation on VAE.

## Requirements

* python 3.10
* Pytorch 1.13

## Usage

To use this code, follow these steps:
+ Create data to work with by running the Data_preprocessing notebooks.
  - Or in order to reproduce results from the paper without running the Data_preprocessing notebooks, please download all files from [here](https://drive.google.com/drive/folders/1wMXgP0x4BRHGMX7fky8C2ohBOBMoRJdk?usp=sharing) from the relevant folder <dataset_name> to Data_preprocessing folder according to the data set you need to run on. 
+ Run either the MF or VAE notebooks that contain notebooks with these models.



