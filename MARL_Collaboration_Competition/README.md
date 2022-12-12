[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135623-e770e354-7d12-11e8-998d-29fc74429ca2.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/42135622-e55fb586-7d12-11e8-8a54-3c31da15a90a.gif "Soccer"


# Collaboration and Competition Project

# Introduction

For this project, you will work with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

![Trained Agent][image1]

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1.  If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01.  Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation.  Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 
# Solving The Environment

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.
- This yields a single **score** for each episode.

The environment is considered solved, when the average (over 100 episodes) of those **scores** is at least +0.5.

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
[Windows (64 bit)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)

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
