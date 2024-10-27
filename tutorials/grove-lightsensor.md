<!--
Written by: casey 

Last updated: 16/08

Ready for Upload: Y

Tasks:
- add picture of microbit graph to 'time to code!'
- validation issue with pin block 'analog read pin (P0), "Detect & Graph the Light Level" step not validated
-->

### @diffs true

# Grove Light Sensor with Microbit

## {Introduction @unplugged}
Let's plot the level of light using @boardname@ and a Grove Light Sensor!
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

![Parts Needed:1x Grove Light Sensor, 1x Grove Shield, 1x micro:bit](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveSensors/GroveLightSensor-parts.png)


## Connecting Everything  @fullscreen @unplugged
1. Plug the Microbit ** ( 3 ) ** into the Shield ** ( 2 ) **
2. Plug the LED ** ( 1 ) ** into the P0/P14 pin.

![image](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/lightsensor.jpg)

## Time to Code @unplugged

First, let's setup the Micro:bit display to plot bar graphs.

## Setup Micro:bit Graph
Place a ``||basic:forever||`` block and insert a ``||led:plot bar graph of ... up to||`` block. 
Change the ``||led:up to||`` number from "0" to "1023" 

```blocks
// @highlight
basic.forever(function () {
   
    led.plotBarGraph(
    0,
    1023
    )
})
```


## Detect & Graph the Light Level
-------------------------------
Place a ``||pins:analog read||`` into the ``||led:plot bar graph of||`` field

```blocks
basic.forever(function () {
    // @highlight
    led.plotBarGraph(
    pins.analogReadPin(AnalogPin.P0),
    1023
    )
})
```

## Add a Pause

To give the sensor enough time to work, place a ``||basic:pause||`` after the ``||led:plot bar graph of... up to..||``

Change the value of the pause to '10'

```blocks
basic.forever(function () {
    led.plotBarGraph(
    pins.analogReadPin(AnalogPin.P0),
    1023
    )
    // @highlight
    basic.pause(10)
})
```


## Download & Test

Click ``|Download|`` to transfer your code

As you cover the light sensor the microbit graph should go up/down

## End of tutorial

Well done! You've reached the end of this tutorial - Click  ``|✓ Done|`` to open a New Project.

```validation.global
# BlocksExistValidator
```
