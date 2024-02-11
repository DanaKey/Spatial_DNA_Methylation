# CH3 Project- Predicting DNA Methylation at individual CpG sites from diluted gene expression data and site context

Welcome to the CH3 project repository! This repository showcases our work on predicting DNA methylation from sequence data and gene expression data at different retention levels, utilizing deep learning techniques enhanced with attention mechanisms. Our project builds upon the framework presented in the paper by [Levy-Jurgenson et al.](https://link.springer.com/chapter/10.1007/978-3-030-18174-1_13)

## Overview

The primary objective of this project is to reproduce and extend the findings presented in the research paper titled "Predicting Methylation from Sequence and Gene Expression Using Deep Learning with Attention" by Levy-Jurgenson et al. Our work is organized into three main parts, with the first two parts focusing on reproducing the original results, while the third part serves as an extension, laying the groundwork for predicting Spatial DNA Methylation.

### 1. Data Preparation
In this initial phase, we reconstructed the datasets required for training and validating our model, adhering closely to the methodology outlined in the paper. The core datasets utilized include gene expression and methylation level data from patients with BRCA and LUAD conditions, coupled with essential human genome, CpG locations, and gene locations data.
Leveraging this raw information, we generated four data files, their structure is demonstrated in the image below: 

1. Sequences Centered around Each CpG Site
2. Distances between CpG Sites and Genes
3. Gene Expression Per Subject
4. Methylation Level Data Per Sample and CpG Site

For an in-depth understanding of our data preparation process, including associated documents and code, refer to the  [Data Preparation Documentation](https://docs.google.com/document/d/1mcqvdV8dOxaLs3zar7T54yrKlKJttkI3Kr0jiwrF3Cs/edit?usp=sharing)

### 2. Model Implementation

The second part of our project involves implementing the model in PyTorch and reproducing the results achieved in the paper using our own code. 
To confirm the validity of each step, we first replicated the original model's performance using our dataset and the original TensorFlow implementation.
Then, we proceeded to train and test our PyTorch model using our dataset, successfully reproducing the results at this stage as well.
To access the model code and instructions with the training and validation environment, please visit the [Model Code Repository](https://github.com/agotliber/CH3_project/tree/main/src).

### 3. Dilution Test: Evaluating Spatial Methylation Prediction

In the third phase, we introduced dilution tests to gauge the potential success of our methylation prediction approach, on spatial biological data. Through this test, we simulated gene expression data typical of spatial samples. We introduced a random dilution process to the gene expression test data, wherein the strength of gene expression serves as the probability of a gene's inclusion in the sample's diluted data.

We conducted the tests at various dilution levels working points: 100, 1000, 5000, 10,000, 15,000, and 20,000 chosen genes. Each working point was subjected to 10 iterations, and we derived the model accuracy statistics based on these iterations. As anticipated, better performance was achieved with higher retention of gene expression data and decreased performance as we approached complete removal of gene expressions.

For a comprehensive insight into the dilution test results and associated performance graphs, please explore the [Dilution Test Results](https://github.com/agotliber/CH3_project/blob/main/Dilution_experiement_ch3.pdf).


For inquiries or support please reach out to agotliber@gmail.com or keydar.dana@gmail.com
