## Auxillary Functions


- Get a summary of current experiment

```python
ptf.Summary()
```

- EDA - Find Num images per class

```python
ptf.EDA(show_img=True, save_img=True);
```

- EDA - Find Missing and corrupted images

```python
ptf.EDA(check_missing=True, check_corrupt=True);
```


- Estimate Training Time

```python
ptf.Estimate_Train_Time(num_epochs=50);
```