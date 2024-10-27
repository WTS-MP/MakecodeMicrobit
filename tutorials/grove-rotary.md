<!--
Written by: casey 

Last updated: 16/08

Ready to release: Y

Tasks:
add photo image of microbit display to 'time to code'
-->


### @diffs true

# Rotary Encoder with Microbit

## {Introduction @unplugged}
Let's plot rotary angles using @boardname@ and a Rotary Angle Sensor!
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

```template
basic.showLeds(`
    . . . . .
    . . . . #
    . . . # .
    # . # . .
    . # . . .
    `)
```


## Collect Parts @unplugged

For this tutorial you will need;

![Parts Needed 1 Rotary, 1 microbit, 1 sheild](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveSensors/GroveRotary.png)


## Connecting Everything  @fullscreen @unplugged
1. Plug the Microbit ** ( 3 ) ** into the Shield ** ( 2 ) **
2. Plug the LED ** ( 1 ) ** into the P0/P14 pin.

![Connection Image](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/rotaryAnglesensor.jpg)

## Time to Code @unplugged

First, let's setup the Micro:bit to plot bar graphs.

## Setup Micro:bit Graph
Place a ``||basic:forever||`` block and insert a ``||led:plot bar graph of ... up to||`` block. Change the ``||led:up to||`` number from '0' to '1023' 

```blocks
// @highlight
basic.forever(function () {
    // @highlight
    led.plotBarGraph(
    0,
    1023
    )
})
```



##  Connect the Rotary Potentiometer to the Micro:bit
-------------------------------
Place a ``||pins:analog read||`` into the ``||led:plot bar graph of||`` field

```blocks
// @highlight
basic.forever(function () {
    // @highlight
    led.plotBarGraph(
        // @highlight
        pins.analogReadPin(AnalogPin.P0),
        1023
    )
})
```

## Add a Pause
-----------------------------------------------------
To give the sensor enough time to work, place a ``||basic:pause||`` after the ``||led:plot bar graph of... up to..||``. The value of the pause should be "100ms"

```blocks
basic.forever(function () {
    led.plotBarGraph(
    pins.analogReadPin(AnalogPin.P0),
    1023
    )
    // @highlight
    basic.pause(100)
})
```



## Download & Test Program
--------------------
Click ``|Download|`` to transfer your code. 

As you turn the rotary angle sensor, the micro:bit graph should go up/down!

## End of tutorial

Well done! You've reached the end of this tutorial - Click  ``|✓ Done|`` to open a New Project.

```validation.global
# BlocksExistValidator
```



