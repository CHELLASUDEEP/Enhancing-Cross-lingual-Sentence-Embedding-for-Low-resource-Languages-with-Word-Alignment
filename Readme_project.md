# Enhancing Cross-lingual Sentence Embedding for Low-resource Languages with Word Alignment
This github repository contains of 2 code files named bitext_retreival.ipynb and bitext_mining.ipynb. Both files are independent of each other. These are seperate tasks

## 1) bitext_retreival.ipynb
Bitext retrieval is the task of retrieving the most relevant sentence from a target language corpus given a query sentence in the source language. I have downloaded the required files sentences.tar.bz2 and links.tar.bz2 manually from tatorba website {https://tatoeba.org/en/downloads}. But no worries, I have created tatoeba_low_resource.csv file which contains 7 pairs of sentences(en-te, en-ka, en-kk, en-jv, en-ml, en-tl, en-mr) using both the tar files. We use this dataset for further purposes. I have uploaded it in this repository.

## 2) bitext_mining.ipynb
Bitext mining involves extracting parallel sentences from two monolingual corpora with the assumption that some of these sentences are translation pairs. For loading the data i have used tensorflow-datasets and hugging face test data of BUCC dataset. U can refer this links {https://www.tensorflow.org/datasets/catalog/bucc} and {https://huggingface.co/datasets/mteb/bucc-bitext-mining}. Let me explain. Tensorflow used a script to generate test and validation data for each of the 4 language pairs (fr ↔ en, de ↔ en, ru ↔ en and zh ↔ en. ). According to the official BUCC dataset information and the script used by tensorflow, we are going to use validation data for training purposes and test data for evaluation purposes. In the code file, by running each cell, we will get the bucc_test.csv and bucc_validation.csv datasets. The huggingface BUCC test data and bucc_test.csv generated through tensorflow is same. So i have used the huggingface BUCC test data for evaluation purpose and bucc_test.csv for training purpose.

## Execution 
1) For bitext_retreival.ipynb, u just need to upload the dataset tatoeba_low_resource.csv for run the code cell by cell accordingly.

2) For bitext_mining.ipynb, there is no need of uploading any dataset. Just run the cell by cell. That will be sufficient.

use google colab T4 GPU for execution purposes.

## NOTE
I have used SimALign instead of WSPAlign for generating the word alignments due to issues in inference code of WSPAlign. The issue was with spacy tokenizer used in WSPAlign but after resolving the issue, the alignment score was too low. So i have used SimALign for generating word alignments.

## Requirements

1) numpy
2) pandas
3) transformers
4) torch
5) datasets
6) sentencepiece
7) os
8) SimAlign
9) gc
10) tqdm
11) sklearn
12) tensorflow-datasets