# Trackmania AI - Reinforcement Learning Agent

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains code for training a reinforcement learning (RL) agent to drive autonomously in Trackmania Nations Forever. The agent learns to race on a track by interacting with the game environment, receiving rewards for good driving behavior, and improving its strategy over time.

## Project Highlights

* **AI Driver:** The agent is trained using an advanced reinforcement learning algorithm called Implicit Quantile Networks (IQN). 
* **Realistic Gameplay:** The agent interacts with Trackmania Nations Forever using TMInterface, a tool that allows external programs to communicate with the game.
* **Vision-Based Control:** The agent uses real-time screen captures (with dxcam) and game data to make driving decisions.

## Getting Started
Before you get started, ensure you have the following prerequisites:

-Nvidia GPU
-Trackmania Nations Forever
(https://nadeo-download.cdn.ubi.com/trackmaniaforever/tmnationsforever_setup.exe)
-TMInterface version <= 1.4.3
(https://donadigo.com/files/TMInterface/TMInterface_1.4.3_Setup.exe)
-Python version = 3.10
(https://www.python.org/downloads/release/python-3100/)
-Make Sure to have CUDA Toolkit 11.8
(https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local)
-PyTorch version 2 with CUDA 11.8
-Open Terminal with Admin at the root folder 

### Prerequisites

**Hardware:**

* Nvidia GPU (required for screen capture)

**Software:**

* Trackmania Nations Forever: [https://nadeo-download.cdn.ubi.com/trackmaniaforever/tmnationsforever_setup.exe](https://nadeo-download.cdn.ubi.com/trackmaniaforever/tmnationsforever_setup.exe)
* TMInterface (version <= 1.4.3): [https://donadigo.com/files/TMInterface/TMInterface_1.4.3_Setup.exe](https://donadigo.com/files/TMInterface/TMInterface_1.4.3_Setup.exe)
* Python (version = 3.10): [https://www.python.org/downloads/release/python-3100/](https://www.python.org/downloads/release/python-3100/)
* CUDA Toolkit 11.8: [https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local](https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local)
* PyTorch version 2 with CUDA 11.8

### Installation

1. **Clone Repository:**
   ```bash
   git clone https://github.com/ShubhamGajjar/TrackMania-ReinforcementLearning.git
   ```

2. **Administrator Terminal:**
* Open a terminal with Administrator privileges in the cloned repository's root folder.



## Logo
![Logo](https://github.com/user-attachments/assets/846ba420-4b3e-40f6-acac-15138404fe36)
