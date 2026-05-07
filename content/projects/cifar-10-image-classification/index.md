---
title: "CIFAR-10 Image Classification"
date: 2026-02-03
summary: "Multi-class image classification pipeline that uses transfer learning with ResNet50 to classify 32×32 RGB images from the CIFAR-10 dataset into ten everyday categories, reaching 40.2% test accuracy through a two-phase training approach."
tags:
  - Computer Vision
  - Deep Learning
  - Image Classification
  - Transfer Learning
  - CNN
tech_stack:
  - Python
  - TensorFlow
  - Keras
  - scikit-learn
  - Pandas
  - Jupyter
links:
  - type: github
    url: https://github.com/krauseannelize/cv-cifar10-classification
    label: Code
  - type: video
    url: https://youtu.be/s3YAemA9kLs
    label: Video Walkthrough
featured: true
status: "Masterschool"
role: "Solo Project"
---

A multi-class image classification pipeline that uses **transfer learning with ResNet50** to classify 32×32 RGB images from the [CIFAR-10 dataset](https://www.cs.toronto.edu/~kriz/cifar.html) into ten everyday categories: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, and truck. The workflow covers pixel normalisation, a custom classification head on top of a pre-trained ResNet50 backbone, and a two-phase training approach: a frozen-base phase to map ImageNet features onto CIFAR's classes, followed by fine-tuning with a small learning rate to adapt the base model itself. Final test accuracy reached **40.2%**, four times better than random guessing on a ten-class problem.

The project also includes an honest analysis of what the model handled well and where it struggled. Classes with distinctive shapes, colour signatures, or consistent backgrounds (ship, automobile, frog) classified strongly, while visually similar pairs (cat-dog, automobile-truck, airplane-ship) confused the model at 32×32 resolution. The clear next steps are data augmentation, training on the full 50,000-image set, dropout regularisation, and lighter architectures like EfficientNet-B0 or MobileNetV2.

Built locally in VS Code as part of Masterschool's deep learning module.
