# ROAD-R Challenge 
This repository contains  code for the first task of the [ROAD-R Challenge](https://sites.google.com/view/road-r/).
The code is built on top of [3D-RetinaNet for ROAD](https://github.com/gurkirt/road-dataset).

The first task requires developing models for scenarios where only little annotated data is available at training time. 
More precisely, only 3 out of 15 videos (from the training partition train_1 of the ROAD-R dataset) are used for training the models in this task.
The videos' ids are: 2014-07-14-14-49-50_stereo_centre_01, 2015-02-03-19-43-11_stereo_centre_04, and 2015-02-24-12-32-19_stereo_centre_04.


## Table of Contents
- <a href='#dep'>Dependencies and data preparation</a>
- <a href='#training'>Training</a>
- <a href='#testing'>Testing</a>
- <a href='#prostprocessing'>Post-processing</a>



## Dependencies and data preparation
For the dataset preparation and packages required to train the models, please see the [Requirements](https://github.com/gurkirt/3D-RetinaNet#requirements) section from 3D-RetinaNet for ROAD.  

To download the pretrained weights, please see the end of the [Performance](https://github.com/gurkirt/3D-RetinaNet#performance) section from 3D-RetinaNet for ROAD.  

![image](https://github.com/RadeenXALNW/ROAD_R_NeurIPS_Challenge/assets/66905164/d04a55ff-9fb7-4b6a-b307-a1d9d3c1867c) 

### Also a [video](https://www.youtube.com/watch?v=5rWeFtprJuQ) sample was given for the full road data annotation




## GPU USAGE 
![image](https://github.com/RadeenXALNW/ROAD_R_NeurIPS_Challenge/assets/66905164/03f9c9bf-6621-4085-81b6-4094943a1447)



#### Go through this [repo](https://github.com/gurkirt/road-dataset) for downloading all the necessary dataset.



### Some Error and User Warning that might cause to crash the environment.
- **Change all the datatype from ``` _np.int to "int"__ ``` for getting rid of attribute error** [ROAD-R-2023-Challenge/data/datasets.py]


**For avoiding UserWarning**

- ROAD-R-2023-Challenge/modules/box_utils.py (Line 368-371) Change it into
```python
        xx1 = x1.index_select(0, idx)
        yy1 = y1.index_select(0, idx)
        xx2 = x2.index_select(0, idx)
        yy2 = y2.index_select(0, idx)
