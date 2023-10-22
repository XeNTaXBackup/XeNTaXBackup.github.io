## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-13T11:44:51+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

Hi guys! Here's maxscript to import [PC] Lords of the Fallen 2014 models with bones and weights (3ds max 2009-2014) if anyone interested  
BMS script by Aluigi & Ekey  to extract files [http://aluigi.altervista.org/papers/bms ... fallen.bms](http://aluigi.altervista.org/papers/bms/others/lords_of_the_fallen.bms)

P.S. This game requires some 'digging" in files, but those models are definitely worth it, IMHO. Report bugs


[LOTF_Scripts.7z](https://xentaxbackup.github.io/file/8654_LOTF_Scripts.7z)
## Post #2
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2015-02-13T18:59:18+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

thank you very much for your work!
would this also work for environmental pieces/static objects?
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-13T20:45:08+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

Well, not planned, since there's no proper way to extract files with right names for now   I bet you will have hard times with finding even character models which should be supported by my script. So, if there will be any questions with that, I will gladly answer to all of them
## Post #4
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2015-02-14T01:20:37+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

unfortunately that file doesn't seem to work.

Sample:
[https://www.dropbox.com/s/4me8jic9h4lus ... 8b.7z?dl=0](https://www.dropbox.com/s/4me8jic9h4lusyc/000000000000038b.7z?dl=0)

using 3DSMax 2012
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-02-14T02:10:52+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

Nice work, man. Unfortunately leg meshes won't import.
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-14T09:09:36+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

TheMask85, sorry was a small mistake in the script - fixed. Let me know about other not working files 

EDIT: Fixed script for some legs meshes, thanks Tosyk for files and bug report!
## Post #7
- Username: jmgg
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Sep 16, 2013 4:20 am
- Post datetime: 2015-02-14T13:52:52+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

How can I extract the .dat files?
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-14T14:09:25+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

You just need to extract .pkg files. Then you will get .dat files right? Then, you just need to identify models among this files - by opening them in any hex editor and look for line char_ or monster_/npc_ at the beginning of file or just trying to import them with script (not with word _apex first). Generally model parts are near to each other, so if you find any part - like boots others are near too. That's the only way for now - game is very well protected, so it's impossible to extract files with correct names and so on. I'm trying to create a list of models now, you must know what most of models are in common.pkg
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-02-14T14:19:45+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

Hi 
Here is a small script for less digging in searching for models.
It finds name model in dat file, creates new folder 'fmesh_files' and copy dat file as fmesh file with model name.
For importing use maxscript.
It requires Blender 249 and Python 26.
How use:
1.run blend file
2.in Blender Text Window press alt+p , select  any dat file and wait some time. 

This game use probably the same game engine as Blood Knights.
And like in Blood Knights all informations about textures, materials, meshes and models are in managers, 
in this case in "data_bin.pkg".
Unfortunately they use full names of files , not numbers or hashes.

Updated: 2015-02-15
 -  for cloth files go to new folder 'cloth_files'. No names. (try search at offset 447 )
[Blender249[LordsOfTheFallen][PC][dat][2015-02-15].zip](https://xentaxbackup.github.io/file/8674_Blender249[LordsOfTheFallen][PC][dat][2015-02-15].zip)
## Post #10
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2015-02-14T18:43:39+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

Thanks Guys!
Here's another Sample:
[https://www.dropbox.com/s/44eptqf7r4xcq ... 32.7z?dl=0](https://www.dropbox.com/s/44eptqf7r4xcqav/LOTF_Sample%232.7z?dl=0)

"char_blacksmith" still appears without leg meshes. maybe it's stored somewhere else? couldn't find them though.
"char_demon_beastmaster" and "char_boss_demon_03" won't load.

keep up the great work!
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-14T20:20:40+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

Fixed. Here's updated script. As for this blacksmith guy, I think he's some sort of a ghost - so, don't have legs (but he should have skirt, hmm strange). Maybe skirt is somewhere else? 

EDIT: Updated for Tosyk's model

EDIT: Updated script for models to use same skeleton, without creating a new one all the time
[LOTF.7z](https://xentaxbackup.github.io/file/8693_LOTF.7z)
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-02-15T00:01:16+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

found a model with broken weights.
[http://www.mediafire.com/download/83s3a8dmmxnus9p](http://www.mediafire.com/download/83s3a8dmmxnus9p)
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-02-15T14:21:27+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

> Reply from Szkaradek123
>
> Hi 
Here is a small script for less digging in searching for models.
It finds name model in dat file, creates new folder 'fmesh_files' and copy dat file as fmesh file with model name.
thanks for this, Szkaradek123. really helpfull. what about all the rest files, which your script doesn't touch, are they not meshes?
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-15T15:03:11+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

I assume there should be other type of LOTF meshes among them, it's  physics-clothing meshes like all capes, cloth, skirts of player's armor and so on. You can see them in my picture at the first post - and they should be imported with LOTF_Apex script
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-02-15T15:15:37+00:00
- Post Title: [PC] Lords of the Fallen 2014 maxscript

> Reply from zaramot
>
> I assume there should be other type of LOTF meshes among them, it's  physics-clothing meshes like all capes, cloth, skirts of player's armor and so on. You can see them in my picture at the first post - and they should be imported with LOTF_Apex scriptwait, but this is common _body mesh.
## Post #16
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-15T15:23:01+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Hmm, I mean this type of meshes. I really didn't try Szkaradek's script yet - if it handles and renames them too, then all others should be not meshes or at least levels, props, environment.
[Char__hero_cleric_03_cloth_01.7z](https://xentaxbackup.github.io/file/8673_Char__hero_cleric_03_cloth_01.7z)
## Post #17
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-02-15T15:48:34+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

What about this mesh [char_hero_cleric_01_body.fmesh](http://www.mediafire.com/download/83s3a8dmmxnus9p)?

> Reply from zaramot
>
> I really didn't try Szkaradek's script yet - if it handles and renames them toodoesn't seems so.
## Post #18
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-15T16:11:20+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Well, file you provided it's just a torso - and it's a first type (main one) of skinned meshes, but there's extra stuff for each of character outfits, it's second format type, just some parts and they are important  
Like this one - Char__hero_warrior_heavy_04_chest_cloth_01, without it character armor is incomplete. Do you agree?
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-16T11:20:17+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Here's script for not skinned meshes like weapons (swords, daggers, shields)
[LOTF_WEAPONS_STATIC.7z](https://xentaxbackup.github.io/file/8688_LOTF_WEAPONS_STATIC.7z)
## Post #20
- Username: dadobojanic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 16, 2012 7:39 pm
- Post datetime: 2015-10-21T19:38:49+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Is there any way to see what map goes to specific object. So far i did all manually by checking uv maps and set manually.
## Post #21
- Username: codenamehunk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 01, 2016 10:40 pm
- Post datetime: 2016-09-01T14:54:08+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

HI! Anyone here? I'm making the retexture of the Last Traitor armor. It's working except the skirt because I don't know how to name the texture of the skirt of that set. Help anybody? I've tried, but nо luck.
This set is char_hero_cleric_04. If someone have max, could you please to look into it...
## Post #22
- Username: Jah
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 08, 2016 2:45 am
- Post datetime: 2016-12-08T23:08:35+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Hey!

The good news: Ekey have released the new extractor for LotF (from Oct 01, 2016). Now with the correct names and without ugly 00000xxx.dat files.

The bad news: it seems that this topic is dead ...
## Post #23
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-12-16T10:27:04+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Could you provide some correctly extracted 3d files? So, I could edit existing script.
## Post #24
- Username: AinkRoin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 16, 2016 6:11 pm
- Post datetime: 2016-12-16T12:41:04+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Сan someone explain in detail how to use the script for the model in 3d max. I can`t understand =(
## Post #25
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2016-12-16T16:58:52+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

@AinkRoin:

What are you having trouble with specifically? The scripts are pretty straightforward to use.

1. First you will need to extract all of the files using the extractor from Ekey or others.
2. Put LOTF.ms, LOTF_Apex.ms, and LOTF_WEAPONS_STATIC.ms in your "C:\Program Files\Autodesk\3ds Max Design 2013\scripts" folder.
3. Open 3DS Max (i'm using 3DSMax Design 2013 x64) and go to MaxScript > Run Script.
4. Select the script you want to run:  

LOTF.ms opens skeletal meshes (.fmesh files). So far they all work for me.
LOTF_Apex.ms I think is supposed to open the cloth meshes (.apb files, I think), although it does not seem to work for me. I could just be doing it wrong.
LOTF_WEAPONS_STATIC.ms opens the weapons and some static .fmesh files. I get errors on most static meshes.

@zaramot:

Good to see you are around. Thanks for your scripts, amazing work.

- Link changed to PM per forum rules -

char_demon_heavy.fmesh is a working skeletal mesh.
char_demon_heavy_cloth_02.apb is a non working cloth mesh (I think)
prop_mummy_01_inst_001.fmesh is a working static mesh
prop_anvil.fmesh is a non-working static mesh. I get the following error on import attempt with this and a lot of other static meshes:

--Runtime error: buildTVFaces: mesh has no texture vertices - $Editable_Mesh:prop_anvil1 @ [0.000000,0.000000,0.000000]

Let me know if there's anything else that is needed.
## Post #26
- Username: Jah
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 08, 2016 2:45 am
- Post datetime: 2016-12-17T10:40:15+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Hello, @zaramot! Huge thx to you, sir))

> Reply from zardalu
>
> https://www.sendspace.com/file/lbaatd
dont work for me so just in case:
[http://dropmefiles.com/BPw57](http://dropmefiles.com/BPw57) (link will be dead after 31 december 2016)

char_hero_cleric_04_body_cloth_01 - it's seems to be a cloth, but LOTF_Apex.ms thrown an error: buildTVFaces: mesh has no texture vertices $Object001 (As Zardalu already mentioned)
chamber_anvil_column_large_base_001_inst_001 - well, that's a simple static mesh, so we just don't have any maxscript for this.
char_cleric - correct working set of 4 parts for cleric model (When importing all this parts in 3dsmax i've got 4 roots in menu. Is it ok?)
## Post #27
- Username: AinkRoin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 16, 2016 6:11 pm
- Post datetime: 2016-12-17T12:28:36+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

thanks for the help. It was possible to load a model, but was faced with another problem. How do I find the texture of it? By name it is impossible to find and close it does not lie. I took model char_hero_spell.fmesh
## Post #28
- Username: Jah
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Dec 08, 2016 2:45 am
- Post datetime: 2016-12-17T21:37:04+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

As i already mentioned (in another forum   ) there probably won't be a textures for this one. Or developers could use something like glow_fire_01 textures in common with some noise function and shader. But that armor looks like char_hero_cleric_07 without cloth, so you probably could use this one instead.
## Post #29
- Username: raiziel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 07, 2016 12:31 am
- Post datetime: 2017-01-11T18:06:50+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Hello. I have a couple of questions( 
I used QBMS script which you have posted in the first message.
The program makes some kind of action but stops and displays a message in the bottom window :
- c_structs: "xmath" "CHUNKS" "(CHUNK_OFF - 0x10) / 4"

In the end, nothing happens and no result. What am I doing wrong? I will be glad if explain like an idiot because I think I followed the instructions but the result is not received but you have it means I missed something or did wrong.

Help please. Really need these models.
## Post #30
- Username: MorgothZeONE
- Rank: advanced
- Number of posts: 51
- Joined date: Tue May 24, 2016 7:59 am
- Post datetime: 2017-01-20T20:59:06+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

I honestly would like to get some of the enemies and bosses.... I just don't know where to look for them
## Post #31
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-03-19T20:01:49+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

All cloth meshes give me an error when i'm trying to import them with Apex script.
Does it even work with max 2014?
## Post #32
- Username: georgesears
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Mar 09, 2016 10:19 pm
- Post datetime: 2017-05-21T21:18:49+00:00
- Post Title: Re: [PC] Lords of the Fallen 2014 maxscript

Zaramot, please contact me via Discord:  George_Sears #9628
