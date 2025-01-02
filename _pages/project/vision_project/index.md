---
title: Detection, Retrieval and Rectification in a Museum Environment
summary: Vision and Cognitive Systems Project 2019/2020.
tags:
  - Deep Learning
  - Computer Vision
date: '2020-06-24T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Neural Network Detection
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: Code
    url: https://github.com/apanariello4/vision-project
url_code: ''
url_pdf: 'https://github.com/apanariello4/vision-project/blob/master/report/report.pdf'
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---

The aim of this work is to detect paintings and people inside a museum environment and then perform retrieval and rectification of the detected painting from a database of high quality images, we also detect statues. The detection of the three objects is performed with a custom trained YOLOv3 network, while the retrieval is done by ORB keypoints. For the rectification we exploit the keypoints obtained by the ORB to find the homography matrix. Once we have found the paintings and the people we can localize the latter by getting the localization of the painting. The direction in which the person is facing is computed by a face detection and assuming that if the person is not looking at the camera then he is facing a painting. We also process screenshots from a 3D model of the museum, replacing paintings with high quality images from a database, using an inverse approach w.r.t the rectification one.

## Retrieval and Rectification
![Retrieval and Rectification](https://raw.githubusercontent.com/apanariello4/vision-project/master/report/pictures/painting_rectification/rectification.png)

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
