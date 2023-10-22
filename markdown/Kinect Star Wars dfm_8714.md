## Post #1
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-08T03:34:47+00:00
- Post Title: Kinect Star Wars dfm

Here is a noesis script to load the 3d models and the modified .tga textures.
to extract the models you need to run xbdecompress.exe (in the official xbox sdk will not be provided) on the podlzx files.
then to extract the podlzx files use this bms script. [viewtopic.php?f=13&p=70398#p70398](http://forum.xentax.com/viewtopic.php?f=13&p=70398#p70398)
then on the resulting pac files it spits out run this bms script. 

```
set MAGIC 0
Do
getdstring MAGIC 4
While MAGIC != "adoY"
getdstring MAGIC2 4
if MAGIC2 == "oMoN"
cleanexit
endif
get SIZE long
getdstring NAME 0x54
savepos OFFSET
log NAME OFFSET SIZE
math offset + size
goto offset
Padding 16
next

```


[star_wars_kinect.rar](https://xentaxbackup.github.io/file/5279_star_wars_kinect.rar)
## Post #2
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-08T05:33:25+00:00
- Post Title: Kinect Star Wars dfm

Wow, thank you very much! The scripts for Noesis work great, though some DFM models in the HVS, MR, and Vehicles folder don't load and somtimes cause Noesis to crash. I'm not sure why this is, but I know I have the latest version of Noesis.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-08T11:58:01+00:00
- Post Title: Kinect Star Wars dfm

to get those models to load all you have to do is copy them out one directory
for instance
\cinematics_pod_bespin_cinematic_hangar_bespin\vehicles\podracers\anakin_pod_cine.dfm
the reason this fails to load is it cant find the material file so just copy the entire folder
\cinematics_pod_bespin_cinematic_hangar_bespin\vehicles\podracers\
to
\cinematics_pod_bespin_cinematic_hangar_bespin\vehicles\
and then they load fine.
## Post #4
- Username: mazor
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-08T14:34:33+00:00
- Post Title: Kinect Star Wars dfm

here is a small script update so if the files are in the wrong path it wont crash it just won't load the external files.

[fmt_star_wars_kinect_dfm.rar](https://xentaxbackup.github.io/file/5282_fmt_star_wars_kinect_dfm.rar)
## Post #5
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2012-04-11T14:17:23+00:00
- Post Title: Kinect Star Wars dfm

I have some problem with xbdecompress.
I have to use like his?
xbdecompress file.podlzx out.podlzx
## Post #6
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-11T17:54:22+00:00
- Post Title: Kinect Star Wars dfm

> Reply from grotesque
>
> I have some problem with xbdecompress.
I have to use like his?
xbdecompress file.podlzx out.podlzx

That's correct.

The weights aren't working correctly or it's just me?
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-11T19:32:27+00:00
- Post Title: Kinect Star Wars dfm

i dint have any issues you would have to tell me the file.
## Post #8
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-11T20:48:51+00:00
- Post Title: Kinect Star Wars dfm

> Reply from chrrox
>
> i dint have any issues you would have to tell me the file.
I'm not at home atm so I can't check but I'll be there soon. I'll check it then.


EDIT: The ones I tested have the same problem, exported as .fbx/.psk

It's the togruta_female in the dance directory
## Post #9
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-12T03:41:00+00:00
- Post Title: Kinect Star Wars dfm

Although your script update fixed the issue with files not finding the proper materials, there still seems to be an issue with a number of models that causes Noesis to crash for another reason I can't understand. Some of these models include:

R2D2.dfm 
tie_fighter.dfm 
droid_enforcer_big.dfm
gasgano_pod_rampage.dfm
mars_guo_pod_rampage.dfm
Delta_7b_Cinema.dfm
b2_droid.dfm

Is anyone else having this problem with these models?
## Post #10
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-04-12T12:38:58+00:00
- Post Title: Kinect Star Wars dfm

Out of curiosity, do the TEX files in Art provide anything. I noticed that there seem to be model textures there. But the model packs themselves have those packaged tga's too.

I guess I'm a wee bit lost. But in which of the pk2s are the dancers? I seem to overall have very few of the DFM's


EDIT

Was probably a bug with BMS
## Post #11
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2012-04-12T17:42:51+00:00
- Post Title: Kinect Star Wars dfm

Same weights problem here with slave Leia (not only in that part of model):
## Post #12
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2012-04-12T21:42:48+00:00
- Post Title: Kinect Star Wars dfm

> Reply from chrrox
>
> the problem is in the stupid format itself I need to fix the vertex weights because the developers were lazy when they made the exporter for star wars. I should have a fix soon.

Thanks for your work!
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-04-12T21:55:44+00:00
- Post Title: Kinect Star Wars dfm

[viewtopic.php?f=28&t=1270](http://forum.xentax.com/viewtopic.php?f=28&t=1270) Please review the new forum rules.
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-13T01:25:35+00:00
- Post Title: Kinect Star Wars dfm

actually the models seem fine you just cant move the twist bones.
## Post #15
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-04-14T01:55:44+00:00
- Post Title: Kinect Star Wars dfm

very sorry if i missed something but i have been trying to extract the podlzx do need to run xbdecompress or is there a bms script to extract them?
## Post #16
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-14T02:12:39+00:00
- Post Title: Re: Kinect Star Wars dfm

both use xbe decompress first then the bls script that works on the pod files.
## Post #17
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-04-14T02:39:29+00:00
- Post Title: Re: Kinect Star Wars dfm

ok well i used xbedecompress.exe and it ask me to overwrite yes/no/all and i click yes and it just deletes them but i was able to back them up before i did it so what do i do? and which is bls script?
## Post #18
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-14T03:16:25+00:00
- Post Title: Re: Kinect Star Wars dfm

> Reply from JakeGreen
>
> ok well i used xbedecompress.exe and it ask me to overwrite yes/no/all and i click yes and it just deletes them but i was able to back them up before i did it so what do i do? and which is bls script?
give a new name to the decompressed file, like this:
xbdecompress file1.podlzx  file1decompressed.podlzx
He meant bms script, the one in the first post.
## Post #19
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-04-14T03:16:45+00:00
- Post Title: Re: Kinect Star Wars dfm

> Reply from junk angel
>
> Out of curiosity, do the TEX files in Art provide anything. I noticed that there seem to be model textures there.
You can change the extension to *.tga and open them with Noesis.
## Post #20
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-04-14T04:07:45+00:00
- Post Title: Re: Kinect Star Wars dfm

> Reply from rexil
>
> JakeGreen wrote:ok well i used xbedecompress.exe and it ask me to overwrite yes/no/all and i click yes and it just deletes them but i was able to back them up before i did it so what do i do? and which is bls script?
give a new name to the decompressed file, like this:
xbdecompress file1.podlzx  file1decompressed.podlzx
He meant bms script, the one in the first post.

i was able to get the pkg files out but they are 1kb is that suppose to be right? and if they are right now do i get the dfm files and textures out of them
## Post #21
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-04-18T00:48:35+00:00
- Post Title: Re: Kinect Star Wars dfm

Heh, makes me want to dust off Episode I Racer and see if we can decrypt its .dat format. HD remakes
## Post #22
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2012-07-07T00:29:18+00:00
- Post Title: Re: Kinect Star Wars dfm

Sorry to bump this but for some reason my texture files look scrambled 
I thought I could just piece it together but the texture also looks incomplete
I decompressed the file with SDK and rand the bms script on it, changed the tex to tga not sure what the problem is.
## Post #23
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-07-07T01:45:06+00:00
- Post Title: Re: Kinect Star Wars dfm

It looks like the image dimensions are somehow screwed up (510x511), they're usually a power of two. That image should probably be 1024x1024.
## Post #24
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-07-07T01:52:35+00:00
- Post Title: Re: Kinect Star Wars dfm

noesis auto converts the textures i am not sure why you are loading them outside of noesis?
## Post #25
- Username: leonkennedy4011
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Sep 21, 2010 8:44 pm
- Post datetime: 2012-07-07T05:23:20+00:00
- Post Title: Re: Kinect Star Wars dfm

Noesis didnt auto convert them for me when I exported the mesh so I changed the extension, maybe I have something turned off.

edit: Im sorry I actually extracted the things wrong, I think I must have deleted a folder by mistake the first time, I re-extracted the files and got it to work fine
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-07-07T21:14:28+00:00
- Post Title: Re: Kinect Star Wars dfm

I don't think you need to mess with *.tex textures in the Art folder. 
There should be proper versions of those textures elsewhere in the files with the *.tga extension by default.
If you're trying to get the Leia in slave outfit just go here and load the dfm file:
XB2PKG\dance\leia_slave.dfm
The proper textures will export along with the character during export of the model.



XB2PKG\droids\b2_droid.dfm crashes Noesis when trying to open it.
## Post #27
- Username: Imogene
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 15, 2012 11:43 am
- Post datetime: 2012-07-09T05:56:12+00:00
- Post Title: Re: Kinect Star Wars dfm

I was just wondering if someone could send me the Leia models and textures? Preferably as .obj. I don't actually have the game, so I can't extract them myself, but I'd appreciate it if someone could do it for me?
## Post #28
- Username: luke9511
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Jul 01, 2012 6:48 am
- Post datetime: 2014-04-17T06:49:03+00:00
- Post Title: Re: Kinect Star Wars dfm

EDIT nvm found it
## Post #29
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2014-04-17T19:56:05+00:00
- Post Title: Re: Kinect Star Wars dfm

> Reply from AceWell
>
> 
XB2PKG\droids\b2_droid.dfm crashes Noesis when trying to open it.

Do any of you guys think you could re-look at the plugin to noesis and fix that cause i'm really wanting that models.
## Post #30
- Username: Slim Offset
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 11, 2018 8:33 pm
- Post datetime: 2018-03-27T21:48:48+00:00
- Post Title: Re: Kinect Star Wars dfm

Does anyone have informations about .ani files ?

I'm trying to export animation of anakin_pod_cine.dfm but i can't do it.

[](https://www.noelshack.com/2018-13-2-1522187030-noesis-anakin.png)

There is a folder with many .ani files but i'm not able to link .dfm and .ani in Noesis.

Wrong path after extraction ?
## Post #31
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2018-09-14T17:01:51+00:00
- Post Title: Re: Kinect Star Wars dfm

Toy Story Mania uses the exact same format, but it doesn't load anything. Is there a difference or am I missing a step?



[https://puu.sh/BuXlj.zip](https://puu.sh/BuXlj.zip)
## Post #32
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-09-14T18:04:01+00:00
- Post Title: Re: Kinect Star Wars dfm

This script was made for 360 big endian format.
Your file you posted is little endian.
It is a different format they changed a lot of things in this version.
## Post #33
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2018-09-14T21:46:45+00:00
- Post Title: Re: Kinect Star Wars dfm

> Reply from chrrox
>
> This script was made for 360 big endian format.
Your file you posted is little endian.
It is a different format they changed a lot of things in this version.
Is it like a completely different format or is there a small change to the script that'll fix it?
## Post #34
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2018-09-28T05:50:47+00:00
- Post Title: Re: Kinect Star Wars dfm

Chrrox , can you update your script to read .smf files ?? regards
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T07:04:58+00:00
- Post Title: Re: Kinect Star Wars dfm

Does this tool not work? [https://forum.xentax.com/viewtopic.php? ... xt#p111156](https://forum.xentax.com/viewtopic.php?f=16&t=11436&p=111156&hilit=KinectStarWars.txt#p111156)
Was made for big endian, afair.
(static models only, no chars (not tested), no anims)
## Post #36
- Username: CZW
- Rank: veteran
- Number of posts: 151
- Joined date: Thu May 05, 2005 10:15 pm
- Post datetime: 2018-09-28T16:06:13+00:00
- Post Title: Re: Kinect Star Wars dfm

> Reply from shakotay2
>
> Does this tool not work? https://forum.xentax.com/viewtopic.php? ... xt#p111156
Was made for big endian, afair.
(static models only, no chars (not tested), no anims)

Hi Shakotay 

it work fine ..
but since i have crash my previous hard drive, as i have told you …
i try to work again on them, and look on start address of each .smf files … close to 1200 files who has been never checked…

by hand it will take a loooong time .. 
i need just to relearn everything you trained me … 
may be you can help me just be identified start address of these files .. i will study the way and find myself the way .. for the next 1000 files ^^

[https://ufile.io/3px06](https://ufile.io/3px06)
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-28T16:54:00+00:00
- Post Title: Re: Kinect Star Wars dfm

Hi CZW,
I've answered in the above linked smf thread.
