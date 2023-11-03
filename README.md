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
	//put your setup code here, to run once
}

void loop() {
	//put your main code here, to run indefinitely
}
```

### Fixing a port error
Go to `Tools -> Port -> COM[X] (Arduino Uno)` (where `[X]` will be some random number)

### Installing the ZumoShield library
Go to `Tools -> Manage Libraries`. Type `ZumoShield` into the search box, and click Install.

### Showing line numbers
Go to `File -> Preferences`, check the `Show line numbers` box, and click OK.

# Light Functions 

# Motor Functions 

# Buzzer Functions 

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
