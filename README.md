

**Disclaimer**

In this public repository, we have intentionally changed some training hyperparameters in the file `./trackmania_rl/misc.py` compared to our private repository to encourage a better understanding of reinforcement learning principles. Training may be inefficient or impossible with the current hyperparameters, we haven't even tested.

The actual training hyperparameters may be released at a later date. In the meantime, feel free to contact us if you have questions or encounter any issues with the code.

To actively participate and share your progress with this code, please join the TMInterface Discord community (https://discord.gg/tD4rarRYpj) first. You can then post your updates in the 'Issues' section on Github or join the conversation in our dedicated thread on the TMInterface Discord (https://discord.com/channels/847108820479770686/1150816026028675133)

**Please note:** This project is a research work-in-progress and may not receive active support for setup or usage.

## Project Overview

This project aims to develop an AI agent capable of driving in Trackmania Nations Forever using reinforcement learning. Our scope includes:
    * Training an RL agent using the IQN algorithm.
    * Designing a reward function that encourages fast and skillful driving.
    * Evaluating the agent's performance on benchmark tracks, potentially comparing it to human players or other AI approaches.

## Background

### Reinforcement Learning Concepts
Reinforcement learning (RL) is a machine learning paradigm in which an agent learns to make decisions by interacting with an environment. The agent takes actions, observes the consequences of its actions in the form of state transitions and rewards, and adjusts its behavior to maximize cumulative reward over time.  

**Core Components of an RL Framework:**

* **Agent:** The AI agent that learns to drive in Trackmania. It makes decisions based on its current understanding of the game.
* **Environment:** The Trackmania game environment, including the track, car physics, and game rules.
* **State:** A representation of the current situation in the game. This project uses:
    * **Image Data:**  Processed screenshots of the game view.
    * **Numerical Features:**  Car speed, position, orientation, gear, control inputs from the previous step, and information about upcoming virtual checkpoints.
* **Action:** The control inputs the agent chooses to apply to the car (e.g., accelerate, brake, steer left, steer right).
* **Reward:** A numerical signal that indicates the desirability of the agent's actions. Rewards encourage the agent to learn good driving behaviors (e.g., progressing along the track, avoiding collisions). 

### Implicit Quantile Networks (IQN) Agent

**Motivation: Handling Uncertainty in Reinforcement Learning**

Traditional deep reinforcement learning algorithms, like Deep Q-Networks (DQN), often estimate a single value for each state-action pair (the expected Q-value). This can be problematic in situations where the environment is highly stochastic (random) or when the agent's knowledge is uncertain. 

**IQN's Solution: Quantile Regression**

The Implicit Quantile Network (IQN) algorithm addresses this issue by estimating the entire *distribution* of Q-values instead of just a single point estimate. It does this using **quantile regression**. 

* **Quantiles:**  Imagine dividing a probability distribution into equal-sized intervals. The points that mark these divisions are called quantiles. For example, the median is the 50th percentile (0.5 quantile), and it divides the distribution in half.
* **Quantile Regression:**  Instead of predicting the average (expected value), quantile regression predicts values at different quantiles of the distribution, allowing you to capture its shape.

**Key Features of an IQN Agent:**

1. **Quantile Embedding Network:**  
   - IQN introduces a special neural network called the *quantile embedding network*. This network takes as input a set of quantile values (e.g., 0.1, 0.3, 0.5, 0.7, 0.9) and produces a corresponding set of feature embeddings.
   - These embeddings represent the different parts of the Q-value distribution.

2. **Combined Feature Representations:**
   - The features extracted from the image data (using a CNN) and numerical state data are combined.
   - These combined features are then multiplied element-wise with the quantile embeddings.  This allows the network to learn different action-value estimates for each quantile.

3. **Estimating the Q-value Distribution:**
   - The output of the network is a set of Q-value predictions, one for each input quantile. These predictions form an approximation of the Q-value distribution for the given state-action pair.

4. **Pinball Loss Function:**
   - IQN uses a special loss function called the *pinball loss* to train the network. The pinball loss encourages the network to predict quantiles accurately.

**Benefits of Using an IQN Agent:**

* **Improved Exploration:**  By capturing the uncertainty in Q-value estimates, IQN can encourage the agent to explore more effectively. It might be more willing to try actions with a wider range of possible outcomes.
* **Robustness to Stochasticity:**  IQN is less sensitive to random variations in the environment, as it considers the full distribution of potential outcomes.
* **Better Risk Management:**  In some RL applications, it's important to consider risk. IQN's ability to estimate the full Q-value distribution allows the agent to make more informed decisions about risk vs. reward.

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
