# Learning To Count Everything
![image](learn2countEverything.png)

This is the official implementation of the following CVPR 2021 paper:


## Dataset download 
Images can be downloaded from here: https://drive.google.com/file/d/1ymDYrGs9DSRicfZbSCDiOu0ikGDh5k6S/view?usp=sharing

Precomputed density maps can be found here: https://archive.org/details/FSC147-GT

Place the unzipped image directory and density map directory inside the data directory.

## Installation with Conda

conda create -n fscount python=3.7 -y

conda activate fscount

python -m pip install matplotlib opencv-python notebook tqdm

conda install pytorch==1.4.0 torchvision==0.5.0 cudatoolkit=10.0 -c pytorch


## Quick demo

Provide the input image and also provide the bounding boxes of exemplar objects using a text file:

``` bash
python demo.py --input-image orange.jpg --bbox-file orange_box_ex.txt 
```

Use our provided interface to specify the bounding boxes for exemplar objects


``` bash
python demo.py --input-image orange.jpg
```


## Evaluation
We are providing our pretrained FamNet model, and the evaluation code can be used without the training.
### Testing on validation split without adaptation
```bash 
python test.py --data_path /PATH/TO/YOUR/FSC147/DATASET/ --test_split val
```
### Testing on val split with adaptation
```bash 
python test.py --data_path /PATH/TO/YOUR/FSC147/DATASET/ --test_split val --adapt
```


## Training 
``` bash
python train.py --gpu 0
```


