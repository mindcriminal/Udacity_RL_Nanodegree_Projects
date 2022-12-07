[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/43851646-d899bf20-9b00-11e8-858c-29b5c2c94ccc.png "Crawler"


# Policy Based Methods Continuous Control Project

# Introduction

For this project, you will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.

![Trained Agent][image1]

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1. 

# Solving The Environment

The task is episodic, and in order to solve the environment,  your agent must get an average score of +30 over 100 consecutive episodes.

# Getting Started
This tutorial details the installation and configuration of the project using local GPU training with NVIDIA GPUs and the NVIDIA CUDA toolkit on a Windows 11 PC

* Install the Anaconda Python distribution which can be found [here](https://www.anaconda.com/)

* Launch Anaconda Prompt (anaconda3) by searching for it in the Start Menu

* Create a new environment setting the Python version to 3.7.  This enables compatibility with dependancies that will be installed later as well as recent versions of CUDA (e.g., v11.6) which enables offline training with a local and current NVIDIA GPU (e.g., RTX 3060)
```bash
conda create -n rl37_anaconda python=3.7
conda activate rl37_anaconda 
```
* Install Visdom (for training monitoring), Torch, and CUDA
```bash
conda install visdom pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.6 -c pytorch -c conda-forge
```
* Install the dependencies under the python folder (copied from Udacity's 'Value-based-methods-main' Github repo with some modification to requirements.txt)
```bash
cd python
pip install .
```
* Download the Windows based Unity Environment and extract into the root of the repo
[Windows (64 bit)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

* Install Jupyter kernel for environment
```bash
python -m ipykernel install --user --name rl37_anaconda
```
* Launch Jupyterlab, change the kernel (Kernel --> Change Kernel -> rl37_anaconda) and run the entire notebook. The agent will be trained and once the environment is solved the model will be saved as a checkpoint file. Be sure the path to the Unity Environment is correct.
```bash
jupyter-lab
```
* Launch Visdom From Your Anaconda Prompt and once the server is up point your web browser to http://localhost:8097. As the training progresses you will see the plots updating.
```bash
python -m visdom.server
```

![Visdom Screenshot](https://github.com/mindcriminal/Udacity_RL_Nanodegree_Projects/blob/main/Policy_Based_Methods_Continuous_Control/visdom_solved.png)
