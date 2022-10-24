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
<ol>
<li>Acquire devkitpro using the above resource links.</li>
<li>Use Windows Powershell to navigate to `\devkitPro\examples\gamecube\graphics\gx\acube` and run the MAKEFILE to generate the .dol.</li>
    <li>Just `make` on the command line in that directory.</li>
<li>Using Dolphin Emulator, run the `acube.dol` file that the makefile output. You'll be greeted by a cool 30x30x30 colored cube.</li>
<li>Alter the `\devkitPro\examples\gamecube\graphics\gx\acube\source\acube.c` file. I changed the cube vertex data on lines 24-31 to `10` instead of `30` (smaller cube)</li>
<li>repeat from step 2 to see your new `acube.dol` file. The old `acube.dol` will most likely still be present, so don't fool yourself into launching the old one in Dolphin and not see your new, smaller cube.</li>
</ol>

## Animal Crossing GCN Findings
<ul>
<li>`message_data.bin` seems to hold (possibly) all the dialogue messages in the game.</li>
<li>`select_data.bin` seems to hold all the player's dialogue responses.</li>
<li>KK Slider's first line of dialogue on a new game appear to be saved in memory at search address `81298360`. I found this by converting part of his message to hex, then searching the Memory of the game when his dialogue was showing. I restarted the game, and the message was saved to the same place.</li>
<li>`81298360` is a memory address that seems to get dialogue data dumped to it when the data is loaded in. Placing a breakpoint here when talking to KK fires off after the player's first dialogue reponse (probably a decent time to load the next set of KK dialogue lines)7</li>
<li>Breakpoint on `803c0a3c` (instruction there should be `li r0, 1`) always gets hit when an animal is about to start talking with (presumably) newly loaded dialogue.</li>
<li>Replacing the function spanning from 803c0a20 -> 803c0a38 makes w/e animal you're talking to emit a one line (null?) value, and loops over and over. So it must be responsible for loading the new data</li>
<li>Dolphin Emu can display the Memory in Ascii... Easier than translating... lol</li>
<li>Some kind of value must be used for line wrapping. Example of me altering the memory locations of the dialogue KK would say next: ![Screenshot](https://user-images.githubusercontent.com/37989193/197431469-f18b864d-c56d-4353-b700-6073902d0675.png)
</li>
<li> </li>
<li> </li>
<li> </li>
<li> </li>
<li> </li>
</ul>

## Using Jamchambs [ac-mod-template](https://github.com/jamchamb/ac-mod-template) to create an Animal Crossing code patch
<ul>
<li>Import the project to visual studio code</li>
<li>make command doesnt work for me.. complains about not having ac-nesrom-save-generator</li>
<li>I believe I need [jamchamb's ac-nesrom-save-generator](https://github.com/jamchamb/ac-nesrom-save-generator) to proceed</li>
<li>does this actually patch AC with custom code, or is it just to put custom NES games into AC??</li>
<li></li>
<li></li>
<li></li>
<li></li>
</ul>
