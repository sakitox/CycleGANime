# CycleGANime
CycleGAN implementation to translate people (and later video game screenshots) to anime

## Introduction

I created a CycleGAN model based on 92,000 human faces and 21,000 anime faces. The objective is to create a style transfer that would learn to generate an anime face from a real one and vice-versa.

## Requirements

Check Requirements.txt

## Distributed TPU training

GAN-like networks are particularly challenging given that they often use multiple optimizers. In addition, GANs also consume a large amont of GPU memory and are usually batch-size sensitive. I could not run it locally on my desktop and resorted to use google colab's TPU offer.

Google Colab does limit usage for free users and is not available for pro upgrade on my locality (London). I prediodically saved epochs using model checkpoints in order to resume training every time my limits were reset.

## Initial examples

TBD

## Results

TBD

## Author

@sakitox

## License

Kaggle data used as inputs, not for commercial use
