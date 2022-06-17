---
layout: post
title: Community Bonding Period Begins
date: 2022-05-27 20:00:00 +0530
tags: [GSoC, simulators, robotics_academy, exercises, backend, frontend]
# permalink: /community-bonding/
description: Exploring and spreading out the choices for the improvement in frontend and backend for the drone based exercises.
---

# **Community Bonding 1**

> *Google Summer of Code starts with the Community Bonding period where we get to know about the community and get familiar with the code base and work style.It's the period of time between when accepted students are announced and the time these students are expected to start coding. This time is an excellent one to introduce students to the community, get them on the right mailing lists, working with their mentors on their timeline for the summer, etc.* [1](https://developers.google.com/open-source/gsoc/resources/glossary#community_bonding_period)

## **How did I contributed in this period?**

The vey first thing was my first official welcome meet with my supportive and considerate mentors. We discussed the accepted proposal and the timeline that was proposed. The deliverables were discussed and the goal for the community bonding period was decided.

**The goal for the community bonding period is as follows:**
- Choosing the most efficient and needed ones from the deliverables with a brief explanation for their selection
- Integrating the timeline with chosen deliverables and if possible then get a headstart for the coding period

**These are the deliverables briefed out for selection for consolidation of drone based exercises as well extending the backend:**

**`Frontend (consolidation of exercises)`**:

**[Drone Cat & Mouse](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/drone_cat_mouse)**:
- Add teleop of mouse
- Improve the the control code of mouse for its autonomous movements
- Add occlusions in difficulty level advance
- on-the-fly selection of Gazebo world(like follow line) for difficulty(worlds with no obstacles to large obstacles)


**[Follow Turtlebot](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/follow_turtlebot)**:
- Add teleop of turtlebot
- Change vel from constant to variable
- Add april tag on top on turtlebot instead of colour plate
- Add occlusions

**[Follow Road](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/follow_road)**:
- Add on-the-fly selection of different shape roads 
- Add timer to classify as difficulty for different shape roads
- Add other objects’ models on road to improve look and increase difficulty

**[Labyrinth escape](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/labyrinth_escape)**:
- Multiple models of labyrinth to load (including circular)
- More realistic model of labyrinth
- More input signals instead of four with problem of finding the inclined angle of arrow for student (can be used in case of circular labyrinth)

**[Position Control](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/position_control)**:
- Multiple routes to select from
- Use light beacons instead of normal construction cones for improving world
- Moving beacons can be improvised for increasing difficulty and appeal of the exercise

**[Rescue People](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/rescue_people)**:
- Modified version of this exercise can be implementing if different rescue situations as following: Forest, Building on fire, earthquake affected building
- Lightning conditions can be varied (day and night) and accordingly an led light model can be added for the student to switch on for getting better camera input

**[Drone gymkhana](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/drone_gymkhana)**:
- Multiple gymkhana course to choose from on-the-fly
- Change or add new models for obstacles(hoops) like hexagonal and other polygon shape for drones to pass through

**[Drone Hangar](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/drone_hangar)**:
- Teleoperated movement of obstacles
- Standardisation of difficulty level for obstacle course in the hangar
- More than one colour of obstacle and their changing velocities to decide difficulty of the exercise 
- Different models added as obstacle namely cylinders, hoops,etc
- Adding checkpoints in between the obstacles to register for the student
- Adding a reset functionality whenever the drone hits the obstacles like a game
- Multiple size of obstacle slabs to standardise difficulty level

**[Visual lander](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/visual_lander)**:
- A separate version or choose-to world can be created where the drone has to land on a moving boat
- Teleop of car or boat
- Creating a road track on which the car will move(only if teleoperation is disabled) (for boat a set of waypoints)
- Updating the visual marker to more visually appealing model like launchpad or an April Tag can be used
- More visually appealing world can be created with buildings and other stationary models after integrating a road track

**[Package delivery](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/package_delivery)**:
- Integrating QR code with the package to get coordinates for the delivery
- Multiple package delivery  with del location on the qr code(only warehouse oc is known)
- Improved world to incorporate multi package delivery(buildings where package has to be delivered & landing marker can also be on top of the building)
- Student needs to incorporate real time path planning algo to solve
- Possible obstacle avoidance task can be incorporated in package delivery where a simple range sensor can be employed in use

**[Power Tower inspection](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/power_tower_inspection)**:
- Change size of the power towers and hence the defect to get a real life size ratio of drone and power tower
- Change size of wires to greater in diameter
- Employing multi-drone system for inspection (student goal will be to incorporate both drone to perform inspection)


**`Backend`**:

- **Replacing PX4 SITL with a lighter simulator. The simulators are as follows:**

