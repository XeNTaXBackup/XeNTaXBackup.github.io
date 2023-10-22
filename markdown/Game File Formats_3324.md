## Post #1
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2009-01-25T01:28:04+00:00
- Post Title: Game File Formats

Hello,

I am a programmer working on graphics programming related topics, one of which involves the area of character animation systems.  I have been looking into becoming more knowledgeable in reverse engineering game file formats.  I was particularly interested in the model and animation formats for a number of games.  I plan on creating model viewer and and animation system to allow viewing, modifying and experimenting with various character animation and motion control systems.  I would like to find more information on the structure of these files in order to attempt implementing their formats into the system.  As I would like to gain more knowledge and experience in reverse engineering, any resources in that regard would be helpful, and I would be glad to apply my skills if I am able to help in any way.

Final Fantasy series.
Metal Gear Solid series.
Kingdom Hearts series.
Zone of the Enders.
Resident Evil series.
Super Smash Brothers series.
Ninja Gaiden series.
Devil May Cry series.
Prince of Persia series.
Metroid Prime series.
God of War series.
Legend of Zelda series.

From lurking here in the forums I am sure there are other games with a good deal of 3d data to work with.  I will be looking into a number of pc games as well.  I am always looking for high quality graphics and animation data to work with.  I plan on doing a number of investigations into gameplay mechanics, control schemes, motion synthesis and retargetting, character animation, blending, locomotion and physics, as well as a number of other areas.

Any information you could provide would be greatly appreciated.

Thanks in advance.
## Post #2
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2009-01-25T14:10:56+00:00
- Post Title: Game File Formats

Like it's follower,DMC3 is using  .pac-files for the skin texture of the characters and weapon.Alo it's using .tm2 for other textures.
Sounds are bin files, but they can be replaced with normal music files by renaming,so it makes fun to switch the music in the game 
If you are interested, you can change the data.pak to data.AFS and open it by AFSExplorer to see the certain files.
Modders also posted an indification thread for the skins:
[http://z9.invisionfree.com/Hells_Atelie ... owtopic=15](http://z9.invisionfree.com/Hells_Atelier/index.php?showtopic=15)

As for PoP, it's more complicated.For sounds it's using sb0 files. Skins and textures are made with .TGA , .MTL , .OBJ and mostly BIN-files.They are packed in a .BF file, just as BG&E.
You can extract them with MultiEx and persianrug, both offered here.


The new game uses   .forge files and uses the same engine as assassins creed.

Unfortunately,nobody knows how to mod the Sand of Time/warrior within/Two Thrones game, like opening the ressource-kit and replace the files in there with modded ones. So I have no idea how to mod the SoT-franchise alittle.
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-01-25T23:42:37+00:00
- Post Title: Game File Formats

this is pretty much spot on what i want. extract models and animations but i just want to play around and import to my 3d engine. SO far i have this:

NIF files native in max, games:

REQUIEM ONLINE, works perfectly in max with models + animations

Then you have quake4 that can import in max with models + animation

I also am looking or final fantasy 11 files. In viewer we can see animations but not eport though yet

I really really really like the animations in CABAL ONLINE and would like to see it extracted
