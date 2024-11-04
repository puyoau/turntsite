# Crosshair Commands & Examples

Dimps are the internal name for the display of active keypresses

## Commands

###```ui_crosshair_style```
Set int to change crosshair style.  
All components are hideable.  
You can remove crossbars from the dot style to make just a dot.  
Using numbers with undefined crosshairs will make it vanish.

| Value | Crosshair |
| - | - |
| 0 | Nothing |
| 1 | Square with crossbars |
| 2 | Dot with crossbars |
| 3 | Column |
| 4 | Tri star |
| 5 | Hot dog |
| 6 | Immutable cross (unaffected by _parts cvars as a fallback) |

###```ui_crosshair_color```
Set 4 ints to change crosshair color and transparency

!!! info "ui_crosshair_color [R] [G] [B] [A]"
    R = Red component (0 to 255)  
    G = Green component (0 to 255)  
    B = Blue component (0 to 255)  
    A = Alpha transparency 0 (transparent) to 255 (opaque)

###```ui_crosshair_scale```
Scale the crosshair size, default 1. Quick and easy.  
Scaling through other custom parts cvars should be more precise, if available.

`ui_crosshair_scale 0.5`

###```ui_crosshair_angle```
Rotate the crosshair around centre, from -180 to 180 degrees. Default 0.
This will carry to all crosshairs so remember to set back to 0 if you change styles!

`ui_crosshair_scale 180`

###```ui_crosshair_parts_c```
Center components can be resized with ints, or made invisible using 0.
ui_crosshair_parts_c [A] [B]
A = width
B = height

###```ui_crosshair_parts_h```
Horizontal crosshair components can be resized with ints, or made invisible using C = 0.
ui_crosshair_parts_h [A] [B] [C]
A = length, must be >=1
B = buffer from center
C = thiccness, zero to hide horizontal components

###```ui_crosshair_parts_v```
Vertical crosshair components can be resized with ints, or made invisible using C = 0.
ui_crosshair_parts_v [A] [B] [C]
A = length, must be >=1
B = buffer from center
C = thiccness, zero to hide vertical components

## Examples

``` title="Red cross (default)"
ui_crosshair_style 1
ui_crosshair_color 255 0 0 255
ui_crosshair_parts_c 2 2
ui_crosshair_parts_h 10 2 2
ui_crosshair_parts_v 10 2 2
```

``` title="Green dot"
ui_crosshair_style 2
ui_crosshair_color 0 255 0 255
ui_crosshair_parts_c 2 2
ui_crosshair_parts_h 1 0 1
ui_crosshair_parts_v 1 0 1
```

``` title="Black CGAZ column"
ui_crosshair_style 3
ui_crosshair_color 0 0 0 255
ui_crosshair_parts_v 40 0 1
```

``` title="Hot Dog"
ui_crosshair_style 5
ui_crosshair_scale 2
```