**[Ardupliot gazebo plugin](https://github.com/SwiftGust/ardupilot_gazebo)**
- Repo for ArduPilot & Gazebo Software In Loop Simulation Interfaces, Models
- Original gazebo models 
- Ardupilot SITL compatible models.
- Ardupilot SITL example worlds
- Ardupilot plugin source files for Gazebo
- Ardupilot plugin header files for Gazebo

*Pros:*
- provide different models from copter to plane to rover, Multi vehicle sim, use of Ardupilot SITL provides access to the full range of development tools available to desktop C++ development, such as interactive debuggers, static analyzers and dynamic analysis tools. This makes developing and testing new features in ArduPilot much simpler.
- Much better community support and stable release builds
- Easy integration with real world drones(not much of concern right now for simulation)

*Cons:*
- The reason we are trying to shift from PX4 applies to ardupilot as well. It’s not a lightweight SITL for drone control. Main goal is a light sim
- Sophisticated system to make modifications to our need and heavy to run 
- The use of Ardupilot SITL is to provide Ardupliot autopilot without hardware in the simulation environment. We need a drone or drones simulated in gazebo and a drone stack to control it in the backend of HAL for all the drone commands : *get_frontal_image,get_ventral_image,get_position,get_velocity,get_yaw_rate,get_orientation,get_roll, get_pitch get_yaw  get_landed_state,set_cmd_pos set_cmd_vel,set_cmd_mix,takeoff & land* and other custom cmnds for specific exercises

**[RotorS](https://github.com/ethz-asl/rotors_simulator)**
- [RotorS](https://www.researchgate.net/publication/309291237_RotorS_-_A_Modular_Gazebo_MAV_Simulator_Framework) is a MAV gazebo simulator(Micro Aerial Vehicle (MAV) simulation framework). It provides some multi-rotor helicopter models such as the AscTec Hummingbird, Pelican, and Firefly, but the simulator is not limited for use with these multicopters.
- There are simulated sensors coming with the simulator such as an IMU, a generic odometry sensor, and the VI-Sensor, which can be mounted on the multi-rotor helicopters.
- This package also contains some example controllers, basic worlds, a joystick interface, and example launch files.

*Pros:*
- different controllers and state estimators can be used interchangeably
- provided controllers can be adapted to a custom vehicle by only changing a parameter file
- Custom controller can be developed
- Custom sensors can be created 
- Multi drones integration done

*Cons:*
- Noetic migration isn’t supported well to a required extent but can be managed
- Maintenance deprived & lack of issue solving support

![Structure of the packages]({{ site.baseurl }}/assets/blog_images/community_bonding/rotors_pkg_struct.png){: .align-center}

**[TUM sim (melodic & noetic)](http://wiki.ros.org/tum_simulator)**
- gazebo simulator for the Ar Drone 2.0 
- The simulator can simulate both the AR.Drone 1.0 and 2.0, the default parameters however are optimised for the AR.Drone 2.0 by now.

*Pros:*
- Light and simple
- Teleop package already available(implementation help for our improvement in drone exercises)

*Cons:*
- Lack of integrated sensors (available ones are IMU & RGB camera
- Only for Parrot AR drone, does not support other drones(no efficient as a choice for multiple models sim)
- Lack of community support 
- No build available for Noetic (needs to be done, time consuming and bound to inefficient developing)

**[MRS gazebo simulation(melodic & noetic)](https://github.com/ctu-mrs/simulation)**
- Support for spawning vehicles into Gazebo simulation, where users can select from multiple UAV platforms. This platform can be additionally equipped with several sensors (rangefinders, 2d lidars, stereo cameras etc.).

*Pros:*
- Have multiple drone models integrated
- Supports multiple drone simulation
- Stable noetic build
- Integrated additional sensors  than RGB cam & IMU

*Cons:*
- Has PX4 as SITL (the SITL which is targeted to be replaced from our platform with something lighter)
- Comparatively heavy to rotors and TUM as it integrates other packages as well for its proper working

*Others found were based or a modified version (according to specific needs) of the ones above*

- **Adding the sensors namely ranging from:**
    LIDAR
    depth cameras
    IR sensors
    range sensors

*Documentation for Student for utilising example control methods when new selected sensors are integrated*

- **Optimising the exercise template using multiprocessing instead of threading in each exercise(benchmarking it with Brain Frequency & htop)**

- **Using simpler models as much as possible or switching to simpler models to avoid breaking of RADI for users without GPU or low-end CPU**

- **Updating the Drone wrapper package according to simulation chosen**

**Issues Created**

- [1](https://github.com/JdeRobot/RoboticsAcademy/issues/1758): MAVROS launch error

**Issues Solved**

- [PR1](https://github.com/JdeRobot/RoboticsAcademy/pull/1759) solves issue [1](https://github.com/JdeRobot/RoboticsAcademy/issues/1758)





