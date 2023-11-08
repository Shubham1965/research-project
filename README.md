# Research Project: 
## On the Conditioning of the Regressor matrix for Identification of Inertial Parameters of an Industrial Manipulator

### This repository is is only for referring to my work for the Coursework named "Research Project" held at RWTH Aachen, offered by my study program "M.Sc. in Robotic Systems Engineering". 

### **Introduction:**
Industrial robots (especially 6-axis) are used for machining tasks in various applications nowadays. In contrast to conventional machine tools, they are less rigid, negatively impacting the workpiece quality. To improve their accuracy and precision, it is necessary to model their dynamic parameters and compensate for torque calibrations. This involves characterizing the robot's dynamic behavior, including all dynamic parameters, and using that information to adjust the control algorithms and improve the robot's performance. The goal is to achieve better control over the robot's movements, reducing errors and increasing the accuracy and repeatability of the machining process. For this purpose, identifying dynamic model parameters of the industrial robot, referring to the inertial parameters of the robot links, Coulomb-viscous friction parameters, and actuator(motor) inertia, becomes paramount. Assuming we have good friction models, the inertial parameters of the robot links and the motor inertia are termed as inertial parameters of the whole robot, which is the focus of this research thesis. 

In most identification routines, there are three common similarities/features: modeling the dynamics, designing excitation trajectories, and using an estimation technique. In modeling, robot dynamics can be derived using either Lagrangian or Newton-Euler formulation. Excitation trajectories ensure persistence in the excitation of the dynamic parameters, resulting in a well-conditioned regressor matrix. Finally, estimation techniques help to build inferences on the estimated dynamic parameters. In this thesis, the focus is on the first two features. Since the approach is directed to find the inertial parameters, the robot dynamics are simplified to find a second-order equation in terms of inertial parameters and friction parameters under a set of assumptions made in choosing the excitation trajectories. The objectives of this thesis are: to obtain an analytical model of the load-side inertia at each axis, to find a collision-free set of configurations of the robot, and to find the optimal ones from that set to optimize the condition number in order to achieve well-conditioned regressor matrix. The theory is presented in the clearest yet rigorous fashion while providing enough advanced material and references so that the reader is prepared to contribute new material to the state-of-the-art.

### **Goals Delivered:**
1. Researched about analytical modeling of robot dynamics and found ways to model the
load-side inertia.
2. Familiarized with the initial parameter-identification toolbox built; the updated one is here
(https://git-ce.rwth-aachen.de/robotmachining/robotmodel/parameter-identification).
3. Developed functions based on algorithms 4.1- 4.8 that give a symbolic form of the load-side inertia in a minimal model form.
    - General-purpose Kinematic Transform (kinematicTransform): an algorithm that helps to do homogeneous transformations.
    - Load-side Inertia (inertiaTransform): initial load-side inertia at a particular axis input.
    - Axiswise Linear Systems (axisLinSys): calculates an axiswise matrix equation of the load-side inertia from inertiaTransform.
    – Eliminate repeating Base Parameter (eliminateRepeatBaseParam): eliminates repeating base parameters.
    – Pre-Minimal Model (preMinimalModel): combines all axiswise matrix equations into a single one.
    – Find Linearly Dependent Base Parameters (findLinDep): finds linearly dependent base parameters.
    – Coefficient multiplication and division (mulbf_divbp): Normalizes the base parameters and base functions.
    – Calculate Minimal Model (calcMinimalModel): calculates the final minimal model of the load-side inertia.
4. Developed a live script named Base_Parameter_Calculations.mlx for ease of understanding of how to model the load-side inertia.
5. Researched about condition number optimization pertaining to designing excitation trajectories and subsequent estimation theory.
6. Developed functions based on algorithms 5.1- 5.3 that give a concise set of configurations that makes the regressor matrix from the minimal model well-conditioned and ready for designing excitation trajectories to find the inertia.
    - Generate Poses(generatePoses): used for discretization or generating random configurations of the robot.
    – Generate Target Matrix (generateTargetMatrix): generating an ideal target matrix for conditioning of regressor matrix.
    – Condition Number Optimization (condNumOpt): gives the final set of well-conditioning configurations.
7. Developed live scripts named Create_collision_free_poses.mlx and Condition_Number_Optimization_simple.mlx for ease of understanding of how to get the optimum set of configurations.
8. Documentation of thesis


### **Contents of the Repo:** 
1. Thesis pdf
