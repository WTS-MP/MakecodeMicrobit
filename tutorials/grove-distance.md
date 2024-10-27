<!-- 
Written by: casey

last updated: 16/08

Ready for Upload: Y

tasks:
potentially spilt into two seperate sections, display and sensor, with second connection image and page later on

-->

### @diffs true

```template
basic.showLeds(`
    . . . . .
    . . . . #
    . . . # .
    # . # . .
    . # . . .
    `)
```

# Ultrasonic Distance Sensor with Microbit, 4-Digit Display & Grove

## {Introduction @unplugged}
Let's detect distance using @boardname@ , Grove and an Ultrasonic Distance Sensor!
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


## Collecting Parts @unplugged @fullscreen
Lets collect all the parts needed for this tutorial

![Parts Needed: 1 ultrasonic sensor, 1 4-digitDisplay, 1 microbit, 1 sheild](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveSensors/Ultrasonic%20Sensor.png)


## Connecting Everything @unplugged

1. Plug the microbit ** ( 4 ) ** into the Shield ** ( 3 ) ** 
2. Plug the Ultrasonic Sensor ** ( 1 ) ** into the P0/P14 pin
(we won't use this until later in the tutorial)
3. Plug the 4-Digit Display ** ( 2 ) ** into the P1/P15 pin 

![Connection Image](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/ultrasonicDisplay.jpg)

## Time to Code! @unplugged

First, we need to program the 4-Digit Display to show an initial value! 

```blocks
let _4Digit: grove.TM1637 = null
_4Digit = grove.createDisplay(DigitalPin.P1, DigitalPin.P15)
_4Digit.show(0)
```
```validation.local
# BlocksExistValidator
* Enabled: false
```

## {step one: set up display}
Remove ``||basic:show leds||`` and place a ``||grove:Set 4Digit to Display||`` block inside the ``||basic:On Start||``. 

Set the pins to ``||grove:P1||`` and ``||grove:P15||``

This tells the microbit how to work with the display.

```blocks
// @highlight
let _4Digit = grove.createDisplay(DigitalPin.P1, DigitalPin.P15)

```

## {Setup Initial Display}
------------------
Now insert a ``||grove:4Digit show number||`` after the ``||grove:Set 4Digit to Display||``

This will show a "0" on the display. Remember to ``|Download|`` the code! 

```blocks
let _4Digit: grove.TM1637 = null
_4Digit = grove.createDisplay(DigitalPin.P1, DigitalPin.P15)
// @highlight
_4Digit.show(0)
```


## Change the Display Preparation
------------------
Place a ``||basic:Forever||`` block and insert a ``||grove:4Digit show number||``. This prepares the display for the Ultrasonic Distance Sensor.

```blocks
let _4Digit: grove.TM1637 = null
_4Digit = grove.createDisplay(DigitalPin.P0, DigitalPin.P14)
_4Digit.show(0)
// @highlight
basic.forever(function () {
    _4Digit.show(0)
})
```


## Ultrasonic Distance
------------------
Replace the "0" in the ``||grove:4Digit show number||`` with a ``||grove:(V2)Ultrasonic Sensor in (cm) at 'PO'||`` block



```blocks
let _4Digit: grove.TM1637 = null
_4Digit = grove.createDisplay(DigitalPin.P0, DigitalPin.P14)
_4Digit.show(0)
basic.forever(function () {
    _4Digit.show
    // @highlight
    (grove.measureInCentimetersV2(DigitalPin.P0))
})
```

## Download & Test Program
--------------------
Click ``|Download|`` to transfer your code.
The 4Digit Display will show how far away something is from the Ultrasonic Sensor!

## End of tutorial
Well done! You've reached the end of this tutorial - Click ``|✓ Done|`` to open a New Project.

```package
Grove=github:seeed-studio/pxt-grove
```

```validation.global
# BlocksExistValidator
```