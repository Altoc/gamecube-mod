# gamecube-mod
Me messin' around with gamecubez

## My Personal Notes:
Next I should...
 - MAKE jamchamb's [ac-mod-template](https://github.com/jamchamb/ac-mod-template) and see if we can apply it as a patch to ACPL

## Notes
- My work was done using a AMD processor PC w/ Windows 10.

## Resources
- [jamchamb](https://github.com/jamchamb?tab=repositories&q=ac&type=&language=&sort=) has a ton of good stuff for modding ACPL
- [devkit pro](https://github.com/devkitPro/gamecube-examples) has real examples of creating .dol files (run in dolphin emu) from c or c++ using makefile
- Visual Studio Code for altering C & C++ files.



## Using DevkitPro to create a .dol executable inside Dolphin Emulator.
1- Acquire devkitpro using the above resource links.
2- Use Windows Powershell to navigate to `\devkitPro\examples\gamecube\graphics\gx\acube` and run the MAKEFILE to generate the .dol.
    - Just `make` on the command line in that directory.
3- Using Dolphin Emulator, run the `acube.dol` file that the makefile output. You'll be greeted by a cool 30x30x30 colored cube.
4- Alter the `\devkitPro\examples\gamecube\graphics\gx\acube\source\acube.c` file. I changed the cube vertex data on lines 24-31 to `10` instead of `30` (smaller cube)
5- repeat from step 2 to see your new `acube.dol` file. The old `acube.dol` will most likely still be present, so don't fool yourself into launching the old one in Dolphin and not see your new, smaller cube.
