# Motor Test Rig: Dynamic Torque and Deadband Characterisation

A test rig for characterising low-cost DC gear motors for robot actuation. It was built during a research internship advised by Prof. Andy Ruina (Jun–Aug 2024, 300+ hours of design, testing and calibration).

| Lift test | Motor under a sinusoidal command |
|---|---|
| [![Lift test](media/rig_lift_test.gif)](media/rig_lift_test.mp4) | [![Sinusoid test](media/motor_sinusoid_test.gif)](media/motor_sinusoid_test.mp4) |

Click a preview to open the full video.

## How it works

A pulley on the motor shaft sits at the top of a tall column. The motor lifts and lowers **different weights** at **different PWM levels**. Recording speed and position for each weight–PWM pair shows how much torque the motor actually delivers at each speed and load, which is its dynamic torque curve. A motor's datasheet only gives a few rated points.

| Full rig | Motor, pulley and encoder |
|---|---|
| ![Full rig](media/rig_full.jpg) | ![Motor close-up](media/rig_motor_closeup.jpg) |

Sensors are connected to a microcontroller that logs speed, torque response and dynamic behaviour for control-system modelling.

## In progress: three deadbands

Cheap gear motors have three separate "dead zones" that make fine control hard. The rig is being used to measure each one on its own:

1. **Gear backlash**: play in the gearbox, so the motor turns a little before the output moves when the direction reverses.
2. **Voltage deadband**: small voltages that are too weak to turn the motor at all.
3. **Static friction**: the extra effort needed to start moving, compared with keeping moving.

Once each is measured, a controller can compensate for it instead of reacting to it as an unexplained error.

## Status

This is a prototype. Results and analysis code will be added here as the measurements are completed.
