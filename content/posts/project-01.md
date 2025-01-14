+++
date = '2025-01-14T12:48:18-06:00'
draft = false 
title = 'Project 01'
+++


# Project-01 My Custom Keymap using Kmonad 

Let me tell you about this wonderful keyboard management tool called 
[Kmonad](https://github.com/kmonad/kmonad)
and how I use it [(link)](https://github.com/Xianzhiwang1/i3-config/).


### My kmonad config
In my own words, kmonad is a software level (contrast to firmware level)
tool that let you to remap your keys however you want. In perticular, 
it allows you to define different **layers**, thus allowing the same key 
to produce different symbols when typed in different layers.

I have three layers (inspired by the `lily58` split keyboard layout,
and the `Corne` keyboard layout found at this [website](https://mark.stosberg.com/markstos-corne-3x5-1-keyboard-layout/)),
and they are as follows:

1. the default: `qwerty` layer

1. numbers on the home row: `lower` layer

1. left down up right at hjkl: `raise` layer

### space key has dual functionality with *tap* versus *hold*:

in the `qwerty` layer:

 - tap: acts as ordinary space key

 - hold: (more than 150 millisecond) toggles into the `lower` layer

If we are already in `raise` layer or `lower` layer:

 - tap the space key: acts as ordinary space key

 - hold the space key: (more than 150 millisecond) toggles back to the `qwerty` layer (not sure if this is useful)

 In addition to the **toggle** functionality, which means one must hold down the toggle key for the layer to remain activated,
there is the **switch** functionality, which means we just need to tap the switch key once, and we are in the desired layer, 
without needing to hold it down the entire time. Then we can tap a another switch key (usually the same key) to swich back to 
the layer we started with. In my config, we have the following swich keys:

1. `F1` key switches between `qwerty` layer and `lower` layer

1. `F2` key switches between `qwerty` layer and `raise` layer

*Note that we don't usually **switch** to the `lower` layer, we would 
rather just use our thumb to **toggle**, so upon release the space key,
we automatically go back to the `qwerty` layer.*

I also put the modifier keys on the Home Row. Thus, I might make the 
`left Shift` key into a `toggle` key for `raise` layer, using the *tap* versus *hold* functionality.

### Home Row Modifiers
I have put the modifier keys on my Home Row with the following order:
 - Pinkie: `Shift`
 - Ring finger: `Ctrl`
 - Middle finger: `Alt` or sometimes called `Meta`
 - Index finger: `Super` aka `Windows key` aka `OS key`

Again, this is using the *tap* versus *hold* functionality. If I *tap* the key,
then I am typing `asdf` and `jkl;` normally. However, if I *hold* the key, i.e., keep my 
finger pressed down on the key longer than 150 millisecond before releasing, then I activate 
the modifier key, and I could tap another key at the same time as one would normally use modifier keys.
(for example, `Ctrl + T` to open a new tab in firefox browser).


### *"Why would I ever want to do this to my keyboard?" you asked.*

well, the philosophy is we could use the thumb more,

use left thumb to hold the space key to toggle into `lower` layer,

then the right hand could easily type

```
`!@#$%`
    `12345`
        `_-+[{`,
```

and upon releasing the space key, we automatically gets back to the `qwerty` layer.

While use right thumb to hold the space key to toggle into `lower` layer,

then the left hand could easily type
```
            `^&*()`
                `67890`
                    `}],.=`,
```
and upon releasing the space key, we automatically gets back to the `qwerty` layer.

Hence, holding the space bar using our thumbs acts like Shift, but with different layers and keys.








