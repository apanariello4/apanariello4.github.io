---
layout: page
title: Clean Air
description: IoT & 3D intelligent systems project 2020-2021
img: assets/img/cleanair.png
importance: 1
category: university
related_publications: false
---

<div class="mb-4">
    <a href="https://github.com/apanariello4/iot-clean-air" class="btn btn-primary me-2" target="_blank">
        🔗 View Code
    </a>
</div>

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

<div class="row">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="https://github.com/apanariello4/iot-clean-air/raw/main/imgs/androidapp.png" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Predictions

Our system is also able to predict PM10 and PM25 pollution values in order to keep the window close even before that the air quality starts worsening. To train the model we use Prophet with open source datasets of italian cities. In production the datasets keep growing thanks to the sensors and the model keeps getting retrined and fine tuned.
