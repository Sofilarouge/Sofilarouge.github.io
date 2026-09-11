---
name: "Rem-U Robotic Arm"
subtitle: "Group project for student initiative Robocol (2019) Universidad de los Andes"
keywords: "keywords: multibody dynamics, mechanical design, prototype construction, motion control, trajectory planning, finite state machine"
image_url: /assets/images/remu2.jpg
director: "Prof. Dr. Carlos Francisco Rodriguez Herrera"
co-authors: "Robocol Team 2019-2020"
summary: "Mechanical design and motion control of a low-budget, 6 DoF robotic arm Intended for use on the exploration rover REM-U for the European rover Challenge (ERC) competition. Project developed as mechanical engineering lead for the student initiative Robocol (2019) Universidad de los Andes."
emphasis: "Being the only Latin American team to qualify, Robocol won the 26th place that year. The next year, we won 3rd."
---
![fish2](/assets/images/remu2.jpg)

Co-Authors: Robocol Team 2019-2020

Mechanical design and motion control of a low-budget, 6 DoF robotic arm Intended for use on the exploration rover REM-U for the European rover Challenge (ERC) competition. Project developed as mechanical engineering lead for the student initiative Robocol (2019) Universidad de los Andes.

![fish2](/assets/images/remu1.jpg)

This project involved the complete design and manufacture of the rover REM-U from scratch as the flagship project for the student initiative Robocol. My main contribution (and the focus of this entry) as lead of mechanical engineering was centered around the robotic arm, for which a budget of less than $500 USD was allocated. The arm was expected to carry a payload of 10 kg.

The first stage of the design was iterative: Required motor driving torques were obtained as a result of a multibody dynamic simulation starting from rough dimensions, configurations, and properties. The model was adjusted and the simulation recalculated until a suitable configuration (with affordable motors) was found.

The project constraints also determined the component and material selection: 3D printed ABS and laser-cut MDF made up most of the structure. For the more robust mechanical couplings, aluminium components were manufactured either by CNC, lathe, or bent aluminium profile sheet. All of the manufacture and assembly was made in-house by the team.

Finally, the same parameters and models used for the dynamic simulation were used to formulate a control strategy. Potentiometers connected to the joints allowed the formulation of closed-loop control. ROS MoveIt was used to control the arm (as well as the rest of the rover) in one of two modes: during manual operation, a user used a joystick to command the position and apperture of the end effector. During autonomous operation, the robot moved to predetermined configurations as defined with a finite state machine.
