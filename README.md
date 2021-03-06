<small class="info">✒ I apologize that English is not my 1<sup>st</sup> language. So these 🗎s are possibly no warranty, just like this license is so. 🐉</small>

---
# 🆇🅴🅻🅵.MagicaGN00T
---

## Overview
* Import models and animation frames from MagicaVoxel `.vox` files.
* Imported meshes have per-vertex color and UV3 as material based voxel data.

## Focused environments in current versions
* [MagicaVoxel](https://ephtracy.github.io/) 0.99.1a
* Unity `2018.2.8f1` `2018.3.0b1`

---

## v2.0.0

### Breaking Changes
* Added `VoxelImporter` is derived from `ScriptedImporter` as a Unity experimental feature in Unity `2018.2.x`.
* `VoxelImporter` can import a MagicaVoxel `.vox` file as an asset. No more extra prefab needed in a project folder.
* `VoxModel` no longer directly used. `VoxModel` will now be contained as named `vox` in its portion of the asset of `.vox` file.
* Asset of `.vox` file is saved by Unity at out of project folder. Therefore, you can reduce the size of the project (repository).
* Added `VoxImportSettings` describes `VoxModel` importing settings isolated from `VoxModel`.
* Example scene `AnimationExample.unity` and corresponded assets are reconstructed. (not fully compatible with previous)

### New
* Added `package.json` is contained for Package Manager.

### New instructions to Import a `.vox` file
1. Add `.vox` file into your project folder.
2. Select it in project window.
3. In the Import Settings (Scripted Importer Editor) inspector by `VoxelImporter`, select the Settings `VoxImportSettings`. (or create a new `VoxImportSettings`)
4. Click `Apply` button. (If it grayed out, `Reimport` instead)

---

## Install via Package Manager
* Temporal `package.json` is contained for Package Manager.
  * For more informations ☛ [XELF.Hexelate.Shader](https://github.com/xelfia/XELF.Hexelate.Shader)

## Advanced Features from original [MagicaGN00T on 30 Mar 2017](https://github.com/xelfia/MagicaGN00T/commit/fe8c4ccb6d27084c32c57d68f417feb526f6e43c)
* Added supports for [MagicaVoxel .vox File Format extension](https://github.com/ephtracy/voxel-model/blob/master/MagicaVoxel-file-format-vox-extension.txt) (of MagicaVoxel 0.99.1a)
* Added supports for LOD (Level of Detail): simple LOD generation.
* Added supports for material categorized meshes: Opaque / Transparent
* Added supports for Scene Graph (`nTRN` / `nGRP` / `nSHP` chunks)
* Added supports for `MATL` (newer Material) chunks
  * Added shader supports for Smoothness / Emission / Metallic
  * Added Transparent shader
* Added supports for `LAYR` (Layer) chunks
  * In Scene Graph, objects will import as inactive when its layer is set invisible.
* Added supports for `rOBJ` (Rendering Setting undocumented) chunks
  * note: Not used in imported models
  * Added `Omits UV unwrapping` option: for fast iteration

## ⚠ Warnings / Limitations
* Scene Graph
  * ⚠ Scale `Origin` should be set `0.5` `0.5` `0.5`. Otherwise, incorrect results.
  * ⚠ Some rotations (flips) have bugs.
  * ⚠ Multiple voxel objects will not merged. That is, arrayed transparent (glass) objects can still be seen visible seams.
* ⚠ This edition written in C#6
  * Required settings: `Player Settings`►`Configuration`►`Scripting Runtime Version`➡`.NET 4.x Equivalent`
* ⚠ Breaking Changes contained in.
  * ⚠ Imported assets are incompatible with the original `MagicaGN00T`. That is, `Generate Model` needed again when you migrate assets.
* ⚠ Colors and materials are imported as per-vertex data. Therefore, original Unity Standard shader does not suitable for this.

## Example Included
* ⚠ Not included examples for advanced features
* ⚠ Image is from the original `MagicaGN00T`

☛ [View `AnimationExample` as WebGL (based on original edition)](https://xelfia.github.io/XELF.MagicaGN00T/)

![Example Image](http://i.imgur.com/hGb84Dt.gif)

### Wireframe
* ⚠ Image is from the original `MagicaGN00T`

![Example Wireframe](http://i.imgur.com/mtUNBTO.png)

### Stores frames in drawers  
* ⚠ Image is from the original `MagicaGN00T`

![Frames in Drawers](http://i.imgur.com/k64ZOU2.png)

### Baked Lighting (placeholder)
* ⚠ Does not currently cared
* ⚠ Image is from the original `MagicaGN00T`

![Baked Imaged](http://i.imgur.com/GiT6omY.png)  
