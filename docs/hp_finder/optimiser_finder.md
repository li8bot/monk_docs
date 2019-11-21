## Optimiser Finder

!> **Important** Before running any finder create a new experiment. [Quick_Mode](quick_mode/quickmode_gluon.md)

- Set analysis Project Name
```python
analysis_name = "Optimiser_Finder";
```

- Select Optimisers to analyse
```python    
optimizers = ["sgd", "adam", "adamax", "rmsprop"];   #Model name, learning rate
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
ptf.Analyse_Optimizers(analysis_name, optimizers, percent_data, num_epochs=epochs, state="keep_none"); 
```

- After the analysis is complete we recieve an output as follows:

```
| Experiment Name   |   Train Acc |   Val Acc |   Train Loss |   Val Loss |
|-------------------+-------------+-----------+--------------+------------|
| Optimizer_sgd     |    0.903079 |  0.904236 |     0.424674 |   0.344579 |
| Optimizer_adam    |    0.941163 |  0.939227 |     0.254955 |   0.351743 |
| Optimizer_adamax  |    0.926796 |  0.930939 |     0.234237 |   0.209012 |
| Optimizer_rmsprop |    0.862258 |  0.696133 |     1.10542  |   4.43701  |
```

- Select the best performing optimiser and update the experiment

```python
## Update Optimiser
ptf.optimizer_adamax(0.001);
ptf.Reload();
```

- Continue training the model
```python
ptf.Train()
```