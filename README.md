# FSRForReShade
An implementation of AMD's FidelityFX Super Resolution for ReShade / SweetFX

Based on goingdigital's shadertoy shader: https://www.shadertoy.com/view/stXSWB

It's essentially a conversion from glsl to hlsl with a few multiply-adds thrown in to reduce instructions.

Designed with SweetFX 2.0 + ReShade. Something may need to be changed for it to work with newer versions.

Downscales the output from the game, then upscales it again.

![Downscaled to 1080p then upscaled back to 4K](https://i.imgur.com/GKFamm4.jpg)
Downscaled to 1080p from 4K then upscaled back to 4K

![1440p -> 4K](https://i.imgur.com/Pg4vsFG.jpg)
Same but to 1440p

![4K -> 4K](https://i.imgur.com/esr8xRN.jpg)
4K scaled to 4K

![Native 4K](https://i.imgur.com/UuRuIgJ.jpg)
Native 4K
