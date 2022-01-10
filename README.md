# NewProjectTemplate
A template for new projects in Unreal Engine 5.

## Installation
1. Download the project
   - Downloads in the releases page are polished, final releases
   - Download the repository as a .zip or clone it for the most up to date version, but it may have bugs
2. Extract the .zip file
3. Copy the files to wherever you keep your Unreal projects
4. Open Unreal Engine 5.0.0 Early Access 2 and open the project
5. Done

## Materials

### Master Materials
Master Materials can be located in `Game/Materials`.

* `surface_material`
  - This material should be used for regular surfaces
  - It supports Albedo, Metallic, Specular, Roughness, Emissive, Normal, AO, POM, and various tiling methods
* `decal_material`
  - This material should be used for regular decals
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
  - Used in `surface_material` and `decal_material`
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
  - Used in `surface_material`, `decal_material`, `blend_material_2` and `blend_material_3`
* `MF_Tiling_StretchingFix`
  - Applys a fix for stretched textures
  - Used in `surface_material`, `decal_material`, `blend_material_2` and `blend_material_3`
* `Rain`
  - Adds a basic rain effect
  - Used in `surface_material`, `blend_material_2` and `blend_material_3`
* `StretchingFix-XY`
  - XY specific streching fix
  - Used in `MF_Tiling_StretchingFix`
* `StretchingFix-XZ`
  - XY specific streching fix
  - Used in `MF_Tiling_StretchingFix`

### Parameter Collections
Material Parameter Collections can be located in `Game/Materials/ParameterCollections`.

* `SunMoon_Rotations`
  - Contains rotation values for the Sun and Moon
  - Used in `DayOff-NightOn_LightFunction`

### Textures
Textures can be located in `Game/Materials/Textures`.

* `DirtMask` folder
  - Contains Lens Dirt textures
* `moon` folder
  - Contains Moon texture
* `Placeholders` folder
  - Contains placeholder textures
  - Used in `surface_material`, `decal_material`, `blend_material_2` and `blend_material_3`

## Blueprints
Blueprints can be located in `Game/Blueprints`.

### DayNightCycle folder
* `DayNightBoolean_Actor`
  - Gives the `SunMoon_Rotations` Material Parameter Collection the Sun and Moon's rotations
* `Moon_BP`
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

## Player

### Player controls

* Mouse Movement - Look Around
* WASD - Movement
* V - Change Camera
* Left Click whilst looking at actor with Physics - Picks up actor
* Right Click whilst looking at actor with Physics - Pokes actor
* Left Click whilst holding an actor with Physics - Drops actor
* Right Click whilst holding an actor with Physics - Throws actor

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