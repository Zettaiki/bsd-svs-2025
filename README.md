# Blind Spot Detection (BSD) with Active Intervention
*Blind Spot Detection safety system with interventions implemented on CARLA simulator using Python.*

This project implements a Blind Spot Detection (BSD) system that detects vehicles in the blind spot of a car and performs active interventions to avoid potential collisions. The system is designed to work in the CARLA simulator, which provides a realistic environment for testing autonomous driving systems.

## Features

- Real-time detection of vehicles in the blind spot using computer vision techniques and sensors data.
- Active intervention (e.g., steering, audio alerts).
- Integration with CARLA simulator.
- Configurable parameters for detection and intervention.

## Requirements

### Hardware

This project has been tested on a system with the following specifications on **low settings** (you may need a similar or better setup for optimal performance):
- CPU: Intel Core i7-6700K
- GPU: NVIDIA GeForce RTX 3050 8 GB VRAM
- RAM: 16 GB
- Storage: SSD with at least 20 GB free space
- Operating System: Windows 10

> You can refer to the [CARLA recommended system requirements](https://github.com/carla-simulator/carla?tab=readme-ov-file#recommended-system) for detailed information on the specific hardware needed.

The simulation supports keyboard controls, but for advanced features such as active intervention, using a compatible steering wheel controller is recommended.

To run the simulation using a steering wheel controller, you’ll need to update the `wheel_config.ini` file to match your controller’s configuration.

### Software
- Python 3.7.x
- Required Python packages (see `requirements.txt`)
- [CARLA simulator](https://github.com/carla-simulator/carla/releases) (version 0.9.15 or later)
- [YOLOv5 nano](https://github.com/ultralytics/yolov5) model for vehicle detection (already included in the project).
- Audio files for alerts (already included in the project).

## Directory structure

The project is structured as follows:

```
src
`-- python
    |-- BSD.ipynb                         # Simulation notebook
    |-- cv_model
    |   `-- yolov5nu.pt                   # Pre-trained YOLOv5 nano
    |-- manual_control.py
    |-- manual_control_steeringwheel.py
    |-- sounds
    |   `-- allert.mp3
    `-- wheel_config.ini                  # Steering wheel config
```

## Setup and Run

After ensuring you have the required hardware, follow these steps to set up and run the project:

1. **Clone the repository**:
  ```bash
  git clone https://github.com/Zettaiki/bsd-svs-2025.git
  cd bsd-svs-2025
  ```

2. **Install Python dependencies**:
  Make sure you have Python 3.7.x installed, then install the required packages:
  ```bash
  pip install -r requirements.txt
  ```

  > You can use a virtual environment like [Miniconda](https://www.anaconda.com/download/success) or venv to manage dependencies.

3. **Download CARLA**:
  Download the CARLA simulator from the [CARLA releases page](https://github.com/carla-simulator/carla/releases).

4. **Run the CARLA server**:
  Open a terminal and navigate to the CARLA directory, then run:
  ```bash
  # For Linux
  ./CarlaUE4.sh

  # For Windows
  .\CarlaUE4.exe
  ```

  > **IMPORTANT:** Make sure the CARLA server is running on `localhost:2000` before starting the simulation notebook.

5. **Open the simulation notebook**:
  Open the `BSD.ipynb` notebook in Jupyter Notebook and run the cells to start the simulation. You can set the parameters for configuration, controller, sensors, and interventions in the notebook.

After running the notebook, you will be able to control the vehicle inside the CARLA simulator and observe the blind spot detection and active intervention features in action.

## License

This project is licensed under the MIT License – see the [LICENSE](./LICENSE) file for details.

The MIT License is a simple and permissive license that allows users to:

- Use the software for any purpose
- Modify the software to suit their needs
- Distribute copies of the software
- Include the software in proprietary projects

The software is provided "as is", without any warranty.

For more information about the MIT License, visit:  
https://opensource.org/licenses/MIT