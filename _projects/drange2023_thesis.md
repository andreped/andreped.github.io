---
layout: page
title: Efficient Multilabel Tissue Segmentation of Histopathological Images using Hybrid Vision Transformer
description: Master's thesis by Markus Drange
img: assets/img/drange2023simclr.png
importance: 1
category: thesis
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/fredriksen2021teacherstudent.png" title="fafa" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Abstract

Histopathology is a central part of medicine, enabling clinicians to provide accurate diagnoses for diseases ranging from cancer to infections. The study of microscopic images is however tedious labour and necessitates extensive expertise. Automation and digitization of pathology workflows could enable higher throughput, less interoperator variation, and faster turnaround times. 

Ever since the breakthrough of convolutional neural networks (CNNs), the field of machine learning for medical image analysis has seen rapid development. The introduction of the new paradigm of transformer models led to further development of the field. This progress has led to researchers adopting both transformers and CNNs to different medical image modalities.

This thesis aims to investigate both architectures applied to histopathological multilabel image classification, and explore how different training configurations affect their performance. 

The models will be trained using the Atlas of Digital Pathology dataset, consisting of 17 668 patches accompanied by labels describing the different tissue types present. The images are derived from 100 slides of human histopathological examinations of different diagnoses, obtained from several body parts, ranging from the brain to the kidney. 

This study presents three CNNs, one vision transformer and two hybrid models and compares their performance. In addition, different configurations of pre-training and data augmentation will be explored.

The results find that a lightweight hybrid model, the MobileViT, combining properties from both CNNs and transformers, achieves the best results, after pretraining in a self-supervised manner. Said model obtained an F1-score of 0.835. The results also showed that without self-supervised pertaining, the ResNet50 and the ViT-16/B were the best-performing models with an F1-score of 0.821 and 0.822, respectively. It was demonstrated that using data augmentation techniques can improve the prediction performance of vision transformers for histopathological image classification, whereas color augmentations might degrade performance.

Keywords: Digital Pathology, Deep Learning, Contrastive Learning, Multilabel, Tissue Segmentation, Semi-supervised Learning

Supervised by André Pedersen, Frank Lindseth, Gabriel Kiss, and Thomas Langø
