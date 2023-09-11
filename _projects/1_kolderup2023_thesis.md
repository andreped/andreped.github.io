---
layout: page
title: End-to-end Image-guided Airway Navigation using Neural Networks with Memory
description: Master's thesis by Ingerid Kolderup
img: assets/img/kolderup2023timedistributed.png
importance: 1
category: thesis
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/kolderup2023timedistributed.png" title="fafa" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Abstract

Due to the complex airway anatomy, clinicians struggle with locating the position of the bronchoscope during bronchoscopy. Even though several navigation techniques have been employed, they come with a significant expense and the requirement of expensive instruments. Low-cost and reusable navigation systems would therefore be highly valuable for the clinicians.

This thesis aims to address this obstacle by proposing an end-to-end image-guided airway navigation system that does not require any external equipment. For this purpose, a baseline model is designed to classify airway segments in synthetic video sequences from a three-dimensional model representing a lung phantom. The model contains a convolutional neural network for feature extraction and a classifier outputting predicted airway segments for the individual images in the sequence. Furthermore, the model was extended into NavigationNet, Multitask NavigationNet and Multicell and Multitask NavigationNet. They include a long short-term memory (LSTM) component for learning temporal dependencies of the extracted features from the convolutional neural network. The last two models feature an extra classification task of direction, and the latter model contains an additional LSTM component. A software prototype to enable real-time image-guiding using the trained models was also developed.

The results show that NavigationNet achieved an F1 score of 0.583 in stateful evaluation when trained and validated with complete video sequences, which clearly outperformed the baseline model. Introducing the LSTM component thus had a positive impact on the classification performance, especially for the minority classes. However, in stateless evaluation, the baseline model was marginally superior than all models, with the exception of evaluation on complete video sequences. Adding direction or the extra LSTM component did not improve the performance of NavigationNet. When evaluated visually using the prototype, the model showed a slightly weaker performance than expected. Nevertheless, the proposed end-to-end navigation system shows promise in addressing the localization challenges in bronchoscopy.

Keywords: Video Navigation, Deep Learning, Long-Short Time Memory, Convolutional Neural Networks, Bronchial classification, Supervised Learning

Supervised by Frank Lindseth, Gabriel Kiss, André Pedersen, Ingrid Tveten, Erlend Fagertun Hofstad, and Thomas Langø
