# Value Based Methods Navigation Project

# Project Details
For this project, you will train an agent to navigate (and collect bananas!) in a large, square world.
An implementation of a Deep Q-Network (DQN) was trained to solve the environment.


The simulation contains a single agent that navigates a large environment.  At each time step, it has four actions at its disposal:
- `0` - walk forward 
- `1` - walk backward
- `2` - turn left
- `3` - turn right

The state space has `37` dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.
A reward of `+1` is provided for collecting a yellow banana, and a reward of `-1` is provided for collecting a blue banana.

# Getting Started
This tutorial details the installation and configuration of the project using local GPU training with NVIDIA GPUs and the NVIDIA CUDA toolkit on a Windows 11 PC

![Local GPU Training](https://github.com/mindcriminal/Udacity_RL_Nanodegree_Projects/blob/main/Value_Based_Methods_Navigation/GPU_Screenshot.png)

* Install the Anaconda Python distribution which can be found [here](https://www.anaconda.com/)

* Launch Anaconda Prompt (anaconda3) by searching for it in the Start Menu

* Create a new environment setting the Python version to 3.7.  This enables compatibility with dependancies that will be installed later as well as recent versions of CUDA (e.g., v11.6) which enables offline training with a local and current NVIDIA GPU (e.g., RTX 3060)
```bash
conda create -n rl37_anaconda python=3.7
conda activate rl37_anaconda 
```
* Install Torch and CUDA
```bash
conda install pytorch==1.12.1 torchvision==0.13.1 torchaudio==0.12.1 cudatoolkit=11.6 -c pytorch -c conda-forge
```
* Install the dependencies under the python folder (copied from Udacity's 'Value-based-methods-main' Github repo with some modification to requirements.txt)
```bash
cd python
pip install .
```
* Download the Windows based Unity Environment and extract into the root of repo
[Windows (64 bit)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

* Install Jupyter kernel for environment
```bash
python -m ipykernel install --user --name rl37_anaconda
```
* Launch Jupyterlab, change the kernel (Kernel --> Change Kernel -> rl37_anaconda) and run the entire notebook. The agent will be trained and once the environment is solved the model will be saved as a checkpoint file. Be sure the path to the Unity Environment is correct.
```bash
jupyter-lab
```
