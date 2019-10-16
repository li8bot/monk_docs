## Switch Mode

<p>This mode is to test pretrained models before carrying out training</p>

- Import library

```python
import os
import sys
sys.path.append("./monk/");
import psutil
from pytorch_prototype import prototype
```

- Create experiment

```python
ptf = prototype(verbose=1);
ptf.Prototype("sample-project-1", "sample-experiment-1");
ptf.Default(dataset_path="./monk/datasets/train", model_name="resnet18", freeze_base_network=True, num_epochs=2);
```
- Switch To Eval Mode

```python
ptf.Switch_Mode(eval_infer=True)
```

- Evaluate on validation dataset

```python
ptf.Dataset_Params(dataset_path="./monk/datasets/val");
ptf.Dataset();
accuracy, class_based_accuracy = ptf.Evaluate();
```

- After getting vanilla model metrics switch To Train Mode

```python
ptf.Switch_Mode(train=True)
```

- Run Training

```python
ptf.update_dataset(dataset_path=["./monk/datasets/train", "./monk/datasets/val"]);
ptf.Dataset(); #Can also use ptf.Reload() here
ptf.Train();
```

- After finishing the training switch back to evaluation mode

```python
ptf.Switch_Mode(eval_infer=True)
```

- Evaluate the trained model on validation dataset

```python
ptf.Dataset_Params(dataset_path="../../../monk/system_check_tests/datasets/val");
ptf.Dataset();
accuracy, class_based_accuracy = ptf.Evaluate();
```

## To Load and Test with custom model

<p>To carry out vanilla test on the current dataset with model trained in some previous experiment. </p>

!> **Important** Following steps are run after library import and creating experiment

- Reset Model

```python
ptf.reset_model();
```
- Load model from external path

```python
ptf.update_model_path("workspace/sample-project-1/sample-experiment-1/output/models/best_model");
```
- Run reload

```python
ptf.Reload();
```
