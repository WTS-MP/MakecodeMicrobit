<!--
written by:  

last updated: 16/08

tasks:
change tutorial name to grove-ledstrip 

-->

### @diffs true

# LED Strip with Microbit & Grove
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
Let's create light using @boardname@ , Grove and LED Strips!
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
Let's collect all the parts needed for this tutorial   
![GroveShield,Servo,Microbit,Cable](https://raw.githubusercontent.com/CarlTS/microbit-grove/master/assets/LED-neopixel-strip.png)

## Connecting Everything @unplugged
Connect the parts together.
![LED Strip to Grove in P0/P14, microbit into the Grove Shield](https://raw.githubusercontent.com/CarlTS/microbit-grove/master/assets/LED-neopixel-connect.png)

## Time to Code @unplugged
We will need to set up the LED Strip to use it correctly.
In the next step, you will need to use ``||neopixel:set [strip] to NeoPixel at Pin [P0] with [24] leds as RGB||`` 
```blocks
let strip = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)
```
```validation.local
# BlocksExistValidator
* Enabled: false
```

## {Coding Time}
► Open the ``||neopixel:Neopixel||`` category in your toolbox   
► Find the ``||neopixel:set (strip) to NeoPixel at Pin [P0] with [24] leds as RGB||`` and place it into the ``||basic:on start||`` block.  
```blocks
// @highlight
let strip = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)
```

## {Setting the colour }
► Now place a ``||neopixel: (strip) show color [red]||`` after the previous block   
💡 This will tell the leds to light up red
```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    let strip = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)
    // @highlight
    strip.showColor(neopixel.colors(NeoPixelColors.Red))
})
```

## Time to test the movement
► ``|Download|`` your code to the micro:bit and watch your LEDs light up!


## Testing Single Colour @unplugged
You should have seen your LED strip light up!  
💡 If it is not lighting up, it might not be plugged in correctly


## Test different numbers
► Try changing the colour instead of red, and test again   
💡 Don't forget to ``|Download|`` each time to test  
💡 Think about how the colours are made.

## {More Control}
► Let us control the colour with a button    
► Insert a ``||input:on button [A] pressed||`` on the workspace   
```blocks
// @highlight
input.onButtonPressed(Button.A, function () {

})
```

## {More Control - adding light}
► Place another ``||neopixel: (strip) show color [red]||`` inside the ``||input:on button [A] pressed||``   
► Set ``||input:[red]||`` to ``||input:[blue]||``
```blocks
input.onButtonPressed(Button.A, function () {
    // @highlight
    strip.showColor(neopixel.colors(NeoPixelColors.Blue))
})
let strip: neopixel.Strip = null
strip = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)

```

## {Download to micro:bit}
► Time to test the Light Control   
► ``|Download|`` your code to the micro:bit    
► Pressing [A] should set the colour to blue
 
## Congratulations @unplugged
You have learnt how to control an LED Strip that could be added to your own project.   
   
Now try the challenges on the following pages   
► Complete Control   
► Rotate Colour

## Complete Control Challenge
► Pressing A sets colour to green   
► Pressing B sets colour to purple   
► Pressing A and B turns leds off

## Rotate Colour Challenge
► Colour changes through all the different hues   
```blocks
let strip = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)
strip.showRainbow(1, 360)
basic.forever(function () {

})
strip.rotate(1)
strip.show()
```

```package
neopixel=github:microsoft/pxt-neopixel#v0.6.12
```

```validation.global
# BlocksExistValidator
```