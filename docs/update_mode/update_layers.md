## Update Layers

!> **Important** After adding any update run `ptf.Reload()`

- Add layers and activations to model for Transfer Learning

```python
ptf.append_dropout(probability=0.1);
ptf.append_linear(final_layer=True);
```

?> **Tip** To list available layers use `ptf.List_Layers()`

?> **Tip** To list available activation functions use `ptf.List_Activations()`
