# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

## Step 1:

Initiate the MobileRobot.

## Step 2:

Connect your PC with the MobileRobot.

## Step 3:

Open Python program.

## Step 4:

Program the movements of the robot using python code.

## Step 5:

Execute the python program.

## Program
```py

Python control code to move the mobilerobot along the predefined path.
Developed by:Ezhil sree J
Register No.: 23012968

from robomaster import robot
import time

if __name__ == '__main__':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis

    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5]
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second) [0.5,2]


    ep_camera = ep_robot.camera
    ep_led = ep_robot.led

    print("Camera streaming started...")
    ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P)  

    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")   
    time.sleep(2)
    


    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=-135, xy_speed=1).wait_for_completed()

    ep_chassis.move(x=1.7, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=135, xy_speed=1).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=0,b=255,effect="on")
    time.sleep(2) 
   
    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()
   
    ep_chassis.move(x=0, y=0, z=90, xy_speed=1).wait_for_completed()

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=0.75).wait_for_completed()

    ep_chassis.move(x=0, y=0, z=-50, xy_speed=0.75).wait_for_completed()

    ep_led.set_led(comp="all",r=0,g=255,b=0,effect="on")
    time.sleep(2)
    ep_chassis.drive_speed(x=0.3,y=0,z=20)
    time.sleep(12)
    ep_chassis.drive_speed(x=0,y=0,z=0)

    ep_camera.stop_video_stream()
    print("Stopped video streaming...")



    
    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

### Initial position:
![output](/initial.png)

### Final position:
![output](/final.png)


## MobileRobot Movement Video:
https://youtube.com/shorts/ccRb3HJysmc?si=fSUsp5v5zGIyrMNq

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.




```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
