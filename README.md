# Trackmania AI - Reinforcement Learning Agent

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains code for training a reinforcement learning (RL) agent to drive autonomously in Trackmania Nations Forever. The agent learns to race on a track by interacting with the game environment, receiving rewards for good driving behavior, and improving its strategy over time.

## Project Highlights

* **AI Driver:** The agent is trained using an advanced reinforcement learning algorithm called Implicit Quantile Networks (IQN). 
* **Realistic Gameplay:** The agent interacts with Trackmania Nations Forever using TMInterface, a tool that allows external programs to communicate with the game.
* **Vision-Based Control:** The agent uses real-time screen captures (with dxcam) and game data to make driving decisions.

## Prerequisites

Before you get started, ensure you have the following prerequisites:

### Hardware:

* 24 Gigs RAM
* Nvidia GPU (required for screen capture)

### Software:

* Trackmania Nations Forever: [Download](https://nadeo-download.cdn.ubi.com/trackmaniaforever/tmnationsforever_setup.exe)
* TMInterface (version <= 1.4.3): [Download](https://donadigo.com/files/TMInterface/TMInterface_1.4.3_Setup.exe)
* Python (version = 3.10): [Download](https://www.python.org/downloads/release/python-3100/)
* CUDA Toolkit 11.8: [Download](https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local)
* PyTorch version 2 with CUDA 11.8

## Installation

**Clone Repository:**
```bash
git clone https://github.com/ShubhamGajjar/TrackMania-ReinforcementLearning.git
```

## To set up the project, follow these steps in Terminal:

1. Open Terminal with Administrative privileges at the root folder
2. Execute: `get-ExecutionPolicy` (run the next step if the output is Restricted)
3. Execute: `Set-ExecutionPolicy Unrestricted` (run as admin)
4. Create a virtual environment: `python -m venv myenv`
5. Activate the virtual environment: `myenv\Scripts\activate`
6. Verify the CUDA version: `nvidia-smi`
7. Install PyTorch with CUDA support: `pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118`
8. Install project dependencies: `pip install -r requirements.txt`
9. Install the project: `python setup.py install --user`

## Getting Started

### Generating "Virtual Checkpoints" for Your Map

To begin a run, follow these steps:

1. Open Trackmania using TMInterface
2. Use `\`` to open and close the console
3. Run the script to generate "virtual checkpoints" for your map: `python ./scripts/observe_manual_run_to_extract_checkpoints.py`.
    - In Trackmania: Editor > New Track/Load Track > edit track
4. Play through the map, staying near the centerline of the road.
5. Stop the script by closing the console: `observe_manual_run_to_extract_checkpoints.py`.
6. Save the map while in the game. The script will save a file in `./maps/map.npy` containing the coordinates of "virtual checkpoints" spaced approximately 10 meters apart.

### Starting Training

1. Open your track and start the test
2. Edit the location of the `map.npy` file at the top of `./scripts/train.py`, specifically at line `zone_centers = np.load(...)`.
3. Open Trackmania Interface and load the map you wish to train on, setting the game resolution to 640x480.
4. Copy the `trackmania_rl` folder to `scripts`.
5. Run the training script: `python ./scripts/train.py`.
6. Monitor training performance via the TensorBoard interface.
7. Be patient; training may take a significant amount of time.


## Logo
![Logo](https://github.com/user-attachments/assets/846ba420-4b3e-40f6-acac-15138404fe36)
