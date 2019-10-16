## Compare Experiment

<p> After creating multiple experiments there comes a stage when you want to compare and find out which experiment was the best, experiments that faced over or underfitting and which loss functions saturated before others.
Visualise accuracy plot with easy to use compare function</p>

- The following plots are generated
    - Training loss and accuracy
    - Validation loss and accuracy
    - GPU usage
    - Training time

- Import Library

```python
import os
import sys
sys.path.append("./monk/");
import psutil
from compare_prototype import compare
```

- Initialise Compare object

```python
ctf = compare(verbose=1);
ctf.Comparison("Sample-Comparison-1");
```

- Add the experiments you wish to compare

```python
ctf.Add_Experiment("sample-project-1", "sample-experiment-1");
ctf.Add_Experiment("sample-project-1", "sample-experiment-2");
ctf.Add_Experiment("sample-project-1", "sample-experiment-3");
ctf.Add_Experiment("sample-project-1", "sample-experiment-4");
ctf.Add_Experiment("sample-project-1", "sample-experiment-5");
ctf.Add_Experiment("sample-project-1", "sample-experiment-6");
```

- Generate Stats

```python
ctf.Generate_Statistics();
```