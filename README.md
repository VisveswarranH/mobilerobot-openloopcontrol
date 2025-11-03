# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

### Step1:
Use from robomaster import robot

### Step2:
Choose the x,y,z - axis movement distance(meters).

### Step3:
Give ep_chassis.move to move straight.

### Step4:
Give time.sleep() for a break.

### Step5:
Give ep_chassis.drive_speed to have a circular movement.

<br/>

## Program
```python
from robomaster import robot
import time

if __name__ == '__main__':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis

   from robomaster import robot
from robomaster import camera
import time

if _name_ == '_main_':
    # Initialize robot connection
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    # Get robot modules
    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)

    # Movement and LED sequence
    sequence = [
        (0.7, 0, 0),
        (0, 0, 30),
        (0.5, 0, 0),
        (0, 0, 30),
        (0.3, 0, 0),
        (0, 0, 15),
        (0.3, 0, 0),
        (0, 0, 12),
        (0.8, 0, 0),
        (0, 0, 12),
        (0.2, 0, -10),
        (0,0,-30),
        (1.4,0,0),
        (0,0,35),
        (0.6,0,0),
        (0, 0, 35),
        (0.8,0,0),
        (0,0,5),
        (0.9,0,0),
        (0,0,10),
        (0.7,0,0),
        (0,0,20),
        (0.8,0,0),
        (0,0,10),
        (0.8,0,0),
        (0,0,45),
        (0.5,0,0),
        (0,0,30),
        (0.6,0,0),
        (0,0,28),
        (1.1,0,0),
        (0,0,25),
        (0.5,0,0),
        (0,0,20),
        (0.8,0,0),
        (0,0,-25),
        (0.4,0,0),
        (0,0,-30),
        (0.6,0,0),
        (0,0,-20),

        (0.7,0,0),

        (0,0,30),
        (0.4,0,0),
        (0,0,40),
        (0.4,0,0),
        (0,0,10),
        (0.4,0,0),

    ]

    for (x, y, z) in sequence:
        ep_chassis.move(x=x, y=y, z=z, xy_speed=1.1).wait_for_completed()
        ep_led.set_led(comp="all", r=255, g=100, b=0, effect="on")

    # Stop camera and close connection
    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming...")

    ep_robot.close()



    
    ep_robot.close()
```

## MobileRobot Movement Image:

<img width="827" alt="image" src="https://github.com/gauthamkrishna7/mobilerobot-openloopcontrol/assets/141175025/886ad367-4566-495a-86d2-702ace7b8c2d">



<br/>
<br/>
<br/>
<br/>

## MobileRobot Movement Video:

https://youtu.be/y06zi_sVCfQ?si=0hFAzhuFf3kyDaBZ

<br/>
<br/>
<br/>
<br/>

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.


<br/>
<br/>

```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
