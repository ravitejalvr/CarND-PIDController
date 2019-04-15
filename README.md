# PID Controller
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

## Introduction

In this project a PID controller has been implemented to control the steering of the vehicle. The first PID calculates the steering value to minimize the CTE (cross-track error) in order to steer the car towards the center of the lane on the road.

## PID Controller Working

The "P" for proportional makes the car steer in proportion to the cross track error. Setting the "Kp" value, which is the constant for "P", very high, make the car overshoot the desired value as the controller tends to correct itself. The constant attempt to reach the desired value with repeated over-shooting results in high oscillations around the desired value.

The "I" for integral sums up all the CTEs as the time passes by. If too many negative CTE values add up, which means the car has been to left of the middle of the lane for a long time, the aggregated value assists the controller in quickly increasing the steering value to bring the car towards the center to reduce the accumulated error. A low "Ki" value means the controller needs to build up large error for the "I" controller to contribute and stays ineffective. A higher "Ki" value reduces the oscillations significantly.

The "D" for differential adds a smoothing effect by adjusting the controller to respond in proportion to the rate of change of error. It makes the steering more responsive when the CTE is large to reach the desired value faster but gradually reduces its responsiveness as it approaches the desired value to prevent overshooting. A high "Kd" value was increasing the osscillations as the car was becoming too responsive when it was away from the middle of the lane and very low "Kd" value was enough to smoothen out the drastic changes in steering angles.

## PID Tuning

All the three gains were tuned manually. The gains for the steering were tuned to ensure the car was riding smoothly between the lane and was able to finish the lap safely. 

The final values obtained for kp, ki and kd are: 0.155,0.00005 and 0.4 respectively.
