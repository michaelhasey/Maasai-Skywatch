
# Maasai Skywatch
by 
Michael Hasey, Luke McKinley, Rhys Broussard

------------------------------------------------

## Intro

<br>

Maasai Skywatch is a proposed online tool that uses publicly available satellite imagery and sophisticated object-detecting algorithms to identify and locate illegal village burns and land-related injustices against the Maasai people.


# Project Page

<br>

```
www.michaelhasey.com/maasai-skywatch
```

## Background

<br>

A semi-nomadic ethnic group, the Maasai are based in the Great Rift Valley of East Africa, between Northern Tanzania and Southern and Central Kenya.  With a population of almost 2 million, they have inhabited the region for centuries, moving their herds of cattle with the seasons.

Government officials and foreign companies in Tanzania and Kenya are using ecotourism and conservation laws to displace indigenous Maasai people, evicting them and denying them access to watering holes and vital grazing for their livestock.  We use computer vision to provide the Maasai with a tool to quickly identify illegal village burns, forced migrations, & potential land grabs.

In addition, our model can identify how many individual houses are located within each village, and thus provide an estimated inhabitant count.  As the Maasai are semi-nomadic and do not have fixed addresses, obtaining population counts is often difficult.  By using deep learning methods such as this, population counts can be acquired more quickly and accurately. 

<br>

![](images/intro_banner2.png)

<br>

## Data

<br>

In order to detect villag burns, we trained an Object Detection Model on a custom dataset of 600 satellite images of Maasai villages compiled and augmented within Roboflow, a dataset builder application.  Our final training dataset contained images of villages in various states (burned, not burned, etc.) , landscapes (desert, grassland, etc.)  and contexts (dense, not dense, etc.), allowing our model to detect village burns in varying environments and locate instances of potential injustice.  In addition, we taught our model to identify villages, individual house counts within villages, and animal corrals.  

Using [labelImg](https://github.com/tzutalin/labelImg), we set bounding boxes around current and former Maasai architectures (villages, corrals, farms, burned villages) before augmenting with color, rotation, and random noise.  

<br>

![](images/data.png)

<br>


## Model Training

In order to autonomously detect Maasai villages, home burnings, and other injustices from above, we used a sophisticated neural network algorithm called [Yolo-V3](https://github.com/eriklindernoren/PyTorch-YOLOv3).  This model was trained to detect maasai villages and animal corrals, individual houses within villages, and villages that have been burned. 

<br>

For model training, follow the instructions and steps within the provided notebook below

```
maasai-village-notebook.ipynb
```

<br>

## Results

<br>

After training our YoloV3 object detection model, we evaluated its performance by testing it on a series of new images it has never been exposed to before.  These images contained unlabelled Maasai villages, burned villages, and corrals for animals set in a variety of landscapes and contexts.   As indicated below, our trained model properly identified and label these objects and instances with a high degree of accuracy. 

<br>

![](images/object_detection_types.png)

<br>


