# Learning to eXplain Recommendations (LXR)

LXR is a model-agnostic, post-hoc framework to explain recommender systems. LXR can work with any differentiable recommender and learns to score the importance of users' personal data with respect to a recommended item. The framework's objective employs a novel self-supervised counterfactual loss function that aims to identify the user data that best explains the item's recommendation. Additionally, we propose several counterfactual evaluation metrics for assessing explanations in recommender systems. Using these metrics, our results demonstrate LXR's capability to provide counterfactual explanations for various recommendation algorithms across different datasets.

For additional information, please refer to the paper available at this [link](https://dl.acm.org/doi/abs/10.1145/3589334.3645560).

## A general overview 
![LXR_diagram](https://github.com/DeltaLabTLV/LXR/blob/main/LXR_diagram.png)

## Repository

This repository contains code for a Learning to eXplain Recommendations (LXR) framework that was evaluated on three publicly available benchmarks, MovieLens1M, a subset of Yahoo!Music dataset and a subset of Pinterest dataset, using two different recommenders, Multi Layer Perceptron (MLP) and Variational Auto Encoder (VAE). Hyperparameters optimization was done using optuna.

## Folders

* **processed_data**: contains three subfolders, one for each dataset. In each dataset folder lies the raw data files.
* **code**: contains several code notebooks:
  - data_processing - code related to the preprocessing step for preparing data to run with our models.
  - help_functions - includes the framework's functions that are being used in all notebooks.
  - recommenders_architecture - specifies the architecture of the recommenders that were used in the paper.
  - recommenders_training - contains code related to VAE and MLP recommenders training.
  - LXR_training - contains code for training LXR model for explaining a specified recommender.
  - metrics - contains code related to model evaluation.
* **baselines**: contains code for LIME and SHAP baselines.
* **checkpoints**: presently, this folder is empty. It is the designated location for saving and loading the trained model's checkpoints. The checkpoints developed during our project are stored in the 'checkpoints' folder on the [drive](https://drive.google.com/drive/u/3/folders/1nD0_5asi4B9dyUN_JYoYT5QJPYeAMWCD).
  
## Requirements

* python 3.10
* Pytorch 1.13
* wandb 0.16.3 (the package we used for monitoring the train process)

## Usage

To use this code, follow these steps:
+ Create data to work with by running the data_processing notebooks.
  - Or in order to reproduce results from the paper without running the data_processing notebook, please download all files from [here](https://drive.google.com/drive/folders/1nD0_5asi4B9dyUN_JYoYT5QJPYeAMWCD?usp=sharing) from the relevant folder <dataset_name> to data_preprocessing folder according to the data set you need to run on. 
+ On every notebook, please specify the "data_name" variable to be 'ML1M'/'Yahoo'/'Pinterest', and the "recommender_name" variable to be 'MLP'/'VAE'.
+ You can train your oun LXR with the 'LXR_training' notebook, test your results in 'metrics' notebook, and test new explanation methods using 'metrics' notebook. 



