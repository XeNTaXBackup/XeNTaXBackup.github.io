## Post #1
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2011-06-03T11:19:44+00:00
- Post Title: Duke Nukem Forever .dat

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-06-03T12:33:37+00:00
- Post Title: Duke Nukem Forever .dat

you should include the (name)dir.dat file too, if there is one.  i'm still downloading it, but it seems these contain filenames and possibly locations.
## Post #3
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-06-03T16:22:22+00:00
- Post Title: Duke Nukem Forever .dat

But there is no "skelsDirectory.dat".

For example in folder X:\GAMEDIR\Textures\Compiled is for "CompTextures000.dat...CompTextures004.dat" is a DIRFILE with name "TextureDirectory.dat"

Here is the "CompTextures004.dat" (it´s the smallest one) [http://www.sendspace.com/file/xvk339](http://www.sendspace.com/file/xvk339)

And the "TextureDirectory.dat"
[TextureDirectory.zip](https://xentaxbackup.github.io/file/4288_TextureDirectory.zip)
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-06-03T18:21:11+00:00
- Post Title: Duke Nukem Forever .dat

> Reply from ZerOHearth
>
> But there is no "skelsDirectory.dat".

For example in folder X:\GAMEDIR\Textures\Compiled is for "CompTextures000.dat...CompTextures004.dat" is a DIRFILE with name "TextureDirectory.dat"

Here is the "CompTextures004.dat" (it´s the smallest one) http://www.sendspace.com/file/xvk339

And the "TextureDirectory.dat"

The format does seem to reference certain groups of files in certain instances, i've no clue how to code so i cant extract it myself, but it seems that the dir/directory files can corespond to one or multiple files, for instance in the first couple lines of texturedirectory.dat:

```
RIDT........../...CompTextures000......CompTextures001......CompTextures002......CompTextures003......CompTextures004.
```

indicates to me it has the filenames /offests for all five (000, 001, 002, 003, and 004). Im not 100% sure, but the offests (or what ever the incremental amouts are) seem to come first, then half to 2/3rds through the file, the filenames start.

edit: some theories, the 1mb skels.dat doesnt seem large enough to contain all the skeletons it references, it could be a directory, but its possible it has atleast a bit of data (orientation or something i havent a clue, its too big for a standard directory, yet to small to hold all the skeletons named in it), and meshes.dat has the meshes with full skeletons. this seems somewhat like what would happen if they had based the duke forever engine off ut2.5, which i remember reading somewhere in like 2008. since the game even seems to have unreal type structure (system folder with core.int, (comparable to a core.u in a system folder in ut2/2.5))  it seems like they just monkeyed around with the basic unreal code over the years.
## Post #5
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-06-03T18:28:41+00:00
- Post Title: Duke Nukem Forever .dat

There is something more for you.

In the file "skels.dat" you can find strings like:
```
characters/aigen_retarget/ai_a_ready_shotgun_crouch_2_stand
characters/aigen_retarget/ai_a_neutral_machinegun_pain_stand_short_left
characters/aigen_retarget/a_scr_map02_graves
characters/aigen_retarget/ai_a_neutral_pistol_stand_idle_01
characters/aigen_retarget/a_scr_map01_talkshow_audience_idle02
characters/aigen_retarget/a_scr_map00_edf_whiteboard_man_with_the_plan
characters/aigen_retarget/ai_a_ready_pistol_pain_stand_big_left
characters/aigen_retarget/aigen_a_normal_idle02
characters/aigen_retarget/a_scr_map01_rant
characters/aigen_retarget/ai_a_ready_fists_stand_strafeleft
characters/aigen_retarget/ai_a_ready_shotgun_pain_crouch_big
characters/aigen_retarget/wounded_scientist_idle_pain2
characters/aigen_retarget/ai_a_neutral_machinegun_stand_turn90left
characters/aigen_retarget/ai_a_ready_machinegun_stand_popoutleft_start
characters/aigen_retarget/ainorm_a_normal_ohyougotme
characters/aigen_retarget/ai_a_ready_rpg_crouch_turn90right
characters/aigen_retarget/ai_a_ready_machinegun_crouch_reload
characters/aigen_retarget/a_scr_map00_edf_whiteboard_gameplan
characters/aigen_retarget/ai_a_ready_shotgun_crouch_popoutright_stop
characters/aigen_retarget/ai_a_ready_fists_stand_idle
characters/aigen_retarget/ai_a_ready_pistol_jump_takeoff
characters/aigen_retarget/ai_a_ready_fists_stand_turn180right
characters/aigen_retarget/aigen_a_shotgun_scared_idle
characters/aigen_retarget/a_edf_map08c_wasp_crash_hit_right_reactions
```

But no extension.
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-06-03T21:43:06+00:00
- Post Title: Duke Nukem Forever .dat

The .dat files are in many different formats. Noesis is currently extracting skeletons, meshes, anims, defs, textures, and the MegaPackage.dat from system. Will be in the next release.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-03T22:31:40+00:00
- Post Title: Duke Nukem Forever .dat

What about the sounds.dat too?
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-06-04T01:34:54+00:00
- Post Title: Duke Nukem Forever .dat

Rename sounds.dat to sounds.mp3 and most players will play the whole thing as a continuous stream.
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-04T02:57:29+00:00
- Post Title: Duke Nukem Forever .dat

umm no what i want is to extract the individual mp3's according tot here file table in the dir DAT file.
## Post #10
- Username: ZerOHearth
- Rank: advanced
- Number of posts: 62
- Joined date: Sun Jun 13, 2010 5:32 pm
- Post datetime: 2011-06-04T10:18:40+00:00
- Post Title: Duke Nukem Forever .dat

> Reply from MrAdults
>
> [..]Noesis is currently extracting skeletons, meshes, anims, defs, textures, and the MegaPackage.dat from system. Will be in the next release.That´s nice to know.   

THUMBS UP
## Post #11
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-06-05T00:44:22+00:00
- Post Title: Duke Nukem Forever .dat

New Noesis is up that supports extracting 5 variants of .dat, I think static meshes are the only content type I haven't tackled. I also gave Duke a very special shirt. [http://www.richwhitehouse.com/index.php?postid=65](http://www.richwhitehouse.com/index.php?postid=65)
## Post #12
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-06-05T00:55:42+00:00
- Post Title: Duke Nukem Forever .dat

isnt duke done in unreal engine ? heard it was. a modified unreal 2.5 engine or something
If thats the case give it a day or so after the full game has come out and gildors unreal viewer should be able to unpack them.
## Post #13
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-06-05T00:58:30+00:00
- Post Title: Duke Nukem Forever .dat

Extensively mutilated UE2.5 has been my impression, yes.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-05T01:01:10+00:00
- Post Title: Duke Nukem Forever .dat

gildor wont support it. 
its so heavily modified.
someone would have to give him a very good donation for him to even look at it.
## Post #15
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-06-05T12:44:40+00:00
- Post Title: Duke Nukem Forever .dat

Weights+skeleton working. I'm going to start working on the exporter and testing model repacking tomorrow.
## Post #16
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-13T17:02:53+00:00
- Post Title: Re: Duke Nukem Forever .dat

hello is there any chance to help me repack texts please ? It should not be hard i guess 

Example:

```
http://loadfiles.in/qahiv2k7xvtg/XBOX_Coalesced_int.bin
```


Thank you
## Post #17
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-06-17T11:34:02+00:00
- Post Title: Re: Duke Nukem Forever .dat

Apparently the full game (PC) texture file structure is different.

There is no MegaPackage.dat file. Instead there are 41 seperate .dat files in the compiled textures directory.

Noesis 3.3 is looking for MegaPackage.dat and wont open/accept any of them instead. MegaPackage.dat must be limited to the demo.  

EDIT:

I just went ahead and extracted TextureDirectory.dat. I'll figure out what goes where...
## Post #18
- Username: MrDeviance
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 27, 2008 12:05 pm
- Post datetime: 2011-06-19T06:18:24+00:00
- Post Title: Re: Duke Nukem Forever .dat

> Reply from SLIFallen
>
> Apparently the full game (PC) texture file structure is different.

There is no MegaPackage.dat file. Instead there are 41 seperate .dat files in the compiled textures directory.

Noesis 3.3 is looking for MegaPackage.dat and wont open/accept any of them instead. MegaPackage.dat must be limited to the demo.  

EDIT:

I just went ahead and extracted TextureDirectory.dat. I'll figure out what goes where...
The full game also has the MegaPackage.dat what are you talking about?
Go look for it, it's in the exact same folder it was in the demo.
Steam\steamapps\common\duke nukem forever\System is the location where you can find the MegaPackage.dat in the full game just like in the demo.
## Post #19
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2011-06-19T10:46:05+00:00
- Post Title: Re: Duke Nukem Forever .dat

> Reply from MrDeviance
>
> SLIFallen wrote:Apparently the full game (PC) texture file structure is different.

There is no MegaPackage.dat file. Instead there are 41 seperate .dat files in the compiled textures directory.

Noesis 3.3 is looking for MegaPackage.dat and wont open/accept any of them instead. MegaPackage.dat must be limited to the demo.  

EDIT:

I just went ahead and extracted TextureDirectory.dat. I'll figure out what goes where...
The full game also has the MegaPackage.dat what are you talking about?
Go look for it, it's in the exact same folder it was in the demo.
Steam\steamapps\common\duke nukem forever\System is the location where you can find the MegaPackage.dat in the full game just like in the demo.

Ok, but only partially my screwup. Thought texture stuff was in the texture folder bit I *DID* do a full file search (and the drive is indexed no less) and windoze did not find it either. Oh well. Thank you.
