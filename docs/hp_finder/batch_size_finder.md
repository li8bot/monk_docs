## Batch Size Finder

!> **Important** Before running any finder create a new experiment. [Quick_Mode](quick_mode/quickmode_gluon.md)

- Set analysis Project Name
```python
analysis_name = "Batch_Size_Finder";
```

- Select Batch sizes to analyse
```python    
batch_sizes = [4, 8, 16, 32]; 
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
ptf.Analyse_Batch_Sizes(analysis_name, batch_sizes, percent_data, num_epochs=epochs, state="keep_none"); 
```

- After the analysis is complete we recieve an output as follows:

```
| Experiment Name   |   Train Acc |   Val Acc |   Train Loss |   Val Loss |
|-------------------+-------------+-----------+--------------+------------|
| Batch_Size_4      |    0.906043 |  0.930018 |     0.388635 |   0.231245 |
| Batch_Size_8      |    0.934778 |  0.943831 |     0.269827 |   0.214775 |
| Batch_Size_16     |    0.948005 |  0.870166 |     0.284627 |   0.401425 |
| Batch_Size_32     |    0.937742 |  0.906998 |     0.380841 |   0.451596 |
```

- Select the best performing batch size and update the experiment

```python
## Update Batch Size
ptf.update_batch_size(8);
ptf.Reload();
```

- Continue training the model
```python
ptf.Train()
```
