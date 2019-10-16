## Update Dataset Params

!> **Important** After adding any update run `ptf.Reload()`

- Update Input data dimensions
```python
ptf.update_input_size(256);
```

- Update Batch Size
```python
ptf.update_batch_size(6);
```

- Enable Shuffle Data
```python
ptf.update_shuffle_data(True);
```

- Update CPU processors in use
```python
ptf.update_num_processors(psutil.cpu_count());
```

- Update Train/Val split
```python
ptf.update_trainval_split(0.6);
```

- Update the dataset path
```python
ptf.update_dataset(dataset_path=["./monk/datasets2/train", "./monk/datasets2/eval"]);
```