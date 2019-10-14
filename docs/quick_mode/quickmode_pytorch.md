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