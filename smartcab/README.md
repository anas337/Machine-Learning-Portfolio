[//]: # (Image References)
[image1]: ./Description-Images/smartcab.jpg "image1"
[image2]: ./Description-Images/metrics.bmp "image2"
[image3]: ./Description-Images/pygame.bmp "image3"


# Reinforcement Learning
## Project: Train a Smartcab How to Drive

## Introduction

In the not-so-distant future, taxicab companies across the United States no longer employ human drivers to operate their fleet of vehicles. Instead, the taxicabs are operated by self-driving agents, known as *smartcabs*, to transport people from one location to another within the cities those companies operate. In major metropolitan areas, such as Chicago, New York City, and San Francisco, an increasing number of people have come to depend on *smartcabs* to get to where they need to go as safely and reliably as possible. Although *smartcabs* have become the transport of choice, concerns have arose that a self-driving agent might not be as safe or reliable as human drivers, particularly when considering city traffic lights and other vehicles. To alleviate these concerns as an employee for a national taxicab company is to use reinforcement learning techniques to construct a demonstration of a *smartcab* operating in real-time to prove that both safety and reliability can be achieved.


![image2]


In this project, we work towards constructing an optimized Q-Learning driving agent that will navigate a Smartcab through its environment towards a goal. Since the Smartcab is expected to drive passengers from one location to another, the driving agent will be evaluated on two very important metrics: Safety and Reliability. A driving agent that gets the Smartcab to its destination while running red lights or narrowly avoiding accidents would be considered unsafe. Similarly, a driving agent that frequently fails to reach the destination in time would be considered unreliable. Maximizing the driving agent's safety and reliability would ensure that Smartcabs have a permanent place in the transportation industry.


## Software Requirements

This project uses the following software and Python libraries:

- [Python 2.7](https://www.python.org/download/releases/2.7/)
- [NumPy](http://www.numpy.org/)
- [pandas](http://pandas.pydata.org/)
- [matplotlib](http://matplotlib.org/)
- [PyGame](http://pygame.org/)

This project requires **Python 2.7** with the [pygame](https://www.pygame.org/wiki/GettingStarted) library installed

If you do not have Python installed yet, it is  recommended that you install the [Anaconda](http://continuum.io/downloads) distribution of Python, which already has the above packages and more included. 

Make sure that you select the Python 2.7 installer and not the Python 3.x installer. `pygame` can then be installed using one of the following commands:

Mac:  `conda install -c https://conda.anaconda.org/quasiben pygame`  
Windows: `conda install -c https://conda.anaconda.org/prkrekel pygame`  
Linux:  `conda install -c https://conda.anaconda.org/tlatorre pygame`  

## Starting the Project

For this project, you can find the `smartcab` folder containing the project files on the [SmartCab project GitHub](https://github.com/anas337/Machine-Learning-Portfolio), under the `smartcab` folder. You may download all files related to this project. 

This project contains four directories:

- `/logs/`: This folder will contain all log files that are given from the simulation when specific prerequisites are met.
- `/images/`: This folder contains various images of cars to be used in the graphical user interface.
- `/Description-Images/`: This folder contains various images  used for ethetic purposes.
- `/smartcab/`: This folder contains the Python scripts that create the environment, graphical user interface, the simulation, and the agents. 

- `smartcab.ipynb`: This is the main file where the analysis of the smartcab is provided.
- `smartcab.html`: This is the main file where the analysis of the smartcab is provided.
- `README.md`: This is the main file where the analysis of the smartcab is provided.

In `/logs/` we have the following five files:

- `sim_no-learing.csv`: This file contains the simulation results in a csv format when learning is disabled.
- `sim_default-learning.txt`: This file contains the simulation results in a text format when learning is enabled but not optimized.
- `sim_default-learning.csv`: This file contains the simulation results in a csv format when learning is enabled but not optimized.
- `sim_improved-learing.txt`: This file contains the simulation results in a text format when learning is optimized.
- `sim_improved-learing.csv`: This file contains the simulation results in a csv format when learning is optimized.

Finally, in `/smartcab/` are the following four files:
 
- `agent.py`: This is the main Python file where The Q-learning algorithm is defined.
- `environment.py`: This Python file will create the *smartcab* environment.
- `planner.py`: This Python file creates a high-level planner for the agent to follow towards a set goal.
- `simulator.py`: This Python file creates the simulation and graphical user interface

## Running the Code

In a terminal or command window, navigate to the top-level project directory `smartcab/` (that contains this README ) and run one of the following commands:

`python smartcab/agent.py` or  
`python -m smartcab.agent`

This will run the `agent.py` file and execute the implemented agent code into the environment.


You might want to enable or disable the visual simulation or change its speed in agent.py (simulation update delay and display) to make it go faster or slower, as per your need you .

## Fixing Common PyGame Problems


The PyGame library can in some cases require a bit of troubleshooting to work correctly for this project.it is very helpful to have it working! If you encounter an issue with PyGame, first see these helpful links below that are developed by communities of users working with the library:
- [Getting Started](https://www.pygame.org/wiki/GettingStarted)
- [PyGame Information](http://www.pygame.org/wiki/info)
- [Google Group](https://groups.google.com/forum/#!forum/pygame-mirror-on-google-groups)
- [PyGame subreddit](https://www.reddit.com/r/pygame/)

![image3]

[Analysis Notebook](https://github.com/anas337/Machine-Learning-Portfolio/tree/master/smartcab/smartcab.ipynb) 
Please visit the notebook linked above to follow step-by-step the analysis at various stages to obtain a clear vision about this project.

## Definitions

### Environment
The *smartcab* operates in an ideal, grid-like city (similar to New York City), with roads going in the North-South and East-West directions. Other vehicles will certainly be present on the road, but there will be no pedestrians to be concerned with. At each intersection there is a traffic light that either allows traffic in the North-South direction or the East-West direction. U.S. Right-of-Way rules apply: 
- On a green light, a left turn is permitted if there is no oncoming traffic making a right turn or coming straight through the intersection.
- On a red light, a right turn is permitted if no oncoming traffic is approaching from your left through the intersection.
To understand how to correctly yield to oncoming traffic when turning left, you may refer to [this official drivers? education video](https://www.youtube.com/watch?v=TW0Eq2Q-9Ac), or [this passionate exposition](https://www.youtube.com/watch?v=0EdkxI6NeuA).

### Inputs and Outputs
Assume that the *smartcab* is assigned a route plan based on the passengers? starting location and destination. The route is split at each intersection into waypoints, and we may assume that the *smartcab*, at any instant, is at some intersection in the world. Therefore, the next waypoint to the destination, assuming the destination has not already been reached, is one intersection away in one direction (North, South, East, or West). The *smartcab* has only an egocentric view of the intersection it is at: It can determine the state of the traffic light for its direction of movement, and whether there is a vehicle at the intersection for each of the oncoming directions. For each action, the *smartcab* may either idle at the intersection, or drive to the next intersection to the left, right, or ahead of it. Finally, each trip has a time to reach the destination which decreases for each action taken (the passengers want to get there quickly).  If the allotted time becomes zero before reaching the destination, the trip has failed.

### Rewards and Goal
The *smartcab* will receive positive or negative rewards based on the action it as taken. Expectedly, the *smartcab* will receive a small positive reward when making a good action, and a varying amount of negative reward dependent on the severity of the traffic violation it would have committed. Based on the rewards and penalties the *smartcab* receives, the self-driving agent implementation should learn an optimal policy for driving on the city roads while obeying traffic rules, avoiding accidents, and reaching passengers? destinations in the allotted time.
