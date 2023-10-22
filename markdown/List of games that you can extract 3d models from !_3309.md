## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-01-19T10:10:21+00:00
- Post Title: List of games that you can extract 3d models from !

i am going to prepare the list of all games that are extractable easily !
please if you extracted 3d models from some games add the name of them to this list thank .
name      fromat
farcry      cgf
crysis      cgf chr
half life 2     mdl
maxpayne    kf2 skd
.................
## Post #2
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-01-20T02:58:28+00:00
- Post Title: List of games that you can extract 3d models from !

Cool Topic, I've always wanted a list like this.

Here are some games with which I've had a lot of success getting into 3dsmax using plugins or scripts. I will add links to the scripts when I find them all:

UNREAL ENGINE GAMES: (updated September 27 2009):

Gildor has created an amazing tool called umodel, which is available here: [http://www.gildor.org/](http://www.gildor.org/) with which you can extract psk/psa files from a variety of Unreal engine games. Umodel also has the capability of exporting Unreal packages to idSoftware's md5mesh and md5anim format, which can be imported back to Max using gildor's updated md5mesh importer script ( [http://www.gildor.org/smf/index.php/topic,87.0.html](http://www.gildor.org/smf/index.php/topic,87.0.html) )

Furthermore, Gildor has also created the ActorX Importer for 3ds Max, which enables you to import .psk/.psa  files directly into 3dsMax. 

Click here for an up-to-date list of the many games that are supported by this excellent tool: [http://www.gildor.org/projects/umodel/compat](http://www.gildor.org/projects/umodel/compat)

GAMEBRYO GAMES

Nif file format games are abundant (Gamebryo Engine). The fine people at [http://niftools.sourceforge.net/wiki/NifTools](http://niftools.sourceforge.net/wiki/NifTools) have created a list with Game titles and extractors where available:

[http://niftools.sourceforge.net/wiki/Ni ... _Resources](http://niftools.sourceforge.net/wiki/Nif_Format/Nif_Resources)

Here are the GAMEBRYO GAMES that I have had success with from the Niftools list:

Star Trek Bridge Commander 
Freedom Force 
Freedom Force vs the 3rd Reich
Morrowind
Dark Ages of Camelot (Animations are not supported)
Loki  (Animations are note supported)
Oblivion
Fallout 3
Megami Tensei: Imagine (use blender to extract the imbedded .dds files from the nif)  
Florensia
Requiem: Bloodymare (one of my favorites, use blender to extract the imbedded .dds files from the nif)
Atlantica Online (Nifskope and Max Nif importer can manipulate .nif files from this game, but look here [viewtopic.php?f=18&t=3263](http://forum.xentax.com/viewtopic.php?f=18&t=3263) to get the .dds files to be readable. I've got most of the textures working, but some nice programmer really needs to simplify this for us.)
Warhammer Online (Uses Nifs for all static meshes, animated meshes are proprietary and are being worked on by these people, but it doesn't look like they plan to release anything for the public [http://www.warhammeralliance.com/forums ... p?t=154460](http://www.warhammeralliance.com/forums/showthread.php?t=154460) )
Worldshift Update Feb 11: Uses Nifs, check the niftools forum for an updated nif.xml file to enable nifskope to work with these .nif files [http://niftools.sourceforge.net/forum/v ... =10&t=2117](http://niftools.sourceforge.net/forum/viewtopic.php?f=10&t=2117)and check here [http://aluigi.altervista.org/papers.htm#others-file](http://aluigi.altervista.org/papers.htm#others-file)for a worldshift archive extractor.

VALVE GAMES:
(Half Life 2 engine, tools are here: [http://www.chaosincarnate.net/cannonfodder/cftools.htm](http://www.chaosincarnate.net/cannonfodder/cftools.htm) Models must first be decompiled using the mdldecompiler from the link, then imported using the .smd importer)

Half-Life 2
Halife Life 2, Episode 1
Sin Episode 1
Dark messiah
Vampire: the Masquerade - Bloodlines (Animations don't work with the current tools, but rigging is ok)

DOOM 3 ENGINE GAMES (Tools are here: [http://www.doom3world.org/phpbb2/viewtopic.php?t=5474](http://www.doom3world.org/phpbb2/viewtopic.php?t=5474) , but also check out Gildor's updated md5mesh importer linked above)

Doom 3
Doom 3: Resurrection of Evil
Quake 4 the Quake 4 md5mesh files are essentially the same as the D3 files, except that they have collision geometry. You can go right into the md5mesh file with a text editor and delete it (it's pretty easy to spot when you compare it to a D3 file) and then there is no difference.
Prey Same format as Doom 3
Quake Wars Game itself used newer binary versions of MD5MEsh files, and files that come with the SDK are version 11 I think, but the newer tools can handle them.

QUAKE 3 ENGINE GAMES: Most links to tools for these games are out of date, but I have been able to import models and animations from all of them into Max in the past. I will see if I can find/post scripts for them if anyone is interested. Some of them have models that are as good as some recent games, despite the older engine.

Quake 3
Star Trek Elite force I
Star Trek Elite Force II
Return to Castle Wolfenstein
Fakk2
American McGee's Alice


OTHERS:

Lineage 2 (Not skinned or rigged) (Tools: [http://icculus.org/freyja/](http://icculus.org/freyja/) ), see above for Gildor's updated tools.
STALKER (can be converted to .smd and imported to max using HL2 smdimporter above, Tool: [http://www.fpsbanana.com/tools/2780](http://www.fpsbanana.com/tools/2780) )
Stalker: Clear Sky:  (can be converted to .smd and imported to max using HL2 smdimporter above, Tool: [http://www.fpsbanana.com/tools/2780](http://www.fpsbanana.com/tools/2780) )
AION MMORPG (Look here for extraction and conversion info [viewtopic.php?f=10&t=2848&st=0&sk=t&sd=a](http://forum.xentax.com/viewtopic.php?f=10&t=2848&st=0&sk=t&sd=a) . Uses CryEngine 1, cgf files can be viewed and extracted using 3dObjectConverter, I've messed around with a hex editor but it would be nice to see a converter to make them into normal cgf files to be more easily manipulated)
Painkiller (Tool: [http://www.dreamcatchergames.com/forums ... hp?t=32608](http://www.dreamcatchergames.com/forums/showthread.php?t=32608) )

SPACE COMBAT FLIGHT SIM GAMES

X2                (Tools: [http://www.doubleshadow.wz.cz/](http://www.doubleshadow.wz.cz/) )
X3 Reunion     (Tools: [http://www.doubleshadow.wz.cz/](http://www.doubleshadow.wz.cz/) )
Space Force: Rogue Universe
Eve Online      (Tools: [http://www.agronom.pl/selvin/EVE/TriExp ... fault.aspx](http://www.agronom.pl/selvin/EVE/TriExporter/tabid/66/Default.aspx) , look for the beta 2 version of the extractor which can convert the .gr2 files) )
Star Wars Battlefront I and II (3D Object Converter)

OLDER GAMES:
Freespace 2
Orb
Quake 2
Daikatana (Quake 2 engine)

The above games can all generally be imported to max and edited with rigging and often animations intact, with a few exceptions. 3D Object converter can get dozens more with no rigging or animations, and 3d Ripper DX can be used to get static meshes out of dozens of more games still.

I'm sure there are others, I will add them as I think of them. Basically, I don't buy a game unless I can play with the models.  : )
## Post #3
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2009-01-26T10:42:33+00:00
- Post Title: List of games that you can extract 3d models from !

Devil May Cry 3: .afs and .pac
tut can be found here: [http://z9.invisionfree.com/Hells_Atelie ... wtopic=118](http://z9.invisionfree.com/Hells_Atelier/index.php?showtopic=118)

Is Prince of Persia SoT/WW/T2T one of the more easy extractable games yet?
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-01-30T09:52:36+00:00
- Post Title: List of games that you can extract 3d models from !

Nice going, with such a list. Keep it up. Made it sticky.
## Post #5
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2009-01-31T00:45:25+00:00
- Post Title: List of games that you can extract 3d models from !

this community inspired me creating the GR2 importer: 
There's page with a list of the games tested.
## Post #6
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-03-01T18:28:32+00:00
- Post Title: List of games that you can extract 3d models from !

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-01T19:45:12+00:00
- Post Title: List of games that you can extract 3d models from !

Just add the -extract before the model name. the tool is in english it gives you the syntax if you just run the exe in a command prompt.
## Post #8
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-03-01T21:04:40+00:00
- Post Title: List of games that you can extract 3d models from !

Okay, I'll try that.


Worked like a charm- had to remember my DOS... been awhile since I had to use that. I remember having to type in Doom.exe and Sopwith.exe. My two favorites!
## Post #9
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-03-06T04:02:00+00:00
- Post Title: List of games that you can extract 3d models from !

Sorry for the double post, but does anyone have information about the Unreal 2 .gem format? I understand it's a proprietary format (correct me if I'm wrong).
## Post #10
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-15T11:12:01+00:00
- Post Title: List of games that you can extract 3d models from !

> Reply from shekofte
>
> i am going to prepare the list of all games that are extractable easily !
please if you extracted 3d models from some games add the name of them to this list thank .
name      fromat
farcry      cgf
crysis      cgf chr
half life 2     mdl
maxpayne    kf2 skd
.................

And ? I really dont understand why is this thread sticky, you wrote nothing useful since January in this thread 

Anyways, thanks to zardalu for nice list
## Post #11
- Username: Nasman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 05, 2009 11:19 am
- Post datetime: 2009-04-05T18:00:45+00:00
- Post Title: List of games that you can extract 3d models from !

Does anyone know how to extract models from Return to Castle Wolfenstein? So far I've only extracted from F.E.A.R. and S.T.A.L.K.E.R., but I really want to know how to extract from Castle Wolfenstein.
## Post #12
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2009-04-14T12:41:09+00:00
- Post Title: List of games that you can extract 3d models from !

> Reply from Nasman
>
> Does anyone know how to extract models from Return to Castle Wolfenstein? So far I've only extracted from F.E.A.R. and S.T.A.L.K.E.R., but I really want to know how to extract from Castle Wolfenstein.

It's been a long time since I played around with these files, but there is a MDC importer/exporter available here: [http://www.davidhsmith.net/](http://www.davidhsmith.net/), it is for GMAX/max 4.2, but if I remember correctly I did have it working with Max 5.0.
## Post #13
- Username: Nasman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Apr 05, 2009 11:19 am
- Post datetime: 2009-04-14T23:20:32+00:00
- Post Title: List of games that you can extract 3d models from !

Thanks for the reply. I'm quite new to gmax, so I don't know how to get the MDC Importer working. I'm used to working with Blender. Can you please explain how to do this? Thanks.
## Post #14
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-05-05T21:12:11+00:00
- Post Title: List of games that you can extract 3d models from !

name format
-----------------
left for dead  .mdl .vtx .vvd
[](http://xs.to)
Genesis Rising .GEOMB
[](http://xs.to)
Painkiller Overdose .pkmdl
[](http://xs.to)
Railroad Tycoon 3 .3dp
[](http://xs.to)
## Post #15
- Username: IIVEnnEII
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 03, 2009 7:27 pm
- Post datetime: 2009-05-09T09:59:07+00:00
- Post Title: List of games that you can extract 3d models from !

Halo 1 ( PC & Xbox )
Halo 2 ( Xbox )
Halo 3 Beta ( Xbox 360 ) *not public*
Halo 3 ( Xbox 360 ) *not public yet*
Gears of War 2 ( Xbox 360 ) *archive extraction not public* (All Unreal 3 Engine games should be possible. Problem: LXZO xompression)
## Post #16
- Username: DrJones
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 15, 2008 2:13 am
- Post datetime: 2009-05-15T07:57:12+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hi,

i'll add my contribution to the list.

.msh and .him 3d files from IL2 sturmovik and Theatre of War series games, at [http://www.allaircraftarcade.com/forum/ ... php?t=7473](http://www.allaircraftarcade.com/forum/viewtopic.php?t=7473)

SFS archive extractor for Theatre of War can be downloaded from [http://www.battlefront.com](http://www.battlefront.com) repository 

[http://www.battlefront.com/index.php?op ... nfo&id=306](http://www.battlefront.com/index.php?option=com_remository&Itemid=314&func=fileinfo&id=306)


br.
Dr.Jones
## Post #17
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-05-15T22:19:33+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hey everyone- got some info about Dawn of War 2!

This is from the Relic Forums:

> Icons/badges/other simple textures:
>
> Largely DXT3 .dds files, greyscale alpha channel is used for simple transparency. White is solid, black is transparent in alpha channel.
>
> 
>
> .abp
>
> Text files. Appears to have been used for pointing to model, animation and texture files in previous games using the engine (ie. CoH). Many of them still exist, but from what I can tell they are obsolete and contain very little information.
>
> 
>
> .model "Relic Chunky"
>
> 3D art information. "Relic Chunky" binary format. Most likely contains mesh and has strings pointing to material, animation and texture information.
>
> 
>
> .bfx
>
> Same as above, but for effects? Perhaps the same format just renamed for conventions (similar to lua/scar/ai).
>
> 
>
> texture files (dds)
>
> The textures use the .DDS format and are broken into several pieces, which is normal now.
>
> 
>
> _diff: "Diffuse map" or texture map. The RGB basic image information, basically 90% of what you see on a model. Has an alpha channel, but I haven't seen any use for it.
>
> 
>
> _nrm: Normal map. Used for bump mapping or "normal mapping" lighting effect (gives simple geometry the appearance of being more complex). Typical RGB normal mapping technique. Again, has an alpha channel, but why?
>
> 
>
> _tem: Team colour map. Used to tell the game where on the texture to apply which type of team colouring (there are 4 types). I've seen red used for primary, green for secondary and purple for tertiary. Has an alpha channel that appears to be unused, but does contain some information on certain textures. Any ideas?
>
> 
>
> _spc: Specular map I believe. This is probably used for specular lighting aka shiny stuff  Although in my exploits I've edited team colour images and it has resulted in really high specular lighting when I haven't even touched the spc file.
>
> 
>
> _drt: No idea, any info? Maybe used as low quality image, but we have mip maps in dds files and the content here looks extremely bizarre, but it is RGB and uses a greyscale alpha channel with appears to contain important information.
>
> 
>
> _ocl: Used for occlusion? Maybe for a glow type effect when the model is occluded. Image appears to be greyscale lighting information, not sure.
>
> 
>
> Some model textures are missing _drt and _ocl maps. Legacy use?
>
> 
>
> .hkx
>
> Havok physics format. Used by the Havok physics engine that is very widespread. Contains some mesh information, but most likely used by Relic for animations and physics.
>
> 
>
> .motiontree
>
> Relic animation format? Probably another "chunky", should check this.
>
> 
>
> .action
>
> Particle effects format? No idea. Possibly similar to bfx.
>
> 
>
> Please contribute any information you have on DoW2 art assets that you have. Has anyone had a problems with specular lighting after editing diffuse or team colour maps? I'm having some weird issues here, perhaps the alpha channel is used in ways i'm not expecting.

If I can extract the files from the .sga files, I'll post them so that others can have a go at them (if I'm allowed to anyway). Let me know if anyone's interested.

Also- does anyone know about the "Unlocked" .sod import script for Star Trek Armada? I've been trying to find it, but every link I find is dead.
## Post #18
- Username: almondega
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 03, 2010 6:39 am
- Post datetime: 2010-01-03T00:01:55+00:00
- Post Title: Re: List of games that you can extract 3d models from !

hi folks
to access .nif files in Florensia, you need to unpack the .pak
for this, i recommend the Dragon UnPACKer
worked fine here, dds + model + animations in blender
## Post #19
- Username: almondega
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 03, 2010 6:39 am
- Post datetime: 2010-01-16T23:42:54+00:00
- Post Title: Re: List of games that you can extract 3d models from !

folks!

Now Blender do import custom Atlantica .nif models and animations
get it here: [http://niftools.sourceforge.net/forum/v ... =13&t=2531](http://niftools.sourceforge.net/forum/viewtopic.php?f=13&t=2531)
(new versions also avaliable)

cya
## Post #20
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2010-02-14T20:58:06+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> ons/badges/other simple textures:
>
> Largely DXT3 .dds files, greyscale alpha channel is used for simple transparency. White is solid, black is transparent in alpha channel.
>
> 
>
> .abp
>
> Text files. Appears to have been used for pointing to model, animation and texture files in previous games using the engine (ie. CoH). Many of them still exist, but from what I can tell they are obsolete and contain very little information.
>
> 
>
> .model "Relic Chunky"
>
> 3D art information. "Relic Chunky" binary format. Most likely contains mesh and has strings pointing to material, animation and texture information.
>
> 
>
> .bfx
>
> Same as above, but for effects? Perhaps the same format just renamed for conventions (similar to lua/scar/ai).
>
> 
>
> texture files (dds)
>
> The textures use the .DDS format and are broken into several pieces, which is normal now.
>
> 
>
> _diff: "Diffuse map" or texture map. The RGB basic image information, basically 90% of what you see on a model. Has an alpha channel, but I haven't seen any use for it.
>
> 
>
> _nrm: Normal map. Used for bump mapping or "normal mapping" lighting effect (gives simple geometry the appearance of being more complex). Typical RGB normal mapping technique. Again, has an alpha channel, but why?
>
> 
>
> _tem: Team colour map. Used to tell the game where on the texture to apply which type of team colouring (there are 4 types). I've seen red used for primary, green for secondary and purple for tertiary. Has an alpha channel that appears to be unused, but does contain some information on certain textures. Any ideas?
>
> 
>
> _spc: Specular map I believe. This is probably used for specular lighting aka shiny stuff  Although in my exploits I've edited team colour images and it has resulted in really high specular lighting when I haven't even touched the spc file.
>
> 
>
> _drt: No idea, any info? Maybe used as low quality image, but we have mip maps in dds files and the content here looks extremely bizarre, but it is RGB and uses a greyscale alpha channel with appears to contain important information.
>
> 
>
> _ocl: Used for occlusion? Maybe for a glow type effect when the model is occluded. Image appears to be greyscale lighting information, not sure.
>
> 
>
> Some model textures are missing _drt and _ocl maps. Legacy use?
>
> 
>
> .hkx
>
> Havok physics format. Used by the Havok physics engine that is very widespread. Contains some mesh information, but most likely used by Relic for animations and physics.
>
> 
>
> .motiontree
>
> Relic animation format? Probably another "chunky", should check this.
>
> 
>
> .action
>
> Particle effects format? No idea. Possibly similar to bfx.
>
> 
>
> Please contribute any information you have on DoW2 art assets that you have. Has anyone had a problems with specular lighting after editing diffuse or team colour maps? I'm having some weird issues here, perhaps the alpha channel is used in ways i'm not expecting.
Dif = diffuse map file - most of it is in greyscale though - to be used along with the _tem
Tem - team color file - usually 4 color bitmaps Blue, green red black - the first three can be changed to your color to colorise the dif map
DRT - a layer that goes on top of the dif, basically Dirt. 

If you download the DOW 1 modtools, it contains a psd with with all the texture files layered on top of each other to show how each works.
## Post #21
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2010-02-21T07:59:28+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from Nasman
>
> Does anyone know how to extract models from Return to Castle Wolfenstein? So far I've only extracted from F.E.A.R. and S.T.A.L.K.E.R., but I really want to know how to extract from Castle Wolfenstein.

Are you speaking of this game?
[http://pc.gamespy.com/pc/return-to-castle-wolfenstein](http://pc.gamespy.com/pc/return-to-castle-wolfenstein)
[http://pc.gamespy.com/mac/return-to-castle-wolfenstein](http://pc.gamespy.com/mac/return-to-castle-wolfenstein)
[http://pc.gamespy.com/pc/return-to-cast ... um-edition](http://pc.gamespy.com/pc/return-to-castle-wolfenstein-platinum-edition)

These are super easy to extract and don't require any special tool, just rename the packages extension from the game format (if i remember correctly its .pk3) to .zip and unzip it!  The game is based on the same IDtech engine as Quake 3, and is well documented just do some quick searching through forums here and Quake forums.

All files extracted maintain a decent file structure and can easily sort through texture, model, map, and sound/music directories.

My addition to the list is for Fear 2: (Taken from [this post](http://forum.xentax.com/viewtopic.php?f=10&t=3382&start=0&st=0&sk=t&sd=a))
Fear2Tools bundle = [http://www.megaupload.com/?d=SILDTR0R](http://www.megaupload.com/?d=SILDTR0R)
I also contributed to the listed post for steps on creating a batch file to quickly unpack the bndl files.

I've not had the chance to check into how to get access to the .mdl files.  The file structure is also somewhat unwieldy,  the main directory game .mdl fils are all 1kb or less.  Most of the meaningful content lies further within the "world" directory which unpacked creates "char" "fx" "materials" "models" "powerups" "prefabs" "snd" "ui" "video" "weapons "worlds" and "data" folders which are all redundant.  Seems like complete game contents local to each level and isolated from the rest of the game.  Personally I don't see the purpose of this particular structure the developers used but It works nonetheless.

I think it would make more sense to start a new post that goes through games' file structures as games like Fear and Aion can get unwieldy to understand how things are stored.

BTW, Aion fully unpacked is over 100 gb, not including audio.  The music directory alone converted from their compact .ogg to standard MP3 @ 192kbps totals just under 6gb!  The sound files unpacked from the game archives are varied, both standard wave and .ogg files are used.  Just these alone directly unpacked from the game sits at just over 1gb.
Just the textures and model data (aside from the few proprietary formats I thought i should keep like the .h32 map files for level data) weighs in at 84.7 gb!  
The game's content is hugely redundant as for each item they use individual CGF's and texture files for the various LOD.  I'm sure this could shrink to as little as 30 gigs or less without all the redundant file data but to do that takes a lot of manual scouring!!!!
## Post #22
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2010-03-20T01:38:33+00:00
- Post Title: Re: List of games that you can extract 3d models from !

@ junk angel- I think the textures are set up differently between DoW1 and DoW2. DoW2 uses a different engine.

@ nasman- What did you use to extract from FEAR? The one tool I found (forgot what it was called) would only extract 3 models- only one of which had texture coordinates...
## Post #23
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-16T19:33:27+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I've documented a lot of the Half-Life (version 10) MDL format and almost all of the James Bond 007: Nightfire (version 11 & 14) MDL format.  Details for all of them are here:
[http://wiki.nfbsp.com/index.php/Research](http://wiki.nfbsp.com/index.php/Research)


[Nightfire Workshop](http://wiki.nfbsp.com/index.php/Nightfire_Workshop) has the Studio Model Tool plugin which can work with these.  .NET programs can access the entire library of definitions in the jbnlib.dll included with Nightfire Workshop.
## Post #24
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2010-04-18T02:34:48+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I wrote(stumbled through) a program to export FF9 models with UVs and geometry, but bone multiplication and animation data, as well as TIM export is not supported.

Characters will be crumpled up due to not having any bones and animations to pose them properly. May or may not work on battle scene backgrounds.

Currently it does not scan files for models either, files must be chopped beforehand.

Some models (containing multiple pieces) will be exported to multiple separate OBJ files.

It is not ready for release, but it is a "Game I can export models from," so I'm mentioning it.
## Post #25
- Username: valvoga
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-05-03T00:02:46+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I suppose I might as well share this list here, I compiled it a long time ago and it's just been sitting around on my hard drive. These are all Playstation Portable games which use the universal Sony GMO format. They can be viewed and converted with a tool I maintain called mesh2rdm. I don't know if anything else supports the GMO format, but I wrote up most of the specs and made them public a long time ago, so anyone can support it if they want to.

```
======================
001. Dissidia: Final Fantasy [i]
002. Castlevania Chronicles [i]
003. Gitaroo Man Lives [i]
004. Ultimate Ghosts N' Goblins [i]
005. Gundam Battle Royale [i]
006. Gundam Battle Universe [i]
007. Jeanne d'Arc [i]
008. R-Type Command [i]
009. Valhalla Knights [i]
010. Exit [i]
011. Exit 2 [i]
012. Bomberman [i]
013. Gripshift [i]
014. Patapon [i]
015. Patapon 2 [i]
016. Practical Intelligence Quotient [i]
017. Rengoku 2 [i]
018. Dynasty Warriors [i]
019. Dynasty Warriors 2 [i]
020. Shin Sangoku Musou 5 Special [i]
021. Fate/Stay Unlimited Codes [c]
022. Namco Museum Battle Collection [i]
023. Bounty Hounds [c]
024. Star Ocean - First Departure [i]
025. Hajime no Ippo Portable: Victorious Spirits [i]

```
## Post #26
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-05-04T07:10:07+00:00
- Post Title: Re: List of games that you can extract 3d models from !

thanks MrAdults so good job
## Post #27
- Username: abc123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 18, 2010 1:52 pm
- Post datetime: 2010-05-19T01:05:29+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from Mirrodin
>
> Just the textures and model data (aside from the few proprietary formats I thought i should keep like the .h32 map files for level data) weighs in at 84.7 gb!  
The game's content is hugely redundant as for each item they use individual CGF's and texture files for the various LOD.  I'm sure this could shrink to as little as 30 gigs or less without all the redundant file data but to do that takes a lot of manual scouring!!!!

Is there a way to view/extract to xml the .h32 file format in Aion?
## Post #28
- Username: Kunigunde
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat May 22, 2010 1:20 pm
- Post datetime: 2010-05-23T23:46:05+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I would like to remind that with “Takaro CryImporter script for 3ds max 6 and above” it is possible to import Cryengine (1) models: version 1.2.1, “imports geometry and animation from Crytek CGF, CGA, CAF and CAL files into 3ds max 7 or above”:

[http://www.takaro.net/downloads.html](http://www.takaro.net/downloads.html)

I was able to import back some models exported with offical exporter plugin from cryengine_mod_sdk_v1.4. I tested Max8/CryExport6.dlu (for Takaro export Maxscripts to work official exporter plugin should be present in Max “plugins” folder).
## Post #29
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-06-09T18:36:46+00:00
- Post Title: Re: List of games that you can extract 3d models from !

How about this : [viewtopic.php?f=16&t=4582](http://forum.xentax.com/viewtopic.php?f=16&t=4582)
## Post #30
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-10T19:30:26+00:00
- Post Title: Re: List of games that you can extract 3d models from !

my list would be
-----------------------
sonic the hedgehog 360
eternal sonata 360
enchanted arms 360
doa4 360
nights into dreams saturn
operation darkness 360
## Post #31
- Username: rafal345
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jun 07, 2010 2:24 am
- Post datetime: 2010-06-12T17:19:26+00:00
- Post Title: Re: List of games that you can extract 3d models from !

NFS U/U2/MW/C/PS/UC - .BIN
Richard Burns Rally - .SGC
Toca Race Driver 3/CMR 2005 - .P3D
GTR2 - .CAR/.TRK/.GMT
rFactor - .MAS (archive) .GMT(3d model)
NFS Shift - .MEB(part)/.BML(full car)/BFF(archive)
GRID - .PSSG
F1 2001/2002/Nascar Sim Racing - .MTS
18 Wheels of Steel - .PMG
Emergency 3 - .V3O
FlatOut - .BGM
GTA IV - .WTF
GTA SA - .DFF
Juiced 2 - .JFS
MotoGranPri2 - .MESH
Left4Dead map - .VMF
Left4Dead model archive - .VPK
Forza Motorsport 3 - .CARBIN
Colin McRae Rally 2 - .C3D
XPand Rally - .3DA
Midtown Madness - .GEO
Viper Racing/Nascar Heat - .MOD
Midtown Madness 2 - .PKG
ReVolt - .PRM
4x4 Evolution 1/2 - .SMF
Racer - .DOF
Test Drive 6 - .DAT
NFS High Stakes - .CRP
NFS Porsche Unleashed - .FCE
Half-Life 2 - .SMD
## Post #32
- Username: chibievil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 12, 2010 9:32 pm
- Post datetime: 2010-07-13T14:30:34+00:00
- Post Title: Re: List of games that you can extract 3d models from !

ok guess it my turn

games i have extracted so far :

Assassin's creed 1 (got 2 not extracted yet)
Resident evil 4
Resident evil 5

thats all i tried so far, and suceeded

for resident evil 5 the tools i used are : Lost planet Arc Extractor, DMC 4MODEL.exe, DMC4tex.exe can be found 
Lost planet arc[http://www.xentax.com/uploads/author/itg/lparcext.rar](http://www.xentax.com/uploads/author/itg/lparcext.rar)
DMC4Tools[http://www.residentevilforums.net/go/aH ... hERTZJVTdT](http://www.residentevilforums.net/go/aHR0cDovL3d3dy5tZ2xkLz9kPUhERTZJVTdT)

for resident evil 4 i used : PMDViewer [http://www.mediafire.com/?lgiz2zvwaqv](http://www.mediafire.com/?lgiz2zvwaqv)

for assassin's Creed 1 and 2 u can use : Maki with the plugins off - animus and lucy which can all be found [http://maki.turfster.be/](http://maki.turfster.be/)
## Post #33
- Username: thugsoldierx
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 17, 2010 5:25 pm
- Post datetime: 2010-07-15T16:27:23+00:00
- Post Title: Re: List of games that you can extract 3d models from !

does any1 know how to extract Marvel ultimate alliance 2 (xbox 360) textures they are .pak files ?

and spiderman 3 (xbox 360 or PC ) textures they are XEPACK files there .

I hope some1 can help me with it i have google it but no info about them .
## Post #34
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-07-19T14:55:46+00:00
- Post Title: Re: List of games that you can extract 3d models from !

wrong section, here you list games that can already be extracted and what tools to use, not asking about if it is possible
## Post #35
- Username: judash137
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 07, 2010 4:22 pm
- Post datetime: 2010-08-04T15:30:58+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from judash137
>
> Pengulord wrote:Devil May Cry 3: .afs and .pac
tut can be found here: http://z9.invisionfree.com/Hells_Atelie ... wtopic=118
Actually, this Tut already dead for a long time, so it cant be count DMC3 in this list 
Can any one repost this tut?
## Post #36
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2010-08-18T17:05:05+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from MrAdults
>
> I suppose I might as well share this list here, I compiled it a long time ago and it's just been sitting around on my hard drive. These are all Playstation Portable games which use the universal Sony GMO format. They can be viewed and converted with a tool I maintain called mesh2rdm. I don't know if anything else supports the GMO format, but I wrote up most of the specs and made them public a long time ago, so anyone can support it if they want to.
Code: Select all(i = immediately visible in binary, c = behind compression/encryption layer)
======================
001. Dissidia: Final Fantasy [i]
002. Castlevania Chronicles [i]
003. Gitaroo Man Lives [i]
004. Ultimate Ghosts N' Goblins [i]
005. Gundam Battle Royale [i]
006. Gundam Battle Universe [i]
007. Jeanne d'Arc [i]
008. R-Type Command [i]
009. Valhalla Knights [i]
010. Exit [i]
011. Exit 2 [i]
012. Bomberman [i]
013. Gripshift [i]
014. Patapon [i]
015. Patapon 2 [i]
016. Practical Intelligence Quotient [i]
017. Rengoku 2 [i]
018. Dynasty Warriors [i]
019. Dynasty Warriors 2 [i]
020. Shin Sangoku Musou 5 Special [i]
021. Fate/Stay Unlimited Codes [c]
022. Namco Museum Battle Collection [i]
023. Bounty Hounds [c]
024. Star Ocean - First Departure [i]
025. Hajime no Ippo Portable: Victorious Spirits [i]

evangelion jo also uses .gmo files 

I wanted to know though if I was looking to rip bounty hounds and it is compressed how would i get the .gmo's?
## Post #37
- Username: OmegaThree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2004 5:06 am
- Post datetime: 2010-09-23T19:01:51+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from potemkis
>
> Sorry for the double post, but does anyone have information about the Unreal 2 .gem format? I understand it's a proprietary format (correct me if I'm wrong).

A little.  I've been deciphering this for the last two or three days.  I have most of the header, three of the four tables (parameters, chunks, and strings), and a few chunks deciphered.  It's not quite enough to export a mesh, not nearly enough for animation.  It's a bizarre, extremely inefficient format.  I'll post what I have in a new thread when it's (more or less) complete, or when I give up on it, whichever comes first.
## Post #38
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-11-20T03:44:35+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from viperzerofsx
>
> 
evangelion jo also uses .gmo files 

I wanted to know though if I was looking to rip bounty hounds and it is compressed how would i get the .gmo's?
Oops, hadn't been paying attention to this topic. As I recall Bounty Hounds is already supported by Noesis. I recall they used a weird archive format that was basically tons of gzips crammed together on sector boundaries, unless I'm thinking of something else. But in any case, you can extract it with Noesis.
## Post #39
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2010-11-29T01:12:18+00:00
- Post Title: Re: List of games that you can extract 3d models from !

hey thanks I'll have to try it in a few days
## Post #40
- Username: hassankamran
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Nov 24, 2010 4:33 am
- Post datetime: 2011-02-04T15:22:32+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Does any one knows how to extract volume.dat files? like way of the samurai 2, i heard that volume .dat contains charcters,stages ect, so if anyone knows where, or what program to use to extract volume.dat? or if am mistaken about volume.dat contains all the characters stages, please inform me as soon as possible. thank you
## Post #41
- Username: poofacetherisen
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 25, 2011 12:02 pm
- Post datetime: 2011-02-07T06:17:19+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from MrAdults
>
> viperzerofsx wrote:
evangelion jo also uses .gmo files 

I wanted to know though if I was looking to rip bounty hounds and it is compressed how would i get the .gmo's?
Oops, hadn't been paying attention to this topic. As I recall Bounty Hounds is already supported by Noesis. I recall they used a weird archive format that was basically tons of gzips crammed together on sector boundaries, unless I'm thinking of something else. But in any case, you can extract it with Noesis.
Wouldn't they get extracted with gitMO? I tried with both and couldn't extract anything. Could have been a bad rip though.
## Post #42
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-02-09T20:17:13+00:00
- Post Title: Re: List of games that you can extract 3d models from !

oh i figured it out you have to get all the little archive files and rip each individually
## Post #43
- Username: poofacetherisen
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Jan 25, 2011 12:02 pm
- Post datetime: 2011-02-10T18:28:28+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from viperzerofsx
>
> oh i figured it out you have to get all the little archive files and rip each individually
Yeah same here, it worked.

> Reply from MrAdults
>
> Code: Select all(i = immediately visible in binary, c = behind compression/encryption layer)
017. Rengoku 2 [i]
Uh, whenever I try to use gitMO on Rengoku II, it crashes. When I search models only it doesn't. And I find it odd that the there's no equipment for the main character found. Did you ever rip it properly?

```
ModVer: 1.0.0.1	 Offset: 0002a1de
```
## Post #44
- Username: DarkStar88
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Feb 16, 2011 12:32 am
- Post datetime: 2011-02-15T17:05:46+00:00
- Post Title: Re: List of games that you can extract 3d models from !

System Shock 2 - Resource extraction is incredibly easy - the archives are renamed ZIP files. Editing them is another story, but is also quite doable.
## Post #45
- Username: Typhox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Dec 15, 2009 12:33 am
- Post datetime: 2011-03-10T02:07:32+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I extracted so far from:
Hexplore
Godzilla Unleashed (Wii)
Godzilla Save The Earth (PS2)
Cities in Motion
## Post #46
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-03-14T21:14:26+00:00
- Post Title: Re: List of games that you can extract 3d models from !

how did you do the ps2 game?
## Post #47
- Username: yair1221
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Feb 26, 2011 3:28 pm
- Post datetime: 2011-04-29T16:32:54+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Half Life 1 engined games(CS 1.6, CS:CZ, CS:S, DOD etc.) 
You just need a gcf tool to open the files in steamapps or models folder, and then use deep exploration or so to convert them

Drift City
The game models can be extracting using a QuickBMS script that i found on this forum, cant remember exactly where though

NFS
I think almost every nfs models can be extracted using ZMod

CNC Generals
The game and its expansion models can be extracted using FinalBIG

Tom Clancy's HAWX files can be extracted using Power Archiver, the files are password-protected though, the password can be found somewhere, You get dat files which can be converted using the following piece of software: [http://forums.ubi.com/eve/forums/a/tpc/ ... rint_topic](http://forums.ubi.com/eve/forums/a/tpc/f/3981007546/m/4101097057/xsl/print_topic)

Thats just a list of the games i own that can be extracted, not including U3 engined games...
## Post #48
- Username: XpucmoBG
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Apr 30, 2011 3:27 am
- Post datetime: 2011-04-29T19:46:27+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from Typhox
>
> I extracted so far from:
Hexplore
Godzilla Unleashed (Wii)
Godzilla Save The Earth (PS2)
Cities in Motion

How did you extracted models from Cities in Motion?

btw, Hello to all, I'm new here as you can see and I'm not american.
## Post #49
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2011-05-07T09:37:27+00:00
- Post Title: Re: List of games that you can extract 3d models from !

My GR2 projects:
- Sacred 2 Fallen Angel - [http://tatooinebase.star-fleet.org/UPLO ... .debug.rar](http://tatooinebase.star-fleet.org/UPLOAD/grnreader98.v1.4.0.3.debug.rar)
- Heroes of Might and Magic V - [http://tatooinebase.star-fleet.org/UPLO ... viewer.rar](http://tatooinebase.star-fleet.org/UPLOAD/HoMM.V.model.viewer.rar)
- Metin2 (follow-up on Sacred 2 Fallen Angel extraction, using grnreader98 v1.4.0.3 - see also [http://tatooinebase.star-fleet.org/UPLO ... n_test.rar](http://tatooinebase.star-fleet.org/UPLOAD/Metin2_footman_test.rar));
These three projects partially follow-up on fedrico's GR2 decoding  
Others by me:
- Homeworld - [http://tatooinebase.star-fleet.org/Tools.download.htm](http://tatooinebase.star-fleet.org/Tools.download.htm)
- Homeworld II - [http://tatooinebase.star-fleet.org/Tools.download.htm](http://tatooinebase.star-fleet.org/Tools.download.htm)
- Blitzkrieg - [http://tatooinebase.star-fleet.org/UPLO ... taller.rar](http://tatooinebase.star-fleet.org/UPLOAD/Tanks.v0.2d.installer.rar)
- NFS5 Porsche Unleashed / Porsche 2000 - [http://tatooinebase.star-fleet.org/UPLO ... .v0.8e.rar](http://tatooinebase.star-fleet.org/UPLOAD/NFS5carpartsEditor.v0.8e.rar)

Not by me:
Turfster's game tools  ( [http://prince.turfster.be/](http://prince.turfster.be/) )
=====================================
- Assassin's Creed;
- Prince of Persia Trilogy;
- Bloodrayne 1 & 2;
- Vampire: Bloodlines;
- Metal Gear Solid 2;
- Tomb Raider Legend.
## Post #50
- Username: lordofnosgoth
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 16, 2011 7:14 am
- Post datetime: 2011-06-15T23:26:24+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I know this is probably the wrong thread, but I need folks to help me extract editable forms of modeling files from UDK games; specifically Transformers: War for Cybertron. Can anyone help me?
## Post #51
- Username: wuannetraam
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 01, 2011 6:08 pm
- Post datetime: 2011-07-01T10:12:15+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hi guys,

I'm new to this forum and I'm desperatly looking for a model from GoW. A locust model.
this one: [http://www.google.nl/imgres?imgurl=http ... 80&bih=608](http://www.google.nl/imgres?imgurl=http://xbox360media.ign.com/xbox360/image/article/906/906303/gears-of-war-2-20080828041705175-000.jpg&imgrefurl=http://comics.ign.com/articles/927/927623p1.html&usg=__4jh2ks2Q4WMs2heyKlytn6T6dqs=&h=348&w=479&sz=72&hl=nl&start=0&zoom=1&tbnid=zkeNT7oMhjx-OM:&tbnh=124&tbnw=192&ei=9JwNTp_8MYa88gOt59nWDg&prev=/search%3Fq%3Dgears%2Bof%2Bwar%2Blocust%26um%3D1%26hl%3Dnl%26sa%3DN%26biw%3D1280%26bih%3D608%26tbm%3Disch&um=1&itbs=1&iact=rc&dur=114&page=1&ndsp=17&ved=1t:429,r:3,s:0&tx=90&ty=104&biw=1280&bih=608) 

I want to import it in 3dsmax for a non-commercial project. I'm willing to pay $20,- if you can give it to me with textures and if possible rigged. I know it's not much but we really need it.  

you can contact me via this thread or via maarten87_ [@] hotmail.com

Thanks in advance,
Maarten
## Post #52
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-07-07T16:33:58+00:00
- Post Title: Re: List of games that you can extract 3d models from !

anything for the ios? furry fan showed me an ace combat xi model but it didn't come out right can it be ripped?
## Post #53
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2011-08-18T13:52:26+00:00
- Post Title: Re: List of games that you can extract 3d models from !

This thread is a complete Cluster F*** why is it stickyed? It is by no means a definitive list.

It would make more sence to have a seperate forum section for individual extractable games or a single updated post with links to the game extraction information.
## Post #54
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-20T02:32:05+00:00
- Post Title: Re: List of games that you can extract 3d models from !

That's what the wiki is for. Or, is an ideal spot for it.
Then you could remove any garbage anytime.
## Post #55
- Username: gtaneverdie
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 30, 2010 12:33 am
- Post datetime: 2011-10-12T14:24:00+00:00
- Post Title: Re: List of games that you can extract 3d models from !

hello
is there any way I could extract model from F.E.A.R 1 and C&C Renegade?
## Post #56
- Username: viperzerofsx
- Rank: veteran
- Number of posts: 95
- Joined date: Thu May 27, 2010 12:07 pm
- Post datetime: 2011-10-16T14:51:33+00:00
- Post Title: Re: List of games that you can extract 3d models from !

did you try the general's tool? they use a very similar engine
## Post #57
- Username: Convarion801
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 30, 2011 1:38 pm
- Post datetime: 2011-12-30T05:42:03+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Im looking for someone to extract about 30-0 images from a game called Space Marine. If you can help me out send me a PM and let me know. Compensation for time is also available and also future work and compensation possible depending on work just send me a PM. We will talk more. Thanks.
## Post #58
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2012-01-12T19:05:08+00:00
- Post Title: Re: List of games that you can extract 3d models from !

SCS Software - Same Engines
Tools: Winrar + Z-Modeler2
Difficulty: Easy
-------------------------------------------
18 Wheels of Steel - Extreme Trucker 2
18 Wheels of Steel - Extreme Trucker 1
18 Wheels of Steel - American Long Haul
18 Wheels of Steel - Haulin
18 Wheels of Steel - Convoy
18 Wheels of Steel - Across America
18 Wheels of Steel - Pedal to the Metal
Truck Saver
UK Truck Simulator
German Truck Simulator
Euro Truck Simulator 1
Bus Driver
Trucks & Trailers - No ZM2 Import yet


Techland - 1C Company - Chrome-Engine
Tools: Z-Modeler2
Difficulty: Easy
-------------------------------------------
Offroad Drive 1 4x4 UAZ
Offroad Drive 2 4x4 Hummer
X-Pand Rally
X-Pand Rally X-Treme
Classic Car Racing
GM Rally
KRAZ
GTI Racing


Simbin - Same Engine based on Race 07
Tools: Luigis Decrypt Tool + Z-Modeler2
Difficulty: Easy
-------------------------------------------
STCC 2 - The Game
Race Room - The Game 2
Race Room - Formula
Race Injection
Race 11 - Retro Pack
Race 11 - GT Power
Race 10 - The WTCC Game
Race 08 - Crowne Plaza Raceway
Race 07 - The WTCC Game
Race 06 - The WTCC Game
BMW M3 Challenge
Lexus IS-F Track Time
GTR Evolution
Volvo - The Game
Race Room - The Game 1
Superleague Formula
STCC 1 - The Game
Race On


3dSimed Support
Tools: 3dSimed
Difficulty: Easy
-------------------------------------------
F1 2011
F1 2010
Colin McRae DiRT 3
Colin McRae DiRT 2
Colin McRae DiRT 1
WRC Fia World Rally Championship 1
TOCA Race Driver GRiD
Superstars V8 2 Next Challenge
Superstars v8 1 Racing


Simbin - Thier old Engine
Tools: GTR/GTL/MAS Unpack Tool + Z-Modeler2
Difficulty: Medium
-------------------------------------------
GTR Fia GT Racing 1
GTR Fia GT Racing 2
GT Legends
R-Factor


Zmodeler 1 and 2 Filter
Tools: Quickbms + Unpacker + Z-Modeler1/2
Difficulty: Medium
-------------------------------------------
Juiced 2 - Hot Import Nights
Test Drive Unlimited 2 (Big/bnk Script)
Need for Speed Shift 2 (Xbox Texture Tool)
Need for Speed Shift 1 (Xbox Texture Tool)
Need for Speed Hot Pursuit
Need for Speed Undercover
Need for Speed ProStreet
Need for Speed Carbon
Need for Speed Most Wanted (Bintex)
Test Drive Unlimited 1 (BNK Script)
FlatOut 2
FlatOut 1
Tough Truck - Modified Monsters (FlatOut)
Crashday
Richard Burns Rally
Rallisport Challenge
GTA IV EfLC (OpenIV)
GTA San Andreas (IMG/TXD Tool)
GTA Vice City (IMG/TXD Tool)
GTA III (IMG/TXD Tool)
Sportscar GT (Old Archive Unpack Tool)


3ds Max User Scripts
Tools: 3ds Max + Unpacktools
Difficulty: Hard
-------------------------------------------
Offroad Drive 3 (Umodel Script)
Mafia 2 (Toseks Script + SDS Decrypt)
Colin McRae Rally 05 (Big Tool) (Old)
colin mcrae rally 04 (Big Tool) (Old)


Usercreated Tools Scripts and Harder Games
Tools: See the List + Deep Exploration
Difficulty: Hard
-------------------------------------------
Forza Motorsport 3 (Forza Studio, Xbox Texture Tool, Quickbms Zip Script)
Need for Speed Underground 2 (BIN2ASE, Bintex)
Need for Speed Underground 1 (BIN2ASE, Bintex)
4x4 Evolution 2 (Archive Unpacker)
4x4 Evolution 1 (Archive Unpacker + Tiff Tool)
Toca Race Driver 3 (Big Tool + p3d2z3d)
Toca Race Driver 2 (Big Tool + p3d2z3d)
Toca Race Driver 1 (Big Tool + p3d2z3d)
World Racing 1 (Check Kroms Website)
World Racing 2 (Check Kroms Website)
Mercedes-Benz Truck Racing (Check Kroms Website)
Ferrari Virtual Race (Check Kroms Website)



Have Fun
## Post #59
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2012-01-20T08:17:39+00:00
- Post Title: Re: List of games that you can extract 3d models from !

welcome guki 
very nice list
## Post #60
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-02-07T19:47:18+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Warammer 40,000 - Space Marine
Red Faction Guerrilla and Armageddon - using 3D Ripper DX
- Can post Renders if anyone is interested


X3 - using tools developed for X3 modding

Batman Arkham City and Asylum - updated umodel

Dead Island - 3D Ripper DX

Dogfighter, Skydrift - 3D Ripper DX

Dynasty Warriors 7 - Offzip, QuickBMS and Maxscript
Legends of Troy - Offzip, QuickBMS and Maxscript

Avatar - Blender import script
## Post #61
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-02-24T10:00:52+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Asura's Wrath XBOX360
Magna Carta 2 XBOX360
All files have a *.xxx format.

UE Viewer
[http://www.gildor.org/downloads](http://www.gildor.org/downloads)
## Post #62
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-07T12:12:34+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from dj082502
>
> Asura's Wrath XBOX360
Magna Carta 2 XBOX360
All files have a *.xxx format.

UE Viewer
http://www.gildor.org/downloads



How do you extract models from 360 games?
## Post #63
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-08T23:20:26+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from Vashey
>
> How do you extract models from 360 games?
Unreal Package Extractor
[http://www.gildor.org/down/25/umodel/extract.zip](http://www.gildor.org/down/25/umodel/extract.zip)
## Post #64
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-10T18:59:35+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I'm sorry but it doesnt work with this, how do you do it exaclty?

I've dumped the game files with Gael wx360 but after this there is nothing I can read with unreal viewer.
## Post #65
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-03-11T01:32:02+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from dj082502
>
> Vashey wrote:How do you extract models from 360 games?
Unreal Package Extractor
http://www.gildor.org/down/25/umodel/extract.zip

Likely need to unpack the files with something like xDVD Mulleter

Try my favorite search tool [http://www.filecrop.com/](http://www.filecrop.com/)

associate the .xxx file to open with umodel to view the file

to extract, you will need to run the command line
umodel -path="full path" -export -all "filename"

(this works easiest if you extract umodel to the same folder as your .xxx files)
( check the umodel documentation for more options )
## Post #66
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-11T14:28:28+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Thing is there is no .xxx file in the game I dumped.
(Tenchu Z for the record)
## Post #67
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-03-11T14:49:15+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from Vashey
>
> Thing is there is no .xxx file in the game I dumped.
(Tenchu Z for the record)

Tenchu Z is not an Unreal Engine game, those are in DirectX with Textures in .xpr

I pulled those out with a combination of a DirectX model viewer 
[url][http://www.janbirsa.com/tools/ModelViewer/url](http://www.janbirsa.com/tools/ModelViewer/url)] with 3D Ripper DX 
and an xpr texture converter that was designed for Tecmo games
## Post #68
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-11T23:13:22+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Exactly!
The other guy in the other thread ( I forgot his name) he dumped every singeld Ninja gaiden 2 model and he said he could do it with tenchu Z, he never told how he'd do all this...
That's so lame.

Is there a way to attach the XPR files with the motion for animations?
## Post #69
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-11T23:17:11+00:00
- Post Title: Re: List of games that you can extract 3d models from !

thanks by the way it worked!


edit: is there a way to prevent it from being "flat" when you import it in a 3D software?
## Post #70
- Username: rmezatang
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Jun 21, 2010 10:32 am
- Post datetime: 2012-03-12T01:25:57+00:00
- Post Title: Re: List of games that you can extract 3d models from !

If you used 3D Ripper on the DirectX Model Viewer, you can use the 3DR import plugin to import the file.  You will be prompted on the import with options.  To correct "skewing" you need to select the projection parameters at the top of the import options (under recommended values).
With game rips, you sometimes have more then one choice here - take your pick
Under the lower options, I typically turn off everything except the "...rendered to rendertarget" unless that imports nothing, then I gradually uncheck until something imports.
You can usually tell my the .3dr file size if there is something there- 1-5kb, probably nothing, over 39MB and you could run into memory problems when importing (depending on your machine)

never looked at the animations there, you can get a whole bunch of animations elsewhere - search "Monster Bones Library" and similar depending on your 3D program - most are either .bvh or .bip
## Post #71
- Username: Vashey
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Mar 15, 2011 9:47 pm
- Post datetime: 2012-03-12T13:39:19+00:00
- Post Title: Re: List of games that you can extract 3d models from !

It worked again thanks.

Did you manage to extract the .bin files?
## Post #72
- Username: HGBCreator
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 23, 2012 7:16 pm
- Post datetime: 2012-03-23T11:23:34+00:00
- Post Title: Re: List of games that you can extract 3d models from !

hi guys ! me extrcted hellderdo game all assest ! but 3d model format is *model* i dont know how to open this file ! anyone know ????? 
2- how to open MV3 model ! format is *FF* ??? 
ANYONE HLP ME ?
## Post #73
- Username: RanJ
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Sep 06, 2011 9:57 am
- Post datetime: 2012-04-07T03:12:12+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Can someone please tell me what tools i would require to extract models from Call of duty MW3? i would be very very grateful.
## Post #74
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2012-05-10T02:04:51+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from Vashey
>
> It worked again thanks.

Did you manage to extract the .bin files?
I haven't been able to extract the .bin files, could you tell me how you went about that?
## Post #75
- Username: Atwaetere
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 30, 2012 2:23 am
- Post datetime: 2012-06-11T16:50:52+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I am very new to this but still very interested. I really want to learn how to do this cool stuff. I have taken the tutorial given earlier. Yet i need many more pointers to guide me. Please help
## Post #76
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-07-04T18:34:55+00:00
- Post Title: Star Wars - Clone Wars Adventures

Star Wars - Clone Wars Adventures

Get the free client by registering here.
[https://www.clonewarsadventures.com/](https://www.clonewarsadventures.com/)

Unpack the *.pack archives with the CWA_Extractor by Uli found here.
[http://forum.modsource.org/index.php?topic=977.0](http://forum.modsource.org/index.php?topic=977.0)

3D Object Converter can open the *.dme model files for viewing or converting to other formats.
[http://web.axelero.hu/karpo/](http://web.axelero.hu/karpo/)


Local backup:


 CWA_Extractor.zip
(5.69 KiB) Downloaded 137 times
## Post #77
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2012-07-13T06:19:49+00:00
- Post Title: Star Wars - Clone Wars Adventures

Lego Island 2 - The brickers revenge
I've successfully researched all the files of this game. I've already wrote an Exporter for .TGA- and (mesh to->) .OBJ-files. At the moment I'm writing an Importer to get the data into Lego Island 2 back. In the future I'm going to write a few specifiactions for the wiki.

So, in the near future you can add "Lego Island 2" to this list of file format-supported games.
## Post #78
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2012-07-13T15:28:32+00:00
- Post Title: Star Wars - Clone Wars Adventures

> Reply from pivke
>
> Lego Island 2 - The brickers revenge
I've successfully researched all the files of this game. I've already wrote an Exporter for .TGA- and (mesh to->) .OBJ-files. At the moment I'm writing an Importer to get the data into Lego Island 2 back. In the future I'm going to write a few specifiactions for the wiki.

So, in the near future you can add "Lego Island 2" to this list of file format-supported games.

good luck
## Post #79
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-08-08T17:09:33+00:00
- Post Title: Star Wars - Clone Wars Adventures

Hi, 

anyone who has a install of 3DX ripper 1.8.1? 
Deep shadows site is down and a copy is nowhere to be found. 

Appreciate in advance.
## Post #80
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-26T00:52:53+00:00
- Post Title: Star Wars - Clone Wars Adventures

3D Ripper
[http://www.sendspace.com/file/ks0wyb](http://www.sendspace.com/file/ks0wyb)
## Post #81
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-08-30T13:21:39+00:00
- Post Title: Star Wars - Clone Wars Adventures

> Reply from chrrox
>
> 3D Ripper
http://www.sendspace.com/file/ks0wyb

Appreciate it chrrox, I found it eventually and ended up forgetting to post there for those who want it.
## Post #82
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-08T17:15:05+00:00
- Post Title: Star Wars - Clone Wars Adventures

Dino and Aliens:
engine: unknown
extensions: .dat, .msh/.cgo, .skl/.chr .anm, .jpg and .tga
tools not public
in this topic is script for quickbms to extract .dat files and script for blender to import .msh files
[viewtopic.php?f=16&t=9385](http://forum.xentax.com/viewtopic.php?f=16&t=9385)
script support:
vertices
faces
uvs
texture you can add in uv/image editor
this is my first import script to blender
## Post #83
- Username: MASS1L1A
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 21, 2012 9:20 am
- Post datetime: 2012-12-08T14:03:21+00:00
- Post Title: Star Wars - Clone Wars Adventures

moved post
## Post #84
- Username: dnmnbg
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 14, 2010 4:22 am
- Post datetime: 2013-01-08T02:11:38+00:00
- Post Title: Star Wars - Clone Wars Adventures

path of exile
## Post #85
- Username: Carnaxus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2011 9:00 am
- Post datetime: 2013-11-13T11:29:01+00:00
- Post Title: Star Wars - Clone Wars Adventures

Games that I "can" extract from: [Full list, bought a license to the program ](http://3doc.i3dconverter.com/formats.html)

Games that I "have" extracted from:
World of Tanks
Shaiya
Morrowind (also imported a few Shaiya models)
Auran Trainz simulator, started in 2006 version and haven't stopped yet XD

Edit:

Wait...this is my first post ever on this forum?...I sincerely doubt that.  Must have been in an old thread that's been deleted.
## Post #86
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2013-11-14T14:17:03+00:00
- Post Title: Star Wars - Clone Wars Adventures

> Reply from Carnaxus
>
> Games that I "can" extract from: Full list, bought a license to the program 

Games that I "have" extracted from:
World of Tanks
Shaiya
Morrowind (also imported a few Shaiya models)
Auran Trainz simulator, started in 2006 version and haven't stopped yet XD

Edit:

Wait...this is my first post ever on this forum?...I sincerely doubt that.  Must have been in an old thread that's been deleted.
you got the first thanks at your first post *suppose it as a badge*
## Post #87
- Username: Carnaxus
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2011 9:00 am
- Post datetime: 2013-11-15T19:14:15+00:00
- Post Title: Star Wars - Clone Wars Adventures

> Reply from shekofte
>
> you got the first thanks at your first post *suppose it as a badge*

Yaaaaaaay!
## Post #88
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2014-04-03T16:22:15+00:00
- Post Title: Star Wars - Clone Wars Adventures

I'm trying to extract files from Code Lyoko: Quest for Infinity from PSP. The files use .gcn .cp2 .pc & .psp formats. Can anyone help me find an extractor for it?
## Post #89
- Username: dirtypantsdan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 03, 2012 3:33 am
- Post datetime: 2014-08-11T00:03:34+00:00
- Post Title: Star Wars - Clone Wars Adventures

Ace Attorney Dual Destinies recently got released on iOS in Japan, I was wondering if it was possible to rip these now that they are in a more familiar format. The models just look so good... Is it possible to do this?
## Post #90
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2014-08-20T21:14:54+00:00
- Post Title: Star Wars - Clone Wars Adventures

Live For Speed - .Vob files
Need For speed Underground 2
GM Rally
GTI Racing

Update. 23/09/2014

Colin mcrae 2005 and 2004
Toca Racer driver 3
V-rally 3
Nascar HEAT
Forza 2 / 3 / 4 / Horizon
Half Life 1 / 2
Driver 3
Dirt Track Racing 3
Evolution GT
Crashday




-----
## Post #91
- Username: ellegirl01
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 28, 2014 1:08 pm
- Post datetime: 2014-09-28T05:52:28+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from almondega
>
> folks!

Now Blender do import custom Atlantica .nif models and animations
get it here: http://niftools.sourceforge.net/forum/v ... =13&t=2531
(new versions also avaliable)

cya

So sorry if this has already been addressed somewhere, but is there any workaround/fix to force Nifskope to open when it crashes to desktop upon loading? The 3DSMax plugin is great, but sometimes I just want to look at the models.
## Post #92
- Username: kmthrong
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Oct 22, 2014 9:19 pm
- Post datetime: 2014-10-30T04:57:48+00:00
- Post Title: Re: List of games that you can extract 3d models from !

and don't forget GTA IV
## Post #93
- Username: kamui
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Oct 30, 2014 4:19 pm
- Post datetime: 2014-10-30T08:31:17+00:00
- Post Title: Re: List of games that you can extract 3d models from !

so, is there any   summary post or file with all nominations?
## Post #94
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2014-12-29T23:19:20+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Call of Duty Advance Warfare  - Lime64  [http://tom-bmx.com/](http://tom-bmx.com/)
## Post #95
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-05T17:15:44+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Sega GT 2002/Online 3D Model .xmx format can be opened with 3D Object Converter 6.0 Gold Edition.
Textures are in .dds only needs to be Flip Vertically.
If you rework the textures the result is really good.

Here and example for how looks when evetything is reworked.
[https://fbcdn-sphotos-d-a.akamaihd.net/ ... 3748_o.jpg](https://fbcdn-sphotos-d-a.akamaihd.net/hphotos-ak-xap1/t31.0-8/10855127_1034747606553309_1257931719949453748_o.jpg)
## Post #96
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2015-07-03T01:07:17+00:00
- Post Title: Re: List of games that you can extract 3d models from !

CHIPICAO how extract mesh of nitro nation?
## Post #97
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2015-07-14T21:45:54+00:00
- Post Title: Re: List of games that you can extract 3d models from !

The models that can't be extracted from Xbox 360 like Marvel Ultimate Alliance Gold Edition, can now be extractable, via ninjaripper on xenia emulators now
## Post #98
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-08-02T13:31:47+00:00
- Post Title: Re: List of games that you can extract 3d models from !

[MechWarrior Online](http://mwomercs.com) and [Star Citizen](http://www.robertsspaceindustries.com).  Probably other modern Cryengine (3.4+) games as well.

See my post here for the tool to do that:

[viewtopic.php?f=33&t=13137](http://forum.xentax.com/viewtopic.php?f=33&t=13137)

Edit:  Add [Armored Warfare](http://aw.my.com/us) to the list.
## Post #99
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2015-10-24T05:35:21+00:00
- Post Title: Re: List of games that you can extract 3d models from !

100000

THIS THREAD EXCEEDS >>> One hundred thousand <<< VISITS
## Post #100
- Username: DonCapputini
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 04, 2015 7:23 pm
- Post datetime: 2015-11-04T13:23:25+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Is there a models from Black Desert somehwere? Looking for them
## Post #101
- Username: LarsMasters
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Aug 25, 2014 10:30 am
- Post datetime: 2015-12-22T01:54:14+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Does anyone know how to extract Marvel Ultimate Alliance 1's Xbox 360 & Wii models? Thx
## Post #102
- Username: lhj117383609
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 07, 2016 8:18 pm
- Post datetime: 2016-09-08T15:31:04+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from shekofte
>
> i am going to prepare the list of all games that are extractable easily !
please if you extracted 3d models from some games add the name of them to this list thank .
name      fromat
farcry      cgf
crysis      cgf chr
half life 2     mdl
maxpayne    kf2 skd
.................

I see this post can be Asphalt 8.Pig to FBX, I would like to export a model used in unity3D, but I am a program developer, do not know how to use the 3dsmax, ask the forum who has made Asphalt 8 model cars or track model can be used in the unity3D file, or in 3dsmax composite molding car model or track model, will be greatly appreciated.
## Post #103
- Username: mcurtix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 29, 2016 1:28 pm
- Post datetime: 2016-10-29T05:40:22+00:00
- Post Title: Re: List of games that you can extract 3d models from !

ive been trying to rip th Fey hero model from Paragon using Ninja Ripper, but no success so far, but somehow i was able to get the textures
## Post #104
- Username: Coleiosis
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Mar 16, 2016 6:51 am
- Post datetime: 2016-11-28T22:38:41+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I would really like some help on extracting models from Twisted Metal: Head-On (Extra Twisted Edition)(PS2). Mainly because I use a Mac, not Windows, so most of the tools I've downloaded are pretty much useless to me.
## Post #105
- Username: k1995
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Dec 09, 2016 3:30 pm
- Post datetime: 2016-12-09T07:59:23+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I would like to ask someone to know how to extract from Japan's Ultraman (Fighting Evolution 4) and (War Genesis Battride), would like to ask how this kind of game should be extracted!
## Post #106
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2017-08-11T01:59:33+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Knight Rider 2 by Davilex works with Niftools.
## Post #107
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2018-09-08T15:55:27+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Is there a list of games we can 'Import' Models into?
## Post #108
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2018-09-08T17:43:57+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from ReeceMix
>
> Is there a list of games we can 'Import' Models into?
you may use this tool as reverse way too for many games as it can extract many of them too :
[https://zenhax.com/viewtopic.php?f=4&t=22](https://zenhax.com/viewtopic.php?f=4&t=22)
## Post #109
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T15:44:33+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from ReeceMix
>
> Is there a list of games we can 'Import' Models into?Not to my knowledge.
But you can just search for games where the model format was fully analyzed, i.e. where each byte of a model file is known, or more precise where all the hex data is "translated" into structures.
In this case it would be possible at least to convert static models from wavefront obj (for example) to the whatever-fully-analyzed-format.

So as a first step you'd need a list of fully analyzed 3D formats, imho.
## Post #110
- Username: LightXPS
- Rank: advanced
- Number of posts: 57
- Joined date: Thu Jan 10, 2019 6:42 pm
- Post datetime: 2019-01-10T10:56:28+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from Pesmontis
>
> [...]
- Metin2 (follow-up on Sacred 2 Fallen Angel extraction, using grnreader98 v1.4.0.3 - see also http://tatooinebase.star-fleet.org/UPLO ... n_test.rar);
[...]

Hey there, another newbie here 

I've got the situation that I plan on extracting at least one model from the game mentioned in the quote (which I isolated there). Problem is, though: I can't seem to find a working model extractor and/or locate the files needed. I tracked it down (in both official and private server versions) to the pack folder - explorer path is C:/Program Files (x86)/Metin2_Germany/pack (on my pc) - and then lose it there. It is a simple graphic though, but the models are 3D.

So, does anyone in here have an idea about a working file extractor and/or some already existing models? I need them for XPS/XNALara and haven't found any so far... Any help in any kind would be appreciated  Also, the link I quoted there is dead. Any ideas on this?
## Post #111
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2019-04-11T22:18:14+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Skyrim. I'm having an issue with animations tho.
## Post #112
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2019-04-21T19:38:08+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I've just tried UModel with NVIDIA Star Wars RTX Demo. Everything seems works with UE4.20.
## Post #113
- Username: asdzx34
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Apr 16, 2019 6:52 pm
- Post datetime: 2019-06-23T12:07:18+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Does anyone know how to extract the flying rpcs3 model?
## Post #114
- Username: hydin
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 02, 2016 1:48 pm
- Post datetime: 2019-10-01T08:46:36+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I've recently discovered a Call of Cthulhu PC game that has an amazing looking ritual dagger in it. Does anyone know if the models are able to be ripped from this? I've searched here and on other forums but haven't seen anything about it.

Any help's appreciated, and thanks!
## Post #115
- Username: AlastairCook
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 12, 2019 3:12 am
- Post datetime: 2019-10-12T10:40:07+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Half Life 2 is the best one i have ever liked. excellent shooting game. would love it to be in 3D mode .
## Post #116
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2019-10-12T21:10:18+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from hydin ↑Tue Oct 01, 2019 4:46 pm at Tue Oct 01, 2019 4:46 pm
>
> 
I've recently discovered a Call of Cthulhu PC game that has an amazing looking ritual dagger in it. Does anyone know if the models are able to be ripped from this? I've searched here and on other forums but haven't seen anything about it.

Any help's appreciated, and thanks!

It's Unreal Engine 4 game and [fully supported](https://www.gildor.org/smf/index.php/topic,6392.0.html) by UE Viewer.
## Post #117
- Username: zgmfx14a
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Oct 19, 2019 8:11 am
- Post datetime: 2019-10-22T02:34:50+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Does anyone know how to extract models from NIOH?
## Post #118
- Username: USA
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 20, 2020 3:58 pm
- Post datetime: 2020-02-20T07:59:48+00:00
- Post Title: Re: List of games that you can extract 3d models from !

You can also take free 3D models from resources like this one [https://creazilla.com/sections/3-3d-models](https://creazilla.com/sections/3-3d-models)
## Post #119
- Username: Dirk808
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 25, 2020 9:09 am
- Post datetime: 2020-03-25T01:14:29+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hello All,

Just after some help

I have a mod from Nascar Heat and looking to get it converted to rfactor if possible. I have no idea how to do it.
## Post #120
- Username: jumpjack
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 25, 2020 9:44 pm
- Post datetime: 2020-05-03T12:51:30+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Almost 10 GB of 3d art&culture full locations: Machu Picchu, St. Peter in Rome, Red Square in Moscow,...
[http://web.archive.org/web/201004150750 ... /locations](http://web.archive.org/web/20100415075028/http://vizerra.com/en/locations)

Models in NIF Gamebryo 20.6.0.0 format; some of them can be read by Noesis and/or Nifskope, others do not, none is correctly exported as of now (textures issues).
## Post #121
- Username: Beridow
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 03, 2020 6:33 pm
- Post datetime: 2020-08-03T10:35:59+00:00
- Post Title: Re: List of games that you can extract 3d models from !

and don't forget GTA IV
## Post #122
- Username: kaosity
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 20, 2021 11:53 pm
- Post datetime: 2021-01-22T17:55:55+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Don't forget the Call of Duty games! Recently started messing with call of duty models, which you can extract with Wraith Archon ([https://wiki.modme.co/wiki/apps/Wraith-Archon.html](https://wiki.modme.co/wiki/apps/Wraith-Archon.html)) which is for the older call of duty games, or Greyhound ([https://github.com/Scobalula/Greyhound](https://github.com/Scobalula/Greyhound)), which is for newer games.
## Post #123
- Username: ErikV
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 06, 2021 6:19 pm
- Post datetime: 2021-02-06T10:53:26+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hi,

Anyone had any success in extracting models from Rogue Trooper Redux? or can someone point me in the right direction as to how it could be done. 

Many thanks
## Post #124
- Username: Pendrake
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 02, 2021 11:01 am
- Post datetime: 2021-03-02T03:04:06+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Given Defiance/Defiance 2050 are shutting down as of April 29th, anyone had any luck porting the 3d assets out of either game? Or know a good ripping tool for use for the Gamebryo engine they run on?
## Post #125
- Username: Generosity
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Mar 25, 2021 3:28 pm
- Post datetime: 2021-03-26T13:16:15+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I guess NifSkope is used for that. Am I wrong?
## Post #126
- Username: arora2deepak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 20, 2021 5:46 pm
- Post datetime: 2021-04-20T11:05:41+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Sorry for the double post, but does anyone have information about the Unreal 2 .gem format?
## Post #127
- Username: Polecze02
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jun 27, 2021 10:46 pm
- Post datetime: 2021-06-27T14:48:45+00:00
- Post Title: Re: List of games that you can extract 3d models from !

hello i need link to this Toca Race Driver 3 (Big Tool + p3d2z3d)

p3d2z3d is no longer available i need this!
## Post #128
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-09-06T14:53:58+00:00
- Post Title: Re: List of games that you can extract 3d models from !

qq speed, garena speed drifters png (actually it's a unity file format with different extension)
## Post #129
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-11-25T02:05:46+00:00
- Post Title: Re: List of games that you can extract 3d models from !

I know this was told about before, but it was very long ago and it used the wrong programs. (ZModeler 2)

You can use 3DSimEd (along with WTCCED) to extract the car files in Volvo the Game!

3DSimEd (costs money!): [http://sim-garage.co.uk/](http://sim-garage.co.uk/)
WTCCED link: [http://aluigi.altervista.org/search.php?src=race07](http://aluigi.altervista.org/search.php?src=race07)
How to use WTCCED: [http://aluigi.altervista.org/papers/wtcced_all.txt](http://aluigi.altervista.org/papers/wtcced_all.txt)
## Post #130
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2021-12-13T20:04:10+00:00
- Post Title: Re: List of games that you can extract 3d models from !

> Reply from ReVolt ↑Thu Nov 25, 2021 10:05 am at Thu Nov 25, 2021 10:05 am
>
> 
I know this was told about before, but it was very long ago and it used the wrong programs. (ZModeler 2)

You can use 3DSimEd (along with WTCCED) to extract the car files in Volvo the Game!

3DSimEd (costs money!): http://sim-garage.co.uk/
WTCCED link: http://aluigi.altervista.org/search.php?src=race07
How to use WTCCED: http://aluigi.altervista.org/papers/wtcced_all.txt

Thanks very amazing guide
## Post #131
- Username: LAZYhero
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 26, 2021 6:13 pm
- Post datetime: 2021-12-26T10:27:22+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hello, is there a scene model export file for Humiliation 2? Can you give me a guide? thank you
## Post #132
- Username: Linuxgod
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Feb 02, 2021 3:19 am
- Post datetime: 2022-01-25T05:13:09+00:00
- Post Title: Re: List of games that you can extract 3d models from !

game models that I received


TERA Online \ Aura Kingdom \ Dragon Nest \ Blade and Soul \ Revelation \ CS GO \ WoW \ Dota 2 \ Aion \ LoL \ GTA Sa \ ArcheAge \ Grand Fantasia \ Battlerite \ ForSaken \ Swordsman Online
## Post #133
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2022-02-08T17:51:21+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Here's a frehsly made Blender importer for Omikron: the Nomad Soul:

[https://github.com/Chevluh/Omikron_Blender_Importer](https://github.com/Chevluh/Omikron_Blender_Importer)
## Post #134
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-03-25T16:45:48+00:00
- Post Title: Re: List of games that you can extract 3d models from !

The formats I have for you guys are Offroad Legends, Bus Derby, and Dust: Offroad Racing.
## Post #135
- Username: LukeAndBobPro
- Rank: beginner
- Number of posts: 30
- Joined date: Fri Jun 04, 2021 3:54 am
- Post datetime: 2022-04-02T22:27:28+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Well, that went well.   
thanks! I guess?
## Post #136
- Username: tusslesebi09
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 12, 2023 5:21 pm
- Post datetime: 2023-03-20T12:00:40+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Using game-specific mods and tools: Some games may have modding communities that have developed tools or mods to extract 3D models from the game. These tools may be specific to the game and may require some technical knowledge to use.
## Post #137
- Username: arsonicus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 07, 2023 11:08 pm
- Post datetime: 2023-08-07T15:18:38+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hello people, anyone knows if there is an extractor for Men of War Assault Squad 2? From .ply to .obj
## Post #138
- Username: Teardrop
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 09, 2023 8:30 pm
- Post datetime: 2023-08-09T12:40:20+00:00
- Post Title: Re: List of games that you can extract 3d models from !

Hi! You can look for general-purpose 3D model conversion tools that support .ply and .obj formats, such as Blender or MeshLab
