## Robot arm controlled by Nextion display and Arduino board

This project aims to connect a Nextion HMI display combined with an Arduino board to control a robot arm from a simple, intuitive on-board GUI.

It is assumed that you are familiar with Arduino boards, basic programming principles and serial connections.

### Nextion HMI display

The Nextion resistive touch-sensitive display card is a Human Machine Interface designed to interface with small IoT applications. 

Its ARM microcontroller takes care of such tasks as GUI widgets rendering, basic variable management and communication.

The Nextion display communicates with any compatible microcontroller with a standard 9600 baud serial connection.

An official editor called Nextion Editor is used to design the GUI and a single compiled file is copied to a micro-SD card which acts as a transfer medium for the display.

### Arduino board

The ubiquitous Arduino programmable board will be the basis of this project.

It provides an easy way to both process data from the Nextion display and control the robot arm with its simple C++ dialect and the various available libraries.

We will use Nextion's Arduino libraries to interact with the display.

### Robot arms, servo-motors and possibilities

Obviously, you might want to control *any* robot arm with this project. As we can not realistically provide a solution for every available robot arm and ours is still at prototyping stage, here's a quick explanation its inner workings and how you might accomodate the software for your own arm :

*insert a picture of our lovely robot arm*

The arm we use is made of 6 servo-motors independently controlled by PWM. Every motor has a corresponding pin on the Arduino board. What we call the "claw" in our software is just the gripping component of the arm.

The code in this repo is structured in such a way to use the basic servo-motor library to control the appropriate angles, their boundaries and link their function to the provided Nextion library's callbacks.

You simply need to remap pins, angles and poses to your own arm's servo arrangements. This can be performed by editing the appropriate setup functions in our code. *maybe include a quick example ?*


### Hardware/Software compatibility

Software available on this repo has been tested with the following hardware and should be broadly compatible across hardware versions :

- Nextion NX4024T032_011 3.2"
- Arduino Uno 

Other sizes of the Nextion HMI can be used, but a GUI image file compiled for one size has to be redesigned to accomodate them.

### Folder structure

Included in this repo are the following folders and appropriate files :

- Arduino : Contains all relevant files for the arduino programming environment.
 - Code : What you will need to compile and send to the board. We recommend copying the folder to your sketchpad and renaming it to something appropriate.
 - Libs : The required libraries for the Nextion GUI. Copy them to your arduino IDE's designated 'libraries' folder. These libraries are available on Nextion's website. *verify*
- Nextion : Contains the required .tft image file, as well as the relevant sources for generation in Nextion's proprietary IDE.
- Tutorial : Contains a PDF file detailing how to use the Nextion display with an arduino board. Do not hesitate to read it.

### Install

1. Clone or download the nextarm repository.
2. Copy the arduino code and libraries to their proper places, compile and send to the board then power it off.
3. Copy the nextion gui image .tft file to a FAT32 formatted micro-SD card of sufficient capacity, insert it in the nextion display, power it on and let it update as instructed on the screen.
4. Power off the display and remove the sd card. The display is now fully prepared and the SD card can be repurposed. Step 3 has to be performed after every GUI redesign or parameter change.
5. Connect the display to the arduino board. *!! should explain default pinout for all relevant steps*
6. Connect the robot arm to the arduino board, check all connections and power on everything.

The assembly should now be functional and you may use the display to control the robot arm.
