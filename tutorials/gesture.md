<!--
Written by:  

Last updated: 19/08

Ready for Upload: Y

-->

### @diffs true

# Grove Sensor with Microbit & Grove
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
Let's create gesture control using @boardname@ , Grove and a Gesture Sensor!
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

<!---------------------------------------------------------------  
-------------------------  NEW ACTIVITY -------------------------
----------------------------------------------------------------->

## Step 1 - Collect Parts @unplugged
Left or Right Gestures
=============
In this activity you will learn how to use the gesture sensor.

Collect the parts you will need;
![Parts Needed: 1 Gesture, 1 microbit, 1 sheild](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveSensors/GestureSensor.png)

## Physical Connection
-------------------
1. Plug the microbit into the Shield 
2. Plug the Gesture Sensor into the I2C Pin
![Connection Image](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/gestureSensor.jpg)


## Step 3 - Program
Coding: Gesture Input
------------------
Place a ``||grove:on gesture||`` block and change the gesture to ``||grove:Right||``

```blocks
grove.onGesture(GroveGesture.Right, function () {
})
```

## Step 4 - Program
Coding: Action from Gesture Input
------------------
Place a ``||basic:show string||`` block inside the ``||grove:on gesture||`` and change the word from "Hello" to "R"

```blocks
grove.onGesture(GroveGesture.Right, function () {
    basic.showString("R")
})
```

## Step 5 - Program
Coding: Other Gestures
------------------
Place a new ``||grove:on gesture||`` block and change the gesture to ``||grove:Left||``
Insert a ``||basic:show string||`` and change the word to "L"


```blocks
grove.onGesture(GroveGesture.Right, function () {
    basic.showString("R")
})
grove.onGesture(GroveGesture.Left, function () {
    basic.showString("L")
})
```
This will now sense both directions

<!---Additional Step needed to demonstrate how pause works so buffer does not fill up --->

## Step 6 - Download Program
Download & Test
--------------------
Click ``|Download|`` to transfer your code

When you move your hand Right, the screen will say "R", when you move your hand Left, the screen will say "L"


```package
Grove=github:seeed-studio/pxt-grove
```

```validation.global
# BlocksExistValidator
```