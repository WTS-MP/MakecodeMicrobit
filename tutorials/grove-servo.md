<!--
Written by:  

Last updated: 06/09

Ready to release: Y

Tasks:
- recreate spilt cable image for 'Collecting Parts' page 

-->

### @diffs true

# Servo Motors with Microbit & Grove
```template
basic.showLeds(`
    . . . . .
    . . . . #
    . . . # .
    # . # . .
    . # . . .
    `)
```
## {Introduction @unplugged}
Let's create movement using @boardname@ , Grove and Servo Motors!
![WTS Logo](https://raw.githubusercontent.com/CarlTS/microbit-grove/master/assets/WTSLogo.png)

  - :lightbulb: **Helpful Hints**   
  Look out for hints indicated by a light bulb   
You can click the ``||game: OK ➔ ||`` or ``| ➔ Next |`` button on the right after each step to continue.

## Testing the micro:bit @unplugged
We want to make sure everything is working correctly before we start.
![Plugging in microbit](https://raw.githubusercontent.com/CarlTS/microbit-grove/master/assets/microbitplugin.gif)   

## {Testing the micro:bit}
We'll begin by testing our microbit   
► Plug in your microbit   
► In the bottom left of the screen select  ``|Download|``  
► You should now see a **✓** on your microbit  -  💡 [Need help connecting?](https://www.youtube.com/watch?v=qSjMDG84bMY)

```blocks
basic.showLeds(`
    . . . . .
    . . . . #
    . . . # .
    # . # . .
    . # . . .
    `)
```

## Collecting Parts @unplugged @fullscreen
Lets collect all the parts needed for this tutorial
![GroveShield,Servo,Microbit,Cable](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveSensors/ServoMotor.png)

## Connecting Everything @unplugged
Connect the parts together.
![Servo to Grove in P0/P14, microbit into the Grove Shield](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveServoAssembled.png)

## Time to Code @unplugged
In the next step, you will need to use ``||input:on button [A] pressed||``
```blocks
input.onButtonPressed(Button.A, function () {
	
})
```
```validation.local
# BlocksExistValidator
* Enabled: false
```

## {Coding Time}
► From the ``||input:Input||`` category in your toolbox, find the ``||input:on button [A] pressed||`` and add it to your workspace.  
💡 This will be the trigger for our servo motor. We will worry about this later!
```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
	
})
```

## {different blocks}
► Now place a ``||pins: Servo Write Pin [P0] to [180]||`` inside the ``||input:on button [A] pressed||``   
💡 This will tell the servo motor where to move to
```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    pins.servoWritePin(AnalogPin.P0, 180)
})
```


## {More Control}
► First, make sure the servo returns to 0 each time. 

► Add a ``||basic:On Start||`` block. Insert a ``||pins: Servo Write Pin [P0] to [0]||`` 

```blocks
// @highlight
 pins.servoWritePin(AnalogPin.P0, 0)

```

## {More Control}
► Let us get more control with another ``||input:on button [A] pressed||`` on the workspace   
► You will need to change the ``||input:[A]||`` pressed to ``||input:[B]||`` pressed
```blocks
input.onButtonPressed(Button.A, function () {
    pins.servoWritePin(AnalogPin.P0, 180)
})
// @highlight
input.onButtonPressed(Button.B, function () {

})
```

## {More Control - Second Location}
► Place another ``||pins: Servo Write Pin [P0] to [180]||`` inside the ``||input:on button [B] pressed||``   
► Set ``||input:[180]||`` to ``||input:[90]||``
```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    // @highlight
    pins.servoWritePin(AnalogPin.P0, 180)
})
// @highlight
input.onButtonPressed(Button.B, function () {
    // @highlight
    pins.servoWritePin(AnalogPin.P0, 90)
})
```

## {Download to micro:bit}
► Time to test the movement   
► ``|Download|`` your code to the micro:bit   
► Press the [A] button on the microbit and it should go to position 180   
► Pressing [B] should go to position 90
 
## Congratulations @unplugged
You have learnt how to control a servo motor that could be added to your own project.   
   
Now try the challenges on the following pages   
► Complete Control   
► Show Feedback   
► Shake Trigger

## Complete Control Challenge
Try coding your microbit so that:   
► Pressing A goes to 20 degrees   
► Pressing B goes to 160 degrees   
► Pressing A and B goes to 90 degrees

## Show Feedback Challenge
Try coding your microbit so that:   
► Pressing A moves the servo and shows a left arrow on the screen   
► Pressing B Shows a right arrow and moves the servo on the screen   

## Shake Trigger Challenge
► When shaking the microbit (Not the servo motor) it moves the Servo   
► Pressing A - resets the servo position   


```blocks
input.onGesture(Gesture.Shake, function () {
	
})
```
## End of tutorial
You've reached the end of this tutorial - Click Done to open a New Project.



```validation.global
# BlocksExistValidator
```