# Autonomous Driving in an Urban Environment

**Platform:** Unity 2022.3.62f3  
**Vehicle:** Autonomous Car (LiDAR + Two Cameras)  
**Project Duration:** 4–5 weeks  
**Environment:** Urban City Simulation


https://github.com/user-attachments/assets/e5292b19-634d-4272-a881-c4e48c506649

## 1. Project Overview

The objective of this project is to develop and extend an autonomous driving simulation in an urban environment using Unity.

The project already includes a city environment, an autonomous vehicle equipped with a LiDAR sensor and two cameras, and static and moving vehicle and pedestrian models. Basic movement scripts are provided for the existing objects.

Students will implement specific functionalities related to autonomous navigation, traffic simulation, pedestrian safety, and semantic environment visualization.

The goal is **to extend the existing simulation rather than build a new project from scratch**.


## 2. Getting Started

### 2.1 Project Setup

1. Download and install **Unity 2022.3.62f3** using [Unity Hub](https://unity.com/download).
2. Download the project from this [OneDrive link](). Request access from the instructor if necessary.
3. Open the provided Unity project and load the city environment scene.

### 2.2 Required Packages

Once the project is loaded, check whether the following packages are installed. Install any missing packages using **Window → Package Manager**.

**A. URDF Importer (if required)**

1. In Package Manager, click **+ → Add package from git URL**.
2. Paste:

   `https://github.com/Unity-Technologies/URDF-Importer.git?path=/com.unity.robotics.urdf-importer#v0.5.2`

3. Click **Add**.

**B. Unity glTFast**

1. In Package Manager, click **+ → Add package by name**.
2. Enter:

   `com.unity.cloud.gltfast`

3. Click **Add** to install.

**C. Universal Render Pipeline (URP)**

1. Open **Window → Package Manager → Unity Registry**.
2. Search for **Universal RP** and install it if necessary.
3. In the Project window, check whether a URP Asset already exists.
4. If not, right-click → **Create → Rendering → URP Asset (with Universal Renderer)**.
5. Open **Edit → Project Settings → Graphics** and assign the URP Asset to **Scriptable Render Pipeline Settings**.
6. Under **Project Settings → Quality**, verify that the active quality level uses the correct URP Asset.

**Note:** If the project already has the required packages and rendering pipeline configured, do not reinstall or replace them.


### 2.3 Unity Project Structure

Familiarize yourself with the **Scene, Hierarchy, Inspector, and Project** windows.

Locate the following components:

| Object / Component | Description |
|---|---|
| Autonomous Car | Main vehicle used for navigation and driving |
| LiDAR Sensor | Sensor mounted on the vehicle |
| Front and Rear Cameras | Two vehicle-mounted cameras |
| Vehicle Models | Static and moving vehicles |
| Pedestrian Models | Static and walking pedestrians |
| Movement Scripts | Existing scripts for controlling object movement |
| Assets | Additional models and reusable components |

**Note:** Students can duplicate existing cars and pedestrians and reuse their movement scripts to create additional traffic scenarios. They do not need to create new vehicle or pedestrian models.

<p align="center">
  <img src="https://github.com/subhransu10/Autonomous_Driving_in_an_Urban_Environment/blob/main/Screenshot%202026-10-15%20174726.png" width="50%">
</p>




## 3. Student Tasks

The project is divided into four modules. Each student is responsible for implementing and testing their assigned module. So as you can see in the screenshot above, Student 1 can use 01_CameraModule (if he/she is working on the camera) and branch all the actors/prefabs in it and so on. This would allow for an easier integration of the modules and also would help the tutors to understand the modules and their functionalities. 

### Student 1 — Autonomous Navigation and Path Planning

**Objective:** Implement autonomous navigation for the vehicle within the urban environment.

**Tasks:**
- Implement basic vehicle movement and steering control.
- Define waypoints or predefined routes along city roads.
- Implement simple path following between selected locations.
- Introduce basic obstacle detection and avoidance.
- Test navigation through different city routes and intersections.

**Expected Result:** An autonomous vehicle capable of following predefined routes and responding to obstacles in the urban environment.

**Note:** Students may use Unity's existing vehicle physics and movement controllers. Developing a complete autonomous driving stack is not required.

### Student 2 — Urban Traffic and Vehicle Simulation

**Objective:** Simulate realistic vehicle movement and basic traffic behavior.

**Tasks:**
- Use the provided vehicle models and movement scripts to create moving traffic.
- Implement predefined driving paths for multiple vehicles.
- Implement basic stopping and starting behavior at intersections.
- Introduce simple traffic rules, such as stopping at designated points or maintaining a safe distance from other vehicles.
- Test traffic movement under different scenarios.

**Expected Result:** An urban traffic simulation with vehicles following predefined routes and responding to simple traffic conditions.

**Note:** Existing vehicle models and movement scripts can be reused and modified.

### Student 3 — Pedestrian Awareness and Safety

**Objective:** Improve autonomous vehicle safety when interacting with pedestrians and other road users.

**Tasks:**
- Use existing static and walking pedestrian models to create different scenarios.
- Implement pedestrian detection using predefined detection zones, raycasts, or simulated sensor information.
- Define safety zones around pedestrians and the autonomous vehicle.
- Implement vehicle slowing or stopping when a pedestrian enters a safety zone.
- Visualize detected pedestrians using markers, bounding boxes, or warning indicators.

**Expected Result:** An autonomous vehicle capable of identifying potential pedestrian hazards and responding safely by slowing down or stopping.

**Note:** Training an object detection model is not required. Unity physics, raycasts, or simulated detections may be used.

### Student 4 — Urban Semantic Mapping and Visualization

**Objective:** Develop a simple semantic representation of the urban environment to improve environmental awareness.

**Tasks:**
- Define semantic categories such as roads, sidewalks, buildings, vehicles, and pedestrians.
- Assign semantic labels or colors to relevant objects in the environment.
- Develop a simple local semantic map or top-down visualization around the vehicle.
- Distinguish static elements (e.g., buildings) from dynamic elements (e.g., moving vehicles and pedestrians).
- Implement controls to enable or disable semantic visualization layers.

**Suggested Colors:**
- **Gray:** Roads
- **Blue:** Buildings
- **Green:** Static objects
- **Red:** Moving objects
- **Yellow:** Pedestrian or safety zones

**Expected Result:** An interactive semantic visualization showing the vehicle's surroundings and distinguishing different urban elements.

**Note:** The semantic representation may use known Unity object labels and positions. Developing a machine-learning-based semantic segmentation system or a complete SLAM pipeline is not required.

<img width="1235" height="936" alt="Screenshot 2026-10-16 104222" src="https://github.com/user-attachments/assets/527a194c-5e07-44ea-8833-23db7cc552f0" />

**Tips from Instructor:** The only coordination requirement I would emphasize to students is that Student 1 and Student 3 must agree on a common vehicle control interface. Student 3 should be able to request slowing or stopping without replacing Student 1's navigation logic. This will make their final integration much easier.

## 4. General Requirements

- Use the provided Unity project and autonomous vehicle model.
- Keep all implementations modular and organized. **Name each module and its scripts clearly** to simplify evaluation.
- Reuse provided vehicle and pedestrian models where appropriate.
- Avoid unnecessary modifications to unrelated components.
- Ensure that the implemented functionalities work correctly in Unity Play mode.
- Simulated sensor data may be used when real sensor processing or external ROS integration is unavailable.
- Coordinate with other students to ensure compatibility between the modules.

## 5. Evaluation and Grading

Each module will be graded out of **100 points**.

| Criteria | Points |
|---|---:|
| Correct implementation of assigned tasks | 30 |
| Functionality and integration | 25 |
| Code organization and explanation | 20 |
| Final demonstration | 25 |
| **Total** | **100** |

## 6. Final Submission

Each student must submit:

1. **Unity Implementation:** Completed scripts, modified assets, and relevant project files.
2. **Demonstration Videos:** A short individual demonstration (2–3 minutes) and a combined working prototype video (no fixed time limit).
3. **Final Presentation and Report:** A concise explanation of the implementation, testing, results, and any limitations.

The final demonstration should show the assigned functionality working in the existing city environment and, where applicable, integrated with the other modules.

**Important:** Evaluation will focus on correct functionality, integration with the provided project, and the student's understanding of their implementation. Unnecessary complexity is not expected.
