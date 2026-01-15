# Computer-Vision-Based-Autonomous-Driving-System-
🚗 Computer Vision–Based Autonomous Driving System
📌 Project Overview

This project presents a Computer Vision–Based Autonomous Driving System designed using a three-layer autonomy pipeline: Perception, Planning, and Control. The system processes video input from a monocular camera to perceive the environment, plan a safe driving path, and generate low-level vehicle control commands such as steering, throttle, and braking.

The primary goal of this project is to demonstrate how vision-only perception, combined with classical planning and control algorithms, can enable autonomous driving without relying on expensive sensors like LiDAR or RADAR.

🧠 System Architecture

The system is divided into three major software modules:

1️⃣ Perception Software

Input: Video stream (.mp4)
Output: Tracked 3D objects with class, ID, and estimated distance

The perception module is responsible for understanding the driving environment using computer vision and deep learning techniques.

Core Components:

2D Object Detection:
YOLOv8 is used to detect road objects such as vehicles, pedestrians, and obstacles in real time.

Monocular Depth Estimation:
MIDAS is employed to estimate object distance from a single camera, converting the 2D detection problem into a 3D perception task.

Multi-Object Tracking:
DeepSORT assigns persistent IDs to detected objects and tracks them across frames, enabling temporal consistency and motion awareness.

Output:

Object ID

Object class

Estimated distance from the vehicle

2️⃣ Planning Software

Input: Perception outputs
Output: Target speed and planned driving path

The planning module determines where and how the vehicle should move based on the perceived environment.

Core Components:

Drivable Area Semantic Segmentation:
Generates a road mask to identify safe driving regions.

Path Planning:
An A* algorithm is used to compute the optimal path within the drivable area.

Behavioral Logic:
A rule-based Finite State Machine (FSM) handles driving decisions such as lane keeping, speed adjustment, and obstacle response using if–then logic.

Output:

Target speed (e.g., 20 km/h)

Planned path coordinates [(x₁, y₁), (x₂, y₂), …]

3️⃣ Control Software

Input: Planned path and target speed
Output: Low-level control commands

The control module converts high-level planning decisions into executable vehicle commands.

Core Components:

PID Controller:
Used for both speed and steering control.

Speed PID:
Generates throttle and brake commands to maintain the desired speed.

Steering PID:
Ensures lane keeping and smooth path following.

Output Commands:

Steering angle

Throttle value

Brake value

🛠️ Technologies Used

Python

OpenCV

YOLOv8

MiDaS (Monocular Depth Estimation)

DeepSORT

A* Path Planning Algorithm

PID Controllers

🎯 Key Features

Vision-only autonomous driving pipeline

Real-time object detection, tracking, and depth estimation

Modular perception–planning–control architecture

Classical path planning with rule-based behavioral logic

Smooth lane keeping and speed control using PID

🚀 Applications

Academic and final-year autonomous vehicle projects

Research on vision-based autonomous systems

Robotics and intelligent transportation systems

Simulation-based self-driving car prototypes

🔮 Future Improvements

Traffic sign and signal recognition

Dynamic obstacle avoidance

End-to-end learning-based planning

Sensor fusion with ultrasonic or IMU sensors

Real-world hardware deployment

⭐ Why this project matters

This project closely mirrors real-world autonomous driving system design, making it an excellent learning and portfolio project that demonstrates practical knowledge of computer vision, robotics, planning, and control systems.

ARCHITECTURE DIAGRAM 

<img width="947" height="608" alt="Architecture divided into three modules " src="https://github.com/user-attachments/assets/26e0613e-a260-40bc-9f52-201020630923" />

YOLO Workflow Diagram 

<img width="526" height="606" alt="Yolo workflow " src="https://github.com/user-attachments/assets/6774033e-25d0-4191-8395-5d276751f2ce" />

YOLO+MIDAS+ByteTrack workflow Diagram 

<img width="465" height="615" alt="yolo+tracking+id+midas " src="https://github.com/user-attachments/assets/b58cf145-6e29-4cc6-b11e-06c409b6a797" />

A*+Depth Diagram 

<img width="522" height="613" alt="Screenshot 2025-11-23 at 12 23 56 AM" src="https://github.com/user-attachments/assets/b6d5dc0c-7107-4e80-8be2-f1991800a783" />




