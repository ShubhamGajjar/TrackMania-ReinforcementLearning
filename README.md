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
    - NVIDIA GPU (for dxcam screen capture)
    - Sufficient CPU and RAM for running the Python agent and training process
- **Software:**
    - Windows 10 (or compatible OS)
    - Trackmania Nations Forever: \[Link to download]
    - TMInterface ([version number]): \[Link to download]
    - Python (3.10 recommended): \[Link to download]
    - CUDA Toolkit (compatible with your PyTorch version): \[Link to download]
    - PyTorch (with CUDA support): \[Link to download instructions]
    - Required Python libraries: Install with `pip install -r requirements.txt`
      (Make sure you create a requirements.txt with all your project's dependencies)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/your-repository-name.git
## Logo
![Logo](https://github.com/user-attachments/assets/846ba420-4b3e-40f6-acac-15138404fe36)
