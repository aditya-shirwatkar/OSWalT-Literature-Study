# OSWalT Literature Study
###### tags: `OSWalT` `Controls` `Mechanical Design`

- [Table of Contents](#oswalt-literature-study)
  * [:memo: List of Papers Read](#-memo--list-of-papers-read)
  * [Papers](#papers)
    * [Vertigo](#vertigo)
        + [Abstract](#abstract)
        + [Technical Background](#technical-background)
    * [Design and Development of a Novel Spherical UAV](#design-and-development-of-a-novel-spherical-uav)
      + [Abstract](#abstract-1)
      + [System Design and Structure](#system-design-and-structure)
      + [Drawbacks](#drawbacks)
      + [Conclusion](#conclusion)
    * [Design and Analysis of a Flying-crawling Spherical Robot for Multi-mode Movement](#design-and-analysis-of-a-flying-crawling-spherical-robot-for-multi-mode-movement)
      + [Abstract](#abstract-2)

> This note is the quick study of previous works done for a wall climbing and omnidirectional spherical system.

## :memo: List of Papers Read

- [x] [VertiGo - a Wall-Climbing Robot including Ground-Wall Transition](#Vertigo)
- [x] [Design and Development of a Novel
Spherical UAV](#Design-and-Development-of-a-Novel-Spherical-UAV)
- [ ] [Design and Analysis of a Flying-crawling Spherical Robot for Multi-mode Movement](#Design-and-Analysis-of-a-Flying-crawling-Spherical-Robot-for-Multi-mode-Movement)

# Papers


## Vertigo

#### Abstract 
VertiGo is a wall-climbing robot that is capable of transitioning from the ground to the wall, The robot has two tiltable propellers that provide thrust onto the wall, and four wheels. One pair of wheels is steerable, and each propeller has two degrees of freedom for adjusting the direction of thrust. By transitioning from the ground to a wall and back again, VertiGo extends the ability of robots to travel through urban and indoor environments.

The robot is able to move on a wall quickly and with agility. The use of propellers to provide thrust onto the wall ensures that the robot is able to traverse over indentations such as masonry. The choice of two propellers rather than one enables a floor-to-wall transition - thrust is applied both towards the wall using the rear propeller, and in an upward direction using the front propeller, resulting in a flip onto the wall.

#### Technical Background
A key research problem in the design of VertiGo robot was to maximize the ratio between thrust output and vehicle weight. Weight is minimized by using a central carbon fibre baseplate, while 3D-printed parts in conjunction with carbon-rods are used for more complex three dimensional structures like the wheel suspension or the wheels themselves. The baseplate provides mounting points for two thruster modules and the wheel suspensions. It also serves as a carrier for all the electronic parts and wires. The thrusters are mounted using a two-ringed Cardan Suspension. Integrated servo motors allow the inner and outer ring to be moved independently from one another. This supports the generation of all the forces required to drive on the floor, on walls and theoretically even on the ceiling. The wheels are mounted with a double wishbone suspension based on model- car oil dampers, but they are not propelled in any way.

The full design has eight individually controlled actuators. To enable a human operator to conveniently drive the vehicle in a way similar to common RC-cars, an onboard computer is incorporated as a controller. It uses data from a 6-axis IMU in the centre of the robot as well as from two infrared distance sensors mounted in front to estimate its orientation in space. Based on this attitude information, the controller then devises the best positions for all actuators to achieve a desired user input.



---


## Design and Development of a Novel Spherical UAV

>Full paper [here](https://dspace.lib.cranfield.ac.uk/bitstream/handle/1826/11192/Design_and_development_of_a_novel_spherical_UAV-2016.pdf?sequence=3&isAllowed=y)


#### Abstract
This paper presents the design and system integration of a novel coaxial, flap actuated, spherical UAV for operations in complex environments, such as buildings, caves or tunnels. The spherical design protects the inner components of the vehicle and allows the UAV to roll along the floor if the environment permits. Furthermore, the UAV can land and takeoff from any orientation and come into contact with objects without putting the propellers
at risk. Flaps at the base of the sphere will generate roll and pitch moments as opposed to conventional swash plate designs while the coaxial setup will provide the necessary yaw moments and increase in thrust to volume ratio of the system. The flaps, placed below the propellers allow for decoupled roll and pitch control in a thrust vectoring manner. The final result of this design is a well-protected, compact, easily controlled, flexible and agile UAV for operations in complex environments. The spherical UAV was successfully flight tested on a number of occasions with various PD and µ-synthesis robust control systems and was observed to be easily stabilised and resistant to external disturbances to certain extent.

### System Design and Structure

The physical shape of the aerial vehicle, the choice of control actuators, the choice of hardware and electrical/electronic design are a vital step to ensure that the final aerial platform is one that is capable of supplying enough thrust to lift-off, enough control authority for stabilisation, enough computational power for control/sensor fusion and can supply the required voltage and current to all components at the same time. This section is subdivided into two main parts, namely: the mechanical design part; and the system integration part.

#### Mechanical Design

The light-weight and rigid mechanical structure of the system is shown in Fig. 1. It was designed such that it could provide maximum protection but also allow the aerial vehicle to manoeuvre freely and efficiently in a challenging environment. The compact size of the vehicle was achieved by the appropriate selection of components such as the ultra-nano-size servos and the 3-blade propellers.

![](https://i.imgur.com/y1UfdCr.png)

the key role of the four individually controlled flaps-surfaces, is to control the vehicle during flight. They have a 90o separation around the inner circumference of the vehicle, and are located below the propellers along the vehicles x and y-axis. Therefore, a roll moment can be generated by constraining the flaps along the x-axis to move together whilst a pitch moment can be generated by constraining the flaps along the y-axis to move together. The yaw moment can be produced by the differential propeller speed.

#### Control Design

The design of spherical UAV allowed for decoupling of the lateral, longitudinal and the vertical dynamics. Flaps along the body $x$-axis were constrained to move together, thereby controlling the lateral dynamics (namely roll) and the flaps along the body $y$-axis were constrained to move together, thereby controlling the longitudinal dynamics
(namely pitch). The vertical dynamics of the spherical UAV was composed of the thrust along the body $z$-axis and the torque about the body $z$-axis, both generated by the coaxial motor-propeller sets. The lateral and longitudinal dynamics were modelled based on pure theory and the mass properties obtained from a 3D CAD drawing and therefore had an amount of uncertainty, whereas  Thrust and torque tests about the body z-axis were carried out to obtain mappings between the input PWM to motor drivers and the thrust and torque produced. In this way the vertical dynamics of the spherical UAV could be modelled with minimum uncertainty.

Non-linear, rigid body dynamics were used for the spherical UAV and control algorithms were designed about the hovering trim state of the sphere that introduces even more uncertainty. For these reasons, a Proportional Differential (PD) controller was designed for the vertical dynamics and a robust controller, that takes uncertainty into consideration, was initially designed for the lateral-longitudinal dynamics.

Fig. 8 shows the structure of the control system for the vertical dynamics. The body axis yaw rate (r) is controlled by two PD controllers (one for each motor).
![](https://i.imgur.com/kXjzBCv.png)

Fig. 9 shows the robust control system design for the
lateral-longitudinal dynamics where $K_{xy}$ is the robust control system and $G_{xy}$ is the lateral-longitudinal dynamics of the sphere. The µ-synthesis technique was used with the MATLAB Robust Control Toolbox. The design procedure was a model matching one with $W_{Q_{xy}}$ being the goal, second order dynamics of the sphere. Frequency weighting $W_{B_{xy}}$ was used to tune model matching characteristics over specific frequency regions, $W_{A_{xy}}$ was used to press down on flap actuation to avoid saturation over certain frequency regions, $W_{u_{xy}}$ and $∆_{xy}$ are used to model the
uncertain longitudinal-lateral dynamics. $W_{N_{xy}}$ is used as a noise generator so that the design control system can account for high frequency noise in the system and sensor dynamics.
![](https://i.imgur.com/Kz3KBqj.png)

Due to control drawbacks mentioned [here](#Drawbacks) 
A different control system design was choosen. 
Fig. 12 shows the PD structure of the lateral-longitudinal dynamics. Inner loop controller Kp and Kq control the roll and pitch rate, respectively, whilst the outer loop controllers Kφ and Kθ controlled the roll and pitch perturbed Euler attitudes, respectively. 
![](https://i.imgur.com/vxcL3vA.png)

The response to reference inputs was seen to be a lot better than the robust control system after substantial control system tuning. 

### Drawbacks 

* <p><b>Problem :</b> Essential amount of airflow is blocked by the components that restrict the overall productive thrust. Around 44% of thrust loss is observed.<br><b>Proposed Solution by the Authors :</b> None</p>

* <p><b>Problem :</b> During flight the acoustic noise, the air turbulence from the propulsion system and the unstable power supply, which is caused by the current draw from the motors, had a major affect on the sensor measurements. For this reason, both ultrasonic modules and the localisation for altitude control were not applied in real-time for feedback to the control system of the spherical UAV.<br><b>Proposed Solution by the Authors :</b> Ultrasonic sensors will be replaced by two light-weight lidar units.</p>

* <p><b>Problem :</b> the acoustic noise generated by the propellers provided far too much interference for the ultrasonic distance measurements to be reliable and<br><b>Solution used by the Authors :</b> Altitude of the spherical UAV was controlled directly through pilot intervention.</p>

* <p><b>Problem :</b> the spherical UAV is not very responsive to control inputs, it is very stable in flight (it does not move off its hover point very easily) and it has a slight negative roll attitude at hover. The non-linear model did not take an unknown source moment into consideration that was restoring the sphere to hover position during flight.</br> <b>Solution used by the Author :</b> The first, design solution was to alleviate the effects of the restoring moment by changing the centre of gravity of the sphere and then use individual PD controllers for the lateral and longitudinal dynamics, this would allow for insight into the system and tuning of the controller gains. The second solution was to include an integral gain to the control system as to overcome the restoring moment, this has the disadvantage of actuator saturation. The former solution was chosen, the reason being it forced actuator saturation too quickly, during the experimental process. Furthermore, based on the control theory of this system, there is no need for I controller in the rotational dynamics.</p>

* <p><b>Problem :</b> The spherical UAV can still be seen to have slight negative roll attitude which has the effect of causing flap saturation when trying to achieve a positive roll.<br><b>Proposed Solution by the Authors :</b> None</p>

* <p><b>Problem :</b> The steady-state error in Lateral-longitudinal PD control is due to the lack of integral control and the inadequate actuation authority.<br><b>Proposed Solution by the Authors :</b> To enhance the authority of actuators (flap) should be shifted further down from the CG and be replaced by more efficient aerofoil designs in order to produce adequate moments.</p>

### Conclusion

A new spherical UAV was designed, built and flight tested. It was found to be very stable in flight and did not achieve zero steady state error for the lateral and longitudinal dynamics under the influence of both the robust control system and the PD control system. This reason for not achieving zero steady state error is caused by a moment that attempts to restore the spherical UAV to hovering trim state and therefore roll and pitch rate dynamics are not type 1 and therefore integral action will be needed by the controller. Shifting centre of gravity, the restoring effect was reduced a little but was still present. The vertical dynamics of the spherical UAV achieved good steady state error and responded quickly to changes in the reference input.

---

## Design and Analysis of a Flying-crawling Spherical Robot for Multi-mode Movement

### Abstract

A novel spherical robot named flying-crawling spherical robot is designed in this paper. It can fly or roll on ground with its single rotor and eight tail fins. When its limbs stretch out it can crawl on the supporting surface. Besides, with its limbs the robot can realize carrying objects, landing on uneven ground and walking on the supporting surface. Dynamic model of the robot in flight mode is established and the motion characteristics are analyzed. A PID control system is designed to enable the robot to achieve stable flight. Trot gait planning of the robot is given and a PID controller is designed for tail fins assistant in crawling mode. Corresponding simulations are carried out and the simulation results verify the proposed methods.

> Full paper [here](https://ieeexplore.ieee.org/abstract/document/8961837/)