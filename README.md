# handwritten-character-segmentation

This repository provides the user with code to segment a handwritten text character by character, and perform recognition later.



## Contents:

0. [Setup](#0-setup)
1. [Dataset Generation](#1-dataset-generation)
2. [Usage](#2-usage)


## 0. Setup:

Clone this repo in your favourite folder:
```
git clone git@github.com:JaumeAlbardaner/handwritten-character-segmentation.git
```

Download Kaggle's EMNIST dataset and extract it inside the repo's folder (https://www.kaggle.com/datasets/crawford/emnist).

Final structure of your repository should look like this:

    ./handwritten-character-segmentation/
    ├── ANN/
    ├── UNet/
    ├── archive/                    # Kaggle dataset
    ├── README.md
    └── Word_Image_Generator.ipynb

## 1. Dataset Generation:

Although we just downloaded the EMNIST Kaggle dataset, it was downloaded in order to build a dataset that adapted to this case study.

Run the code contained in `Word_Image_Generator.ipynb`. This should make the following structure under the folder UNet:

    ./UNet/
    ├── XTest/
    ├── XTrain/
    ├── YTest/                    
    ├── YTrain/
    ├── classes.csv
    └── UNet.ipynb

Where the XTrain and XTest folders contain the images of the generated words, and YTest and YTrain contain their pixel-wise labels.

## 2. Usage:
