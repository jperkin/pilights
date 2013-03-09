# pilights - fun scripts for controlling LEDs via Raspberry Pi

This is a simple collection of shell scripts designed to make it easy for
children to play with a set of LEDs attached to a Raspberry Pi via GPIO.

## Usage

The main configuration and setup is in the `pilights` file, and assumes a
default layout of 3 LEDs attached like this:

    GPIO17  Red
    GPIO18  Yellow
    GPIO21  Green

There is also optional support for a second set of lights:

    GPIO22  Red2
    GPIO23  Yellow2
    GPIO24  Green2

2 functions are supplied, `turn` and `wait`:

    turn <light> <on|off>
    wait <seconds>

So a simple script to turn the red light on and then off again 2 seconds 
later would be:

    . ./pilights
    
    turn red on
    wait 2
    turn red off

Both functions are designed to be case-insensitive and also allow additional
arguments for optional clarity.  The above could instead be written like this:

    TURN RED LIGHT ON
    WAIT 2 SECONDS 
    TURN RED LIGHT OFF

for that retro feel ;)

There is also a simple alias for a 'while true' loop:

    repeat
      turn red on
      wait 0.2
      turn red off
      wait 0.2
    done

## Example Scripts

A number of example scripts are provided.

* `flashlight` flashes the red LED.
* `flashlights` flashes the red, yellow, and green LEDs.
* `flashlights2` flashes both sets of red, yellow, and green LEDs.
* `trafficlights` runs a traffic light simulation with the first set of LEDs.
* `trafficlights2` runs a full traffic light simulation with both sets of LEDs.

You are encouraged to play with these scripts and edit them to observe the
change in behaviour.

Have fun!
