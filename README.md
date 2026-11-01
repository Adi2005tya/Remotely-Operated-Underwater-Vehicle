

# Remotely Operated Underwater Vehicle (ROV)

A modular 6-Degree-of-Freedom (6-DOF) Remotely Operated Underwater Vehicle engineered for subsea exploration, featuring an 8-thruster vector layout, custom power distribution architecture, and a ROS2/Stonefish simulation framework.

---

##  Project Overview & Objectives
This iteration resolves key limitations of the previous ROV (positive buoyancy preventing deep diving, hull water leakage, and 4-DOF motion constraints) by introducing:
* **6-DOF Maneuverability:** Full vector control over surge, sway, heave, roll, pitch, and yaw.
* **Enhanced Waterproofing & Structural Integrity:** Heavy-duty chassis designed with modular frame plates and sealed electronics enclosures.
* **Virtual Simulation Pipeline:** ROS2 Humble and Stonefish underwater simulator integration for virtual teleoperation.

---

##  Subsystem Breakdown

### 1. Mechanical Subsystem
* **Chassis Design:** Custom aerodynamic side and top frame plates modeled in SolidWorks to reduce hydrodynamic drag and lift forces while providing mounting slots for cameras and ultrasonic sensors.
* **Thruster Layout:** 8-thruster vector configuration to execute multi-directional movement.
* **Hydrodynamic Drag & Thrust Analysis:**
  * **Forward/Backward Motion Drag:** ~52 N (total thrust required with 1.5x safety factor: 78 N, amounting to ~27.5 N per thruster).
  * **Vertical Motion Drag:** ~109 N.
<img width="371" height="272" alt="image" src="https://github.com/user-attachments/assets/c3e6cc42-ad01-4e27-8ae5-0ff478438785" />      <img width="371" height="272" alt="Screenshot 2026-07-21 133840" src="https://github.com/user-attachments/assets/412060c4-e9d3-40c2-aa5a-ba33e6aa977a" />

### 2. Electronics Subsystem
* **Propulsion:** Eustance Technology ET03e subsea thrusters (400KV BLDC motor, 60mm tri-blade ducted propeller, max thrust 2.7 kgf, depth rating up to 150m).
* **Control Stack:** Microcontroller interface using an STM32 communicating with a Jetson Nano for bi-directional ESC control.
* **Power Distribution Board (PDB):** Custom PCB designed in KiCad tailored for 6S ESCs, integrating a 12V buck converter for the Jetson Nano, XT30 connectors, status LEDs, and power switches.

### 3. Simulation Subsystem
* **Environments:** Virtual prototyping in ROS2 Humble (Gazebo) and Stonefish Underwater Simulator.
* **URDF & Mesh Optimization:** Decimated SolidWorks STL mesh complexity from ~200,000 faces down to ~20,000 faces to eliminate simulation lag.
* **Axis Realignment:** Re-oriented URDF mesh coordinates from ENU (East-North-Up) to NED (North-East-Down) convention using Blender for Stonefish compatibility.
* **Teleoperation:** Real-time joystick control integrated with the virtual underwater model.
  
<img width="371" height="272" alt="Screenshot 2026-07-21 133840" src="https://github.com/user-attachments/assets/412060c4-e9d3-40c2-aa5a-ba33e6aa977a" />

---

##  Demos & Resources
* [Workflow Overview Video](https://drive.google.com/file/d/1tumq7myhD0F0fn916JNyVTQZ7rnXnrdl/view?usp=sharing)
* [Thruster Test Rig Demo](https://drive.google.com/file/d/17q8BuS4U6lU7hv4bZlOOMpbZ4kT4iIvW/view?usp=sharing)
* [Stonefish Simulation Demo](https://drive.google.com/file/d/1GcuKHrodTHqe-r14VugnsbsC-ehGKpWe/view?usp=sharing)



https://github.com/user-attachments/assets/a4059753-8d77-4097-9e0c-ac4d6053b122


<img width="1600" height="876" alt="image" src="https://github.com/user-attachments/assets/0aab0efa-00b3-45fc-af13-3772f7ead140" />







