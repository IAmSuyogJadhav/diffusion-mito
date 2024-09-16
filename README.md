# INF-8606 diffusion-mito
Generating Synthetic fluoresence images of mitochondria.

## Environment Setup
Using conda, create a new environment with the following command:
```bash
conda env create -f env.yml
```

## Task 1
Training code can be found in the file `task1_training.ipynb`. The training is launched by setting `NOISY` to `False` for T1-noisefree and `True` for T1-noisy, in the notebook.

## Task2 
Training code can be found in the file `task2_training.py`. The training is launched by running:

1) T2-noisefree
```bash
accelerate launch train_controlnet_mito.py --pretrained_model_name_or_path benjamin-paine/stable-diffusion-v1-5 --mito_data_dir ../data_experiments/data/mito_variable_sbrs_big_80nm --learning_rate 0.0001 --mito_image_subdir xy_max_noisefree_uint8
```

2) T2-noisy
```bash
accelerate launch train_controlnet_mito.py --pretrained_model_name_or_path benjamin-paine/stable-diffusion-v1-5 --mito_data_dir ../data_experiments/data/mito_variable_sbrs_big_80nm --learning_rate 0.0001 --mito_image_subdir xy_max_uint8
```

## Training Data and Trained Models
The training data and the 4 trained models weight around 45 GB, and are made available on request.
