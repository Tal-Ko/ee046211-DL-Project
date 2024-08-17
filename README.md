# ee046211-DL-Project

<h4 align="center">
Technion ECE 046211 - Deep Learning
  <br>
  <img src="https://raw.githubusercontent.com/taldatech/ee046211-deep-learning/main/assets/dl_intro_anim.gif" height="300">
</h4>

<h4 align="center">
    <a href="https://colab.research.google.com/github/Tal-Ko/ee046211-DL-Project/blob/sentiment-analysis/DL_goemotions_classification.ipynb">
        <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">
    </a>
</h4>

* [Introduction](#introduction)
* [Repository Structure](#repository-structure)
* [Local Installation](#local-installation)
* [Usage](#usage)
* [License](#license)

## Introduction

This repository is part of the final project required in the ECE 046211 Deep Learning course in the Technion. Here we implemented and benchmarked multiple RNN models (LSTM, xLSTM and GRU) in the task of emotion classification of the [GoEmotions](https://github.com/google-research/google-research/blob/master/goemotions/) dataset.

Emotion classification is a critical task in natural language processing with applications ranging from customer service to mental health analysis. The GoEmotions dataset, created by Google Research, is one of the most comprehensive datasets for this task, covering 27 emotion categories. However, in its current status it imposes a harsh class imbalance. With our limited resources we had to downscale the classes from 27 to 7 primary emotions governed by Paul Ekman's research.

We employed several preprocessing steps to the raw data, such as the aforementioned emotion grouping and text augmentation using [TextAttack](https://textattack.readthedocs.io/en/master/) to improve the models' ability to learn and generalize.

## Repository Structure

All of the code exists within the `DL_goemotions_classification.ipynb` notebook, split into sections for ease of use. The entire notebook can be executed without interruptions. Inside the ntoebook you can find the following chapters:

* [Data Preprocessing](DL_goemotions_classification.ipynb#data-preprocessing)
    * [Data Loading](DL_goemotions_classification.ipynb#data-loading)
    * [Data Augmentation](DL_goemotions_classification.ipynb#data-augmentation)
    * [Data Tokenization and Vectorization](DL_goemotions_classification.ipynb#data-tokenization-and-vectorization)
    * [DataLoaders](DL_goemotions_classification.ipynb#dataloaders)
    * [Statistics](DL_goemotions_classification.ipynb#statistics)
* [Training Functions](DL_goemotions_classification.ipynb#training-functions)
* [Hyper Parameters](DL_goemotions_classification.ipynb#hyper-parameters)
* [Models](DL_goemotions_classification.ipynb#models)
    * [LSTM Model](DL_goemotions_classification.ipynb#lstm-model)
    * [xLSTM Model](DL_goemotions_classification.ipynb#xlstm-model)
    * [GRU Model](DL_goemotions_classification.ipynb#gru-model)
    * [RWKV Model](DL_goemotions_classification.ipynb#rwkv-model)
* [Optuna](DL_goemotions_classification.ipynb#optuna)
    * [Framework](DL_goemotions_classification.ipynb#framework)
    * [LSTM Study](DL_goemotions_classification.ipynb#lstm-study)
    * [GRU Study](DL_goemotions_classification.ipynb#gru-study)
    * [RWKV Study](DL_goemotions_classification.ipynb#rwkv-study)
* [Training](DL_goemotions_classification.ipynb#training)
    * [LSTM Train](DL_goemotions_classification.ipynb#lstm-train)
    * [GRU Train](DL_goemotions_classification.ipynb#gru-train)
    * [RWKV Train](DL_goemotions_classification.ipynb#rwkv-train)
* [Comparison](DL_goemotions_classification.ipynb#comparison)

In addition, we include the following folders which contain items tracked by Git LFS:
- **images** - Model SVG images
- **notebook_outputs** - Complete notebook executions with outputs and graphs, for each of the successful executions and best results we got along the way. This folder serves as a "history book" where the progress of this project can be viewed.

## Local Installation

The required packages can be found in the [environment](environment.yml) file, they can either be installed manually or using anaconda:

```
conda env create -f environment.yml
```

Activate the environment by:

```
conda activate sentiment_analysis
```

## Usage

On local installations using the provided [environment](environment.yml) file, simply execute the notebook (use Jupyter Notebook, JupyterLab, Visual Studio Code or any other IDE that supports ipynb files). Note that on Google Colab you may have to install several packages manually.

## Results

Below are the key results from our emotion classification experiments:

### Training and Validation Losses and Accuracies
![Training and Validation Losses and Accuracies](images/results_losses_accuracies_plot.png)

This graph illustrates the training and validation losses and accuracies over time for the different models. The curves help us assess the learning progress and generalization capabilities of each model.

### Test Set Confusion Matrices
![Test Set Confusion Matrices](images/results_test_set_confusion_matrices.png)

The confusion matrices show the performance of our models on the test set, providing insight into which emotions were correctly or incorrectly classified.

For more detailed insights, you can view the final notebook [here](notebook_outputs/DL_goemotions_classification_62.43_61.49_61.16.ipynb).

## License

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)