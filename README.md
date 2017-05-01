# Unscented Kalman Filter Project:
Implemented unscented Kalman filter using the CTRV motion model. We will be using the bicycle simulation data. 

## Output:
### RMSE:

0.0698414

0.0827661

0.336433

0.248774


### Details:
Kalman filters have the same three steps:

1. Initialization
2. Prediction
3. Update

A standard Kalman filter can only handle linear equations. Both the extended Kalman filter and the unscented Kalman filter allow you to use non-linear equations; the difference between EKF and UKF is how they handle non-linear equations. But the basics are the same: initialize, predict, update.

Nonlinear state estimation is a challenge problem. The Extended Kalman Filter (EKF) has become a standarded formulation for nonlinear state estimation. However, it may cause significant error for highly nonlinear systems because of the propagation of uncertainty through the nonlinear system.

The Unscented Kalman Filter (UKF) is a novel development in the field. The idea is to produce several sampling points (Sigma points) around the current state estimate based on its covariance. Then, propagating these points through the nonlinear map to get more accurate estimation of the mean and covariance of the mapping results. In this way, it avoids the need to calculate the Jacobian, hence incurs only the similar computation load as the EKF.


## Dependencies

* cmake >= v3.5
* make >= v4.1
* gcc/g++ >= v5.4

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./UnscentedKF path/to/input.txt path/to/output.txt`. You can find
   some sample inputs in 'data/'.
    - eg. `./UnscentedKF ../data/obj_pose-laser-radar-synthetic-input.txt`

## To do:
1. Use NIS to help tune your parameters
2. Visualize the ground truth, sensor measurements, and your Kalman filter results
3. Compare UKF and EKF project results. Both projects use the same data file. RMSEshould be lower for the UKF project than the EKF project

## References:

1. https://github.com/balzer82/Kalman
2. https://www.youtube.com/watch?v=CaCcOwJPytQ&list=PLX2gX-ftPVXU3oUFNATxGXY90AULiqnWT&index=1
3. https://medium.com/@anthony_sarkis/what-is-a-kalman-filter-and-why-is-there-an-unscented-version-bc5f6e77c509
4. https://carnd.slack.com/messages/C4BN20M33/convo/C4BN20M33-1493506676.583204/
5. https://classroom.udacity.com/nanodegrees/nd013/syllabus
6. https://medium.com/tag/kalman-filter
