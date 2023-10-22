## Post #1
- Username: HELLFIRE
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-18T16:31:27+00:00
- Post Title: Game support requests

Hi to all the coders and programmers out there. Thanx for all the good work on this GRAF editor. I've been using it since C&C Generals came out and it never failed me.

However I also want to edit other games which the program doesn't support. Here is a list:

 Splinter Cell  (including expansions)
 Doom 3
 Half-Life 2
 ALL the Battlefield games
 Medal of Honor (Orginal, expansions and Pacific Assault)
 Previous C&C games ( I have a XCC editor but can't you oncorporate  
                                   into MX for easier use?)

If you can reply and give me an overview of all the technical difficulties of these modifications, I would really appreciate it.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-18T17:05:27+00:00
- Post Title: Game support requests

Well, Doom 3 is actually a zip file, so you should already be able to open it using WInRAR or something. 

The others I will need a plugin for (or a library) to address the compression methods used. Of course, I will always include them, if I am able to find these things.
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-18T18:11:48+00:00
- Post Title: Game support requests

hi 

medal of honor (Orginal, expansions) = use zip method and open with winzip or something

but medal of honor pacific assualt use new package file (can you download mod tools for edit game)

Battlefield game use rfa package (can you download "game extractor" from [http://www.watto.org](http://www.watto.org) site)

and 

half life 2 have not package file
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-20T06:12:56+00:00
- Post Title: Game support requests

OK, here is some feedback...

- Splinter Cell (including expansions)
This game ( and all Tom Clancy Games? ) are based on the Unreal gaming engine - therefore a special plugin would need to be made in order to support this format. I believe that Mr Mouse *may* be making a plugin for the Unreal engine, but I can't confirm that. Game Extractor ([http://www.watto.org/extract](http://www.watto.org/extract)) will open Unreal engine files and extract the contents from them, but I am working on an improved plugin that gives file extensions and better audio extraction - email me if you want the updated plugin.

- Doom 3
Like they all said, it is just a ZIP archive, so it should already be supported

- Half-Life 2
I have tried hard to add support for this game, but it isn't that easy. I have some partial specs for the BSP files, which I think were either maps or graphics archives, and specs for the CACHE archives - although the later would not really be needed since they get overwritten each time you load the game. I will need to look more into this game to see what I can do - but like I said it isn't a nice game to work with in terms of MexCom support.

- ALL the Battlefield games
The archive format is easy, but the files are encrypted or compressed using a proprietry method - therefore it will need a special plugin to open the archives. Game Extractor will open the archives, but won't decrypt the files. I think Dragon Unpacker will do it all properly though, so maybe try that.

- Medal of Honor (Orginal, expansions and Pacific Assault)
I can't remember the format for the original games, but it wasn't too difficult. Pacific Assult uses a different format to the previous games though, but again it isn't too hard. I think we should be able to add support for these games. Game Extractor does currently open these archives.

- Previous C&C games
Most of the C&C games encrypt their archives using a Blowfish algorithm, which is a real beast to try and implement. Not much chance of this being supported. 


So, in overview, most of these games would be kinda difficult to implement, as they have special features like compression and encryption  which makes it difficult to work with. However, we may be able to help out with some of the games.

Thanks mate.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-08-03T02:47:59+00:00
- Post Title: Game support requests

I bought Game extractor and I'm happy that it can read Unreal engine files but I can't get any of the useful files out.  All I can see when I even specify which game format I'm opening (ut2004) say .utx texture packages ALL I see are .color and .ubits.  I can't really do anything with these.  I would love to be able to extract static meshes, I know that in UT2004 the static meshes in the packages are .ASE files which are Maya/Max/Lightwave compatible.

- In response to Battlefield games, if you're trying to open Battlefield 2 files, simply copy the .zip files in root folder of each Mod  ex: Battlefield2/Mods/BF2  or Battlefield2/Mods/xpack for special forces pack.  Also, copy the Levels folder as the levels are Zip packages with all kinds of files inside.  Then you can freely extract the contents from these zip files.  

BF2 has a different file structure than most games...

Most games tend to follow a directory structure for finding types of files  like below:
Models
Materials or Textures
Sounds
Music

Battlefield does it differently, instead they have the following directory structure

Common Client (Common or shared content that exists no matter what level the game loads)

Level dependent (This means you have to look inside the level packages to find specific content that may have been for that level only)

Also, everything about that object is stored along that folder's path
For example:

\Objects_client\Weapons\Handheld\eurif_famas

This directory contains 3 folders:
Meshes, Sounds, Textures

Get the idea?

As far as 3d models or mesh data the game has 2 different formats which I haven't figured out if I can import into any 3d package yet...

.staticmesh
.mesh

The 3rd type is .collisionmesh, this is just a simple shape that does not contain any useful 3d geometry, though it is 3d geometry it's simply a block that is used for collision calculations by the game engine.
