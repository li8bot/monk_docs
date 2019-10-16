## Update Transforms

!> **Important** After adding any update run `ptf.Reload()`

- Reset Transforms

```python
ptf.reset_transforms();
```

- Apply new Transforms

```python
ptf.apply_random_horizontal_flip(train=True, val=True)
ptf.apply_normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225], train=True, val=True, test=True)
```

?> **Tip** List Available Transforms using `ptf.List_Transforms()`

!> **Important** To understand how to utilise <b>transforms</b> in your project check [Expert_Mode](expert_mode.md)