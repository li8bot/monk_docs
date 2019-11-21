## Input Dimension Finder

!> **Important** Before running any finder create a new experiment. [Quick_Mode](quick_mode/quickmode_gluon.md)

- Set analysis Project Name
```python
analysis_name = "Input_Size_Finder";
```

- Select input shapes to analyse
```python    
input_sizes = [224, 256, 512];
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
ptf.Analyse_Input_Sizes(analysis_name, input_sizes, percent_data, num_epochs=epochs, state="keep_none"); 
```

- After the analysis is complete we recieve an output as follows:

```
| Experiment Name   |   Train Acc |   Val Acc |   Train Loss |   Val Loss |
|-------------------+-------------+-----------+--------------+------------|
| Input_Size_224    |    0.903991 |  0.91989  |     0.418979 |   0.316026 |
| Input_Size_256    |    0.904903 |  0.899632 |     0.414027 |   0.364695 |
| Input_Size_512    |    0.905359 |  0.905157 |     0.418753 |   0.354991 |
```

- Select the best performing input shape and update the experiment

```python
## Update Input Size
ptf.update_input_size(224);
ptf.Reload();
```

- Continue training the model
```python
ptf.Train()
```