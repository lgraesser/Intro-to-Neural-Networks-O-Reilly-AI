# Introduction to Neural Networks with Keras

Please come with Keras, Theano or Tensorflow, and Matplotlib installed

Instructions for installing the relevant libraries with conda environments or virtualenv are below. These instructions also explain how to download the materials for the tutorial.

If you already have the libraries installed then please clone the repo using the terminal commands below

```shell
# In the terminal create a directory that you want to contain this repo and navigate to it
mkdir <directory_name>
# eg. mkdir NN_tutorial
cd <directory_name>

# Clone the repo
git clone https://github.com/lgraesser/Intro-to-Neural-Networks-O-Reilly-AI.git
cd Intro-to-Neural-Networks-O-Reilly-AI

# Launch jupyter notebook
jupyter notebook
```

## Installation Instructions

The instructions below will help you set up a virtual environment, get all of the scripts and data, and install all of the libraries required for this tutorial. There are two sets of instructions. If you have the Anaconda distribution of Python then follow the instructions "1. Using Anaconda". Otherwise follow the instructions "2. Using virtualenv."
  
#### 1. Using Anaconda
If you have the anaconda distribution of Python (see [here](http://conda.pydata.org/docs/using/envs.html) for more info), then follow the instructions below. 

**Linux/Mac**

```shell
# In the terminal create a directory that you want to contain this repo and navigate to it
mkdir <directory_name>
# eg. mkdir NN_tutorial
cd <directory_name>

# Clone the repo
git clone https://github.com/lgraesser/Intro-to-Neural-Networks-O-Reilly-AI.git
cd Intro-to-Neural-Networks-O-Reilly-AI

# Then, create a virtual environment
conda env create -f environment.yml
# Note: the environment will be named NN_tutorial and will be set up with python 3.5

# Switch into your new environment
source activate NN_tutorial

# Launch jupyter notebook
jupyter notebook

# When you need to exit the environment (at the end of the tutorial for example), type.
source deactivate
```

**Windows**

```shell
# In the terminal create a directory that you want to contain this repo and navigate to it
mkdir <directory_name>
# eg. mkdir NN_tutorial
cd <directory_name>

# Clone the repo
git clone https://github.com/lgraesser/Intro-to-Neural-Networks-O-Reilly-AI.git
cd Intro-to-Neural-Networks-O-Reilly-AI

# Then, create a virtual environment
conda env create -f environment.yml
# Note: the environment will be named NN_tutorial and will be set up with python 3.5

# Switch into your new environment
activate NN_tutorial

# Launch jupyter notebook
jupyter notebook

# When you need to exit the environment (at the end of the tutorial for example), type.
deactivate
```

#### 2. Using virtualenv
To use virtualenv (see [here](http://docs.python-guide.org/en/latest/dev/virtualenvs/) for more info) follow the instructions below.

```shell
# In the terminal, install virtualenv
pip install virtualenv
# Create a directory that you want to contain the repo and navigate to it
mkdir <directory_name>
# eg. mkdir NN_tutorial
cd <directory_name>

# Create a new virtual environment
virtualenv NN_tutorial
# Switch into your new environment
source NN_tutorial/bin/activate

# Clone the repo
git clone https://github.com/lgraesser/Intro-to-Neural-Networks-O-Reilly-AI.git
cd Intro-to-Neural-Networks-O-Reilly-AI

# Install the relevant libraries in your virtual environment
pip install -r requirements.txt

# Launch jupyter notebook
jupyter notebook

# When you need to exit the environment (at the end of the tutorial for example), type.
deactivate
```

### Troubleshooting

#### Import Error: No module named tensorflow

Your version of Keras is using Tensorflow instead of Theano as the backend.

To change the backend to Theano you need to change the settings in the Keras config file.

First check if you have one by navigating to the directory listed below then typing ```ls``` to list the files contained in that directory. The commands are below.

```shell
cd ~/.keras/
ls
```

If there is a file named keras.json then open it by typing  ```open keras.json```  The default configuration looks like this.

```
{
    "image_dim_ordering": "tf",
    "epsilon": 1e-07,
    "floatx": "float32",
    "backend": "tensorflow"
}
```

Change the value of "backend" to "theano" and "image_dim_ordering" to "th". Save and close the file.

    
Alternatively, if there is no keras.json file then create one and open it by typing

```
touch keras.json
open keras.json
```

Then copy the information below into the file and save it.

```
{
    "image_dim_ordering": "th",
    "epsilon": 1e-07,
    "floatx": "float32",
    "backend": "theano"
}
```

#### Keras can be imported in Python but not IPython

If Keras is working in Python but not IPython, this is because the sys.paths of the two are different. Lucy Park has the answer. Follow [her tutorial](https://www.lucypark.kr/blog/2013/02/10/when-python-imports-and-ipython-does-not/) (only a few steps) and this should fix it

## Acknowledgements

Thank you to Nidhin Pattaniyil for his detailed feedback on the setup and installation instructions.
