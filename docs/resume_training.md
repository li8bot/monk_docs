## Resume Training

- Create a Training experiment

```python
import os
import sys
sys.path.append("./monk/");
import psutil

from pytorch_prototype import prototype

ptf = prototype(verbose=1);
ptf.Prototype("sample-project-1", "sample-experiment-1");


ptf.Default(dataset_path="./monk/datasets/train", model_name="resnet18", freeze_base_network=True, num_epochs=10);

ptf.Train();
```


### Interrupt and Resume training

- Update <b>resume_train</b> to "True" to resume training from the last trained epoch

```python
ptf = prototype(verbose=1);
ptf.Prototype("sample-project-1", "sample-experiment-1", resume_train=True);
ptf.Train()
```