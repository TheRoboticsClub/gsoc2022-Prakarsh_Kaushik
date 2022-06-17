---
layout: post
title: Mid way into the Bonding  
date: 2022-06-03 20:00:00 +0530
tags: [GSoC, simulators, robotics_academy, exercises, backend, frontend]
# permalink: /community-bonding/
description: Chosen deliverables from the presented choices in the meeting.
---

# **Community Bonding 2**

> *The next goal of the community bonding period was to layout the chosen deliverables after discussion in the meeting with the mentors. This choice is based in the goals of the organisation as well which ones would I like to work on. The choice is made because of the limited period of coding and so much to contribute on. For the choices regarding the deliverables, please refer to the previous community bonding* [post.](https://theroboticsclub.github.io/gsoc2022-Prakarsh_Kaushik/2022/05/27/community-bonding.html) The calendar is presented with integrated timeline for the selected 


## **Decision time?!**

**Some parameters to consider for decision:**

- Total working hours: 175 hrs
- Coding period decided with mentor: from 17 June (as weekly meet is on every Friday)
- Period assigned for 175 hrs: 17 June to 9 September (12 weeks)
- Decided average weekly working hours: 20 hrs (3 hrs per day (approx))
- Doing the rough maths for 175 hrs: 175/20 :> 9 weeks approx

*As this is the average working hours to put in so 9 weeks can fluctuate from from 8 to 12 weeks depending on the number of hours invested and the difficulty of the deliverables when encountered.*



**These are the deliverables with the reasons of choosing them for consolidation of drone based exercises and for extending the backend:**

**Distribution of decided 9 weeks:**

*Backend needs to be developed first before moving to the frontend*

### **`Backend (6-7 weeks)`**:

- **Chosen lighter simulator to replace PX4 SITL:**

[RotorS](https://github.com/ethz-asl/rotors_simulator) is a MAV gazebo simulator(Micro Aerial Vehicle (MAV) simulation framework). It provides some multi-rotor helicopter models such as the AscTec Hummingbird, Pelican, and Firefly, but the simulator is not limited for use with these multicopters.

![Structure of the packages]({{ site.baseurl }}/assets/blog_images/community_bonding/rotors_pkg_struct.png){: .align-center}

*TODO: develop the coding framework for integrating this sim with drone exercises*

Alloted time: 1.5 weeks

- **Adding sensors:** 

planar LIDAR, depth cameras, IR sensors, range finder

*TODO: find sensor xacro gazebo plugins*

Alloted time: 1.0 weeks

- **Updating drone_wrapper**

*TODO: update the drone_wrapper pacakge with the rotors simulator replacing the PX4 SITL*

Alloted time: 1.5 weeks

-  **Multiprocessing**

*TOD0: add the multiprocessing architecture to all drone based exercises for increasing the performance and benchmarking the results*

Alloted time: 2-3 weeks


### **`Frontend (consolidation of exercises)(2-3weeks)`**:

- **1st week:**

**[Rescue People](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/rescue_people)**:
- Lightning conditions can be varied (day and night) and accordingly an led light model can be added for the student to switch on for getting better camera input
- Random initial position for the people to rescue

**[Power Tower inspection](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/power_tower_inspection)**:
- Change size of the power towers and hence the defect to get a real life size ratio of drone and power tower
- Change size of wires to greater in diameter

- **2nd week:**

**[Package delivery](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/package_delivery)**:
- Integrating QR code with the package to get coordinates for the delivery
- Multiple package delivery  with del location on the qr code(only warehouse oc is known)
- Improved world to incorporate multi package delivery(buildings where package has to be delivered & landing marker can also be on top of the building)

- **3rd week:**

**[Drone Hangar](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/drone_hangar)**:
- Standardisation of difficulty level for obstacle course in the hangar
- More than one colour of obstacle and their changing velocities to decide difficulty of the exercise 
- Different models added as obstacle namely cylinders, hoops,etc
- Adding checkpoints in between the obstacles to register for the student
- Adding a reset functionality whenever the drone hits the obstacles like a game
- Multiple size of obstacle slabs to standardise difficulty level
- Add depth camera to drone


**[Labyrinth escape](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/labyrinth_escape)**:
- Multiple models of labyrinth to load (including circular)
- More realistic model of labyrinth
- More input signals instead of four with problem of finding the inclined angle of arrow for student (can be used in case of circular labyrinth)
- Add planar lidar sensor

*One of the exercise in 3rd week may need additional time after 9 weeks*

**Adding documentation required**


### Remaining 3 weeks from 12 weeks:

- **1st week:**

**[Drone Cat & Mouse](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/drone_cat_mouse)**:
- Add teleop of mouse
- Improve the the control code of mouse for its autonomous movements
- on-the-fly selection of Gazebo world(like follow line) for difficulty(worlds with no obstacles to large obstacles)

- **2nd week:**

**[Follow Turtlebot](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/follow_turtlebot)**:
- Add teleop of turtlebot
- Change vel from constant to variable
- Add april tag on top on turtlebot instead of colour plate

- **3rd week:**

**[Visual lander](https://jderobot.github.io/RoboticsAcademy/exercises/Drones/visual_lander)**:

- Creating a road track on which the car will move(only if teleoperation is disabled) (for boat a set of waypoints)
- Updating the visual marker to more visually appealing model like launchpad or an April Tag can be used
- More visually appealing world can be created with buildings and other stationary models after integrating a road track

**Adding documentation required**
