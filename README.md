# Autonomous Driving Perception Validation | CARLA Simulator

## 📌 Overview
This repository contains a professional-grade simulation environment developed in **CARLA** for the validation of LiDAR-based perception systems. The project focuses on the automated deployment of industrial infrastructure and the real-time analysis of sensor coverage over complex target patterns.

It demonstrates a **Digital Twin** approach: validating how a high-resolution LiDAR (64 channels) perceives objects at long distances (up to 250m) under specific infrastructure layouts.

---

## 🛠️ Key Technical Features

### 1. Automated "Clean Segment" Search
The script implements a robust search algorithm to find optimal road segments within the CARLA maps. It evaluates:
- **Local Curvature:** Ensures the segment is straight enough for long-range sensor testing.
- **Cumulative Yaw:** Validates the overall direction.
- **Junction Detection:** Filters out intersections to maintain a controlled testing environment.

### 2. Infrastructure Digital Twin (Procedural Spawning)
Instead of manual placement, the environment procedurally generates infrastructure patterns:
- **Dynamic Patterning:** Alternates between low (5.5m) and high (8.0m) infrastructure assets.
- **Large-Scale Signage:** Spawns complex targets composed of multiple tiles to test point cloud density.
- **Batch Processing:** Uses asynchronous batch commands for high-performance actor deployment.

### 3. Real-Time Perception Analysis
The core of the project is the `on_lidar` callback logic:
- **Occupancy Grid Analysis:** Projects 3D LiDAR points onto a 2D plane relative to the target's coordinate system.
- **Adaptive Tolerance:** Implements a distance-based tolerance model ($0.10 + 0.006 \times distance$) to account for beam divergence and sensor noise.
- **Coverage Metrics:** Calculates the percentage of the target "hit" by the sensor, providing a "Full Detection" vs. "Partial Detection" status.

---

## 🚀 Tech Stack
- **Simulation:** CARLA Simulator (Town04).
- **Language:** Python 3.x.
- **Libraries:** `math`, `struct` (for binary data unpacking), `random`.
- **API Focus:** Synchronous Mode, Traffic Manager Integration, Ray-cast LiDAR API.

---

## 📂 Repository Structure
- `lidar_perception_validation.py`: Main execution script.
- `assets/`: Simulation captures and sensor trace results.
- `docs/`: Technical notes on occupancy grid calculations.

## 📫 Contact
[LinkedIn](https://www.linkedin.com/in/pablo-de-la-maza-valles/) | [Email](pablomazav@gmail.com)
