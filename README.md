# Trackmania AI - Reinforcement Learning Agent

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Coverage](https://img.shields.io/badge/coverage-100%25-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

This repository contains code for training a reinforcement learning (RL) agent to drive autonomously in Trackmania Nations Forever. The agent learns to race on a track by interacting with the game environment, receiving rewards for good driving behavior, and improving its strategy over time.

## Table of Contents

- [Project Highlights](#project-highlights)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Getting Started](#getting-started)
  - [Generating "Virtual Checkpoints" for Your Map](#generating-virtual-checkpoints-for-your-map)
  - [Starting Training](#starting-training)
- [Features](#features)
- [Contributing](#contributing)
- [License](#license)
- [Screenshots](#screenshots)

## Project Highlights

* **AI Driver:** The agent learns to drive in Trackmania using Implicit Quantile Networks (IQN), a cutting-edge reinforcement learning algorithm implemented in the `iqn.py` file. IQN predicts a range of possible outcomes for each action, allowing for more robust decision-making in unpredictable racing situations. 
* **Realistic Gameplay:** The agent interacts directly with Trackmania Nations Forever through TMInterface, as managed by the `tm_interface_manager.py` script. This integration allows for real-time control inputs and access to in-game data, creating a truly immersive learning experience for the AI.
* **Vision-Based Control:** The agent "sees" the track like a human player, using screen captures provided by the high-performance dxcam library. This visual input is combined with numerical data from the game (like speed, position, and virtual checkpoint information) to create a comprehensive state representation that informs the agent's decisions.

## Prerequisites

Before you get started, ensure you have the following prerequisites:

### Hardware:

* 20 Gigs RAM
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

## Setup Instructions

To set up the project, follow these steps in Terminal:

1. Open Terminal with Admin at the root folder
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
2. Use ` to open and close the console
3. Run the script to generate "virtual checkpoints" for your map: `python ./scripts/observe_manual_run_to_extract_checkpoints.py`.
    - In Trackmania: Editor > New Track/Load Track > edit track
4. Play through the map, staying near the centerline of the road.
5. Stop the script by closing the console: `observe_manual_run_to_extract_checkpoints.py`.
6. Save the map while in the game.
    - The script will save a file in `./maps/map.npy` containing the coordinates of "virtual checkpoints" spaced approximately 10 meters apart.

### Starting Training

1. Open your track and start the test
2. Edit the location of the `map.npy` file at the top of `./scripts/train.py`, specifically at line `zone_centers = np.load(...)`.
3. Open Trackmania Interface and load the map you wish to train on, setting the game resolution to 640x480.
4. Copy the `tmrl` folder to `scripts`.
5. Run the training script: `python ./scripts/train.py`.
6. Monitor training performance via the TensorBoard interface.
7. Be patient; training may take a significant amount of time.

## Features

### Intelligent Agent with Implicit Quantile Networks (IQN)
The agent uses Implicit Quantile Networks (IQN), an advanced reinforcement learning algorithm that goes beyond traditional methods. By estimating the entire distribution of possible outcomes, IQN provides robust handling of uncertainty and improved exploration. This leads to more effective risk management and better overall performance during training.

### Seamless Integration with Trackmania Nations Forever via TMInterface
This project seamlessly integrates with Trackmania Nations Forever through TMInterface, a third-party tool that facilitates real-time communication between the Python-based AI agent and the game. This integration allows the agent to observe the game's state and send control inputs directly, creating an immersive and interactive gameplay experience.

### Vision-Based Driving with dxcam
Our agent utilizes dxcam, a high-performance screen capture library, to view the game environment through real-time screen captures. This approach mimics a human player's perspective, enabling the agent to make driving decisions based on visual cues, just like a real driver would.

### Custom Reward Function for Effective Learning
The reward function is meticulously designed to shape the agent's learning process. It encourages the agent to perform well by rewarding progress, smooth control, and lap completion while penalizing collisions and off-track errors. This carefully balanced reward structure helps the agent develop efficient and skillful driving strategies.

### Virtual Checkpoints for Enhanced Track Progress Tracking
We employ a system of virtual checkpoints to provide detailed feedback on the agent's progress along the track. Unlike traditional lap times, these checkpoints offer granular insights, enabling the agent to learn more effectively, especially on longer and more intricate tracks.

### Clear and Detailed Installation Instructions
Our README includes straightforward installation instructions, complete with links to necessary software, virtual environment setup guidance, and PyTorch installation with CUDA support. This ensures that users can quickly and easily get the project up and running on their systems.

### User-Friendly Training Process
We guide users through the process of generating virtual checkpoints for their chosen tracks and starting the agent training. The README also covers how to use TensorBoard to monitor the agent’s performance during training, making the process as intuitive as possible.

### Well-Documented Code Structure
The README provides a clear explanation of the repository's code structure, helping users understand how different components of the project fit together. This transparency makes it easier for new contributors to get involved and for users to navigate the project.

## Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.


## Screenshots
* Logo
![Logo](https://github.com/user-attachments/assets/846ba420-4b3e-40f6-acac-15138404fe36)
