---
layout: post
title:  "Photo Clustering"
date:   2021-12-13 08:00
categories: jekyll
permalink: /posts/photoclustering
image: "https://github.com/nherger/nherger.github.io/blob/master/photos/PhotoCluster_banner.png?raw=true"
---

How can my passions for photography and data science be combined? By using a pre-trained Deep Learning model to cluster hundreds of photos of course!

<!--more-->

Over the past couple of years, I have taken thousands of photos, many of which I look back on way too rarely. Inspired by a <a href="https://cs.stanford.edu/people/karpathy/cnnembed/" target="_blank">blog post</a> by Andrej Karpathy, I decided to use Deep Learning to automatically cluster my best photos that I've taken over the past roughly 5 years, and print the resulting collage on a large canvas for the living room.

I manually selected 1024 photos (to end up with a square of 32x32 photos), fed them into a pre-trained <a href="https://keras.io/api/applications/vgg/VGG-16" target="_blank">VGG-16</a>  model from keras, with the final (classification) layer removed. Through that, I obtained vector embeddings for each photo (dimension: 224, 224, 3), which I used to compute pairwise similarities. Based on dissimilarity scores, I was able to project the images on a 2D space via t-SNE.

I was quite pleased with the result. The automatic clustering worked really well -- clusters of animals, snow, bicycles, food, portraits, and sunrises are clearly visible. Some examples are shown below. It's a fun way to make use of the large amount of photos I had on my hard drives, and I thoroughly enjoyed re-discovering them in this novel way of representation.

![Photo Clustering](https://github.com/nherger/nherger.github.io/blob/master/photos/PhotoCluster_overview.png?raw=true)
