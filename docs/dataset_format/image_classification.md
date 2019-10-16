## Image Classification

**Two formats of Datasets are supported by image classification models and can be initialised as follows**

1a. Images split into folders of respective classes with only the training class
```python
ptf.Default(dataset_path="./monk/datasets/train", model_name="resnet18", freeze_base_network=True, num_epochs=2);
```

1b. Images split into folders of respective classes with only the training and val/test class
```python
ptf.Default(dataset_path=["./monk/datasets/train", "./monk/datasets/val"], model_name="resnet18", freeze_base_network=True, num_epochs=2);
```

2a. A folder with training images with a label CSV file listing all images and classes
```python
ptf.Default(dataset_path="./monk/datasets/train", path_to_csv="./monk/datasets/train.csv", model_name="resnet18", freeze_base_network=True, num_epochs=2);
```

2b. 2 folders with training and val/test images with label CSV files for both training and val/test set
```python
ptf.Default(dataset_path=["./monk/datasets/train", "./monk/datasets/val"], path_to_csv=["./monk/datasets/train.csv","./monk/datasets/val.csv"], model_name="resnet18", freeze_base_network=True, num_epochs=2);
```