# NewProjectTemplate
A template for new projects in Unreal Engine 5.

## Installation
### Project Installation
1. Download the project
   - Downloads in the releases page are polished, final releases
   - Download the repository as a .zip or clone it for the most up to date version, but it may have bugs
2. Extract the .zip file
3. Copy the files to wherever you keep your Unreal Engine projects
4. Open Unreal Engine 5.0.0 Early Access 2 and open the project
5. Done

### Pre-compiled Shaders Installation (Still testing)
1. Download the pre-compiled shaders from the latest release *(pre-compiled shaders will only be updated with new releases)*
2. Copy/Move the `Common` folder and place it in `C:\Users\<user>\AppData\Local\UnrealEngine`

## Updating existing projects
If you have a project that already uses this template, but you'd like to update it with new master materials and such,

1. Download the new version
2. Go into the `Content` folder and copy whatever you'd like to update.
3. Replace the old files with the new ones.

The shaders will need to recompile (~250 shaders), but once that's done, everything should just work.

## Materials
### Master Materials
Master Materials can be located in `Game/Materials`.

* `surface_material`
  - This material should be used for regular surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
* `surface_material_additive`
  - This material should be used for small details (such as screws, bumps, cable ports, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Has shadows disabled
* `surface_material_masked`
  - This material should be used for regular surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - Has masked opacity
* `decal_material`
  - This material should be used for regular decals
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods
* `decal_material_stain`
  - This material should be used for decals that are stains (such as puddles, dirt, blood, etc.)
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, Opacity, POM and various tiling methods
* `blend_material_2`
  - This material should be used for surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - It also supports `HeightLerp`ing between two indentical instances of `surface_material`
* `blend_material_3`
  - This material should be used for surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
  - It also supports `HeightLerp`ing between three indentical instances of `surface_material`

### Example Material Instances
Example Material Instances can be located in `Game/Materials/ExampleMaterials`.

* `blend-material_2_example`
  - Shows an example of a typical instance of `blend-material_2`
* `blend-material_3_example`
  - Shows an example of a typical instance of `blend-material_3`
* `DayOff-NightOn_LightFunction`
  - Shows an example of a light function taking advantage of the project's Day/Night time cycle

### Material Functions
Material Functions can be located in `Game/Materials/Functions`.

* `MF_MapAdjustments`
  - Adds configuration options
  - Used in `surface_material`, `decal_material` and `decal_material_stain`
* `MF_MapAdjustments_1`
  - Adds configuration options
  - Used in `blend_material_2` and `blend_material_3`
* `MF_MapAdjustments_2`
  - Adds configuration options
  - Used in `blend_material_2` and `blend_material_3`
* `MF_MapAdjustments_3`
  - Adds configuration options
  - Used in `blend_material_2` and `blend_material_3`
* `MF_Tiling_CustomUVs`
  - Adds custom tiling options
  - Used in `surface_material`, `decal_material`, `decal_material_stain`, `blend_material_2` and `blend_material_3`
* `MF_Tiling_StretchingFix`
  - Applys a fix for stretched textures
  - Used in `surface_material`, `decal_material`, `decal_material_stain`, `blend_material_2` and `blend_material_3`
* `Rain`
  - Adds a basic rain effect
  - Used in `surface_material`, `blend_material_2` and `blend_material_3`
* `StretchingFix-XY`
  - XY specific streching fix
  - Used in `MF_Tiling_StretchingFix`
* `StretchingFix-XZ`
  - XY specific streching fix
  - Used in `MF_Tiling_StretchingFix`
* `Wind`
  - Adds options for Wind
  - Used in `blend_material_2` and `blend_material_3`

### Parameter Collections
Material Parameter Collections can be located in `Game/Materials/ParameterCollections`.

* `SunMoon_Rotations`
  - Contains rotation values for the Sun and Moon
  - Used in `DayOff-NightOn_LightFunction`

### Textures
Textures can be located in `Game/Materials/Textures`.

* `DirtMask` folder
  - Contains Lens Dirt textures
* `Moon` folder
  - Contains Moon texture
* `Placeholders` folder
  - Contains placeholder textures
  - Used in `surface_material`, `decal_material`, `decal_material_stain`, `blend_material_2` and `blend_material_3`

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

## Level
The main level is located in `Game/Level.uasset`.

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

## Player
### Player controls

* Mouse Movement - Look Around
* WASD - Movement
* V - Change Camera
* Left Click whilst looking at actor with Physics - Picks up actor
* Right Click whilst looking at actor with Physics - Pokes actor
* Left Click whilst holding an actor with Physics - Drops actor
* Right Click whilst holding an actor with Physics - Throws actor

### UI
The HUD that the player sees can be configured by opening `Game/Player/UI/PhysicsUI.uasset`.

The HUD uses the Inverted Fisheye effect, so if you want to disable that, just click on the retainer box and set the effect material to nothing.

Additional things can be configured by opening `Game/Player/UI/UI.uasset`.

## Project Settings
### Rendering

* Uses Ray Traced GI
  - 2 Max bounces
  - 6 Samples per pixel
* Uses Ray Traced Reflections
  - 4 Max bounces
  - 3 Samples per pixel
* Uses Ray Traced Shadows
  - Sun and Moon cast shadows with 5 samples per pixel, everything else has 1 sample per pixel.