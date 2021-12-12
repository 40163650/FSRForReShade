# FSRForReShade
An implementation of AMD's FidelityFX Super Resolution for ReShade / SweetFX

Based on goingdigital's shadertoy shader: https://www.shadertoy.com/view/stXSWB

It's essentially a conversion from glsl to hlsl with a few multiply-adds thrown in to reduce instructions.

Designed with SweetFX 2.0 + ReShade. Something may need to be changed for it to work with newer versions.

Downscales the output from the game, then upscales it again.
