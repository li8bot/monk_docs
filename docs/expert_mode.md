## Expert Mode

<p>This is comprehensive approach and uses available functions and modules for better transfer learning. The best approach will be to use this as a template and plug the right functions where necessary</p>

- Start by importing the library

```python
import os
import sys
sys.path.append("./monk/");
import psutil
from pytorch_prototype import prototype
```

- Create your experiment

```python
ptf = prototype(verbose=1);
ptf.Prototype("sample-project-1", "sample-experiment-1");
```

- Set dataset parameters and apply Transforms

```python
ptf.Dataset_Params(dataset_path="./monk/datasets/train", split=0.9,input_size=224, batch_size=16, shuffle_data=True, num_processors=3);

# Transform
ptf.apply_random_horizontal_flip(train=True, val=True);
ptf.apply_normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225], train=True, val=True, test=True);

# Set Dataset
ptf.Dataset();
```

- Set Model Params 

```python
ptf.Model_Params(model_name="resnet18", freeze_base_network=True, use_gpu=True, use_pretrained=True);
```

- Apply additional layers to model 

```python
ptf.append_dropout(probability=0.1);
ptf.append_linear(final_layer=True);
```

- Set Model

```python
ptf.Model()
```
- Auxiliary Functions - Freeze Layers

```python
ptf.Freeze_Layers(num=10);
```

- Set Training Params

```python
ptf.Training_Params(num_epochs=2, display_progress=True, display_progress_realtime=True, 
        save_intermediate_models=True, intermediate_model_prefix="intermediate_model_", save_training_logs=True);
```




- Set Optimizer

```python
ptf.optimizer_adam(0.001);
```

- Set Learning rate schedulers

```python
ptf.lr_fixed();
```

- Set Loss

```python
ptf.loss_softmax_crossentropy()
```

- Finally Run Training

```python
ptf.Train();
```