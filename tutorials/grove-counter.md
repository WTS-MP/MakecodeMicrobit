### @diffs true

# 4-Digit Display with Microbit

## {Introduction @unplugged}
Let's count using @boardname@, Grove and a 4-Digit Display!

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

## Collecting Parts @unplugged

For this tutorial you will need;

![Parts Needed: 1 4-digitDisplay, 1 microbit, 1 sheild](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveSensors/4DigitDisplay.png)

## Connecting Everything @fullscreen @unplugged 
1. Plug the Microbit (3) into the Shield (2)
2. Plug the 4Digit Display (1) into the P0 pin
![Connection Image](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/4digitdisplaysetup.jpg)

## Time to Code ! @unplugged

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

## Setup the display
Place a ``||grove:Set 4Digit to Display||`` block inside a ``||basic:On Start||``. Set the pins to ``||grove:P0||`` and ``||grove:P14||``

```blocks
// @highlight
let _4Digit = grove.createDisplay(DigitalPin.P0, DigitalPin.P14)

```

## Program the Initial Setup
Now insert a ``||grove:4Digit show number||`` after the ``||grove:Set 4Digit to Display||``. This will show a 0 on the display.

Remember to click ``|Download|`` !

```blocks
let _4Digit: grove.TM1637 = null
_4Digit = grove.createDisplay(DigitalPin.P0, DigitalPin.P14)
// @highlight
_4Digit.show(0)
```

## Change the Display
Place a ``||input:On Button A Pressed||`` and insert a ``||grove:4Digit show number||``

This prepares the display for a random number generator in the next step

```blocks
// @highlight
    input.onButtonPressed(Button.A, function () {
        // @highlight
        _4Digit.show(0)
    })
    
    let _4Digit: grove.TM1637 = null
    _4Digit = grove.createDisplay(DigitalPin.P0, DigitalPin.P14)
    _4Digit.show(0)
```


## Display Random Numbers
Inside the ``||math:Math||`` tab, you will find the ``||math: pick random '0' to '10'||``

Replace the "0" in the ``||grove:4Digit show number||`` with the ``||math: pick random '0' to '10'||`` block

```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    _4Digit.show(randint(0, 10))
})
let _4Digit: grove.TM1637 = null
_4Digit = grove.createDisplay(DigitalPin.P0, DigitalPin.P14)
_4Digit.show(0)
```

## Download & Test Program 

Click ``|Download|`` to transfer your code.
When you press the 'A' button, the number will randomly change on the 4 Digit Display

## End of tutorial

Well done! You've reached the end of this tutorial - Click  ``|✓ Done|`` to open a New Project.

```package
Grove=github:seeed-studio/pxt-grove
```

```validation.global
# BlocksExistValidator
* markers: validate-exists
```
