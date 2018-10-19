C64 graphics
============

The basics
----------

To set the border color we use `d020`, for the background color we'd use `d021`. The full color list we can find on the [c64 wiki](http://www.c64-wiki.com/index.php/Color).

Examples:

```
←MO
  PC  SR AC XR YR SP
;BA93 33 60 04 3D FB
 .A 1000
 1000 LDA #01	; white
 1002 STA D020
 1005 JMP 1000
 1008 F
,1000 LDA #01
,1002 STA D020
,1005 JMP 1000
.G 1000
(white border set, freeze)
```

We used an endless loop because otherwise the border would just flash and we wouldn't see anything.

After this example a soft reset is required.
