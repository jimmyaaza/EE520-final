Overview
===

This initiative was developed as the culminating project for the EEP520 class at the University of Washington. It showcases a complex maze designed using the Enviro framework, paired with a simulated robot that utilizes both Enviro and Elma for its navigation tasks. The robot adopts a strategy of following the right wall of the maze, allowing it to effectively navigate through the convoluted paths and dead ends. This technique proves to be efficient in tackling mazes with complex designs. Once the robot completes its journey through the maze, a completion message is shown in the terminal, and the robot is set to automatically begin its path anew.

Key challenges
===

Challenge 1:
Initially, my strategy involved placing a block at the maze's terminus to initiate a collision event with the robot, aiming to reset its position subsequently. Unfortunately, this method resulted in unforeseen 'segmentation errors' among other complications. To circumvent these obstacles, I adopted a programmatic solution to confirm the robot's maze completion upon reaching a predetermined location in the upper right corner, thus eliminating the earlier encountered problems. Concurrently, the robot's mission was to independently find its way through any maze without a set path. This ambition propelled me to investigate a variety of navigational techniques, amongst which the 'follow the wall' method stood out. Despite its initial counterintuitiveness, this strategy of having the robot persistently trail one wall consistently guided it to the maze's exit. This approach was both unexpectedly straightforward and efficacious, highlighting its effectiveness in ensuring the robot's successful navigation through mazes of any complexity.

Challenge 2:
I ran into a problem where the robot kept getting stuck because of the friction with the maze walls. To fix this, I changed the simulation settings to remove wall friction. This made things simpler and stopped the robot from getting stuck.


Build and use instructions:
===
General usage:
	Run the docker container in the command window, please follow the step in the Setup Instruction.

Setup Instruction:
	1. Open up CMD or docker  
      2. Navigate to the direction of the file folder in CMD  
      3. Using docker run -p80:80 -p8765:8765 -v $PWD:/source -it klavins/enviro:v1.2 bash to install and start using enviro.  
      4. Type "esm start" to start.  
      5. Type "enviro" to run the program.   
      6. Use "ctrl-c" to stop the program.  
      7. Use "exit" to exit the Docker container and stop it  

Sources:
===
- The following link from Medium.com was used to determine how to program a robot to follow the walls to guide it to its exit: https://andrewyong7338.medium.com/maze-escape-with-wall-following-algorithm-170c35b88e00
- This project uses Enviro and Elma offered through the EEP 520 course
