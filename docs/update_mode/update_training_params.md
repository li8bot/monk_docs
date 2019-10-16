## Update Training Parameters

!> **Important** After adding any update run `ptf.Reload()`

- Update the number of Epochs

```python
ptf.update_num_epochs(5)
```

- To get metrics during an epoch enable realtime progress display

```python
ptf.update_display_progress_realtime(False)
```

- To enable/disable progress display

```python
ptf.update_display_progress(True)
```

- To save intermediate models after every epoch

```python
ptf.update_save_intermediate_models(False); 
```

- To save logs about your experiment. Required to generate comparison.

```python
ptf.update_save_training_logs(True)
```


