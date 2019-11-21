## Model Finder

!> **Important** Before running any finder create a new experiment. [Quick_Mode](quick_mode/quickmode_gluon.md)

- Set analysis Project Name
```python
analysis_name = "Model_Finder";
```

- Select Models to analyse
    - First element in the list- Model Name
    - Second element in the list - Boolean value to freeze base network or not
    - Third element in the list - Boolean value to use pretrained model as the starting point or not
```python    
models = [["resnet34", True, True], ["resnet50", False, True], 
          ["densenet121", False, True], ["densenet169", True, True], ["densenet201", True, True]];  
```

- Set number of epochs for each experiment
```python
epochs=5;
```

- Percentage of original dataset to take in for experimentation
```python
percent_data=10;
```

- Run analysis
    - "keep_all" - Keep all the sub experiments created
    - "keep_non" - Delete all sub experiments created
```python
ptf.Analyse_Models(analysis_name, models, percent_data, num_epochs=epochs, state="keep_none"); 
```

- After the analysis is complete we recieve an output as follows:

```
| Experiment Name                            |   Train Acc |   Val Acc |   Train Loss |   Val Loss |
|--------------------------------------------+-------------+-----------+--------------+------------|
| Model_resnet34_freeze_base_pretrained      |    0.820525 |  0.891344 |     0.618046 |  0.384872  |
| Model_resnet50_unfreeze_base_pretrained    |    0.964652 |  0.967772 |     0.125821 |  0.152006  |
| Model_densenet121_unfreeze_base_pretrained |    0.963284 |  0.969613 |     0.141027 |  0.0954968 |
| Model_densenet169_freeze_base_pretrained   |    0.875257 |  0.92081  |     0.468529 |  0.255893  |
| Model_densenet201_freeze_base_pretrained   |    0.885975 |  0.91989  |     0.469252 |  0.334477  |
```

- Select the best performing model and update the experiment

```python
## Update Model Architecture
ptf.update_model_name("densenet121");
ptf.update_freeze_base_network(True);
ptf.update_use_pretrained(True);
ptf.Reload();
```

- Continue training the model
```python
ptf.Train()
```