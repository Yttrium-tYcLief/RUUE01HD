# Animal Crossing: City Folk HD Project
[Project Thread on Dolphin Forums](https://forums.dolphin-emu.org/Thread-hd-project-animal-crossing-city-folk-ruue01)

This project aims to recreate every texture used in Animal Crossing: City Folk with a 100% vectorized, from-scratch version of the original. This repository will contain source files and a 4x render of every texture made with those source files. This repo will _not_ contain dumped game files, and will not be the primary source for downloading releases.

This repo is intended for collaboration between contributors. If you'd like help with released content, please leave a reply on the project's [thread](https://forums.dolphin-emu.org/Thread-hd-project-animal-crossing-city-folk-ruue01). Only open an issue if you see a problem with a texture.

## Prerequisites for contributing
* **Adobe Photoshop**
  * I use CC 2015 but any recent version (CS4+) should be okay.
* **Dolphin 5.0** or later
  * Technically Dolphin v4.0-5234 or later, but since 5.0 is the current stable release just use that.
  * This is important because r5234 introduced the [new custom texture format](https://forums.dolphin-emu.org/Thread-dolphin-custom-textures-info), which this project exclusively uses.
* **RUUE01**
  * Because of the huge number of differences based on locale it's important to unify around one game version. Only contribute and work on files from the US (E01) release of the game.

## Workflow
1. Import the dumped PNG from the Dump folder into Photoshop. Make sure it's using the new file format:
   * `./Dump/tex1_215x165_f89b34590140b5e1_bdb5ed7b3f25d518_10.png` = Good
   * `./Dump/RUUE01_2c654d3c_5.png` = **BAD**
2. Immediately re-save it with the exact same filename (except for the extension) as a PSD, inside of the `./WIP/` folder.
   * `./WIP/tex1_215x165_f89b34590140b5e1_bdb5ed7b3f25d518_10.psd`
3. Increase the resolution to 4x of the original in every dimension - for instance, a 64x64 texture should be resized to 256x256 (64 × 4 = 256). [Use **nearest neighbor** scaling](http://i.imgur.com/Ynfca5p.png).
4. Draw over the existing texture using vector tools.
   * Use only shapes (Pen Tool, Shape Tools), Smart Filters (applying a regular filter to a vector layer automatically makes it a smart filter), Vector Masks, Text (Type Tool), and Fill/Adjustment Layers (Layer > New > Fill Layer).
   * The key to 100% vectorization is smart layering, **clipping masks**, and layer organization (groups). I cannot stress clipping masks enough.
   * Watch my video demonstration if you're having trouble getting started.
5. Save your PSD.
6. Re-save as a PNG with the same filename (except for file extension) to `./Load/`.
   * If you're trying to test the current iteration of your texture in the game, copy all of the files in the `./Load/` folder to your `%Documents%/Dolphin Emulator/Load/Textures/RUUE01/` folder, overwriting files.
     * If you already have the game open, go to `Options > Graphics Settings > Advanced > Utility` and disable, and then re-enable the `Custom Textures` checkbox. This will clear the texture cache and force Dolphin to reload all custom textures without restarting the game.
7. Close the document inside of Photoshop.
8. Move the PSD file from the `./WIP/` folder to the `./Done/` folder when it's done.
