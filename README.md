# Manipulability Transfer
The MATLAB codes show simple examples for the manipulability transfer between a teacher and a learner. The former
demonstrates how to perform a task with a desired time-varying manipulability profile, while the latter reproduces the
task by exploiting its own redundant kinematic structure so that its manipulability ellipsoid matches the demonstration.

This approach offers the possibility of transferring posture-dependent task requirements such as preferred directions
for motion and force exertion in operational space, which are encapsulated in the demonstrated manipulability ellipsoids.

The proposed approach is first built on a GMM/GMR model that allows for the geometry of the SPD manifold to encode and
retrieve appropriate manipulability ellipsoids. This geometry-aware approach is later exploited for redundancy resolution,
allowing the robot to modify its posture so that its manipulability ellipsoid coincides with that of a demonstration.


### Code description

	- demo_ManipulabilityTransfer01
		This code shows how a robot can exploit its redundancy to modify its manipulability so that it
		matches, as close as possible, a desired manipulability ellipsoid (possibly obtained from another
		robot or a human). The approach evaluates a cost function that measures the similarity between
		manipulabilities and computes a nullspace velocity command designed to change the robot posture
		so that its manipulability ellipsoid becomes more similar to the desired one. The user can:

		1. Define the number of states of the model
		2. Choose two different cost functions to be minimized through redundancy resolution
		3. Modify the robot kinematics by using the Robotics Toolbox functionalities
		

	- demo_ManipulabilityTransfer02
		This code shows how a robot learns to follow a desired Cartesian trajectory while modifying its
		joint configuration to match a desired profile of manipulability ellipsoids over time. The
		learning framework is built on two GMMs, one for encoding the demonstrated Cartesian trajectories,
		and the other one for encoding the profiles of manipulability ellipsoids observed during the
		demonstrations. The former is a classic GMM, while the latter is a GMM that relies on an
		SPD-matrices manifold formulation. 
		
		The demonstrations are generated with a 3-DoFs planar robot that follows a set of Cartesian
		trajectories. The reproduction is carried out by a 5-DoFs planar robot. The user can:

		1. Define the number of states of the models
		2. Define the number of iterations for the nullspace redundancy resolution
		3. Choose two different cost functions to be minimized through redundancy resolution
		4. Set the gradient step
		5. Modify the robots (teacher or student) kinematics by using the Robotics Toolbox
		functionalities
		
		
	- demo_ManipulabilityTransfer02b
		This code implements the same manipulability transfer approach as 'demo_ManipulabilityTransfer02'. 
		However, this code used a numerical approximation for the gradient of the cost function, which is 
		crucial to speed up computation times (specially when Stein divergence is used). The user can:

		1. Define the number of states of the models
		2. Define the number of iterations for the nullspace redundancy resolution
		3. Choose two different cost functions to be minimized through redundancy resolution
		4. Set the gradient step
		5. Modify the robots (teacher or student) kinematics by using the Robotics Toolbox
		functionalities
		

### References  
	
	[1] Rozo, L., Jaquier, N. Calinon, S. and Caldwell, D. (2017). Learning Manipulability Ellipsoids for
	Task Compatibility in Robot Manipulation. IEEE Intl. Conf. on Intelligent Robots and Systems (IROS).	

### Authors

	Leonel Rozo, Noemie Jaquier and Sylvain Calinon
	http://leonelrozo.weebly.com/
	http://programming-by-demonstration.org/
		
	This source code is given for free! In exchange, we would be grateful if you cite the following
	reference in any academic publication that uses this code or part of it:

	@article{Rozo17IROS, 
	  author 	= "Rozo, L. and Jaquier, N. and Calinon, S. and Caldwell, D. G.",
	  title  	= "Learning Manipulability Ellipsoids for Task Compatibility in Robot Manipulation",
	  booktitle 	= "Intl. Conf. on Intelligent Robots and Systems ({IROS})",
	  year   	= "2017",
	  month  	= "September",
	  pages  	= "" 
	}

