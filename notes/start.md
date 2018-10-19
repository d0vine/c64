C64 primer
==========

Intro
-----

The stuff that I describe here is done mostly (or entirely, we'll see how much I'll be into foolin' around with c64) on the BlackBox v8 cartridge. The symbol `←` means the arrow key, on the VICE emulator it's under tilde (`~`).

Convention
----------

Since letter input is case insensitive, remember to input the text with lowercase letters only. We will use uppercase letters only to be consistent with what is shown on the screen.

For code listings, we will use the convention shown below:

```
←MO
  PC  SR AC XR YR SP
;BA93 33 60 04 3D FB
 .A 1000
 1000 Z01 LDA #01	; white
 1002 STA D020
 1005 JMP Z01
 1008 F
,1000 LDA #01
,1002 STA D020
,1005 JMP 1000
.G 1000
(white border set, freeze)
```

This means that:

- we enter the monitor mode (described below)
- we start assembling the program at address `0x1000` (remember that numbers/addresses are in hex)
- load hex value `0x01` into the accumulator
- store the accumulator value under address `d020` (border color)
- jump back to address `0x1000` thus creating an endless loop
- finish the program (`F`)
- run the program from address `0x1000`

Please note how:

- register values are printed at the monitor start (`PC`, `SR`, `AC` etc.),
- we tell the assembler where to write the program in memory - we need to know where the program can be stored, otherwise we can do some harm (like a CPU jam requiring a reset),
- hex **values** (not addresses) are prepended with the `#` symbol,
- current addresses are indicated as a prefix to an assembly mnemonic - this is **very** important, as what we input are **only the mnemonics and their operands**; addresses will be calculated automatically,
- labels are prefixed with `Z` and can be used with `JMP` (so that we don't need to know the exact address at the moment of writing),
- comments are indicated with `;` - those are only for your information, do not input them into the assembler (to save you some time),
- a remark is added in parantheses - this is just to describe a side effect should there be any. 

Monitor mode
------------

When playing around with assembly, inspecting memory etc. we will use the monitor mode. To enter the monitor mode, input:

```
←MO
```

from the main screen (after pressing the `SPACE` button). To exit this mode, simply press `X` and `ENTER`, you'll be back at the start screen (indicated by the `READY` message).

Monitor commands:

```
TODO (table?)
```

Memory layout
-------------

TODO