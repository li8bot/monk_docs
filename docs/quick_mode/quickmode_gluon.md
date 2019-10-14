## Quick Mode -- Gluon

### Import Monk library
- Place <b>monk</b> inside your project folder

```python
import os
import sys
sys.path.append("./monk/");
import psutil
from gluon_prototype import prototype
```

### Create Workspace and Experiment
?> **Info** Rename `sample-project` and `sample-experiment`
```python
gtf = prototype(verbose=1);
gtf.Prototype("sample-project", "sample-experiment");
```

### Load Dataset 
- Update <b>dataset path</b> to the location of training images split into different folders

```python
gtf.Default(dataset_path="./monk/dataset/train", model_name="resnet18", freeze_base_network=True, num_epochs=2)
```

### Select CNN Model
- Update <b>model_name</b> from available list of architectures

```python
gtf.Default(dataset_path="./monk/dataset/train", model_name="resnet18", freeze_base_network=True, num_epochs=2)
```
?> **Tip** To list available models run `gtf.List_Models()`

### Set Number of Epochs
- Update <b>num_epochs</b> to desired value.

```python
gtf.Default(dataset_path="./monk/dataset/train", model_name="resnet18", freeze_base_network=True, num_epochs=2)
```

### Run training
```python
gtf.Train()
```