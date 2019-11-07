# Monk
#### Monk is an open source framework for finetuning Deep Neural Networks using Transfer Learning
[![Version](https://img.shields.io/badge/version-v1.0-lightgrey)](https://github.com/abhi-kumar/monk_v1) &nbsp; &nbsp;
[![Build_Status](https://img.shields.io/badge/build-passing-green)](https://github.com/abhi-kumar/monk_v1)


## Create an image classification experiment.
- Load foldered dataset
- Set number of epochs
- Run training


<pre style="color:#000000;background:#f1f0f0;">ptf <span style="color:#806030; ">=</span> prototype<span style="color:#806030; ">(</span>verbose<span style="color:#806030; ">=</span><span style="color:#c00000; ">1</span><span style="color:#806030; ">)</span>
ptf<span style="color:#806030; ">.</span>Prototype<span style="color:#806030; ">(</span><span style="color:#800000; ">"</span><span style="color:#e60000; ">sample-project-1</span><span style="color:#800000; ">"</span><span style="color:#806030; ">,</span> <span style="color:#800000; ">"</span><span style="color:#e60000; ">sample-experiment-1</span><span style="color:#800000; ">"</span><span style="color:#806030; ">)</span>
ptf<span style="color:#806030; ">.</span>Default<span style="color:#806030; ">(</span>dataset_path<span style="color:#806030; ">=</span><span style="color:#800000; ">"</span><span style="color:#e60000; ">./dataset_cats_dogs_train/</span><span style="color:#800000; ">"</span><span style="color:#806030; ">,</span> 
    			model_name<span style="color:#806030; ">=</span><span style="color:#800000; ">"</span><span style="color:#e60000; ">resnet18</span><span style="color:#800000; ">"</span><span style="color:#806030; ">,</span> freeze_base_network<span style="color:#806030; ">=</span>True<span style="color:#806030; ">,</span> num_epochs<span style="color:#806030; ">=</span><span style="color:#c00000; ">2</span><span style="color:#806030; ">)</span>
ptf<span style="color:#806030; ">.</span>Train<span style="color:#806030; ">(</span><span style="color:#806030; ">)</span>
</pre>

## Inference



## Compare Experiments

- Add created experiments with different hyperparameters
- Generate comparison plots

<pre style="color:#000000;background:#f1f0f0;">ctf <span style="color:#806030; ">=</span> compare<span style="color:#806030; ">(</span>verbose<span style="color:#806030; ">=</span><span style="color:#c00000; ">1</span><span style="color:#806030; ">)</span><span style="color:#806030; ">;</span>
ctf<span style="color:#806030; ">.</span>Comparison<span style="color:#806030; ">(</span><span style="color:#800000; ">"</span><span style="color:#e60000; ">Sample-Comparison-1</span><span style="color:#800000; ">"</span><span style="color:#806030; ">)</span><span style="color:#806030; ">;</span>
ctf<span style="color:#806030; ">.</span>Add_Experiment<span style="color:#806030; ">(</span><span style="color:#800000; ">"</span><span style="color:#e60000; ">sample-project-1</span><span style="color:#800000; ">"</span><span style="color:#806030; ">,</span> <span style="color:#800000; ">"</span><span style="color:#e60000; ">sample-experiment-1</span><span style="color:#800000; ">"</span><span style="color:#806030; ">)</span><span style="color:#806030; ">;</span>
ctf<span style="color:#806030; ">.</span>Add_Experiment<span style="color:#806030; ">(</span><span style="color:#800000; ">"</span><span style="color:#e60000; ">sample-project-1</span><span style="color:#800000; ">"</span><span style="color:#806030; ">,</span> <span style="color:#800000; ">"</span><span style="color:#e60000; ">sample-experiment-2</span><span style="color:#800000; ">"</span><span style="color:#806030; ">)</span><span style="color:#806030; ">;</span>
    <span style="color:#806030; ">.</span>
    <span style="color:#806030; ">.</span> 
    <span style="color:#806030; ">.</span>
</pre>




## Features 
- Image Classification
    - Foldered Datasets
    - CSV Datasets


### TODO :
- Add compare experiment graph
- Add code snippets of easy resume, copy, update


