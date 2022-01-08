---
layout: page
title: Pulmonary Tumor Segmentation Utilizing Mixed-Supervision in a Teacher-Student Framework
description: Master's thesis by Vemund Fredriksen and Svein Ole M. Svele
img: assets/img/fredriksen2021teacherstudent.png
importance: 1
category: thesis
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/fredriksen2021teacherstudent.png" title="fafa" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Cancer is a leading cause of death in the developed world, and lung cancer is the most lethal. Clinical experts rely on advanced medical imaging techniques and visual inspection to detect lung tumors. Prognosis is highly dependent on the stage of cancer, and mortality can be reduced by early detection. Recent development in machine learning techniques shows promise for automating time-consuming tasks that are currently performed manually by trained experts.

Lack of annotated data is one of the primary constraints in developing automatic methods for
medical image segmentation tasks. Public datasets often contain different degree of annotations, if any. In an attempt to address some of these problems, we have investigated the potential of training deep neural networks that can learn from a larger set of less accurately annotated data, to improve performance on lung tumor segmentation. We implemented a framework, based on the recently emerging Teacher-Student design, to utilize bounding box annotated datasets to facilitated lung tumor segmentation learning.

Our research shows that using a sufficiently large, less accurately annotated dataset, the Teacher-Student framework can improve segmentation and detection performance. We also demonstrate that our produced teacher may be used as a semi-automatic method to facilitate the labeling of medical images.

Our best model, trained from only 48 human-annotated images and 991 teacher-annotated
images (given bounding box supervision), reached a Dice Coefficient Score of 0.7156 on the
MSD dataset, tested on nine images, which is on the state-of-the-art level. Another model
trained under the same conditions, reached a perfect tumor-level F1 Score of 1.0 on the MSD
dataset.

Keywords: Lung Cancer, Deep Learning, Medical Image Segmentation, Mixed Supervision,
Teacher-Student Framework
