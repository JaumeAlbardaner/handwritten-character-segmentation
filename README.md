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

Although we just downloaded the EMNIST Kaggle dataset, it was downloaded in order to build a dataset that adapted to this case study (the words contained in variable `phrase`).

Run the code contained in `Word_Image_Generator.ipynb`. This should make the following structure under the folder UNet:

    ./UNet/
    ├── XTest/
    ├── XTrain/
    ├── YTest/                    
    ├── YTrain/
    ├── classes.csv
    └── UNet.ipynb

Where the XTrain and XTest folders contain the images of the generated words, and YTest and YTrain contain their pixel-wise labels.

## 2. UNet model:

A way of segmenting characters in an image of a handwritten word can be to apply a UNet. In order train one, the previous artificial dataset with the masks in every image was constructed.

By running `UNet.ipynb` any user can generate their own UNet weights. These are stored in variable emnist.h5.

Furthermore, since this dataset was artificially created and the text in every image is previously known, one might want to improve segmentation by limiting what classes take part in the np.argmax operation.

## 3. ANN model:

Since a model was obtained that can detect where each letter is, this model can be combined with a simple ANN model to evaluate what character each letter is.

This can be run 

## 3. CNN model: