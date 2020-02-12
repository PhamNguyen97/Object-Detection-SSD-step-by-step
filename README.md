# Object-Detection-SSD-step-by-step
Step-by-step SSD training on own dataset

## Dependencies Installation
1. Clone [Tensorflow Object Detection API Repo](https://github.com/tensorflow/models)   
```
git clone https://github.com/tensorflow/models.git
```
2. Install dependencies required in [Requirement](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md)   

## Data Preparation
1. New data can be labeled using [lableImg Repo](https://github.com/tzutalin/labelImg)   
Note: label files should be in VOC format (.xml files)   
2. Split data into train and validation sets:   
> Split randomly with 80% training and 20% validation
> Convert .xml files into train.tfrecord and valid.tfrecord files   

## Train SSD with own dataset
1. Modify **.config** file in */samples/configs/<>.config*   
2. Train SSD as show in [Tensorflow Repo](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/running_locally.md)   
```
# From the tensorflow/models/research/ directory
PIPELINE_CONFIG_PATH={path to pipeline config file}
MODEL_DIR={path to model directory}
NUM_TRAIN_STEPS=50000
SAMPLE_1_OF_N_EVAL_EXAMPLES=1
python object_detection/model_main.py \
    --pipeline_config_path=${PIPELINE_CONFIG_PATH} \
    --model_dir=${MODEL_DIR} \
    --num_train_steps=${NUM_TRAIN_STEPS} \
    --sample_1_of_n_eval_examples=$SAMPLE_1_OF_N_EVAL_EXAMPLES \
    --alsologtostderr
```
## Inference
1. Turn trained model into frozen graph   
2. 
