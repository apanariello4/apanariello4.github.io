---
title: Clean Air
summary: Autmatically keep the internal air quality at its best, with pollution prediction.
tags:
  - IoT
  - Deep Learning
date: '2021-05-18T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: Clean Air Infrastructure
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: Code
    url: https://github.com/apanariello4/iot-clean-air
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---
*IoT & 3D intelligent systems project 2020-2021*


**Clean Air** is a automatic system able to keep the internal air quality at best possible level, measuring the internal CO<sub>2</sub> and the external PM10 and PM25. It opens the windows when the volume of CO<sub>2</sub> is high and the PMs values are low enough.

## Structure

| Description       |      Codebase     |
|-------------------|:-----------------:|
| Database          |       SQLite      |
| Web App Backend   |    Python/Flask   |
| Web App Frontend  | Jinja2/Javascript |
| Android App       |        Java       |
| Predictions       |      Prophet      |
| Window Controller |    Arduino/C++    |
| Communications    |     HTTP/MQTT     |

## Web App

The Web App is the centre of this system. The backend part manages the database and all the requests, while in the frontend is possible to manage ones dispositives and remotely activate them.

## Android App
The Smartphone Client let us add new devices to our profile via QRCode and manage them.

<img src="https://github.com/apanariello4/iot-clean-air/raw/main/imgs/androidapp.png" width="300">

## Predictions

Our system is also able to predict PM10 and PM25 pollution values in order to keep the window close even before that the air quality starts worsening. To train the model we use Prophet with open source datasets of italian cities. In production the datasets keep growing thanks to the sensors and the model keeps getting retrined and fine tuned.
