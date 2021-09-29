# Towards Rotation Invariance in Object Detection - ICCV 2021

Authors: [Agastya Kalra](https://kalraa.github.io), [Guy Stoppi](https://github.com/guystoppi), [Bradley Brown](https://www.bradbrown.ca), [Rishav Agarwal](https://github.com/rra94), [Achuta Kadambi](https://visual.ee.ucla.edu)

Links: [paper](https://arxiv.org/abs/2109.13488) / [supplement](https://github.com/akasha-imaging/ICCV2021/blob/main/Supplement.pdf) 

<img width="122" alt="image" src="https://user-images.githubusercontent.com/12487598/135300445-a819f61b-b6ab-472b-bb83-9ce6353273cc.png">

### Our Rotation Augmentation (blue) vs Previous Rotation Augmentation (red):
![ellipse](https://user-images.githubusercontent.com/12487598/135296130-8e94a699-8037-472d-a693-edd8d19c3be7.gif)
![largest_crop](https://user-images.githubusercontent.com/12487598/135296965-9b8b4a5b-2ec3-46f7-a4f6-dd30af99e7a1.gif)

We propose a mathematically sound rotation augmentation scheme in object detection that leads to better rotation invariance/equivariance that can be implemented in a few lines of code. 

### Results
<img width="629" alt="image" src="https://user-images.githubusercontent.com/12487598/135298949-295a0de0-ebe8-48c6-a0e3-0b60c36ebd2e.png">

<img width="1043" alt="image" src="https://user-images.githubusercontent.com/12487598/135299915-e7e1fb7c-3c2f-4153-b057-18d69aeb3387.png">

<img width="934" alt="image" src="https://user-images.githubusercontent.com/12487598/135299995-d97ae602-3e60-4524-ad89-893b63c930a5.png">

<img width="922" alt="image" src="https://user-images.githubusercontent.com/12487598/135299952-ef30eced-844a-4e7a-b062-056d91faae33.png">

### Code:
Here we provide the optimization code for maximizing expected IoU and deriving the ellipse using tensorflow and gradient descent in the optimization.ipynb file. For the RU Loss and Ellipse method we provide pseudo-code here and will be making pull requests soon. 

#### Ellipse Rotation:
<img width="319" alt="image" src="https://user-images.githubusercontent.com/12487598/135301014-aa0f8a33-1595-411c-a9b1-e470beee54d8.png">


#### RU Loss:
<img width="337" alt="image" src="https://user-images.githubusercontent.com/12487598/135300871-72d2e269-a648-457f-925e-2f484862f727.png">


### How it works?
Existing repos all use the largest box approach to rotating a bounding box, but this causes oversized boxes. We optimize for expected IoU and find that an ellipse shape
<img width="500" alt="image" src="https://user-images.githubusercontent.com/12487598/135301192-9b52d395-d7a0-4d1a-a176-ea49d27da692.png">

We then add a Rotation Uncertainty loss that allows the model to adapt the uncertain rotated label. 
<img width="398" alt="image" src="https://user-images.githubusercontent.com/12487598/135301379-4c06cf6a-1a26-4ff5-a59b-c2fb4e977b6d.png">


### License (MIT):
"Copyright 2021 Boston Polarimetrics, Inc. (dba Akasha Imaging)

"Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

"The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

"THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE." 

### Citations:
If you find this work useful, please cite the paper as follows:
```latex
@inproceedings{kalra2021rotation,
      title={Towards Rotation Invariance in Object Detection}, 
      author={Agastya Kalra and Guy Stoppi and Bradley Brown and Rishav Agarwal and Achuta Kadambi},
      journal={2021 IEEE/CVF International Conference on Computer Vision (ICCV)},
      year={2021}
}
```





