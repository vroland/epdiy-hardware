# EPDiy Hardware 

Design files for [EPDiy](https://github.com/vroland/epdiy) controllers, controller variants, display adaptors, and other related hardware.  
See [vroland.github.io/epdiy-hardware/](https://vroland.github.io/epdiy-hardware/) for available hardware.

## What is EPDiy?

Please refer to the [main project repository](https://github.com/vroland/epdiy) for more information.

## Cloning

Make sure to clone recursively, to get hardware library submodules:
```
git clone git@github.com:vroland/epdiy-hardware.git --recursive
# or with http
git clone https://github.com/vroland/epdiy-hardware.git --recursive
```

## Contributing Hardware

Contributions in the form of adapter boards, utilities or epdiy variants are always welcome!
Please submit a PR and make sure your KiCAD project is in the right format, so our automation can build 
the manufacturing files and overview page:

* For every board, the KiCAD project should be given a unique name, and have the same name as the containing folder. 
  Example: `epdiy-v7/epdiy-v7.{kicad_pro,kicad_pcb,kicad_sch}`. 
  An existing KiCAD project can be renamed by selecting `File -> Save As` in the main KiCAD window and saving it to a folder with the new name.
* Unless you *explicitly* specify otherwise, your contribution will be licensed under the Creative Commons Attribution-ShareAlike 4.0 International License.
  Feel free to mention in the README in your project folder how you want to be attributed.
  Please indicate in the PR if you intend to use a different license.
* Each board needs a README.md in it's project folder, which will also appear as description in the presentation page.
  Refer to `epdiy-v7/README.md` for an example.
* If it's a helper or an adapter board, place it in the appropriate `helpers` or `adapters` folder.
* Delete the manufacturing files and keep only the sources.
  Since we generate those automatically, having potentially outdated ones in the repo will be confusing. 
* Add your board to the `BOARDS` list in the root `Makefile`.
  This enables the continuous integration to build the manufacturing files for your board.

## Available Hardware

The full list of available hardware is available at [vroland.github.io/epdiy-hardware/](https://vroland.github.io/epdiy-hardware/).
For each board, we provide:

- Gerber files
- Bill of Materials (BoM)
- Pick & Place Positioning file
- PDF Schematic
- 3D model of the board for use in CAD

## Licensing

Unless otherwise specified, the hardware sources provided are licensed under the terms of the Creative Commons Attribution-ShareAlike 4.0 International License.
<a rel="license" href="https://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License <img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a> 
