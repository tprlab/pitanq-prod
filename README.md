# Package
* Chassis plate
* Acrylic plate
* Chassis sides
* Chassis hardware pack
* Chassis motors
* Tracks
* Raspberry PI
* MicroSD card
* Camera
* Motor Driver
* Power converter
* Servo controller
* Batteries
* Charger
* Camera stand
* Camera stand motors
* Wires
* Screws
* Screwdriver

# Chassis
## Wheel
There are parts for one wheel:
![](https://pitanq.com/img/guide/wheel_parts.jpg)

* Put the brass standoffs between the wheels and fix them together with M3 screws.
* Put the bearings into the wheels
* Put the coupling through the bearings
* Fix the coupling to the bearing with M2 screw
The assembled wheel looks like that:
![](https://pitanq.com/img/guide/wheel_parts.jpg)

There are parts for a driving wheel:
![](https://pitanq.com/img/guide/driving_wheel_parts.png)

Assembled driving wheel:

![](https://pitanq.com/img/guide/driving_wheel.png)

## Side assemble
Attach shock absorbers and springs to the side. 
![](https://pitanq.com/img/guide/side.png)
## Attach motors
Attach the motor to the side with M3 screws
![](https://pitanq.com/img/guide/motor.jpg)
## Attach wheels
Attach the driving wheel to the motor shaft:
![](https://pitanq.com/img/guide/wheel_motor.png)
Attach a wheel to another end of the side with two washers and M4 screw:
![](https://pitanq.com/img/guide/rim_wheel.png)
Then attach the other wheels the same way.

The whole side looks like that:
![](https://pitanq.com/img/guide/whole_side.png)

Put tracks on the wheels with wheels rims between the track teeth. Adjust the tracks length and connect both sides with a black needle.

## Attach sides to plate
Using M4 screws attach side to the plate.

![](https://pitanq.com/img/guide/chassis.jpg)

## Attach standoffs to plate
Using black M3 screws attach the brass standoffs at top of the plate.
![](https://pitanq.com/img/guide/standoffs.jpg)

## Attach battery holder to the plate
Using 2 M3 flat head screws attach the battery holder to the bottom of the plate
![](https://pitanq.com/img/guide/battery_holder.jpg)

## Camera assemble
### Assembly camera stand
### Attach camera stand to the chassis plate
Using 2 M2 screws and nuts attach the camera stand with rear holes.
Make sure the stand mount allows to tilt to the right angle to the right and left.
![](https://pitanq.com/img/guide/cam_stand.jpg)

## Attach Camera and the ultrasonic sensor to the camera board
Remove paper from the camera board
Using 4 M2 screws and nuts attach the camera to the board
(Use a piece of scotch patch to back the camera again the plate)
Using 4 M1.6 screws and nuts attach the ultrasonic sensor to the board
![](https://pitanq.com/img/guide/cam_board.jpg)

## Attach camera board to stand
Using the vertical slots set the board on the stand fins.
Pull the camera cable underneath into the gap between servo-motor and lower part of the stand
![](https://pitanq.com/img/guide/stand_panel.jpg)

## Prepare SD Card
We recommend to set up SD card and insert it into Raspberry Pi before putting it on the acrylic plate. 
### Configure Wi-Fi
* Insert SD card to the adapter
* Insert the adapter to the computer
* Create a text file “wpa_supplicant.conf”
* Type or paste:

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=US

network={
    ssid="NAME-OF-YOUR-WIFI"
    psk="PASSWORD-TO-YOUR-WIFI"
    key_mgmt=WPA-PSK
}
```

* It is recommended to create an empty file named “ssh”. I will allow a remote access to the Raspberry Pi.
* Insert SD Card to Raspberry Pi

## Electrical assemble
Remove paper from the acrylic plate
Put the acrylic plate such way the most holes are on the right side
Using short M3 screws attach to the plate:
* Raspberry Pi
Using long M3 screws attach to the plate:
* Power Converter
* Motor Controller
* PWM Controller
![](https://pitanq.com/img/guide/plate.jpg)

## Wiring
### Wire Raspberry Pi and Motor Driver
* Using 15cm blue wire connect Raspberry Pi #40 to Motor Driver IN4
* Using 15cm green wire connect Raspberry Pi #38 to Motor Driver IN3
* Using 15cm yellow wire connect Raspberry Pi #36 to Motor Driver IN2
* Using 15cm orange wire connect Raspberry Pi #32 to Motor Driver IN1

![](https://pitanq.com/img/guide/rasp_motor.jpg)

### Wire Raspberry Pi and PWM Controller
* Using 15cm red wire connect Raspberry Pi #2 to PWM VCC 
* Using 15cm black wire connect Raspberry Pi #9 to PWM GND
* Using 15cm white wire connect Raspberry Pi #3 to PWM SCA 
* Using 15cm brown wire connect Raspberry Pi #5 to PWM SCL

![](https://pitanq.com/img/guide/rasp_pwm.jpg)

### Connect Raspberry Pi and Power Converter and prepare leads
* Connect Raspberry Pi mini-USB with Power converter
* Attach wire leads to Motor Driver
* Attach wire leads to PWM Controller

![](https://pitanq.com/img/guide/connect_usb.jpg)
## Attach plate to chassis
Attach the acrylic plate to the chassis standoffs with 4 black M3 screws
![](https://pitanq.com/img/guide/plate_chassis.jpg)

## Connect camera
Connect camera cable to Raspberry Pi
![](https://pitanq.com/img/guide/rasp_cam.jpg)

## Connect Power Converter with Motor Driver, PWM Controller and Battery
Use leads from the battery holder, Motor Driver and PWM controller to connect them to terminals of Power Converter.
Red wires are going to IN+ terminal, Black wires are going to IN- terminal.
![](https://pitanq.com/img/guide/connect.jpg)

## Wire Camera Stand and PWM Controller
Attach cables of stand servomotors to PWM controller:
* The lower cable is going to 0 channel.
* The upper cable is going to 1 channel.
![](https://pitanq.com/img/guide/servo_wire.jpg)

## Wire Motor Controller and motors
Attach motors leads to the motor controller terminals.
Right motor side leads are going to the right side of the controller.
Left motor leads are going to the left side of the controller.
Red leads are going to front terminals.
![](https://pitanq.com/img/guide/motor_connect.jpg)

## Wire Raspberry Pi and Ultrasonic sensor
Using a scotch patch attach Level Shifter to the plate (on the left from Raspberry Pi, the power pins of the chip are toward the rear - look at the back side of Level Shifter to identify the power pins).
Attach 6 wires to the Level Shifter:
(One side of the Level Shifter is marked 3V, another one - 5V)
Attach 5V side wires to:
* V+ pin of last (or any free) channel of PWM
* GND pin of the same channel of PWM
* Echo pin of the ultrasonic sensor
Attach 3V side wires to:
* 3V pin of Raspberry Pi (Pin #1, the first on the far inner side)
* GND pin of Raspberry Pi (Pin #6, the third on the far outer side)
* GPIO19 pin of Raspberry Pi (Pin #35, the third on the near inner side)

Then attach 3 more wires of the ultrasonic sensor:
* The longest wire goes from VCC pin of the sensor to 5V pin of Raspberry Pi (Pin #4, the second on the far outer side)
* GND pin of the sensor goes to pin #39 (the first on the near inner side)
* TRIG pin of the sensor goes to pin# 37 (the second on the near inner side)

![](https://pitanq.com/img/guide/sound_wire.jpg)

## Raspberry Pi pinout
Source: https://learn.adafruit.com/assets/22438
![](https://pitanq.com/img/guide/gaming_pin-legend.png)

## Software setup
Download an application for Android on [Google Play](https://play.google.com/store/apps/details?id=tprlab.com.pitanq)
## Turn the tank on
* Put the batteries into the holder (Charge them if necessary).
* Turn on the small switch on the holder.
## Control the PiTanq
* Wait for a minute when Raspberry Pi loaded
* Find IP-address of the Raspberry.
(
_I would recommend Fing software for that (absolutely no affiliation) or check the WI-FI router connections._
_[Fing on Google Play](https://play.google.com/store/apps/details?id=com.overlook.android.fing)_
)
* Run the PiTanq application
* Enter the found IP address:
![](https://pitanq.com/img/guide/pitanq_main_small_cut.png)

* As far as everything OK, the dashboard screen should appear:
![](https://pitanq.com/img/guide/dash_empty.png)

On this screen you can:
* Update a python service working on the Raspberry. (The update means the code will be updated from the master branch of this repo: https://github.com/tprlab/pitanq)
* Control the tank movements (blue buttons)
* Control pan and tilt  of the camera stand (orange buttons)
* Take a photo (red button)
After a photo has been taken it is possible
* Find a cat using OpenCV-provided Haar cascade for cat faces.
* Detect objects using Tensoflow-powered neural network and OpenCV-DNN module.

You can get more info or buy the tank on the [product site](http://pitanq.com).
