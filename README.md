## Project: Search and Sample Return


### A comprehensive discussion around implementation decisions can be found on the Documentation of the project.

---

[//]: # (Image References)

[image1]: ./misc/rover_image.jpg



**Libraries to be installed**
numpy~=1.19.4
eventlet~=0.29.1
Pillow~=7.0.0
Flask~=1.1.2
opencv-python~=4.4.0.46
matplotlib~=3.3.3
sklearn~=0.0
scikit-learn~=0.23.2
Keras~=2.4.3
scikit-image~=0.18.0
python-engineio==3.13.0
python-socketio==4.6.1

Make sure to create an environment and intall the right packages' versions to run the project .

**How to run**

In your anaconda base environment make sure to execute the command : conda activate <New Environment Name> in order to move to the new environment you have created .
Open your simulator and choose Autonomous mode. 
Then if you are using the Linux operating system type in your terminal <New Environment>: python drive_rover.py => this command should run the drive_rover.py file and then the project will run in the simulator .

**Results**

![alt text][image1]

The Rover does a good job following the left wall avoiding trouble by getting unstuck if necessary. It also collects most of the sample rocks it finds on its path. It maps up to 97% of the terrain with a fidelity of 73.5%.

**Return to the starting point**

The final piece of the puzzle was to have the Rover to go back to the initial position and come to a complete stop.
There are many ways to implement this but the easiest (and for what I would go first) would be to save the initial position when the simulation starts and query if the Rover is close to this position AND all (or most) of the rock samples have been already collected. This condition would bring the Rover to a new state: "home"
Once in the home state the Rover would, just like for the rock state, slow down and steer on the direction of the initial position, stoping when close enough.

**Improvements and Future Work**

Focusing on the project requirements we will try to increase the fidelity up to 95% .



**Collect all the sample rocks**

One of the problems that I notice with my state machine is that it goes back to a previous state whenever a rock is no longer in sight. This is problematic for rocks that are hidden under tight spots. When the Rover approaches and breaks violently that causes the camera to miss the rock for a few frames causing the state to go back to forward mode skipping the rock completely.
To solve this would require improvements on both the state tracking and also the control of the Rover to avoid slamming the breaks when approaching a rock.






