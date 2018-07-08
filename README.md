# CarND-Controls-MPC
Self-Driving Car Engineer Nanodegree Program

---

## Steps
1. Fitting a line based on road waypoints
2. Implementing MPC class.
3. Calculating actuator values based on current state
4. Testing and tuning values.

## Model
1. px - current x position of vehicle in global coordinate
2. py - current y position of vehicle in global coordinate
3. ptsx - x position of waypoints on track in global coordinate
4. ptsy - y position of waypoints on track in global coordinate
5. psi- orientation of vehicle
6. v - current velocity 
7. delta - current steering of angle of car
8. a - current throttle

## polynomial fitting
1. Transfer points from global coordinate to car's coordinate
2. using polyfit funtion polynomial is generated using waypoints

## Latency
1. To account for 100ms latency between controls generated and actually applied, I predicted where car will be after 100ms. Predicted state based on this and fed into true model. Here as well coordinated were transferred from global coordinate system to car's coordinate system.

## Tuning
1. Tried different values of N and dt, earlier used 20 and 0.2 but fount it is slow to react. Settled with 15 and 0.12. If I increase N, I found model to be slow. 

## Results
1. Build is generated locally with no errors and verified with simulator that no car leaves track.
