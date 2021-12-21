# FSRForReShade
An implementation of AMD's FidelityFX Super Resolution for ReShade / SweetFX

Based on goingdigital's shadertoy shader: https://www.shadertoy.com/view/stXSWB

It's essentially a conversion from glsl to hlsl with a few multiply-adds thrown in to reduce instructions.

Designed with SweetFX 2.0 + ReShade. Something may need to be changed for it to work with newer versions (I think the vertex shader `FullscreenTriangle` needs to be replaced with `PostProcessVS`).

Downscales the output from the game, then upscales it again.

## Usage

Prerequisites:

- Have ReShade / SweetFX "installed" for the game you want to shade

Required:

- Copy the shader to the shaders folder, e.g. "NFSUnderground2/SweetFX/Shaders", where all the other shaders live
- In "SweetFX/SweetFX_Settings.txt" add the line `#define USE_FSR 1` after the use custom line
- In "SweetFX/Shaders/Main.h" add the following code after custom:

```
/*-----------------------.
  | ::        FSR       :: |
  '-----------------------*/
#if (USE_FSR == 1)
	#include "SweetFX\Shaders\FSR.h"
#endif
```

Optional:

- Edit line 259 of "SweetFX/Shaders/FSR.h" to change the value of `rendersize` to the size you want to shrink the image to before it is upscaled.

## Screenshots

![Downscaled to 1080p then upscaled back to 4K](https://i.imgur.com/GKFamm4.jpg)
Downscaled to 1080p from 4K then upscaled back to 4K

![1440p -> 4K](https://i.imgur.com/Pg4vsFG.jpg)
Same but to 1440p

![4K -> 4K](https://i.imgur.com/esr8xRN.jpg)
4K scaled to 4K

![Native 4K](https://i.imgur.com/UuRuIgJ.jpg)
Native 4K
