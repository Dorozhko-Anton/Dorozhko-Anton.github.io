---
layout: post
title:  "Good labelling tools can save you the day (or even more time)"
categories: 
tags: 
image: "/assets/images/wintics_series/labelling.png"
summary: "Review of SOTA for labelling utils and services."
author: Anton
d3: False
---

![label](/assets/images/wintics_series/labelling.png){: .center-image }

# How to increase the speed of labellization ?

pre-labellization 

interface 



# Webbased / desktop / mobile ?


# Custom labelling solutions 


# Opensource labelling tools 

https://www.trantorinc.com/blog/best-data-labeling-tools-2019/

Annotorious  (add bbox, polygon to your site, js)
LabelMe (simple annotation tool, require registration)
Labelbox (python SDK, bboxes, polygons, editting, consensus, review steps)
Sloth (oss, add configurations)

https://www.quora.com/What-is-the-best-image-labeling-tool-for-object-detection
https://www.datasetlist.com/tools/

https://www.researchgate.net/post/Can_anyone_suggest_an_image_labeling_tool_for_object_detection

# Startups 

## [Scale](https://scale.com/) 

Scale is the Data Platform for AI. 

![scale_services](/assets/images/wintics_series/scale_products.png){: .center-image }

We are mostly interesting in `2D Boxes` annotations for now. 
Scale proposes a price of `$0.08 / Image + $0.08 / Annotation` 

Let's make a rough calculation. If we want 200 images with on average 6 objects it will cost us :
200*0.08 * (1 + 6) =  112 $

For denser images, say with 50 images on average:
200*0.08 * (1 + 50) =  816 $

For simple 2D Box cases it might be costly, but they have a lot more different types of tasks. And segmentation with 6.4$ by image is quite good. Radar and Lidar point clouds require good tools to make labelisation faster, as well as video annotations and Sensor fusions, so the added value of that company is great.  

TODO: add simple js calculations with slider 

You create a task with instructions and examples as a request to scale API and labeller will do it. [API docs](https://scale.com/docs#create-computer-vision-tasks)



## [DBrain](https://dbrain.io/)

Same as Scale but it is only ready to propose you a demo. 

## [Hasty](https://hasty.ai)

Create Project -> Access rules -> Manual annotation examples -> Start to receive AI support (when model is ready) -> Manual Review Tool 

2D Bbox
Polygon
Countour (with countour detection)
MagicWand (segmentation)
Brush (segmentation)
Grabcut (segmentation in the selection, with cut brush)

Classifier of the selection 
Object-detection assistant (prelabelisation)




# Big providers 

https://www.mturk.com/

https://cloud.google.com/data-labeling/docs/

DataTurks [https://dataturks.com/] 