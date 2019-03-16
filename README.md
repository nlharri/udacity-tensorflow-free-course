# Free Tensorflow Course from Udacity
These are the exercises and notes taken during Udacity's free Tensorflow Course.

# Preparation

## Install Tensorflow
I'm using Ubuntu 18.04

### Python3, pip3

```Bash
sudo apt-get update && sudo apt-get upgrade && sudo apt-get dist-upgrade
sudo apt-get install python3-dev python3-pip
sudo pip3 install -U virtualenv
```

### Create virtual environment in ./venv

#### The --system-site-packages Option

If you build with virtualenv --system-site-packages ENV, your virtual environment will inherit packages from /usr/lib/python2.7/site-packages (or wherever your global site-packages directory is).

This can be used if you have control over the global site-packages directory, and you want to depend on the packages there. If you want isolation from the global system, do not use this flag.

If you need to change this option after creating a virtual environment, you can add (to turn off) or remove (to turn on) the file no-global-site-packages.txt from lib/python3.7/ or equivalent in the environments directory.

More: https://virtualenv.pypa.io/en/latest/userguide/#the-system-site-packages-option

#### The command

Create a new virtual environment by choosing a Python interpreter and making a ./venv directory to hold it:

```Bash
virtualenv --system-site-packages -p python3 ./venv
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

```Bash
virtualenv --system-site-packages -p python3 ./projectname
source projectname/bin/activate
```

### Install ipykernel and numpy in virtual environment
```Bash
pip install ipykernel
pip install numpy
ipython kernel install --user --name=projectname
jupyter notebook
```
