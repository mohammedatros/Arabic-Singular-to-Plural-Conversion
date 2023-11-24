# Arabic Singular-to-Plural Conversion

This repository contains the data files and Jupyter notebooks required to reproduce the models and results reported in our *"Neural Arabic Singular-to-Plural Conversion with a Pre-trained Character-BERT and a Fused Transformer"* paper.

This work aims at approaching the MIG task suggested by [SIGMORPHON](https://github.com/sigmorphon/2022InflectionST/blob/main/part2/README.md). We start with pre-training an Arabic Character-BERT on the MLM task, and then fusing it into a transformer encoder-decoder model.

The links provided in the notebooks are downloadable, and hence no extra coding is required to enable their running. It is necessary to run the notebooks using Google Colab, except for the second notebook which was run on Kaggle kernels, otherwise when reading the files from their paths an error will be raised, unless the paths are corrected correspondingly.

## Table of Contents
1. [Datasets](#1.datasets)
2. [Model Architectures](#archs)

<a name=1.datasets></a>
## 1. Datasets
There are two datasets used in this work, one for the pre-training stage and the other of the downstream task. The pre-training dataset is the [Arabic Wikipedia (test split)](https://www.kaggle.com/datasets/abedkhooli/arabic-bert-corpus/discussion/129597) which has been cleaned a made publicly avaiable by [Abed Khooli](https://www.kaggle.com/abedkhooli) on [Kaggle](https://www.kaggle.com/). 

The downstream task datasets are probived by the [SIGMORPHON](https://github.com/sigmorphon) competition organizers and are publicly avaiable [here](https://github.com/sigmorphon/2022InflectionST/tree/main/part2).

<a name="archs"></a>
## 2. Model Architectures
Firs, we start with pre-training a Character-BERT (CBERT) for the first time in the Arabic NLP domain. 1,134,950 Arabic unique words are used for this stage, and the model is trained on an MLM task. 
Two different architectures are developed in this work, namely the ***fused*** and the ***direct*** architectures. The first extracts the embeddings from CBERT and feed them to both the encoder and decoder parts of the transformer. While the second directly employs CBERT as and encoder for the Transfomer. Both the ***fused*** and the ***direct*** architectures can be illustrated in the next two diagrams.

### Fused Architecture
<img src="/figures/Computational%20Linguistics%20Model-Fused.png"  alt="Fused Architecture" width="1200">

### Direct Architecture

<img src="/figures/Computational%20Linguistics%20Model-Direct.png"  alt="Direct Architecture" width="600">
