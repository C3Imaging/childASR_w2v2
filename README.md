# CAN SELF-SUPERVISED LEARNING SOLVE THE PROBLEM OF CHILD SPEECH RECOGNITION?

## Abstract

Despite recent advancements in deep learning technologies, Child Speech Recognition remains a challenging task. Current Automatic Speech Recognition (ASR) models require substantial amounts of annotated data for training, which is scarce. In this work, we explore using the ASR model, wav2vec2, with different pretraining and finetuning configurations for self-supervised learning (SSL) toward improving automatic child speech recognition. The pretrained wav2vec2 models were finetuned using different amounts of child speech training data, adult speech data, and a combination of both, to discover the optimum amount of data required to finetune the model for the task of child ASR. Our trained model achieves the best word error rate (WER) of 7.42 on MyST child speech dataset, 2.99 on PFSTAR dataset and 12.47 on CMU KIDS dataset as compared to any other previous methods. Our models outperformed the wav2vec2 BASE 960 on child speech which is considered state-of-the-art ASR model on adult speech by just using 10 hours of child speech data in finetuning. The analysis of different types of training data and its effect on inference is also provided by using combination of datasets in pretraining, finetuning and inference. No language model was used in this work. 

## Table of Results with Checkpoints

This repository provides trained checkpoints for finetuning across different child speech datasets for improving the performance on ASR for child speech.

### TABLE II: WER FOR DIFFERENT PRETRAINING (ADULT SPEECH DATASETS) AND FINETUNING (ADULT SPEECH DATASET) EXPERIMENTS ON THE MYST, PF-STAR, CMU KIDS AND LIBRITTS ‘DEV-CLEAN’ DATASETS.

| **Setup**   | **Model ID** | **Pretraining Model Configuration** | **Pretraining dataset** | **Finetuning dataset** | **WER MyST_test** | **WER PFS_test** | **WER CMU_KIDS** | **WER dev_clean** |
| :---    | :------: | :-----------------------------: | :-----------------: | :----------------: | :-----------: | :----------: | :----------: | :-----------: |
|         | 1        |                                 |                     | LS_10m             | 31.48         | 30.05        | 33.38        | 15.90         |
|         | 2        | BASE                            | Librispeech         | LS_100h            | 17.82         | 15.96        | 18.73        | 4.16          |
|         | 3        |                                 |                     | LS_960h            | **15.41**     | **11.20**    | **16.33**    | **3.40**      |
| SET - A | 4        |                                 |                     | LS_10m             | 26.47         | 27.14        | 29.37        | 15.35         |
|         | 5        | LARGE                           | Librilight          | LS_100h            | 13.15         | 11.63        | 16.18        | 3.79          |
|         | 6        |                                 |                     | LS_960h            | **12.50**     | **8.56**     | **14.85**    | **3.28**      |

### TABLE III: WER FOR DIFFERENT PRETRAINING (ADULT AND CHILD SPEECH DATASETS) AND FINETUNING (MYST CHILD SPEECH DATASET) COMBINATIONS ON THE MYST, PF-STAR, CMU KIDS AND LIBRITTS ‘DEV-CLEAN’ DATASETS.

| **Setup**   | **Model ID** | **Pretraining Model Configuration** | **Pretraining dataset** | **Finetuning dataset** | **WER MyST_test** | **WER PFS_test** | **WER CMU_KIDS** | **WER dev_clean** |
| :---    | :------: | :-----------------------------: | :-----------------: | :----------------: | :-----------: | :----------: | :----------: | :-----------: |
|         | 7        |                                 |                     | MyST_10m           | 28.84         | 41.34        | 34.18        | 21.45         |
|         | 8        | BASE                            | Librispeech         | MyST_1h            | 18.75         | 31.84        | 23.13        | 13.91         |
|         | 9        |                                 |                     | MyST_10h           | 13.46         | 28.68        | 19.59        | 10.94         |
| SET - B | 10       |                                 |                     | MyST_55h           | **8.13**      | **14.77**    | **16.47**    | **7.72**      |
|         | 11       |                                 |                     | MyST_10m           | 33.01         | 44.36        | 39.91        | 46.45         |
|         | 12       | LARGE                           | Librilight          | MyST_1h            | 14.91         | 26.21        | 18.74        | 11.59         |
|         | 13       |                                 |                     | MyST_10h           | 12.92         | 25.05        | 17.72        | 10.04         |
|         | 14       |                                 |                     | MyST_55h           | **7.51**      | **12.46**    | **15.25**    | **6.43**      |
|         | 15       |                                 |                     | MyST_10m           | 29.16         | 45.71        | 37.56        | 35.39         |
|         | 16       | BASE                            | Librispeech MyST_Complete | MyST_1h      | 21.89         | 38.53        | 29.03        | 20.45         |
| SET - C | 17       |                                 |                     | MyST_10h           | 16.18         | 32.95        | 25.06        | 16.83         |
|         | 18       |                                 |                     | MyST_55h           | **10.34**     | **25.47**    | **23.15**    | **13.48**     |

