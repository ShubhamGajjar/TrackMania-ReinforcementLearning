# Trackmania AI: Training an Agent to Dominate the Track

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the code for a reinforcement learning project focused on training an AI agent to drive in Trackmania Nations Forever.

## Project Overview

The goal of this project is to develop an intelligent agent that can learn to navigate and race effectively in Trackmania. We utilize the power of deep reinforcement learning, specifically the Implicit Quantile Network (IQN) algorithm, to train an agent that can master the complex control and decision-making required for success in this challenging racing game.

**Key Features:**

* **IQN Agent:** Employs the IQN algorithm to estimate the distribution of action-values, enabling more robust and efficient learning.
* **Image and Numerical State Representation:** Utilizes both image data (captured with dxcam) and numerical game state features to provide a comprehensive understanding of the game environment to the agent.
* **Custom Reward Function:**  Designed to encourage fast lap times, smooth driving, and track completion while penalizing collisions and off-track behavior.
* **Integration with TMInterface:** Leverages TMInterface for seamless communication between the Python agent and Trackmania Nations Forever, allowing real-time data exchange and control input.

## Getting Started

### Prerequisites:

- **Hardware:**
    - Nvidia GPU (required for dxcam screen capture) 
- **Software:**
    - Trackmania Nations Forever: [https://nadeo-download.cdn.ubi.com/trackmaniaforever/tmnationsforever_setup.exe](https://nadeo-download.cdn.ubi.com/trackmaniaforever/tmnationsforever_setup.exe)
    - TMInterface (version <= 1.4.3): [https://donadigo.com/files/TMInterface/TMInterface_1.4.3_Setup.exe](https://donadigo.com/files/TMInterface/TMInterface_1.4.3_Setup.exe)
    - Python (version = 3.10): [https://www.python.org/downloads/release/python-3100/](https://www.python.org/downloads/release/python-3100/)
    - CUDA Toolkit 11.8: [https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local](https://developer.nvidia.com/cuda-11-8-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local)
    - PyTorch version 2 with CUDA 11.8 

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/ShubhamGajjar/TrackMania-ReinforcementLearning.git
   ```

## Logo
![Logo](https://github.com/user-attachments/assets/846ba420-4b3e-40f6-acac-15138404fe36)
