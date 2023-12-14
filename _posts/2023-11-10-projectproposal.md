---
layout: post
title: Project Proposal
permalink: /projectproposal
---

## What is the main idea of the project?

- The project has two tiers: First, using computer vision on a flying drone to stitch together a map of the environment. Second, using that map to generate an optimal path for the drone from point A to point B.
- Because the drone can maneuver in 3D, the optimal path will be a 3D path.

## What hardware platforms or interfaces are you planning to use, if any?

- We are planning to use a quadcopter. In particular, we will interface with a DJI mavic mini.
- [RosettaDrone](https://github.com/RosettaDrone/rosettadrone) is a framework for developing and testing software for DJI drones. It provides a MAVLink wrapper which allows users to control DJI drones using MAVLink-speaking ground control stations and offers tools and features for implementing and testing AI scripts.

<figure
    style=
        "display: block;
        margin-left: auto;
        margin-right: auto;
        width:90%;"
>
    <img 
        src="./images/drone_control_components.png"
        alt="Drone Control Components"
    >
</figure>

## Provide some motivation for your project. Why does your team want to pursue this? What possible applications does the project have? Given our discussions in class, are there possible implications for society? (Note: We’re not expecting a lengthy analysis, but some ideas and consideration.)

- Alex: I am interested in the intersection of computer vision and a physical robotics system and how the two can complement each other. Additionally, I am interested in exploring pathfinding algorithms and how to optimize them for drone navigation; what is the tradeoff between shortest path and optimal path for safely maneuvering?
- Rajiv: I am interested in the opportunity to use the outputs of one algorithm to feed into another, and the iterative development process. I like that although this project is multifaceted and complex, there are degrees of completion which have been accounted for from the initial structuring to provide a safety net in cases of unexpected difficulty.
- Possible Applications: Mapping and pathfinding are both important problems for autonomous navigation. Uses include surveying new areas and finding/building roads between places of interest.
- Implications for Society: See below.

## How are you planning to engage with the Ethics and Responsible Use Statement part of the project?

- Drones with autonomous capabilities will inherently increase the power of those at the top of power structures and decrease the ability of those at the bottom to resist. This has been a problem of technology in general before the advent of autonomous robotics, but these greater levels of autonomy have allowed for the manpower limitations to be removed from oppressive regimes of all forms. With enough money, now, a dictator could surveil all corners of their control and crush any resistance. We look to talk about the dangers of an enforcement force which scales with financial investment in our ethics statement, and talk about ways that we as a robotics community can work to ensure the technologies we build are for the good of all humans.

## What topics will you explore and what will you generate? What frameworks / algorithms are you planning to explore (do your best to answer this even if things are still fuzzy)? What is your MVP? What are your stretch goals?

- We will explore the following topics
  - Interfacing between Python script and android/iOS drone SDK.
  - Visual SLAM
  - Object detection for start/goal
  - Pathfinding
- MVP
  - Manually fly a drone around the Academic Center, stream the camera feed back to a laptop, perform visual SLAM on the camera feed to generate a map of the space. While mapping, recognize and detect the starting and ending positions indicated with some type of marker.
- Stretch Goal
  - Using the generated map and the locations of the start/end markers, find the optimal path from start to end, balancing speed, maneuverability, and the drone’s safety.

## Outline, in detail, what you intend to have accomplished by each of the milestones.

- Friday 11/17
  - Have a drone and be able to teleoperate and receive data (camera feed, altitude, odometry).
- Tuesday 12/5
  - Teleoperate drone to collect video data to be used for mapping. Have a first pass at a visual SLAM algorithm working.

## Conduct a [pre-mortem](https://comprobo23.github.io/assignments/performing_a_project_premortem.pdf) on your project. Write at least 5 risks to the success of your project (where success could be in relation to your learning or the final project output)

- Roadblocks between existing platforms would quickly kneecap this project. We are working with a mobile SDK which interacts with a java program which interacts with our python environment - we rely on the stability of things outside of our python code
- Difficulty in onboarding onto these platforms, time to get up-to-speed
- Overscoping - we believe that we have structured our project such that there are intermediate checkpoints that we can reach even if we don’t hit the desired final product; however, because neither of us have worked with SLAM before, it is possible that it will take longer than we expect to get a working algorithm.
- Unanticipated challenges with hardware bringup. Both of us agreed that we did not want setting up hardware to be a major part of this process, but it is possible that it takes us longer than we expect to get a drone setup working, which will take time away from algorithmic development.
- Low communication bandwidth between the drone and our computer. As mentioned above, we are planning to communicate with the drone through a series of channels, any one of which could be a limiting factor in how quickly we can send and receive data. This is important because we are planning on doing the data processing / computing on our own device due to low compute power on the drone. This could limit how quickly we can create a mapping of acceptable fidelity.

## Given each of your YOGAs, in what ways is this project well-aligned with these goals, and in what ways is it misaligned? If there are ways in which it is not well-aligned, please provide a potential strategy for bringing the project and your learning goals into better alignment. There should be an individual section for each person on the team addressing the fit between the YOGA and the project topic.

- Rajiv: This project is well-aligned with each of my learning goals. My first learning goal concerns learning to use external tools quickly and effectively to implement them into my development process: because our first goals include onboarding ourselves onto at least 2 new open-source tools and 1 physical robot, I think this first goal will have a lot of new data fed to its metrics. My second goal involves using data creatively as well as integrating multiple data streams into one picture of the world. Because of the access to data like heading and altitude as well as the focus on computer vision, I think that this project will give me plenty of opportunities to stretch how I use a sparse but diverse data field to my advantage. My third and final goal concerned development cycle compartmentalization through git issues and branches: since Alex and I had great success pursuing this structure the last time we worked together on the localization project, I expect this project to also follow suit and display my resounding success at implementing this cycle into my own workflows.
- Alex: I think that this project directly correlates with two of my learning goals, and could potentially be brought in line with the third. I have a learning goal directed towards exploring the interaction between computer vision and a physical robotic system, and this project completely captures that. I have another learning goal directed towards social context for robotics and real-world implications of the technology; I think that the Ethics Statement and Responsible Use helps bring that goal into focus by thinking about how this project fits into a larger context. My third goal is focused on exploring the difference between simulated and physical testing; I think it is possible for this project to incorporate development that is supported by both physical and simulated testing, which would give me a way to meet this third learning goal as well.
