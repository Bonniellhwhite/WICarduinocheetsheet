# Basic tools

### Basic structure of a program
```c
//Include statements go first
#include <SomeFileName.h>
#include <SomeOtherFile.h>

//Second, global constants:
const int someConstant = 0;
const int otherConstant = 200;

//Third, global variables:
int oneVar = 2;
ZumoMotors motors;
ZumoBuzzer buzzer;

//Fourth, your own functions:
void doSomething() {
	//...
}

void doSomethingElse() {
	//...
}

//Finally, your program's core functions
void setup() {
	//...
}

void loop() {
	//...
}
```

### Fixing a port error
Go to `Tools -> Port -> COM[X] (Arduino Uno)` (where `[X]` will be some random number)

### Installing the ZumoShield library
Go to `Tools -> Manage Libraries`. Type `ZumoShield` into the search box, and click Install.

### Showing line numbers
Go to `File -> Preferences`, check the `Show line numbers` box, and click OK.

# Light Functions 
### Headers
in `setup(
	pinMode(13, OUTPUT);
 )`
### Built-in functions
Light on: `digitalWrite(LED_PIN,HIGH);`
Light off: `digitalWrite(LED_PIN,HIGH);`
Delay:  `delay(250)`

# Motor Functions 
### Headers
Import Library: `#include <ZumoMotors.h>`
Initialize Motors: `ZumoMotors motors;`
Global Variables: `Speed = 10`

### Built-in functions
Motor on: `motors.setSpeeds(SPEED, SPEED);`
Motor off: `motors.setSpeeds(0, 0);`
Delay:  `delay(250)`

# Buzzer Functions 
### Headers
Import Library: `#include <ZumoBuzzer.h>`
Initialize Motors: `ZumoBuzzer buzzer;`
Global Variables: `const int VOLUME = 15` and `const int OCTAVE = 3`

### Built-in functions
Play Note: `buzzer.playNote(NOTE_G(OCTAVE), DURATION, VOLUME);`
Note Play / Stop Duration: `delay(DURATION);`
Stop Note: `buzzer.stopPlaying();`

Notes listed here: https://pololu.github.io/zumo-shield-arduino-library/_pololu_buzzer_8h.html#note_macros

# Sensor Functions 
### Header file
```c
#include <ZumoReflectanceSensorArray.h>
```

# Debugging (Serial Monitor) 

