Overview
===

This project was created as the capstone for the EEP520 course at the University of Washington. It features a labyrinth constructed within the Enviro framework, accompanied by a robotic simulation that leverages both Enviro and Elma for maze navigation. The robot employs a wall-following algorithm to trace the maze's right-hand side until it reaches the conclusion. This method is effective for maneuvering through intricate labyrinths that include cul-de-sacs. Upon successfully navigating the entire maze, a notification is displayed in the terminal, and the robot is programmed to restart its journey.

Key challenges
===
Challenge 1:
My initial attempt to set up the Enviro platform with Git Bash was met with a frustrating error that stated, 'the input device is not a TTY.' After some research and troubleshooting, I discovered that using 'winpty' as a prefix for commands in mintty could solve this issue. Implementing winpty in my Windows setup ultimately allowed me to overcome this hurdle. Additionally, I encountered several other configuration challenges specific to Windows but was able to resolve them through online resources and discussions with peers.

Challenge 2:
The goal for the robot was to autonomously navigate through any maze without a predefined route. This objective led me to explore various strategies, including the somewhat counterintuitive 'follow the wall' method. Surprisingly, this approach, where the robot consistently follows one wall, reliably led it to the maze's exit, proving both simple and effective.

Challenge 3:
I faced an unexpected issue where the robot would get stuck due to friction against the maze walls. To address this, I decided to eliminate wall friction in the simulation settings, which simplified interactions and prevented the robot from becoming trapped.

Challenge 4:
Establishing a mechanism to detect the maze's completion presented its own set of challenges. Initially, I placed a block at the maze's end to trigger a collision event with the robot, intending to reset the robot's position. However, this approach led to unexpected 'segmentation errors' and other anomalies. I resolved this by programmatically determining the robot's completion of the maze when it reached a specific position in the upper right corner, avoiding the previous issues.
Install and run the code:
===
You can also build the docker environment, described in env/Dockerfile, yourself, with the following commands. These commands were tested using git bash within VS Code:

    git clone https://github.com/jeffiskater/final_project.git
    docker run -p80:80 -p8765:8765 -v "/$(pwd -W):/source" -it klavins/enviro:alpha bash
    esm start
    enviro

If you are using Windows system, using this command

    winpty docker run -p80:80 -p8765:8765 -v $PWD:/source -it klavins/enviro:v1.61 bash
    

Run and/or use the project
===
When you enter the "enviro" command, the project runs automatically.

Sources:
===
- The following link from allabout Circuits.com was used as the conceptual basis for the wall following code implemented in this project. The truth tables provided are the primary resources utilized.
https://www.allabout Circuits.com/projects/how-to-build-a-robot-follow-walls/
- This project uses Enviro and Elma offered through the EEP 520 course
