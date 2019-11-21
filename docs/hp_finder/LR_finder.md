## Learning Rate Finder

!> **Important** Before running any finder create a new experiment. [Quick_Mode](quick_mode/quickmode_gluon.md)

- Set analysis Project Name
```python
analysis_name = "Learning_Rate_Finder"
```

- Select LR to analyse
```python    
lrs = [0.01, 0.005, 0.001, 0.0001]; 
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
ptf.Analyse_Learning_Rates(analysis_name, lrs, percent_data, num_epochs=epochs, state="keep_none"); 
```

- After the analysis is complete we recieve an output as follows:

```
| Experiment Name      |   Train Acc |   Val Acc |   Train Loss |   Val Loss |
|----------------------+-------------+-----------+--------------+------------|
| Learning_Rate_0.01   |    0.90764  |  0.895028 |     0.411713 |   0.362229 |
| Learning_Rate_0.005  |    0.877537 |  0.901473 |     0.611189 |   0.442408 |
| Learning_Rate_0.001  |    0.690992 |  0.746777 |     1.58159  |   1.326    |
| Learning_Rate_0.0001 |    0.266363 |  0.299263 |     3.00295  |   2.90935  |
```

- Select the best LR and update the experiment

```python
## Update Learning Rate
ptf.update_learning_rate(0.01);
ptf.Reload();
```

- Continue training the model
```python
ptf.Train()
```