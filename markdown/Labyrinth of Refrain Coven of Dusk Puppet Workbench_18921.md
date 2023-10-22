## Post #1
- Username: TKLF
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 13, 2017 2:14 pm
- Post datetime: 2018-10-12T01:38:19+00:00
- Post Title: Labyrinth of Refrain: Coven of Dusk Puppet Workbench

Puppet Workbench
tl;dr - Script that allows you to replace the images for portraits for your party (puppets) by repacking .dds to .dds.phyre files used by the game.

First time posting here, but here's a kinda-crappy and dirty Python script I made for repacking .dds files to specific .dds.phyre files for use with the PC version of the game.
The README in the zip should have all you need to know on how to use, etc.
Only tested on Win7 64bit.

1. You need Python 3.7.0 and Pillow library installed
2. Photoshop with Nvidia's DDS plugin
3. .dds files must be vertically flipped and must match intended .dds.phyre file's width/height
4. Run script (or drag-drop dds onto it), pass the correct arguments depending on the file you want to replace so the script knows what file it is

Conceptually it's just taking the .dds image data and moving it back into the .dds.phyre of the same type, then changing a path inside the file, and should work for pretty much every .dds.phyre for the game (the script only handles a select number of them, though). Manually doing it by hand is a hex-editor and copy-paste.
Also don't really have the technical expertise to help troubleshoot any issues that come up, so uh, good luck! lol.
Download: [https://mega.nz/#F!PkM0xSJK!q-ptV6ZphyqHJFTNhnqX3A](https://mega.nz/#F!PkM0xSJK!q-ptV6ZphyqHJFTNhnqX3A)

Cheers, mug

EDIT:
puppetWorkbench v0.6c - Fixed files being generated with wrong size
puppetWorkbench v0.7b - Combined gender/class param so you get to type less for the same effect, what fun
puppetWorkbench v0.7c - Updated README and minor semantic changes to code (no effect on performance)
## Post #2
- Username: TKLF
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 13, 2017 2:14 pm
- Post datetime: 2018-10-20T23:03:24+00:00
- Post Title: Labyrinth of Refrain: Coven of Dusk Puppet Workbench

Puppet Facebench (what a name...)
This one's not so much a pack/repack script but helpful in the long run, I guess.
Companion script to Puppet Workbench that just lets you slap together a CharaFace_Icon sheet through "chips".
The README in the zip should have all you need to know on how to use, etc.
Only tested on Win7 64bit. Like Puppet Workbench, requires Python 3.7.0 and Pillow library.
Can be extracted to the same folder as Puppet Workbench with no drawbacks.

Complete set for editing in your waifus or whatever, have fun.

Download (same as above): [https://mega.nz/#F!PkM0xSJK!q-ptV6ZphyqHJFTNhnqX3A](https://mega.nz/#F!PkM0xSJK!q-ptV6ZphyqHJFTNhnqX3A)
Also see the templates.zip for the chip templates and whatnot.
## Post #3
- Username: reiokami
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 25, 2017 8:06 pm
- Post datetime: 2021-10-14T11:24:23+00:00
- Post Title: Labyrinth of Refrain: Coven of Dusk Puppet Workbench

i am so lost from the 
"modName" steps.
What is that do? because of that i cant understand what the correct synthax is
## Post #4
- Username: TKLF
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 13, 2017 2:14 pm
- Post datetime: 2021-11-01T04:09:23+00:00
- Post Title: Labyrinth of Refrain: Coven of Dusk Puppet Workbench

I did not make a GUI for this, so please make sure you've installed python, and familiarize yourself with how to use CLI tools if you haven't already.
Your input .DDS file should be in the same directory as the .py script file used to do the conversion.

If you want examples of the syntax the script uses, I have included a few examples at the end of ---IV. Usage in the README, and are included below for your convenience.

EXAMPLES: 
Full-Sized Female Aster Knight Portrait for Palette 1:

```
input.dds babbysFirstMod -fak -1p
```


CharaFace_icon: (do not include other params)

```
input.dds babbysFirstMod
```


Demon Reaper Chibi, all palettes: (does not take gender)

```
input.dds babbysFirstMod -dr -chibi
```


Female Marginal Maze Battle Portrait, all palettes:

```
input.dds babbysFirstMod -fmm
```


"modName" is just to prepend your own label to the front of the filename so you can keep your files organized. The script generates your .dds.phyre files in a folder with "modName". In the above examples, "babbysFirstMod" is the "modName" I used.

Therefore, the output file would be "babbysFirstMod.Full_Length_039_4k.dds.phyre", in the "babbysFirstMod" folder, which will be inside the "mods" folder in the same directory as the .py script.
for example,
[..]\puppetWorkbench\mods\babbysFirstMod\
will be where the "babbysFirstMod.Full_Length_039_4k.dds.phyre" file will be saved.

So in the above example, you would remove "babbysFirstMod." (note the . as well) from the filename so it becomes "Full_Length_039_4k.dds.phyre", before (or after) you move it to the game's directory to apply it, detailed instructions are in ---V. "Installation" of files in the README.
