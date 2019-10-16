## Copy Experiment

- For cases where you want to copy a previous experiment with a few tweaks to test marginal changes

    - Create an experiment

    ```python
    import os
    import sys
    sys.path.append("./monk/");
    import psutil

    from pytorch_prototype import prototype

    ptf = prototype(verbose=1);
    ptf.Prototype("sample-project-1", "sample-experiment-1");
    ptf.Default(dataset_path="./monk/datasets/train", model_name="resnet18", freeze_base_network=True, num_epochs=2);
    ptf.Train()
    ```

    - Create a new experiment and set <b>copy_from</b> while initialising the prototype class

    ```python
    ptf = prototype(verbose=1);
    ptf.Prototype("sample-project-1", "sample-experiment-2", copy_from=["sample-project-1", "sample-experiment-1"]);
    ```
 
    - Reset Transforms if required

    ```python
    ptf.reset_transforms();
    ptf.reset_transforms(test=True);
    ```

    - Apply new transforms

    ```python
    ptf.apply_random_horizontal_flip(train=True, val=True);
    ptf.apply_normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225], train=True, val=True, test=True);
    ```

    - Update number of epochs, optimisers, lr_schedulers.

    ```python
    ptf.update_num_epochs(3);
    ptf.optimizer_adam(0.001);
    ```
    
    !> **Reload function** After adding any updates run `ptf.Reload()`

    - Retrain

    ```python
    ptf.Train()
    ```
