## Quick Mode -- Pytorch

### Import Monk library
- Place <b>monk</b> inside your project folder

```python
import os
import sys
sys.path.append("./monk/");
import psutil
from pytorch_prototype import prototype
```

### Create Workspace and Experiment
?> **Info** Rename `sample-project` and `sample-experiment`
```python
ptf = prototype(verbose=1);
ptf.Prototype("sample-project", "sample-experiment");
```

### Load Dataset 
- Update <b>dataset path</b> to the location of training images split into different folders

```python
ptf.Default(dataset_path="./monk/dataset/train", model_name="resnet18", freeze_base_network=True, num_epochs=2)
```

### Select CNN Model
- Update <b>model_name</b> from available list of architectures

```python
ptf.Default(dataset_path="./monk/dataset/train", model_name="resnet18", freeze_base_network=True, num_epochs=2)
```
?> **Tip** To list available models run `ptf.List_Models()`

### Set Number of Epochs
- Update <b>num_epochs</b> to desired value.

```python
ptf.Default(dataset_path="./monk/dataset/train", model_name="resnet18", freeze_base_network=True, num_epochs=2)
```

### Run training
```python
ptf.Train()
```

### Run evaluation
- Set mode <b>eval_infer</b> to True
```python
ptf.Prototype("sample-project-1", "sample-experiment-1", eval_infer=True);
```

- Update <b>dataset_path</b> to the validation folder
```python
ptf.Dataset_Params(dataset_path="./monk/datasets/val");
ptf.Dataset();
accuracy, class_based_accuracy = ptf.Evaluate();
```

### Run inference on single or batch of images
- Set mode <b>eval_infer</b> to True
```python
ptf.Prototype("sample-project-1", "sample-experiment-1", eval_infer=True);
```

- On single images
```python
img_name = "./monk/datasets/test/0.jpg";
predictions = ptf.Infer(img_name=img_name, return_raw=True);
print(predictions)
```

- On batch of images
- Update <b>img_dir</b> to the Test folder
```python
output = ptf.Infer(img_dir="./monk/datasets/test/", return_raw=True)
print(output[0:10])
```