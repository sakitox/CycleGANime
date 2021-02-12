# CycleGANime
CycleGAN implementation to translate people (and later video game screenshots) to anime

## Introduction

I created a CycleGAN model based on 92,000 human faces and 21,000 anime faces. The objective is to create a style transfer that would learn to generate an anime face from a real one and vice-versa.

## Requirements

Check Requirements.txt

Datasets obtained from Kaggle:
  
  Anime faces dataset: https://www.kaggle.com/scribbless/another-anime-face-dataset
  
  Human faces dataset: https://www.kaggle.com/ashwingupta3012/human-faces
  
## Data Preparation

The human faces come in a variety of sizes between 500-600 px, while the anime faces claim all to be 256x256. However, I found errors when fed into the CycleGAN do to inconsistent sizes in this dataset.

I proceeded to resize all images (with padding) and resave them later to be transformed into TFRecords datasets that are optimized for fast data injection in distributed TPU's.

The data preparation notebook can be found in this repository as 'datasetbuilding v2'

the TFRecords datasets for both anime and humans were uploaded to a google bucket for assimilation via google colab. These records are not present in this repository due to their large size.

## Distributed TPU training

GAN-like networks are particularly challenging given that they often use multiple optimizers. In addition, GANs also consume a large amont of GPU memory and are usually batch-size sensitive. I could not run it locally on my desktop and resorted to use google colab's TPU offer.

Google Colab does limit usage for free users and is not available for pro upgrade on my locality (London). I prediodically saved epochs using model checkpoints in order to resume training every time my limits were reset.

## Initial examples

<div style="-webkit-column-count: 3; -moz-column-count: 3; column-count: 3; -webkit-column-rule: 1px dotted #e0e0e0; -moz-column-rule: 1px dotted #e0e0e0; column-rule: 1px dotted #e0e0e0;">
    <div style="display: inline-block;">
        ### Anime Faces

![alt text](https://github.com/sakitox/CycleGANime/blob/main/Anime/10004131_result.jpg?raw=true)

![alt text](https://github.com/sakitox/CycleGANime/blob/main/Anime/10006043_result.jpg?raw=true)

![alt text](https://github.com/sakitox/CycleGANime/blob/main/Anime/10009741_result.jpg?raw=true)

    </div>
    <div style="display: inline-block;">
### Human Faces

![alt text](https://github.com/sakitox/CycleGANime/blob/main/Human/0000.png?raw=true)

![alt text](https://github.com/sakitox/CycleGANime/blob/main/Human/0001.png?raw=true)

![alt text](https://github.com/sakitox/CycleGANime/blob/main/Human/0002.png?raw=true)

    </div>
</div>


## Results

TBD

## Author

@sakitox

## License

Kaggle data used as inputs, not for commercial use
