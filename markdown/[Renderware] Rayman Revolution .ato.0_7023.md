## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-07-20T10:06:48+00:00
- Post Title: [Renderware] Rayman Revolution *.ato.0

Hey everyone,

I need your help opening Rayman Revolution's model (*.ato.0) files.
Rayman Revolution is a PS2 Renderware game. That means its files are very, very similar to lots of other games, including the GTA III, Vice City and San Andreas trilogy.
With that information, I've already been able to import the *.ato.0 files into 3DSmax, using [KAM's script](http://www.gtagarage.com/mods/show.php?id=9172) to open the GTA model files, by simply renaming them to *.dff. The textures won't work though - even if I would be able to extract them (explained later in this post). According to [RW Analyze](http://www.steve-m.com/downloads/tools/rwanalyze/), there are no texture references inside the *.ato.0 files. I don't know if this is true, because RW Analyze doesn't read all the files correctly.

Textures are located in texture dictionaries in the same folder: they are *.rw3.0 files and possibly *.lm3.0 files (they both seem to contain graphical data).
They are very similar to GTA's *.txd files, but I can't open them correctly using any available extractor.

So, all I ask is some help to determine the slight differences between Rayman Revolution's and GTA's files, extract the models and their textures correctly and combine them.
Here are two levels' model and texture files: [http://www.box.net/shared/hur51xmyshvg3pp046yi](http://www.box.net/shared/hur51xmyshvg3pp046yi)
There are also *.lv2 and *.pt2 files, but I have no idea what they are for. Any information about them would be appreciated too. 

Good luck!
## Post #2
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-08-21T11:10:18+00:00
- Post Title: [Renderware] Rayman Revolution *.ato.0

Bump for great justice. I'd LOVE it if you guys could look at this for a few minutes, but it's only been downloaded 3 times so far.

I found out that the game uses Renderware 3.0, according to the logo shown at the beginning of the game.
In the PS2 code, I also found some comments about the *.ato.0 files being named that way because they contain "atomic" data in "clumps". All that should sound very familiar to anyone who's ever worked with Renderware before, in the SDK or while modding any GTA or other RW-based game. 
The texture dictionaries also may contain *.TFX files. I have no idea what those are and if they are really *.TFX files, but they are according to an error message I found:

> ERROR --> Trying to set an unsupported Texture Function in TEX0.TFX
Again, I'd love it if you'd take a look at this for a few minutes and post your results. I've been stuck for weeks now...
