# XboxController [![Build Status](https://travis-ci.org/frc2879/XboxController.svg?branch=master)](https://travis-ci.org/frc2879/XboxController) [![Release](https://jitpack.io/v/frc2879/XboxController.svg)](https://jitpack.io/#frc2879/XboxController)
This class wraps around the Joystick class in order to make working with Xbox360 controllers less of a pain. The values from this class can be used in two ways.
You could either check each Button every cycle with .get(), or you could call commands directly from the Buttons with .whenPressed()

## Setup
Add the JitPack repository to your build file 
```
repositories {
			...
			maven { url 'https://jitpack.io' }
		}
```
Add the dependency
```
dependencies {
	        compile 'com.github.frc2879:XboxController:1.0'
	}
```
## Usage
Initialization
````
myXboxController = new XboxController( <port the controller is on (starts at 0)> );
myXboxController.leftStick.setThumbstickDeadZone( .2 ); // Optional. See code below for defaults.
````

Using buttons
````
myXboxController.a.whenPressed( new MyCommand() );
myXboxController.lb.toggleWhenPressed( new MyCommand() );
myXboxController.rightStick.whenPressed( new MyCommand() );
````

Getting values directly
````
if( myXboxController.leftStick.getY() > .4 ) ...
````
Support of legacy methods (NOTE: These values are straight from the Joystick class. No deadzone stuff or anything)
````
if( xboxController.getX() > .4 ) ...
````
