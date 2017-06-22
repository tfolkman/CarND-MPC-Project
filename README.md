# CarND-Controls-MPC
Self-Driving Car Engineer Nanodegree Program

---

## Cost Function

For my cost function, I followed the equations from the "Mind the Line" quiz which incorporated the reference state, actuators, and sequential actuations. I also took the advice from the workshop and added extra weight to cte and epsi. This allowed the car to go fast on the straight-aways, but slow down enough on the turns.

## Hyper-parameters

For my model, I chose a value of 10 for the time step length and a value of 0.1 for the elapsed duration between time steps. This brings us to a total prediction horizon of one second. I actually started with these values from following some of the walk-through provided. I experimented with increasing the predicted horizon to 2 seconds by increasing the time step length to 20, but didn't see much improvement and it took longer to run. I didn't try increasing the elapsed duration as it was recommended to use a value as small as possible. Also, going below 0.1 didn't seem reasonable to me.

## Preprocessing Waypoints

I did preprocess the waypoints such that the x and y values were 0. This made the rest of the calculations easier. 

## Latency

To deal with latency, I just used the kinematic model equations to move my state values into the future by 100 milliseconds.