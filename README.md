# Trackmania AI - Reinforcement Learning Agent

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains code for training a reinforcement learning (RL) agent to drive autonomously in Trackmania Nations Forever. The agent learns to race on a track by interacting with the game environment, receiving rewards for good driving behavior, and improving its strategy over time.

## Project Highlights

* **AI Driver:** The agent is trained using an advanced reinforcement learning algorithm called Implicit Quantile Networks (IQN). 
* **Realistic Gameplay:** The agent interacts with Trackmania Nations Forever using TMInterface, a tool that allows external programs to communicate with the game.
* **Vision-Based Control:** The agent uses real-time screen captures (with dxcam) and game data to make driving decisions.

## Getting Started

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
Use code with caution.
Markdown
Administrator Terminal:
Open a terminal with Administrator privileges in the cloned repository's root folder.
Virtual Environment:
get-ExecutionPolicy       # If output is 'Restricted', run the next command
Set-ExecutionPolicy Unrestricted   # Run as Administrator
python -m venv myenv
myenv\Scripts\activate
Use code with caution.
Bash
Install Dependencies:
nvidia-smi              # Verify your CUDA version
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install -r requirements.txt
python setup.py install --user
Use code with caution.
Bash
Running the AI Agent
Launch Trackmania: Open Trackmania Nations Forever using TMInterface.
TMInterface Console: Use the backtick (`) key to open and close the TMInterface console.
Track Mapping
Checkpoint Generation Script:
python ./scripts/observe_manual_run_to_extract_checkpoints.py
Use code with caution.
Bash
Trackmania Editor:
Go to Editor > New Track/Load Track in Trackmania.
Edit the track as desired (or load an existing track).
Drive a Lap: Manually drive one lap around the track in the editor.
Stop the Script: Stop the observe_manual_run_to_extract_checkpoints.py script.
Checkpoint File: You should now have a map.npy file in the maps folder, containing the virtual checkpoints for the track.
Training the Agent
Select Track: Open the track you want to train on in Trackmania and start a test run.
Configure train.py:
Edit the filename in ./scripts/train.py to use the correct map.npy file.
Ensure the trackmania_rl folder is in the scripts folder.
Start Training:
python ./scripts/train.py
Use code with caution.
Bash
Code Structure
agents/: Contains the IQN agent implementation.
experience_replay/: Contains the experience replay buffer implementation.
scripts/: Contains scripts for checkpoint generation and agent training.
tm_interface_manager.py: Manages communication with Trackmania via TMInterface.
misc.py: Contains configuration settings and utilities.
requirements.txt: Lists Python dependencies.
License
This project is licensed under the MIT License - see the LICENSE file for details.
**Explanation:**

- **Removed Personal Information:**  The README no longer includes developer names or specific links to personal profiles.
- **Clearer Structure:**  I've reorganized the content for better readability.
- **Detailed Instructions:** The "Running the AI Agent" section provides step-by-step guidance for mapping and training.
- **Code Structure:**  A brief overview of the code organization helps users navigate the repository. 

Remember to:

- **Update Placeholder:** Replace `your-username/your-repository-name` with your actual GitHub details.
- **Add Results and Future Work:**  Include a summary of your project's findings and potential directions for improvement.
- **Acknowledgements:**  Optionally acknowledge any libraries or resources you used.

This new `README.md` provides a generic and informative starting point for your Trackmania AI project on GitHub!
## Logo
![Logo](https://github.com/user-attachments/assets/846ba420-4b3e-40f6-acac-15138404fe36)
