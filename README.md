# Free Tensorflow Course from Udacity
These are the exercises and notes taken during Udacity's free Tensorflow Course.

# Preparation

## Install scripts

**Prerequisites**: Python3, pip3, virtualenv are already installed.

1. `CreateMachineLearningVirtualEnv.sh`: create virtual environment in folder MachineLearningVirtualEnv
2. `InstallMachineLearningAppsInVirtualEnv.sh`: installed required pip packages. Must be run in the virtual environment
3. `StartMachineLearningVirtualEnv.sh`: start the virtual environment.

### Quit from virtual environment

```Bash
deactivate
```

### Start Jupyter

```Bash
jupyter notebook
```

## Install Tensorflow from scratch

I was using Ubuntu 18.04.

### Python3, pip3

```Bash
sudo apt-get update && sudo apt-get upgrade && sudo apt-get dist-upgrade
sudo apt-get install python3-dev python3-pip
sudo pip3 install -U virtualenv
```

### Create virtual environment in `./venv`

#### The --system-site-packages Option

If you build with `virtualenv --system-site-packages ENV`, **your virtual environment will inherit packages from /usr/lib/python2.7/site-packages (or wherever your global site-packages directory is).**

This can be used if you have control over the global site-packages directory, and you want to depend on the packages there. **If you want isolation from the global system, do not use this flag.**

If you need to change this option after creating a virtual environment, you can add (to turn off) or remove (to turn on) the file no-global-site-packages.txt from lib/python3.7/ or equivalent in the environments directory.

More: https://virtualenv.pypa.io/en/latest/userguide/#the-system-site-packages-option

#### The command

Create a new virtual environment by choosing a Python interpreter and making a ./venv directory to hold it:

##### With system-wide package usage

```Bash
virtualenv --system-site-packages -p python3 ./venv
```

##### Without system-wide package usage - better option in my opinion

```Bash
virtualenv -p python3 ./venv
```

### Activate virtual environment

```Bash
source ./venv/bin/activate
```

When virtualenv is active, your shell prompt is prefixed with (venv).

Install packages within a virtual environment without affecting the host system setup. Start by upgrading pip:

### Upgrade pip

```Bash
pip install --upgrade pip
```

### List packages installed within virtual environment

```Bash
pip list 
```

### Exit the virtual environment

```Bash
deactivate
```

## Install Tensorflow

```Bash
pip install --upgrade tensorflow
```

## Prepare Jupyter notebook in virtual environment

This assumes Jupyter notebook is already installed in the system.

### Create new virtual environment

#### Option 1: system-wide package usage

```Bash
virtualenv --system-site-packages -p python3 ./projectname
source projectname/bin/activate
```

#### Option 2: package usage only in the virtual environment

```Bash
virtualenv -p python3 ./projectname
source projectname/bin/activate
```

### Deactivate virtual environment

```Bash
deactivate
```

### Install Jupyter, ipykernel and numpy in virtual environment, and starting Jupyter notebook

Inside the virtual environment:

```Bash
pip install ipykernel
pip install numpy
pip install jupyter 
ipython kernel install --user --name=projectname
jupyter notebook
```

# Notes

## Useful Terms

* **Feature**: The input(s) to our model
* **Examples**: An input/output pair used for training
* **Labels**: The output of the model
* **Layer**: A collection of nodes connected together within a neural network.
* **Model**: The representation of your neural network
* **Dense and Fully Connected (FC)**: Each node in one layer is connected to each node in the previous layer.
* **Weights and biases**: The internal variables of model
* **Loss**: The discrepancy between the desired output and the actual output
* **MSE**: Mean squared error, a type of loss function that counts a small number of large discrepancies as worse than a large number of small ones.
* **Gradient Descent**: An algorithm the internal variables a bit at a time to gradually reduce the loss function.
* **Optimizer**: A specific implementation of the gradient descent algorithm. (There are many algorithms for this. In this course we will only use the “Adam” Optimizer, which stands for ADAptive with Momentum. It is considered the best-practice optimizer.)
* **Learning rate**: The “step size” for loss improvement during gradient descent.
* **Batch**: The set of examples used during training of the neural network
* **Epoch**: A full pass over the entire training dataset
* **Forward pass**: The computation of output values from input
* **Backward pass (backpropagation)**: The calculation of internal variable adjustments according to the optimizer algorithm, starting from the output layer and working back through each layer to the input.
* **Flattening**: The process of converting a 2d image into 1d vector
* **ReLU**: An activation function that allows a model to solve nonlinear problems
* **Softmax**: A function that provides probabilities for each possible output class
* **Classification**: A machine learning model used for distinguishing among two or more output categories
* **Training Set**: The data used for training the neural network.
* **Test set**: The data used for testing the final performance of our neural network.
