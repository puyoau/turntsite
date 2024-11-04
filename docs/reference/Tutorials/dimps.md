# Input Display ("Dimp") Commands and Examples

Dimps are the internal name for the display of active keypresses

## Commands

###```ui_dimp_style```

Set int to change the dimp style.

For now, using a number with an undefined crosshair will just vanish it until a new one is set.

| Value | Description |
| ----- | ----------- |
| 0     | Nothing     |
| 1     | Small arrows and single letters around crosshair |
| 2     | Pixel arrows and graphics at bottom of screen |
| 3     | Legacy Elim dimp with a touchup |

###```ui_dimp_color_pressed```

Sets color of dimp icons when associated key is being pressed.

Set 4 ints to change color and transparency.

ui_dimp_color_pressed [R] [G] [B] [A]

R = Red component (0 to 255)  
G = Green component (0 to 255)  
B = Blue component (0 to 255)  
A = Alpha transparency 0 (transparent) to 255 (opaque)

###```ui_dimp_color_unpressed```

Sets color of dimp icons when associated key is NOT being pressed.

Set 4 ints to change color and transparency.  

ui_dimp_color_unpressed [R] [G] [B] [A]

R = Red component (0 to 255)  
G = Green component (0 to 255)  
B = Blue component (0 to 255)  
A = Alpha transparency 0 (transparent) to 255 (opaque)

## Examples

``` title="Default"
ui_dimp_style 1
ui_dimp_color_pressed 255 255 255 255
ui_dimp_color_unpressed 255 255 255 128
```

``` title="Red pixel arrows that vanish unless pressed"
ui_dimp_style 2
ui_dimp_color_pressed 255 0 0 255
ui_dimp_color_unpressed 0 0 0 0
```