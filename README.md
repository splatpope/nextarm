## Robot arm controlled by Nextion display and Arduino board

This project aims to connect a Nextion HMI display combined with an Arduino board to control a robot arm from a simple, intuitive on-board GUI.

### Nextion HMI display

The Nextion resistive touch-sensitive display card is a Human Machine Interface designed to interface with small IoT applications. 

Its ARM microcontroller takes care of such tasks as GUI widgets rendering, basic variable management and communication.

The Nextion display communicates with any compatible microcontroller with a standard 9600 baud serial connection.

An official editor called Nextion Editor is used to design the GUI and a single compiled file is copied to a SD card which acts as a storage medium for the display.

### Arduino board

The ubiquitous Arduino programmable board will be the basis of this project.

It provides an easy way to both process data from the Nextion display and control the robot arm with its simple javascript-inspired language and the various available libraries.

We will use Nextion's Arduino libraries to interact with the display.

### Robot arms, servo-motors and possibilities

Obviously, you might want to control *any* robot arm with this project. As we can not realistically provide a solution for every available robot arm and ours is pretty basic anyway, here's a quick rundown of how ours works and how you might accomodate the software for your own arm :

*insert our lovely robot arm*

The arm we use is made of 6 servo-motors independently controlled by PWM. Every motor has a corresponding pin on the Arduino board. What we call the "claw" in our software is just the gripping component of the arm.

You simply need to remap pins, angles and poses to your own arm's servo arrangements. *explicit that*


### Hardware/Software compatibility

Software available on this repo has been tested with the following hardware and should be broadly compatible across hardware versions :

- Nextion NX4024T032_011 3.2"
- Arduino Uno 

Other sizes of the Nextion HMI can be used, but a GUI image file compiled for one size has to be redesigned to accomodate them.

### Install

1. Clone or download the nextarm repository
2. *extract arduino code and libs at the right place, compile and send to board, power off*
3. *copy nextion gui image .tft file to FAT32 formatted sd card, insert in nextion, power on, let it update code*
4. *power off, remove sd card, now GUI is fully prepared*
5. *connect GUI serial to arduino, maybe give some images*
6. *connect robot arm to arduino, check all connections, power on every thing*
7. *???*
8. *profit*



```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/splatpope/nextarm/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
