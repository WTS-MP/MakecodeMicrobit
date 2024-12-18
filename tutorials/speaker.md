<!--
written by: casey 

last updated: 26/11

Ready for Upload: Y

Image Update: Complete
-->

### @diffs true

# Speaker with Microbit

## {Introduction @unplugged}
Let's play music using @boardname@ and an external Speaker!
![WTS Logo](https://raw.githubusercontent.com/WTS-MP/MakecodeMicrobit/refs/heads/master/assets/WTSLogo.png)

  - :lightbulb: **Helpful Hints**   
  Look out for hints indicated by a light bulb   
You can click the ``||game: OK ➔ ||`` or ``| ➔ Next |`` button on the right after each step to continue.

## Testing the micro:bit @unplugged
We want to make sure everything is working correctly before we start.

![Plugging in microbit](https://raw.githubusercontent.com/WTS-MP/MakecodeMicrobit/refs/heads/master/assets/microbitplugin.gif)   

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

![Parts Needed: 1 Speaker, 1 microbit, 1 sheild](https://raw.githubusercontent.com/WTS-MP/MakecodeMicrobit/refs/heads/master/assets/GroveSensors/GroveSpeaker.png)


## Physical Connection @fullscreen @unplugged

1. Plug the Microbit ** ( 3 ) ** into the Shield ** ( 2 ) **
2. Plug the Grove Speaker ** ( 1 ) ** into the P0/P14 pin.

![Connection Image](https://raw.githubusercontent.com/WTS-MP/MakecodeMicrobit/refs/heads/master/assets/GroveSensors/speaker.jpg)

## Playing Tones
Place a ``||input:on button A pressed||`` block and insert a ``||music:play tone 'middle C' for '1 beat'||`` block. 

Try out different notes!

```blocks
// @highlight
input.onButtonPressed(Button.A, function () {
    // @highlight
    music.playTone(262, music.beat(BeatFraction.Whole))
})
```

## Playing Melodys

Place a ``||input:on button A pressed||`` block and change  ``||input:[A]||``  to  ``||input:[B]||`` 

Insert a ``||music:play melody||`` block. Create a melody

```blocks
input.onButtonPressed(Button.A, function () {
    music.playTone(262, music.beat(BeatFraction.Whole))
})
// @highlight
input.onButtonPressed(Button.B, function () {
    // @highlight
    music.playMelody("- - - - - - - - ", 120)
})
```


## Download Program

Click ``|Download|`` to transfer your code

When you press 'A' the tone will play, when you press  'B'  the melody will play

## Play Around 

Try out different melodies and beats per minute (bpm)

Remember to ``|Download|`` if you make changes!

## End of tutorial

Well done! You've reached the end of this tutorial - Click  ``|✓ Done|`` to open a New Project.

```validation.global
# BlocksExistValidator
```
-