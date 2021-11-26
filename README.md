# Guild-Wars-2-Ray-Tracing

SETUP

1. Download my latest shader pack which includes everything except RTGI from here:  , or go get the shaders from their sources. I didn't write any of them. Don't forget the ray tracing shader (RGTI) requires you go sign up for the dev's Patreon.

2. If you have a file named "d3d9.dll" in the root of your PSOBB folder, you can probably skip this step. If you instead have "d3d8.dll" in there, or the default that comes with Ephinea is dinput8.dll... Go get the latest DX8to9 dll file named "d3d8.dll" from https://github.com/crosire/d3d8to9/releases and put it in the root of the PSOBB directory, overwriting the default if you're asked. Feel free to back anything up at any time. This file makes PSOBB DX9, which lets reshade work.

    Download the modded version of ReShade that disables the network buffer overflow: https://github.com/Not-Smelly-Garbage/Reshade-Unlocked/releases. It's required for this game to bypass the reshade network buffer overflow. Install it, targeting online.exe, and using DX9. Don't set up any default shaders is my suggestion, my zip has the ones you need except RGTI.

    Unpack the shaders and put them in the reshade-shaders directory in the PSOBB folder. If there's no reshade-shaders directory, make sure you installed ReShade (the modded one) in step 3 first. If you did that, just make the directory named reshade-shaders and put the contents of the zip in there. In the Reshade install or edit, you can hit "edit ReShade settings" and make sure: -> Preset is .\PSO-RayTracing[whatever version is].ini -> Effect path, Texture path is set as such: [Drive]:\Users[user]\reshade-shaders\Shaders\ and [Drive]:\Users[user]\reshade-shaders\Textures -> Leave the rest unchecked, you can enable fps/clock/performance mode in reshade in the game.

    Download the PSO-RayTracing-v[X].ini file in this repo and put it in the root with online.exe and psobb.exe.

    When you load the game ReShade defaults to "Home" to launch the menu. You can pick the ini from the top. You may need to set the global processing parameters so I will save you a lot of headaches. Put this in [General] in the ReShade.ini (not my ini, the default reshade one), OR just read it and type the values in ReShade after clicking the button to edit the global preprocessing settings: PreprocessorDefinitions=RESHADE_DEPTH_LINEARIZATION_FAR_PLANE=5000,RESHADE_DEPTH_INPUT_IS_UPSIDE_DOWN=0,RESHADE_DEPTH_INPUT_IS_REVERSED=0,RESHADE_DEPTH_INPUT_IS_LOGARITHMIC=0

That's it, you should be able to launch ReShade when you start PSOBB and select the "PSO-RayTracing-v[X]" profile. It;s still worth learning how it works, especially if you want to tweak things from this point.

TROUBLESHOOTING

Make sure you set the depth buffer in reshade (under the d3d9 tab). You might have to use the DisplayDepth shader to see if its detecting depth as you try the different depth buffers with your monitor resolution to find the right one. It can be a little tricky. Actually it's a lot tricky. Please recheck that you did step 6 above.
