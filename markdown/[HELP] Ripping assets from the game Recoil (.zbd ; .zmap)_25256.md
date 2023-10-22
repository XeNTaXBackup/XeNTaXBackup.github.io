## Post #1
- Username: thedaemonsultan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 16, 2022 1:49 am
- Post datetime: 2022-04-15T19:05:29+00:00
- Post Title: [HELP] Ripping assets from the game "Recoil" (.zbd ; .zmap)

Hi,

I am trying to rip assets from an old game i.e "Recoil" for a personal project. I understand the copyright concerns.

Any help or guidance would be appreciated. My main focus is to be able to get the 3d assets of the vehicle(tanks, planes, turrets. etc) and the map of the levels.

Game: Recoil
Developer: Zipper Interactive and Westwood Studios
Engine: GameZ
Year: 1999
Other games on the same engine: MechWarrior 3
File Format: .zbd and .zmap
DirectX6


 *.ZBD


From my understanding, these are the breakdown of the .zbd files.
sounds*.zbd - Sound archives
interp.zbd - Interpreter scripts (drive which files the engine loads)
anim.zbd - Pre-compiled animation definitions
gamez.zbd - Game asset/GameZ archives (containing texture references, materials, meshes)
image.zbd`, `rtexture*.zbd`, `texture*.zbd - All image/texture archives
zrdr.zbd -?


I have tried various software to rip assets but to no success. It might be because I did not use them properly or they are not compatible with the game i.e(3dRipper, render doc)

I have had a bit of success with some software, i.e GameExtractor, MultiEx Commander, TerranMechworks/mech3ax, and Ninja ripper.

GameExtractor

It is able to open 'image.zbd`, `rtexture*.zbd`, `texture*.zbd , sounds*.zbd.
it is not able to open 'zrdr.zbd', 'gamez.zbd', 'anim.zbd', 'interp.zbd'

'sounds*.zbd'
It opens in the software and shows all the subfiles it has inside it.
Extracts as .wav files. (Which is good and useable)

'image.zbd`, `rtexture*.zbd`, `texture*.zbd'
It opens in the software and shows all the subfiles it has inside it.
Able to view the hex code (/character/byte) 
In the "image investigator", I am having difficulties figuring out what to input in the options.
Through my trial and error, some of the images are visible when the "Image Data Format" is set to 'RGB565', 'DXT5', 'DXT3' and 'DXT1' .
But these settings don't work for all images. 
Even though these '*.zbd's should be images, some of the subfiles seem like they might be 3D models (just based on the names). I have tried viewing them in the "Mesh Investigator" but have not had any success.
I have tried to use the "convert image to" and "convert 3D model to" options but still have only gotten .file as the export.


MultiEx Commander

Some files open as hex files.
on the MultiEx Commander website, it says it cant edit the archive.

TerranMechworks/mech3ax

This is an unofficial reverse engineering effort for MechWarrior3, published on GitHub. 
My line of thinking was that MechWarrior3 and Recoil are developed by Zipper Interactive, on the GameZ engine and use the same file setup + formats, I could use it to extract assets from Recoil. 
The documentation is more directed toward a coder/programmer, which has made the tool a bit difficult to use. 
It uses cmd/PowerShell, which is not my field of expertise but I have been able to learn and extract some files.


"interpt.zbd"
Interpreter scripts (drive which files the engine loads)
The tool is able to extract it to a '*.json', 
'image.zbd`, `rtexture*.zbd`, `texture*.zbd' , 'gamez.zbd' , 'anim.zbd'
Even though the tool says it can extract these files I have not had any success. 
It could be due to me using it wrongly or it just can't extract Recoil game files.

Ninja ripper
Using the DDraw Wrapper, I have been able to get "3d screenshots" 
They are distorted and the texture files are not being captured. 
I might be able to use this data but it requires a lot of manual cleanups.



*.zmap
The directory for it is "...\Recoil\maps\". this is the only reason I believe that they have the level files. 
The format is '*.zmap'.
As for trying to open the map files, I have had zero luck.


Conclusion as of now

The most progress I have made is in '*.zbd' formats. 
The most promising tools/Software has been GameExtractor, TerranMechworks/mech3ax and Ninja Ripper.

If anyone can make more headway or guide me in any way possible that would be super helpful and  highly appreciated


thank you



GameExtractor [http://www.watto.org/game_extractor.htm](http://www.watto.org/game_extractor.htm) ... he%20game.
MultiEx Commander [https://multiex.xentax.com/](https://multiex.xentax.com/)
TerranMechworks/mech3ax [https://github.com/TerranMechworks/mech3ax](https://github.com/TerranMechworks/mech3ax)
Ninja ripper [https://gamebanana.com/tools/5638](https://gamebanana.com/tools/5638)
## Post #2
- Username: thedaemonsultan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 16, 2022 1:49 am
- Post datetime: 2022-05-13T06:38:13+00:00
- Post Title: [HELP] Ripping assets from the game "Recoil" (.zbd ; .zmap)

Mech3ax

okay, so I was misusing the tool, my bad. 
'image.zbd`, `rtexture*.zbd`, `texture*.zbd'  , "sounds*.zbd" , "interpt.zbd"  have been extracted. 
gamez.zbd' , 'anim.zbd'   Have not been extracted

DNE=Does Not Exisit
see attachment below
[recoil-fixed edition v0-5 data.png](https://xentaxbackup.github.io/file/22221_recoil-fixed edition v0-5 data.png)
