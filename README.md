# CAN SELF-SUPERVISED LEARNING SOLVE THE PROBLEM OF CHILD SPEECH RECOGNITION?

## Abstract

Despite recent advancements in deep learning technologies, Child Speech Recognition remains a challenging task. Current Automatic Speech Recognition (ASR) models require substantial amounts of annotated data for training, which is scarce. In this work, we explore using the ASR model, wav2vec2, with different pretraining and finetuning configurations for self-supervised learning (SSL) toward improving automatic child speech recognition. The pretrained wav2vec2 models were finetuned using different amounts of child speech training data, adult speech data, and a combination of both, to discover the optimum amount of data required to finetune the model for the task of child ASR. Our trained model achieves the best word error rate (WER) of 7.42 on MyST child speech dataset, 2.99 on PFSTAR dataset and 12.47 on CMU KIDS dataset as compared to any other previous methods. Our models outperformed the wav2vec2 BASE 960 on child speech which is considered state-of-the-art ASR model on adult speech by just using 10 hours of child speech data in finetuning. The analysis of different types of training data and its effect on inference is also provided by using combination of datasets in pretraining, finetuning and inference. No language model was used in this work. 

## Table of Results with Checkpoints

This repository provides trained checkpoints for finetuning across different child speech datasets for improving the performance on ASR for child speech.
