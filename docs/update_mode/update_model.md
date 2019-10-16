## Update Model Parameters

!> **Important** After adding any update run `ptf.Reload()`

- Update the CNN architecture

```python
ptf.update_model_name("resnet50");
```

?> **Tip** To list available models use `ptf.List_Models()`

- Enable/Disable GPU usage based on availability

```python
ptf.update_use_gpu(True);
```

- Select pretrained network or Train selected architecture from scratch

```python
ptf.update_use_pretrained(True);
```

- Freeze layers in the selected pretrained CNN and set number of layers to freeze

```python
ptf.update_freeze_base_network(True);
ptf.update_freeze_layers(10);
```

