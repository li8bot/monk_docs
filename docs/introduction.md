# Monk
#### Monk is an open source framework for finetuning Deep Neural Networks using Transfer Learning
[![Version](https://img.shields.io/badge/version-v1.0-lightgrey)](https://github.com/abhi-kumar/monk_v1) &nbsp; &nbsp;
[![Build_Status](https://img.shields.io/badge/build-passing-green)](https://github.com/abhi-kumar/monk_v1)


## Create an image classification experiment.
- Load foldered dataset
- Set number of epochs
- Run training

```python
ptf = prototype(verbose=1)
ptf.Prototype("sample-project-1", "sample-experiment-1")
ptf.Default(dataset_path="./dataset_cats_dogs_train/", 
                model_name="resnet18", freeze_base_network=True, num_epochs=2)
ptf.Train()
```

## Inference

```python
img_name = "./monk/datasets/test/0.jpg";
predictions = ptf.Infer(img_name=img_name, return_raw=True);
print(predictions)
```


## Compare Experiments

- Add created experiments with different hyperparameters
- Generate comparison plots

```python
ctf = compare(verbose=1);
ctf.Comparison("Sample-Comparison-1");
ctf.Add_Experiment("sample-project-1", "sample-experiment-1");
ctf.Add_Experiment("sample-project-1", "sample-experiment-2");
    .
    . 
    .
```
