# Installation

## 0) Clone library from github
```console
foo@bar:~$ git clone https://github.com/Tessellate-Imaging/monk_v1
```
## 1) Setup virtual environment

```console
foo@bar:~$ virtualenv -p python3 monk
foo@bar:~$ workon monk
```

## 2) Setup Dependencies

### 2.a) Install dependencies for CPU-only
```bash
foo@bar:~$ cd monk_v1/installation
foo@bar:~$ pip install -r requirements-cpu.txt
```
### 2.b) Install dependencies for systems with GPU
#### For CUDA == 9.0
```bash
foo@bar:~$ cd monk_v1/installation
foo@bar:~$ pip install -r requirements-cu9.txt
```
#### For CUDA == 10.0 (Colab/Kaggle)
```bash
foo@bar:~$ cd monk_v1/installation
foo@bar:~$ pip install -r requirements-cu10.txt
```

#### 2.c) For Tensorflow == 2.0
#### For CUDA == 9.0
```bash
foo@bar:~$ cd monk_v1/installation
foo@bar:~$ pip install -r tensorflow2-cpu.txt
```

#### For CUDA == 10.0
```bash
foo@bar:~$ cd monk_v1/installation
foo@bar:~$ pip install -r tensorflow2_gpu.txt
```

## 3)Install Monk globally
```bash
foo@bar:~$ pip install -e .
```

## Select a Deep Learning frameworks to Quick Start 
<br/>
<span>
<button style="background-color:#AAA"><a class="pytorch" href="#/quick_mode/quickmode_pytorch"><img style="padding-top:10px" src="https://upload.wikimedia.org/wikipedia/commons/9/96/Pytorch_logo.png" width="100px" height="30px"/></a></button>&nbsp; &nbsp;&nbsp; 
<button style="background-color:#AAA"><a class="keras" href="#/quick_mode/quickmode_keras"><img style="padding-top:5px" src="https://s3.amazonaws.com/keras.io/img/keras-logo-2018-large-1200.png" width="100px" height="30px"/></a></button>&nbsp; &nbsp;&nbsp; 
<button style="background-color:#AAA"><a href="#/quick_mode/quickmode_gluon"><img style="padding-top:5px" src="https://gluon.mxnet.io/_static/gluon_white.png" width="100px" height="30px"/></a></button>
</span>
