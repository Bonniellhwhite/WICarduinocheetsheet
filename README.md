# Basic tools

### Basic structure of a program

First, `#include` statements go at the very top of the file, to include libraries for the motors, buzzer, or sensor array:
```c
#include <SomeFileName.h>
#include <SomeOtherFile.h>
```

Second, global constants and global variables that can be accessed by any function:
```c
const int SOME_CONSTANT = 0;
const int OTHER_CONSTANT = 200;
int oneVar = 2;
ZumoMotors motors;
ZumoBuzzer buzzer;
```

Third, your own functions:
```c
void doSomething() {
	//...
}

void doSomethingElse() {
	//...
}
```

Finally, your program's core functions:
```c
void setup() {
	//put your setup code here, to run once
}

void loop() {
	//put your main code here, to run indefinitely
}
```

### Fixing a port error ("Problem uploading to board")
Go to `Tools -> Port -> COM[X] (Arduino Uno)` (where `[X]` will be some random number)

### Installing the ZumoShield library
Go to `Tools -> Manage Libraries`. Type `ZumoShield` into the search box, and click Install.

### Showing line numbers
Go to `File -> Preferences`, check the `Display line numbers` box, and click OK.

# Light Functions 
The light (LED) allows your robot to make signals.
### Header file
None needed

### Required setup code
```c
const int LED_PIN = 13;

void setup() {
	pinMode(LED_PIN, OUTPUT);
	//...
}
```
### How to use
Light on: `digitalWrite(LED_PIN, HIGH);`<br>
Light off: `digitalWrite(LED_PIN, LOW);`<br>
Delay:  `delay(250);`<br>

# Motor Functions 
The motors allow your robot to move.
### Header file
```c
#include <ZumoMotors.h>
```

### Required setup code
```c
const int SPEED = 100;
ZumoMotors motors;
```

### Built-in functions
Move forwards: `motors.setSpeeds(SPEED, SPEED);`<br>
Move backwards: `motors.setSpeeds(-SPEED, -SPEED);`<br>
Stop moving: `motors.setSpeeds(0, 0);`<br>
Delay:  `delay(250);`<br>

Reference link: https://pololu.github.io/zumo-shield-arduino-library/class_zumo_motors.html

# Buzzer Functions 
The buzzer allows your robot to make sounds.
### Header file
```c
#include <ZumoBuzzer.h>
```

### Required setup code
```c
const int VOLUME = 15;
const int OCTAVE = 4;
ZumoBuzzer buzzer;
```

### How to use
```c
const int DURATION = 250;
buzzer.playNote(NOTE_G(OCTAVE), DURATION, VOLUME);
delay(DURATION);
buzzer.stopPlaying();
```

Reference link: https://pololu.github.io/zumo-shield-arduino-library/class_zumo_buzzer.html <br>
Notes listed here: https://pololu.github.io/zumo-shield-arduino-library/_pololu_buzzer_8h.html#note_macros

# Sensor Functions 
The reflectance sensor array allows your robot to sense reflected light underneath it.
### Header file
```c
#include <ZumoReflectanceSensorArray.h>
```

### Required setup code

```c
ZumoReflectanceSensorArray sensors;
//...

void setup() {
	sensors.init();
	//...
}
```

### How to use

```c
int values[6];
//...
sensors.read(values);
int leftmostSensor = values[0];
int rightmostSensor = values[5];
```

Reference link: https://pololu.github.io/zumo-shield-arduino-library/class_zumo_reflectance_sensor_array.html

# Debugging (Serial Monitor)
The Serial Monitor allows you to print data to a console on your screen, much like the `print` statement in Python. You can use it to debug your code, e.g., to check the value of your sensors.

### Header file
None needed

### Required setup code

```c
void setup() {
	Serial.begin(9600);
	//...
}
```

### How to use

```c
int someVariable;
//...
Serial.println("Some text");
Serial.println(someVariable);	//outputs the actual number in the variable
```

To read the output, ensure your robot is connected to the computer, then click the magnifying glass button on the top right to open the Serial Monitor.
