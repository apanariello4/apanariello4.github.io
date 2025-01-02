---
title: 'TrackFlow: Multi-Object tracking with Normalizing Flows'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Gianluca Mancusi
  - admin
  - Angelo Porrello
  - Matteo Fabbri
  - Simone Calderara
  - Rita Cucchiara

# Author notes (optional)
# author_notes:
#   - 'Equal contribution'
#   - 'Equal contribution'

date: '2023-07-01T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
# publishDate: '2017-01-01T00:00:00Z'

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In *International Conference on Computer Vision 2023*
publication_short: In *ICCV'23*

abstract:
  "The multi-object tracking field has recently seen a renewed interest in the good old schema of *tracking-by-detection*, as its simplicity and strong priors spare it from the complex design and painful babysitting of *tracking-by-attention* approaches. In view of this, we aim at extending tracking-by-detection to **multi-modal** settings, where a comprehensive cost has to be computed from heterogeneous information *e.g.* 2D motion cues, visual appearance, and pose estimates. More precisely, we follow a case study where a rough estimate of 3D information is also available and must be merged with other traditional metrics (*e.g.*, the IoU). To achieve that, recent approaches resort to either simple rules or complex heuristics to balance the contribution of each cost. However, *i)* they require careful tuning of tailored hyperparameters on a hold-out set, and *ii)* they imply these costs to be independent, which does not hold in reality. We address these issues by building upon an elegant probabilistic formulation, which considers the cost of a candidate association as the *negative log-likelihood* yielded by a deep density estimator trained to model the conditional joint probability distribution of correct associations. Our experiments, conducted on both simulated and real benchmarks, show that our approach consistently enhances the performance of several tracking-by-detection algorithms."

# Summary. An optional shortened abstract.
summary: "We propose a novel approach to multi-object tracking that leverages Normalizing Flows to learn a joint probability distribution over the costs of candidate associations. Our experiments show that our approach consistently enhances the performance of several tracking-by-detection algorithms."

tags: [Multi-Object Tracking, Normalizing Flows, Deep Learning, Computer Vision]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/abs/2308.11513'
url_code: ''
url_dataset: ''
url_poster: 'publication/mancusi2023trackflow/poster_trackflow_iccv2023.pdf'
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Overview of TrackFlow.'
  focal_point: 'center'
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
# projects:
#   - example

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
# slides: example
---
<!--
{{% callout note %}}
Click the _Cite_ button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /callout %}}

{{% callout note %}}
Create your slides in Markdown - click the _Slides_ button to check out the example.
{{% /callout %}}

Supplementary notes can be added here, including [code, math, and images](https://wowchemy.com/docs/writing-markdown-latex/). -->
