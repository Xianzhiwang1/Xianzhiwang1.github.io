# Project-01 My Custom Keymap using Kmonad 

Let me tell you about this wonderful open source project Kmonad and how I use it


### My kmonad config

I have three layers (inspired by the `lily58` split keyboard layout,

and the `Corne` keyboard layout found at this [website](https://mark.stosberg.com/markstos-corne-3x5-1-keyboard-layout/)

the default: `qwerty` layer

numbers on the home row: `lower` layer

left down up right at hjkl: `raise` layer

### space key has dual functionality with *tap* versus *hold*:

in the `qwerty` layer:

tap: acts as ordinary space key

hold: (more than 150 millisecond) toggles into the `lower` layer

If we are already in `raise` layer or `lower` layer:

tap the space key: acts as ordinary space key

hold the space key: (more than 150 millisecond) toggles back to the `qwerty` layer (not sure if this is useful)

`F1` key switches between `qwerty` layer and `lower` layer

`F2` key switches between `qwerty` layer and `raise` layer

*Note that we don't usually **switch** to the `lower` layer, we would 
rather just use our thumb to **toggle**, so upon release the space key,
we automatically go back to the `qwerty` layer.*

I also put the modifier keys on the Home Row. Thus, I might make the 
`left Shift` key into a `toggle` key for `raise` layer, using the *tap* versus *hold* functionality.

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







