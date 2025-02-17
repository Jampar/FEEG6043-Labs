# Intelligent Mobile Robotics (FEEG6043) Repository

## Overview

This repository contains the code developed for the **Intelligent Mobile Robotics** module (**FEEG6043**) at the **University of Southampton**. The module focuses on the theory and practice of robotic perception and reasoning, essential for mobile autonomous vehicles operating in dynamic, unstructured environments across land, sea, and air.

## Repository Structure

```
├── desktop/Projects/FEEG6043  # Project-specific files
├── docs/                      # Documentation and reports
├── logs/                      # Log files and system outputs
├── src/                       # Source code for the project
├── webots/                    # Webots simulation files
├── LICENSE                    # License file (GPL-3.0)
├── README.md                  # Project documentation
├── crontab_startup.sh         # Startup script for automation
├── install.sh                 # Installation script
├── setup.py                   # Python package setup file
```

## Setting up Robot and Simulator

### Robot Kits

Each team receives a **WheelySmart** robot kit for use during practicals. These robots include:

- **Pi-Top[4]** robot kit (platform and computer)
- **2 x Servomotors** with encoders (wheel control)
- **1 x Lidar Slamtec RPLidar A1** (environment sensing)
- **1 x Aruco marker** (external localization)
- Charger, fireproof charging bag, and an Ethernet cable

Robot batteries last about 2 hours without running the wheels. Robots must be booked in **3-hour blocks** during term time via email at least 1 day in advance.

### C1.2 Laptops

Each team receives a laptop for developing and operating the robots. Laptops use **university accounts** and must be booked via email **one day in advance**.

### C1.3 External Position & Heading Sensor Data

- The **Aruco camera system** measures the robot's position and heading.
- Data is streamed via Ethernet cable during practicals and stored for later analysis.
- The **Aruco marker** must be placed correctly on the robot for accurate localization.

### C1.4 Setting Up Your Laptop

#### First Login

1. Connect the laptop to the network via Ethernet.
2. Log in using your university credentials.

#### Install Python

1. Search for **Anaconda 3** in the **Software Centre**.
2. If unavailable, download it from [Anaconda's official site](https://www.anaconda.com/products/individual) and install.

#### Install Webots

1. Download **Webots** from the official website.
2. Install **for me only** in the default location.
3. Allow access on all networks when prompted.

#### Install FEEG6043 Robot Software

1. Download **uos\_feeg6043\_build-main** from Blackboard.
2. Extract it to your **OneDrive - University of Southampton** folder.
3. Open an **Anaconda prompt** and navigate to the extracted directory:
   ```bash
   cd "C:\Users\your_username\OneDrive - University of Southampton\feeg6043\uos_feeg6043_build-main"
   ```
4. Install dependencies:
   ```bash
   pip install -U --user -e .
   ```

#### Test Installation

1. Open **Webots** → File → Open World → Load `imr_webots.wbt`.
2. Run:
   ```bash
   python src/show_laptop.py --simulation
   ```
3. The robot should move in simulation.

### C1.5 Connecting to a WheelySmart Unit

1. Turn on the robot and note the **Wi-Fi name** and **password** displayed.
2. Connect to the **pi-top-XXXXXX** Wi-Fi.
3. Open an **Anaconda prompt**, navigate to your repository folder, and run:
   ```bash
   python src/show_laptop.py
   ```
4. The robot will move, but no intelligence is applied yet.

### Turning Off the Robot

Hold the **power switch** for **10 seconds**.

### Charging the Robot

- Plug the USB-C charger into the **frontmost port** with the **lightning symbol**.
- Place the robot in a **fireproof charging bag**.

### Troubleshooting

- **Webots cannot find Python**
  - Open **Anaconda prompt**, run:
    ```bash
    where python
    ```
  - Copy the first result and update `webots/controllers/webots_robot/runtime.ini` accordingly.
- **ZeroROS issues or robot not moving**
  - Ensure dependencies are installed with:
    ```bash
    pip install -U --user -e .
    ```
  - Check for errors in **Anaconda prompt**.

## License

This project is licensed under the **GPL-3.0 License**. See the [LICENSE](LICENSE) file for details.
