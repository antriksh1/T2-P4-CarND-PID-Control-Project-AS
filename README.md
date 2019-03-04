# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Objective:
The goal of this project was to implement a simple PID Controller i.e. Proportional - Integeral - Derivative Controller, which controls the vehicle steering input based on how far away from the correct path it is. 


---

## Reflection:

### Effects of each of the P, I, D components

- Proportional (P): This controls the error proportional to the value of the error. Therefore it results in overshooting. By itself, it also seemed to be the most aggressive controller, because the higher the error, the more aggressive the steering, i.e. the more impactful it is to try to bring the car back to the center. 

Having a just a P controller resulted in a constantly oscillating controller, because of overshooting.
This overshooting led to more correction, which led to higher steering inputs, which in-turn led to higher over-shooting, and very quickly the oscillations rose to a very high degree. 

Overall, it has the correctional effect in bringing the car back to its intended path.

- Integral (I): This controls the error of the past values. As described in lectures, this is the intergral term, i.e. area between the true-path and the path-taken in the past. This controller tries to eliminate the residual cumulative error. 

Having just an I controller resulted in a car which just drifted to one side and eventually started going in circles. This is the result of accumulation of error and therefore the steering correction eventually increasing.

Overall, it had the effect of controlling past errors.

### Choosing the final hyperparameters

---

### Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

Fellow students have put together a guide to Windows set-up for the project [here](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/files/Kidnapped_Vehicle_Windows_Setup.pdf) if the environment you have set up for the Sensor Fusion projects does not work for this project. There's also an experimental patch for windows in this [PR](https://github.com/udacity/CarND-PID-Control-Project/pull/3).

### Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