### TABLE IV: WER FOR DIFFERENT PRETRAINING (ADULT SPEECH DATASETS) AND FINETUNING (PFSTAR CHILD SPEECH DATASET) COMBINATIONS ON THE MYST, PF-STAR, CMU KIDS AND LIBRITTS ‘DEV-CLEAN’ DATASETS.

| **Setup**   | **Model ID** | **Pretraining Model Configuration** | **Pretraining dataset** | **Finetuning dataset** | **WER MyST_test** | **WER PFS_test** | **WER CMU_KIDS** | **WER dev_clean** |
| :---    | :------: | :-----------------------------: | :-----------------: | :----------------: | :-----------: | :----------: | :----------: | :-----------: |
|         | 19       |                                 |                     | PFS_10m            | 35.91         | 16.43        | 33.53        | 30.43         |
|         | 20       | BASE                            | Librispeech         | PFS_1h             | 33.52         | 7.36         | 29.55        | 16.61         |
| SET - D | 21       |                                 |                     | PFS_10h            | **31.86**     | **3.48**     | **27.49**    | **13.95**     |
|         | 22       |                                 |                     | PFS_10m            | 37.10         | 16.78        | 35.13        | 23.85         |
|         | 23       | LARGE                           | Librilight          | PFS_1h             | 30.81         | 14.19        | 28.54        | 21.89         |
|         | 24       |                                 |                     | PFS_10h            | **27.17**     | **3.50**     | **21.35**    | **11.60**     |

### TABLE V: WER FOR DIFFERENT PRETRAINING (ADULT DATASETS) AND FINETUNING (ADULT AND CHILD SPEECH DATASETS) COMBINATIONS ON THE MYST, PF-STAR, CMU KIDS AND LIBRITTS ‘DEV-CLEAN’ DATASETS.

| **Setup**   | **Model ID** | **Pretraining Model Configuration** | **Pretraining dataset** | **Finetuning dataset** | **WER MyST_test** | **WER PFS_test** | **WER CMU_KIDS** | **WER dev_clean** |
| :---    | :------: | :-----------------------------: | :-----------------: | :----------------: | :-----------: | :----------: | :----------: | :-----------: |
|         | 25       |                                 |                     | LS_960h, MyST_55h  | 8.18          | 12.17        | 14.12        | 1.24          |
|         | 26       | BASE                            | Librispeech         | LS_960h, PFS_10h   | 15.42         | 3.74         | 15.31        | 1.41          |
|         | 27       |                                 |                     | MyST_55h, PFS_10h  | **7.94**      | **2.91**     | 15.97        | 7.64          |
|         | 28       |                                 |                     | LS_960h, MyST_55h, PFS_10h | 8.13  | 3.12         | **13.76**    | **1.20**      |
| SET - E | 29       |                                 |                     | LS_960h, MyST_55h  | 8.06          | 9.31         | 13.20        | 1.34          |
|         | 30       | LARGE                           | Librilight          | LS_960h, PFS_10h   | 13.18         | 3.17         | 13.19        | **1.32**      |
|         | 31       |                                 |                     | MyST_55h, PFS_10h  | **7.42**      | **2.99**     | 14.18        | 5.79          |
|         | 32       |                                 |                     | LS_960h, MyST_55h, PFS_10h | 8.17  | 3.33         | **12.77**    | 1.40          |

