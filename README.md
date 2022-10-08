# Form-Segmentor
A trained model to segment form images into individual form inputs based on input labels

*** 

# Research

As the title of the repo suggests, this is an image segmentation task. There are 3 types of image segmentation.

Task | Definition
--- | ---
Semantic Segmentation | Partitions the image into regions of 'things', each belonging to a class but doesn't separate all the things in each class further, so an image containing 2 people for example will just identify there are 2 regions of class 'person', it won't differentiate between each individual.
Instance Segmentation | Partitions the image into separate regions without identifying the class of those regions. Taking the example from above, it will know there are two different objects (people) but it won't know those objects are of class 'person'. It just knows there are two separate objects based on region similarity and boundaries. It will also identify the separate regions in the background(sky, ground) as will semantic segmentation.
Panoptic Segmentation | This is a combination of the previous two tasks. It will divide the image into separate regions of things while also identifying the classes each region belongs to. So it will know there is a sky,ground, etc.. as well as there being two regions of 'person' each being separate from the other, in other words 2 instances of class 'person' present.


[Source](https://www.v7labs.com/blog/image-segmentation-guide#h3)

---

For our task we want to split the image into separate regions of label/input pairs, as well as button. We won't worry about object detection (OD) here as it might be too slow without ML. This project will serve as the preprocessor to an ML model for OD. Since there are multiple classes (button, input, label, etc...) lets try and use panopctic segmentation.



![image segmentation algorithms](https://assets-global.website-files.com/5d7b77b063a9066d83e1209c/61252d1629671c610b13f6f5_image-segmentation.png)
