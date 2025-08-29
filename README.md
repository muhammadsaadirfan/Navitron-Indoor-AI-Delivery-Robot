# Navitron: Indoor AI Delivery Robot

---

![alt text](navitron_header.png)

---



<div class="section-border">

## 1. Introduction

#### Navitron is an indoor autonomous delivery robot built with ROS, Jetson Nano, and advanced navigation frameworks. It combines hardware integration, AI-based navigation, and simulation-first development for practical robotics applications.

The project demonstrates real-world indoor delivery use cases such as restaurant service, office logistics, and smart home automation.

</div>

---

<div class="section-border">

## 2. What's special?

The **Navitron** isn't just another mobile robot a complete educational ecosystem designed to teach hardware integration, embedded programming, and AI/robotics concepts using **ROS 1 Melodic**. This platform bridges the gap between theory and practice by providing:

- Real-world hardware integration experience
- **ROS-based software architecture** understanding  
- Practical navigation and SLAM implementation
- Low-cost, accessible component selection


1. **Processing Unit (Jetson Nano)**:
   - Runs ROS 1 Melodic master node
   - Handles high-level navigation algorithms
   - Processes LIDAR data for SLAM
   - Manages system coordination and visualization

2. **Motor Control Subsystem**:
   - Hoverboard for real-time motor control
   - Encoder feedback for precise odometry
   - rosserial communication with ROS

3. **Sensor Integration**:
   - LIDAR for navigation and obstacle detection
   - D435 for Vision.
   - Encoders for dead reckoning
   - Battery monitoring for system health

4. **Navigation Stack**:
   - SLAM using gmapping
   - Path planning with move_base
   - Costmap-based obstacle avoidance
   - tf tree for coordinate transformations

</div>

---


<div class="section-border">

## 6. Bill of Materials (BOM)

### Core Hardware Components

| Component | Quantity | Purpose | Estimated Cost |
|-----------|----------|---------|----------------|
| **Jetson Nano** | 1 | Main processing unit for ROS 1 Melodic | $350 |
| **Hoverboard** | 1 | Motor control and sensor interface | $60 |
| **Intel Realsense D435** | 1 | Drives two DC motors with current protection | $500 |
| **Encoder Motors (2x)** | 2 | DC motors with built-in encoders for odometry | $40 |
| **RPLIDAR A1M8** | 1 | 360° laser scanner for navigation | $99 |
| **Battery Pack (7.4V LiPo)** | 1 | Power supply for entire system | $30 |
| **Robot Chassis Kit** | 1 | Mechanical platform and wheels | $100 |
| **Jumper Wires & Connectors** | 1 set | Electrical connections | $3 |

**Total Estimated Cost: ~$1187**

### Tools Required

- Soldering iron and solder
- Multimeter for electrical testing
- Screwdriver set
- Wire strippers
- Hot glue gun (optional)
- 3D printer access (optional, for custom mounts)

### Software Requirements

| Software | Version | Purpose |
|----------|---------|---------|
| **Ubuntu** | 18.04 LTS | Operating system for ROS 1 Melodic |
| **ROS 1** | Melodic | Robotic middleware framework |
| **Arduino IDE** | 1.8+ | Programming Arduino firmware |
| **Python** | 2.7| ROS node development |

</div>

---

<div class="section-border">

### Data Flow Diagram

```
                                                    ┌────────┐
                                                    │ LIDAR  │
                                                    └──┬─────┘
                                                       │
                                                       ▼
                                                  ┌────────────┐
                           ┌─────────────────────►│ ROS Topics │◄─────────────────┐
                           │                      └────┬───────┘                  │
                           │               ┌───────────┘                          │
                           │               ▼                                      │
                           │          ┌────────────┐     ┌─────────────┐          │
                           │          │  SLAM Node │────►│  Map Server │          │
                           │          └────┬───────┘     └────┬────────┘          │
                           │               │                  │                   │
                           │               ▼                  ▼                   │
                           │     ┌────────────┐         ┌────────────────┐        │
                           │     │Obstacle    │◄────────│ Local Costmap  │        │
                           │     │Detection   │         └────────────────┘        │
                           │     └────┬───────┘                                   │
                           │          │                                           │
                           │          ▼                                           │
                           │     ┌──────────────┐       ┌────────────────┐        │
                           │     │ Path Planner │──────►│ Global Planner │        │
                           │     └────┬─────────┘       └────┬───────────┘        │
                           │          │                      ▼                    │
                           │          ▼               ┌───────────────┐           │
                           │     ┌────────────┐       │Navigation Cmds│───────────┘
                           │     │   STM32    │◄──────│   (cmd_vel)   │
                           │     └────┬───────┘       └───────────────┘
                           │          ▼
                           │     ┌─────────────┐
                           │     │ Motor Driver│
                           │     └────┬────────┘
                           │          ▼
                           │       ┌──────┐
                           │       │Wheels│
                           │       └──┬───┘
                           │          │
                           │          ▼
                           │     ┌─────────────┐
                           │     │  Encoders   │
                           │     └────┬────────┘
                           │          ▼
                           │     ┌─────────────┐
                           └─────│ Odometry    │
                                 └─────────────┘
```




## 🙏 Thank You!

Thank you for exploring this project. 

If you have **any suggestions, feedback, or improvements**, feel free to open an issue or reach out to me directly. Collaboration and learning go hand in hand, and I'd love to hear from you!

View project details on LinkedIn:  
https://www.linkedin.com/posts/muhammad-saad-irfan_navitron-extremeroboticstesting-ros-activity-7336042995940528128-gcyA?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAEaCBx4BwPxrXkGLUEZO_Q7QODTfpKU4I6M

---
## 👤 About the Author

**Muhammad Saad**  
🎓 Mechatronics and Control Engineering Student  
🏫 University of Engineering and Technology, Lahore  
📍 Lahore, Pakistan  
📧 Email: [msaadmceu@gmail.com](mailto:msaadmceu@gmail.com)



