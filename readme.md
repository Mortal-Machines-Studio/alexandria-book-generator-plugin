# Alexandria - Procedural Book Generator Plugin For UE5
A simple book generator utilizing PCG in Unreal Engine 5. Named after, you guessed it, the Library of Alexandria. 


## Prerequisites
 - PCG plugin enabled | [Unreal Docs](https://dev.epicgames.com/documentation/en-us/unreal-engine/procedural-content-generation-overview#requiredsetup)
## Compatible Engine versions
  - 5.5
  - Feel free to test it with older versions, but PCG has changed a lot between 5.2 and 5.4

## Installation
- Download the Latest release from the sidebar
- Place the contents of the latest release into your Engine\Plugins folder
Windows: `C:\Program Files\Epic Games\UE_[version]\Engine\Plugins`

https://dev.epicgames.com/documentation/en-us/unreal-engine/working-with-plugins-in-unreal-engine#plugininstallationlocations

## Usage
- Drag `BP_PCG_Book_Generator_Actor` into the game world.
  - Can be found under `Plugins\Alexandria - Book Generator` in the content browser.
  - If you can't find it in the `Open Assets` window `Ctrl-P` you might need to enable `Show Plugin Content` in its settings.
- Adjust Parameters to your liking
- `Overview` map in the Plugin folder has example actors for different orientations, parameters and material overrides

## Parameters

### Actor
#### Additional Books `Transform|Array`
- Used for adding extra books, eg.: leaning book at the end, book on top of stack


### PCG Component

#### Seed `Int`
- Controls book generation, any given seed will generate the same set of orders for meshes selected from `Book Meshes`

#### Book Meshes `Static Mesh|Array`
- Array of Meshes used to randomly (based on seed) pick from
- *Note: Meshes should have the same orientation as the ones included in the plugin. Currently, I don't account for different orientation during point generation.*
#### Number of Books `Int`
- Pretty self-explanatory
#### Stack Direction `Enum|Left,Right`
- Decides which direction the books stack
#### Gap Range `FVector2D`
- a Min-Max range that determines the gap between individual books. Values get selected randomly between the two values.
#### Location Offset Min & Location Offset Max `FVector`
- Location randomness added to individual books
#### Rotation Offset Min & Rotation Offset Max `FRotator`
- Rotation randomness added to individual books
#### Scale Min & Scale Max `FVector`
- Scale randomness added to individual books
#### Cover/Page Override Materials `UMaterialInstance|Array`
- Material Overrides for both Cover and Pages Material Slot on the included meshes `Plugin/Meshes`.
- *This is more of an example of how to implement something like this if you want to override materials on your meshes.*

## Known Issues
- Warning for `Attribute 'CoverOverrideMaterials' for material overrides is not present in the metadata` when MaterialOverrides are not set. If you know how to fix this without overcomplicating the PCG Graph, hit me up.
- Point Generation doesn't account for Mesh Orientation

## Contacts
- Email: [hello@mortalmachinesstudio.com](mailto:hello@mortalmachinesstudio.com)
- Bluesky: [@davidborsodi.com](https://bsky.app/profile/davidborsodi.com)

## License
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
