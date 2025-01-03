---
layout: page
title: Detection, Retrieval and Rectification in a Museum Environment
description: Vision and Cognitive Systems Project 2019/2020
img: assets/img/vision-project.png
importance: 1
category: university
related_publications: false
---

<div class="mb-4">
    <a href="https://github.com/apanariello4/vision-project" class="btn btn-primary me-2" target="_blank">
        🔗 View Code
    </a>
    <a href="https://github.com/apanariello4/vision-project/blob/master/report/report.pdf" class="btn btn-secondary" target="_blank">
        📄 PDF Report
    </a>
</div>

The aim of this work is to detect paintings and people inside a museum environment and then perform retrieval and rectification of the detected painting from a database of high quality images, we also detect statues. The detection of the three objects is performed with a custom trained YOLOv3 network, while the retrieval is done by ORB keypoints. For the rectification we exploit the keypoints obtained by the ORB to find the homography matrix. Once we have found the paintings and the people we can localize the latter by getting the localization of the painting. The direction in which the person is facing is computed by a face detection and assuming that if the person is not looking at the camera then he is facing a painting. We also process screenshots from a 3D model of the museum, replacing paintings with high quality images from a database, using an inverse approach w.r.t the rectification one.

## Retrieval and Rectification
{% include figure.liquid loading="eager" path="https://raw.githubusercontent.com/apanariello4/vision-project/master/report/pictures/painting_rectification/rectification.png" title="Retrieval and Rectification" class="img-fluid rounded z-depth-1" %}

# Features
- [x] **Painting detection:** predict a ROI for each painting
    - [x] **Statue detection:** predict a ROI for each statue
- [x] **Painting rectification:** correct the perspective distortion of each painting
- [x] **Painting retrieval:** match each detected painting to the paintings DB
- [x] **People detection:** predict a ROI around each person
    - [x] **Face detection:** determine whether each person is facing a painting
- [x] **People localization:** assign each person to one of the rooms of the Gallery
- [x] **Painting replacing:** replace a painting of a view from the 3D model with
        its corresponding picture in the paintings DB, appropriately deformed to match the 3D view
