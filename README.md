# NewProjectTemplate
A template for new projects in Unreal Engine 5.

![](https://img.shields.io/github/downloads/RYRY1002/NewProjectTemplate/total) ![](https://img.shields.io/github/commit-activity/m/RYRY1002/NewProjectTemplate) ![](https://img.shields.io/github/license/RYRY1002/NewProjectTemplate) ![](https://img.shields.io/github/issues/RYRY1002/NewProjectTemplate) ![](https://img.shields.io/github/v/release/RYRY1002/NewProjectTemplate?include_prereleases) ![](https://img.shields.io/github/repo-size/RYRY1002/NewProjectTemplate) ![](https://img.shields.io/github/stars/RYRY1002/NewProjectTemplate) ![](https://img.shields.io/github/contributors/RYRY1002/NewProjectTemplate)

## Installation
### Project Installation
1. Download the project
   - Downloads in the releases page are polished, final releases
   - Download the repository as a .7z or clone it for the most up to date version, but it may have bugs
2. Extract the .7z/.zip file
3. Copy the files to wherever you keep your Unreal Engine projects
4. Open Unreal Engine 5.0.2 and open the project
5. Done

### Pre-compiled Shaders Installation
1. Download the pre-compiled shaders from the latest release *(pre-compiled shaders will only be updated with new releases)*
2. Copy/Move the `Common` folder and place it in `C:\Users\<user>\AppData\Local\UnrealEngine`

### Plugins
If any of these plugins are not present, you will be prompted to disable them at launch.
You may need to recompile shaders if you choose to do this.

You may be prompted to recompile some plugins, this is required for the editor to start.
This only needs to be done once.

* NVIDIA DLSS/IS
  - Real time, AI powered image upscaling
  - Can be downloaded from https://developer.nvidia.com/rtx/ray-tracing/dlss/get-started#ue-version
  - Install to Engine\Plugins\Marketplace
* GraphPrinter
  - Makes it much easier to share graphs with other users
  - Credit to https://github.com/Naotsun19B/GraphPrinter
  - Comes pre-installed
* HLSL Material
  - Allows you to write materials in HLSL directly in the editor
  - Credit to https://github.com/Phyronnaz/HLSLMaterial
  - Comes pre-installed

## Updating existing projects
If you have a project that already uses this template, but you'd like to update it with new master materials and such,

1. Download the new version
2. Go into the `Content` folder and copy whatever you'd like to update.
3. Replace the old files with the new ones.

The shaders will need to recompile (~250 shaders), but once that's done, everything should just work.

## Materials
### Material Layer Assets
All base Material Layer assets can be located in `Game/Materials/_Layers`.

* `MasterBlends/Normal/blend-mask`
  - Uses a mask to blend between layers
* `MasterBlends/Normal/blend-procedural`
  - Uses perlin noise, lerps and height maps to blend between layers
* `MasterLayers/Normal/surface`
  - This layer asset should be used for regular surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
* `MasterLayers/Normal/surface_additive`
  - This layer asset should be used for things that are added to the scene (such as fire, steam, holograms, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Uses additive blend mode
* `MasterLayers/Normal/surface_masked`
  - This layer asset should be used for things that are either transparent or opaque (such as fences, chains, grates, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses masked blend mode
* `MasterLayers/Normal/surface_subsurface`
  - This material should be used for opaque materials where light bounces inside of them (such as wax, jade, skin, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Subsurface Amount, Subsurface Color and various tiling methods
* `MasterLayers/Normal/surface_translucent`
  - This layer asset should be used for things that are partially transparent (such as glass panes, bottles, water, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses translucent blend mode

* `MasterBlends/VT/VT_blend-mask`
  - Uses a mask to blend between layers
  - Uses virtual textures
* `MasterBlends/VT/VT_blend-procedural`
  - Uses perlin noise, lerps and height maps to blend between layers
  - Uses virtual textures
* `MasterLayers/VT/VT_surface`
  - This layer asset should be used for regular surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Uses virtual textures
* `MasterLayers/VT/VT_surface_additive`
  - This layer asset should be used for things that are added to the scene (such as fire, steam, holograms, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Uses additive blend mode
  - Uses virtual textures
* `MasterLayers/VT/VT_surface_masked`
  - This layer asset should be used for things that are either transparent or opaque (such as fences, chains, grates, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses masked blend mode
  - Uses virtual textures
* `MasterLayers/VT/VT_surface_subsurface`
  - This material should be used for opaque materials where light bounces inside of them (such as wax, jade, skin, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Subsurface Amount, Subsurface Color and various tiling methods
  - Uses virtual textures
* `MasterLayers/VT/VT_surface_translucent`
  - This layer asset should be used for things that are partially transparent (such as glass panes, bottles, water, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses translucent blend mode
  - Uses virtual textures

### Master Materials
Master Materials can be located in `Game/Materials/_MasterMaterials`.

* `Normal/surface_material`
  - This material be used for regular surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
* `Normal/surface_material_additive`
  - This material asset should be used for things that are added to the scene (such as fire, steam, holograms, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Uses additive blend mode
* `Normal/surface_material_masked`
  - This material should be used for things that are either transparent or opaque (such as fences, chains, grates, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses masked blend mode
* `Normal/surface_material_subsurface`
  - This material should be used for opaque materials where light bounces inside of them (such as wax, jade, skin, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Subsurface Amount, Subsurface Color and various tiling methods
* `Normal/surface_material_translucent`
  - This material should be used for things that are partially transparent (such as glass panes, bottles, water, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses translucent blend mode
* `Normal/decal_material`
  - This material should be used for regular decals
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods
* `Normal/decal_material_modulating`
  - This material should be used for decals that are added to the scene, but need shadowing (such as screws, cable ports, braille, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods
  - Uses modulate blend mode
* `Normal/decal_material_stain`
  - This material should be used for decals that are stains (such as puddles, dirt, blood, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods

* `VT/VT_surface_material`
  - This material should be used for regular surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Uses virtual textures
* `VT/VT_surface_material_additive`
  - This material should be used for things that are added to the scene (such as fire, steam, holograms, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Uses additive blend mode
  - Uses virtual textures
* `VT/VT_surface_material_masked`
  - This material should be used for things that are either transparent or opaque (such as fences, chains, grates, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses masked blend mode
  - Uses virtual textures
* `VT/VT_surface_material_subsurface`
  - This material should be used for opaque materials where light bounces inside of them (such as wax, jade, skin, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Subsurface Amount, Subsurface Color and various tiling methods
  - Uses virtual textures
* `VT/VT_surface_material_translucent`
  - This material should be used for things that are partially transparent (such as glass panes, bottles, water, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, Opacity and various tiling methods
  - Uses translucent blend mode
  - Uses virtual textures
* `VT/VT_decal_material`
  - This material should be used for regular decals
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods
  - Uses virtual textures
* `VT/VT_decal_material_modulating`
  - This material should be used for decals that are added to the scene, but need shadowing (such as screws, cable ports, braille, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods
  - Uses modulate blend mode
  - Uses virtual textures
* `VT/VT_decal_material_stain`
  - This material should be used for decals that are stains (such as puddles, dirt, blood, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods
  - Uses virtual textures

### Example Material Instances
Example Material Instances can be located in `Game/Materials/ExampleMaterials`.

* `DayOff-NightOn_LightFunction`
  - Shows an example of a light function taking advantage of the project's Day/Night time cycle
* `layer_example`
  - Shows an example of material layers being used

### Material Functions
Material Functions can be located in `Game/Materials/Functions`.

* `ApplyUVsLayers`
  - Applies UVs to layered materials
* `BreakNormalFromHeight`
  - This reverses the effect of the `StoreHeightInNormal` function 
* `MapAdjustments`
  - Adds configuration options
  - Used in all materials
* `Opacity`
  - Fix for `surface_material_masked` and `VT_surface_material_masked`
* `POM`
  - Adds Parallax Occlusion Mapping
  - Used in all master materials
* `StoreHeightInNormal`
  - Appends the height map to the normal map.
* `T2DtoFloat`
  - Converts a texture object to a float
* `UVs`
  - UV solution
* `Wind`
  - Adds options for Wind
  - Used in `blend_material_2` and `blend_material_3`
* `WorldAlignedTexture`
  - Function used for perfect scaling
  - Slightly modified version of `Engine\Content\Functions\Engine_MaterialFunctions01\Texturing\WorldAlignedTexture`

* `OldUVs` folder
  - Filled with an old UV solution
  - Deprecated, use `UVs` function instead
* `Rain\oldRain`
  - Rain solution
  - Deprecated, use `Rain\Rain` function instead
* `Rain\oldRain` folder
  - Filled with functions and textures used in the `oldRain` function
  - Deprecated, use `Rain\Rain` function instead
* `Rain\Rain`
  - Rain solution
* `Rain\SubFunctions` folder
  - Functions used in the `Rain\Rain` function
* `Rain\Textures` folder
  - Textures used in the `Rain\Rain` function

### Parameter Collections
Material Parameter Collections can be located in `Game/Materials/ParameterCollections`.

* `SunMoon_Rotations`
  - Contains rotation values for the Sun and Moon
  - Used in `DayOff-NightOn_LightFunction`
* `GlobalRainValues`
  - Contains values used in rain functions

### Textures
Textures can be located in `Game/Materials/Textures`.

* `DirtMask` folder
  - Contains Lens Dirt textures
* `LensFlares`
  - Contains a bunch of lens flares that you might want to use
* `Moon` folder
  - Contains Moon texture
* `Placeholders` folder
  - Contains placeholder textures
  - Used in all materials

### Post Process Materials
Post Process Materials can be located in `Game/Materials/PostProcess` 

* `Fisheye`
  - Basic fisheye effect
  - Used in `Game/Player/Blueprints/PlayerCharacter.uasset` whilst in Third Person

### UI Materials
UI Materials can be located in `Game/Materials/UI`

* `FisheyeUI`
  - Same basic fisheye effect as in `Game/Player/Materials/Fisheye.uasset` but converted to work with UIs
  - Used in `Game/Player/UI/Physics_WidgetHUD.uasset`

## Blueprints
Blueprints can be located in `Game/Blueprints`.

### DayNightCycle folder
* `DayNightManager`
  - Gives other assets vital information about the Day/Night cycle
* `Moon`
  - Fake Moon

### Spline_Movement folder
* `Spline_Movement_Template`
  - Actor to be moved along the spline defined in `Spline_Movement_Track`
* `Spline_Movement_Track`
  - Defines the track that `Spline_Movement_Template` will move along

### WeatherSystem folder
* `WeatherManager`
  - Controls weather across various assets

### Example folder
* `DayNightLight1`
  - Light that turns on at night, and off during the day
  - Light contains various performance optimizations
* `DayNightLight2`
  - Same as `DayNightLight1` except with 2 lights

## Level
Levels can be located in the main `Game` directory.

* `Empty`
  - As the name suggests, this level is empty
* `Level`
  - This is the main level
* `MainMenu`
  - This is the level featured in the main menu. It's the one with the sky

### World Partition Grids
* `Landscape`
  - Used for landscapes and buildings
* `Actors`
  - Used for large actors (such as streetlamps, shipping containers, etc)
* `SmallActors`
  - Used for small actors (such as trashbags, rubbish decals, etc)

## Day/Night cycle system
The day/night cycle is controlled via the level blueprint and `DayNightManger`.

The level blueprint is what actually rotates the directional lights, `DayNightManager` tells other actors whether it is day or night. (This is useful for example with streetlamps. By accessing the Boolean in `DayNightManager`, the streetlamp can be turned on and off depending on whether it is day or night).

### Examples of Day/Night cycle system

An example of such a streetlight is provided in `Game/Blueprints/Examples/DayNightLight.uasset`. (When placing this blueprint, make sure to select the `DayNightManager` from the details panel)

Another example of the Day/Night cycle system in use is the `DayOff-NightOn_LightFunction` file found in `Game/Materials/ExampleMaterials`.

## Particles
Particles can be located in `Game/Content/Particles`.

## Player
### Player controls

* Mouse Movement - Look Around
* WASD - Movement
* V - Change Camera
* Left Click whilst looking at actor with Physics - Picks up actor
* Right Click whilst looking at actor with Physics - Pokes actor
* Left Click whilst holding an actor with Physics - Drops actor
* Right Click whilst holding an actor with Physics - Throws actor
* Esc - Pause
* P - Pause

### UI
The HUD that the player sees can be configured by opening `Game/Player/UI/PhysicsUI.uasset`.

The HUD uses the Inverted Fisheye effect, so if you want to disable that, just click on the retainer box and set the effect material to nothing.

Additional things can be configured by opening `Game/Player/UI/UI.uasset`.

### Menus
The menus can be found in `Game/Player/UI/MainMenu`, `Game/Player/UI/PauseMenu`, and `Game/Player/UI/LoadingScreen` respectively.

All of the code inside the menus is extremely simple, and should not require explaining.

There is also `Game/Player/UI/SettingsMenu`, the code inside this blueprint is somewhat complex.
Luckily, you shouldn't need to edit it. You should only need to edit the design of the menu.

## Cinematics
In order to get up and running with rendering cinematics, make sure to

1) Download [ffmpeg](https://ffmpeg.org/download.html)
2) Go to Project Settings > Plugins > Movie Pipeline CLI Encoder and set "Executable Path" to `bin\ffmpeg.exe` in the .zip you download in the prior step
3) If you have a GPU that isn't capable of using NVENC, replace "Video Codec" with "`libx264`"

When ready to actually render the cinematics, load the preset "`MovieRenderQueueSettings`" located in `Game/Cinematics`.

If you're unsure how to use the Movie Render Queue feature, please read the [official documentation](https://docs.unrealengine.com/5.0/render-cinematics-in-unreal-engine/).
