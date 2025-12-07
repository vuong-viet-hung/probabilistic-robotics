
---
Robot environment:
- The robot acquires information about its environment using its **sensors**.
- The robot influences its environment through its **actuators**.
---
State:

- **Dynamic state** vs **Static state**

- State: $x$, state at time $t$: $x_t$

- Typical state variables:
	- Robot:
		- **Pose**:
			- 6 state variables: 3 variables for location (Cartesian coordinates), 3 variables for orientation (pitch, roll, yaw)
			- For robots confined to planar environments: 3 variables (2 location coordinates in the plane and its heading direction (yaw))
		- **Kinematic state** (configuration of the robot’s actuators):
			- The joint angles of revolute joints
		- **Dynamic state** (robot velocity and the velocities of its joints):
			- 6 velocity variables, one for each pose variables
	- Environment:
		- **Location and features of surrounding objects in the environment**:
			- **Landmarks**: distinct, stationary features of the environment that can be recognized reliably
		- **Location and velocities of moving objects and people**

- **Complete state** vs **Incomplete state**:
	- A state $x_t$ will be called complete if past states, measurements, or controls carry no information that would help us predict the future more accurately. **Markov chains** are temporal processes that meet these conditions.

- **Continuous state** vs **Discrete state** vs **Hybrid state**
---
Environment Interaction:

|                  | **Measurement**                                                                                              | **Control actions**                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| Interactions     | **Measurement**: The robot gather information about the state through its sensors.                           | **Control actions**: The robot influence the state of its environment through its actuators.                              |
| Data             | **Environment measurement data**: $z_t$ provides information about the state of the environment at time $t$. | **Control data**: $u_t$ provides information about the change of state in the environment in the time interval $(t-1;t]$. |
| Set measurements | $z_{t_1:t_2}=z_{t_1},z_{t_1+1},z_{t_1+2},...,z_{t_2}$                                                        | $u_{t_1:t_2}=u_{t_1},u_{t_1+1},u_{t_1+2},...,u_{t_2}$                                                                     |
| Information      | Provides information about the environment’s state $\Rightarrow$ increase the robot’s knowledge              | Inherent noise in robot actuation and the stochasticity of robot environments $\Rightarrow$ induces a loss of knowledge   |
- Even if the robot does not perform any action itself, state usually changes. Thus, we will assume that the robot always executes a control action
- Even though **odometers** are sensors, we will treat odometry as control data, since they measure the effect of a control action.
---
