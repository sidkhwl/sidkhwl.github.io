---
layout: post
title:  "DeblurGAN: Blind Motion Deblurring Using Conditional Adversarial Networks"
date:   2019-11-24
---

As part of the course requirements of Neural Networks and Fuzzy Logic in the 5th semester, we were supposed to implement a research paper of our choice from a huge list of 72 papers assorted by TAs of the course. You can find them [here](https://bitsnnfl.github.io). We were allowed to be team up with 2 other students taking the course.
<br>
With a time of just 2 days to choose the paper, we skimmed through the abstract of all the listed papers and zeroed down to implement the [DeblurGAN paper](https://arxiv.org/pdf/1711.07064.pdf). You can find the code [here](https://github.com/siddhantkhandelwal/deblur-gan/).

## What is Image Deblurring?

Blurry images are caused due to motion of the camera lense, rotational components, or slight movement on the part of the target itself. The blur is modelled by the following equation:

`` `IB = k(M) * IS + N` ``

 - IB is the blurry image
 - IS is the sharp image
 - k(M) is the unknown blur chanel 
 - \* is the convolution operation

## DeblurGAN

DeblurGAN is an end-to-end learned method for motion deblurring. It achieves state of the art performance both in structural similarity and visual appearance.

![Results on GoPro_Large Dataset]({{ site.url }}{{ site.baseurl }}/img/result_go_pro_large.png)

### Model Architecture

![GAN Model Architecture]({{ site.url }}{{ site.baseurl }}/img/model-arch.png)

*  It contains two strided convolution blocks, nine residual blocks and two transposed convolution blocks.
* Each ResBlock consists of a convolution layer, instance normalization layer and ReLU activation. Dropout regularization

with a probability of 0.5 is added after the first convolution layer in each ResBlock.

* The critic network is Wasserstein GAN with gradient penalty. The architecture of critic network is identical to PatchGAN. All the convolutional layers except the last are followed by InstanceNorm layer and LeakyReLU with α = 0.2.

## Performance

* We trained for 200 epochs (original implementation was 300 epochs)
* Metrics
  + PSNR
  + SSIM

SSIM and PSNR are image similarity tests. They are used to determine, how much quality is lost with the encoding process. PSNR is an engineering abbreviation for peak signal-to-noise ratio. SSIM stands for structural similarity index and is a more complex test aimed to determine perceivable difference between two images.

Our model's performance

| PSNR | SSIM   |
|------|--------|
| 25.4 | 0.8208 |

## Results

Our model successfully deblurs the images without loss of context and contrast.

![Model's results on GoPro_Large Dataset]({{ site.url }}{{ site.baseurl }}/img/result_model_go_pro_large-1.png)

![Model's results on GoPro_Large Dataset]({{ site.url }}{{ site.baseurl }}/img/result_model_go_pro_large-2.png)

![Model's results on GoPro_Large Dataset]({{ site.url }}{{ site.baseurl }}/img/result_model_go_pro_large-3.png)

## Referred Implementation

* We referred to [Raphael Meudec's](https://github.com/RaphaelMeudec) Keras implementation for the model's architecture [here](https://github.com/RaphaelMeudec/deblur-gan).

Here's a link to the [final presentation](https://github.com/siddhantkhandelwal/deblur-gan/blob/master/DeBlurGAN%20Presentation.pdf).

