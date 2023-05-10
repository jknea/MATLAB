# Bouncing Ball Dynamics  
This MATLAB livescript is for modeling a bouncing with initial position x0 and initial velocity v0 conditions for a given time period from t = 0s to some final time.  The system of a ball under the external input of gravity is modeled in state-space and solved using the ODE45 numerical solver.  The ground surface is represented as a height condition check in the ODE45 event function.  
## State-Space Reperesentation of the Problem
System is defined as x'' = -g  (input u = g)   
We then have:  z2' = x'', z2 = x', z1 = x  
The state vector z = [z1; z2]  
z' = [z1'; z2'] = [z2; z2'] = Az + Bu = [0 1; 0 0]z + [0; -1]u  
## Position vs. Time for Various Initial Conditions  
![image](https://github.com/jknea/MATLAB/assets/80857526/0f0e10cf-359b-44f9-91f5-51ded0d99f68)
## Velocity vs. Time for Various Initial Conditions  
![image](https://github.com/jknea/MATLAB/assets/80857526/8943a4ea-a9e0-4bc6-8f27-803e637c6c15)
## Zeno Effect  
The ball will technically never stop bouncing although the magnitude of height and velocity will become infinitessimal.  The code implements a check on the velocity and stops the simulation once it reaches a very small value to prevent stalling due to the Zeno effect.  
