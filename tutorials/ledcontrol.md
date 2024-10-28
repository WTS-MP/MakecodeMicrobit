<!--
Written by: casey 

Last updated: 16/08

Ready for Upload: Y

Tasks:
name change to grove-led, (replace other with grove-ledstrip)

-->

### @diffs true

# Grove LED control with Microbit

## {Introduction @unplugged}
Let's turn a LED on and off using @boardname@ and a Grove LED!
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

![Parts Needed: 1x Grove LED, 1x Grove Shield, 1x micro:bit](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/GroveSensors/GroveLED-parts.png)


## Physical Connection  @fullscreen @unplugged
1. Plug the Microbit ** ( 3 ) ** into the Shield ** ( 2 ) **
2. Plug the LED ** ( 1 ) ** into the P0/P14 pin.

![image](https://raw.githubusercontent.com/CarlTS/grove-sensor-tutorial/master/images/ledbuttonpress.jpg)


## Turning the light On

Place an ``||input:on Button A Pressed||`` then add a ``||pins:digital Write Pin||`` block (Under Advanced)

Change the '0' to a '1' (This will make the light turn on)

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
   
    pins.digitalWritePin(DigitalPin.P0, 1)
})

```
1 = On

0 = Off

##  Turning the light Off

Place another ``||input:on Button A Pressed||`` and change the button option to ``||input:[B]||``

Add another ``||pins:digital write pin||``

```blocks
input.onButtonPressed(Button.A, function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
})
// @highlight
input.onButtonPressed(Button.B, function () {
    // @highlight
    pins.digitalWritePin
     (DigitalPin.P0, 0)
})
```
1 = On

0 = Off

## Download & Test

Click ``|Download|`` to transfer your code and press button A and B to see if the works 

## End of tutorial

Well done! You've reached the end of this tutorial - Click  ``|✓ Done|`` to open a New Project.

```validation.global
# BlocksExistValidator
```

