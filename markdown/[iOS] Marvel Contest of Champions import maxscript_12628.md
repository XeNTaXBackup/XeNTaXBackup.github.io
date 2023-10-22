## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-20T12:59:24+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Hi guys! Here's maxscript to import [iOS] Marvel Contest of Champions with bones and weights (3ds max 2009-2014) 
Tool to extract files [https://www.sendspace.com/file/sbh6ik](https://www.sendspace.com/file/sbh6ik)
Tool for textures [http://community.imgtec.com/developers/ ... vrtextool/](http://community.imgtec.com/developers/powervr/tools/pvrtextool/)

NOTE: Models are in Class43_meshes folder, skeletons are in Class90_avatar. Skeletons doesn't have right names, so just open them in notepad to see whom they belong



P.S. Report bugs


[Marvel_Contest_Of_Champions.7z](https://xentaxbackup.github.io/file/8786_Marvel_Contest_Of_Champions.7z)
## Post #2
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-02-20T20:31:08+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Found it... I've extracted the files via winzip how do I extract the files in characters.assetbundle to get the .bin files?
## Post #3
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-02-21T09:34:02+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

How did you get the Class43_meshes and Class90_avatar folders? I am not able to get any folders like that :/
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-21T10:13:51+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Disunity tool   As I see there's not much people familiar with Unity3d extraction, so I'll write a short instruction and upload tool with GUI here. Just wait a moment guys!
## Post #5
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-02-21T13:00:10+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Oh, thanks I was able to get it working  Although there may be some missing skeleton files.. im checking to see if they are spread throughout the character files, but some characters may share skeletons.
## Post #6
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-02-21T13:10:37+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

I'm not getting any subfolders when I use disunity on the .assets files.
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-21T13:15:48+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Glad to heard you get it working  Skeletons are in Class90 folder, and yes you're right some characters using same skeleton - like winter soldier using captain's america skeleton lol
Also, here's updated script for more models support (static/props/weapons)

Artworkplay, do you have .obb file? It's just a zip file, inside it you'll find character folder with characters.assetbundle. Use DisUnity on it, and you'll have bunch of Class** folders   You need Class43 and Class90 folders in order to get characters

P.S. Don't forget to choose extract-raw option in DisUnity!
[Marvel_Contest_Of_Champions.7z](https://xentaxbackup.github.io/file/8727_Marvel_Contest_Of_Champions.7z)
## Post #8
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-02-21T13:37:29+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Got as far as extracting the characters.assetbundle but there is no Class43 or Class90 directories... only Class221
## Post #9
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-02-21T13:38:54+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

use Disunity [https://github.com/ata4/disunity/releases](https://github.com/ata4/disunity/releases)

```
disunity extract-raw C:\MARVEL_Contest_of_Champions\marvelbattle.app\Data\characters\characters.assetbundle
```


note:folder name there no space
## Post #10
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-02-21T15:14:30+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Figured out the directories are Avatar and Mesh... script working beautifully so far.
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-21T16:57:08+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Cool! Looks very nice    Also, I'm working on other Unity3d game called Marvel Avengers: Initiative [https://www.youtube.com/watch?v=nSmZQIedqtc](https://www.youtube.com/watch?v=nSmZQIedqtc)
## Post #12
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-02-21T17:05:01+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Ooh nice.
Zaramot would you have any idea which skeleton Ms Marvel and Captain Marvel would use? I've tried numerous skeletons, and they all cause them to have bad weights, neither of them have skeletons of their own.
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-21T19:55:50+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

For Ms Marvel fits -217467467.bin skeleton, but it's definitely not female one. Hmm, I'll try to find right for you
## Post #14
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-02-21T19:58:16+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Yea I saw that too and it was male, but its pretty much the correct one as the cloth is the same...
## Post #15
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-21T20:15:14+00:00
- Post Title: [iOS] Marvel Contest of Champions import maxscript

Yeah, you're right almost the same - just male lol For Captain Marvel -684400645.bin skeleton would fit nicely
## Post #16
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-02-22T09:32:20+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Here's MsMarvel model with correct skeleton and weights (.fbx file+.dds textures) in case someone will need her  
[https://www.sendspace.com/file/j0rqi7](https://www.sendspace.com/file/j0rqi7)
## Post #17
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2015-02-22T09:49:43+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Thank you!
## Post #18
- Username: kovalevich007
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 12, 2010 11:03 pm
- Post datetime: 2015-03-04T13:23:03+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Is it possible to import from other games having the model and the skeleton?
[https://yadi.sk/d/ncVa6vgCf2xtB](https://yadi.sk/d/ncVa6vgCf2xtB)

I imported only the skeleton
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-04T15:05:26+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

000003_bin.JPG (185 KiB) Viewed 240 times


should not be too hard to change the max script with these parameters?
(face indices count and vertex count are one less; too lazy to change/reupload the pic)
## Post #20
- Username: kovalevich007
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 12, 2010 11:03 pm
- Post datetime: 2015-03-04T16:09:25+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

The issue has been resolved, thank you
## Post #21
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-03-04T16:30:19+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Kovalevich007, what is the name of the game? It looks like my script works fine for this game, just need to scale model a bit and rotate it to look at front
## Post #22
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2015-05-20T21:08:17+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Here's MsMarvel model with correct skeleton and weights (.fbx file+.dds textures) in case someone will need her


Hi zaramot! How, i can extract this models with bones and skinning?
## Post #23
- Username: ekardon
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Jun 27, 2015 10:32 am
- Post datetime: 2015-06-27T02:36:38+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Script works fine thanks.  However I got the following error with the attached file.

[-1790435810.zip](https://xentaxbackup.github.io/file/9353_-1790435810.zip)
## Post #24
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2015-10-19T13:41:36+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Can Anybody help... i am getting this error...
P.S I have checked that bone and mesh match...
And sorry if i am bumping this topic....
## Post #25
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-19T13:58:44+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from SSingh511
>
> Can Anybody help... i am getting this error...
P.S I have checked that bone and mesh match...
And sorry if i am bumping this topic....script may use techniques wich are not supported by your version of 3ds max - my guess.
## Post #26
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2015-10-19T14:56:41+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Thanks... i got it....but is there any way to make it compatible (3ds max 9 not 2009) or any other alternative...?
## Post #27
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-19T16:49:24+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from SSingh511
>
> Thanks... i got it....but is there any way to make it compatible (3ds max 9 not 2009) or any other alternative...?I'm sure that scriptwrighter will not willing to make his script compatible with outdated software. but I understand and feel sorry for you.
## Post #28
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2015-10-20T04:17:53+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from Tosyk
>
> SSingh511 wrote:Thanks... i got it....but is there any way to make it compatible (3ds max 9 not 2009) or any other alternative...?I'm sure that scriptwrighter will not willing to make his script compatible with outdated software. but I understand and feel sorry for you.

Maybe now its time for me to update my Max to maybe 10 or 11......
## Post #29
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2015-10-23T09:58:09+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from SSingh511
>
> Tosyk wrote:SSingh511 wrote:Thanks... i got it....but is there any way to make it compatible (3ds max 9 not 2009) or any other alternative...?I'm sure that scriptwrighter will not willing to make his script compatible with outdated software. but I understand and feel sorry for you.

Maybe now its time for me to update my Max to maybe 10 or 11......

Thanks to Zaramot for this script!!!
Upgrading was useful i updated it to 12....
I extracted this Hulkbuster modrel with bones....if anyone needs it..... ;
[http://ssingh511.deviantart.com/art/HUL ... -567780105](http://ssingh511.deviantart.com/art/HULKBUSTER-rigged-567780105)

Is there any way to load Anims also....?
## Post #30
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2015-10-23T10:26:15+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from SSingh511
>
> Is there any way to load Anims also....?hardly
## Post #31
- Username: MarvelousPotato
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2015 11:17 am
- Post datetime: 2015-11-21T14:24:40+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

hey, does anyone know about cyclops's skeleton?
## Post #32
- Username: Juseight
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 09, 2016 2:02 pm
- Post datetime: 2016-05-09T07:15:26+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Hi guys!

May 5 of 2016, I try to do this guide for get that render of that new heroes only for fun and created avatar and wallpapers ...but i cant get correctly to files.

First you need disunity_v0.3.4 to get files. Class41_meshes and Class90_avatar don't exits with names. This are the files:



> 

When i used the command disunity bundle-extract I got this:

> 

Of course with this i can see a least the texture in the program "PowerVRSDKSetup-2016_R1.2". But I can do anymore  I need help guys i try with 3ds Max 2016 and Maya 2016 with RealFlow and didn't get results . I spend a lot of time in this.     

hope you guys can help me. I see videos in youtube ([https://www.youtube.com/watch?v=GG-BKSCFDCQ](https://www.youtube.com/watch?v=GG-BKSCFDCQ)) but they don't help anyone      

Greetings!
## Post #33
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2016-10-09T03:27:42+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

In this new update of CoC, assetbundles file have been encrypted or secured in such a way that disunity only display file name but doesn't extract it and unity studio shows finished loading 0 files... so need a new script or something for this new type of encryption....
## Post #34
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2016-10-09T17:02:37+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from SSingh511
>
> In this new update of CoC, assetbundles file have been encrypted or secured in such a way that disunity only display file name but doesn't extract it and unity studio shows finished loading 0 files... so need a new script or something for this new type of encryption....
Yes. We need the new scripte please!
## Post #35
- Username: Raphael Splinterson
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jul 31, 2016 12:36 pm
- Post datetime: 2016-11-02T00:04:50+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from SSingh511
>
> In this new update of CoC, assetbundles file have been encrypted or secured in such a way that disunity only display file name but doesn't extract it and unity studio shows finished loading 0 files... so need a new script or something for this new type of encryption....
Same problem. Help me please.
## Post #36
- Username: MarvelousPotato
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Nov 14, 2015 11:17 am
- Post datetime: 2016-11-28T00:11:18+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Disunity is no longer working in any way, and I am at a loss.
[image.jpeg](https://xentaxbackup.github.io/file/11960_image.jpeg)
## Post #37
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2016-11-28T02:00:13+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Maybe you can ask at this disunity thread [viewtopic.php?f=33&t=10739&start=30](http://forum.xentax.com/viewtopic.php?f=33&t=10739&start=30)
## Post #38
- Username: sandex7978
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 19, 2017 3:44 pm
- Post datetime: 2017-09-01T06:39:29+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

I am able to extract the 43/mesh & 90/avatar files but not with disunity and I don't understand how I am to associate them with the .bin files for the maxscript. Any ideas?
## Post #39
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2017-09-01T08:28:17+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Open the .bin file in notepad and check the header (or somewhere around there), you will see the name of the character it belongs to.
## Post #40
- Username: sandex7978
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 19, 2017 3:44 pm
- Post datetime: 2017-09-01T16:55:03+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from TRDaz
>
> Open the .bin file in notepad and check the header (or somewhere around there), you will see the name of the character it belongs to.

No, what I mean is that I have already exported the 43 to the character named .mesh and the 90 to the character named .avatar. What I don't know what to do from there is use the maxscript importer which is looking for a .bin file not a .mesh or .avatar
## Post #41
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-09-02T02:58:49+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from sandex7978
>
> TRDaz wrote:Open the .bin file in notepad and check the header (or somewhere around there), you will see the name of the character it belongs to.

No, what I mean is that I have already exported the 43 to the character named .mesh and the 90 to the character named .avatar. What I don't know what to do from there is use the maxscript importer which is looking for a .bin file not a .mesh or .avatar
Use the latest Unity Studio and save yourself the time since it exports most character models of the latest versions of the app.
## Post #42
- Username: sandex7978
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 19, 2017 3:44 pm
- Post datetime: 2017-09-03T15:11:41+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from artworkplay
>
> sandex7978 wrote:TRDaz wrote:Open the .bin file in notepad and check the header (or somewhere around there), you will see the name of the character it belongs to.

No, what I mean is that I have already exported the 43 to the character named .mesh and the 90 to the character named .avatar. What I don't know what to do from there is use the maxscript importer which is looking for a .bin file not a .mesh or .avatar
Use the latest Unity Studio and save yourself the time since it exports most character models of the latest versions of the app.

Awww, CMON... This tool is WAY TOO dope!!! Thanks so much, Im in fn heaven at moment!!!
## Post #43
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-09-05T15:54:02+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

Any progress? I need the new cool characters.
## Post #44
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-09-06T04:30:28+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from logansan25
>
> Any progress? I need the new cool characters.
Try new version of Unity Studio :
[https://ci.appveyor.com/project/Perfare ... /artifacts](https://ci.appveyor.com/project/Perfare/unitystudio/branch/master/artifacts)
 Tutorial (just in case) :
[https://www.vg-resource.com/thread-3114 ... #pid634545](https://www.vg-resource.com/thread-31141-post-634545.html#pid634545)
## Post #45
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-09-17T13:56:00+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from Rutabaga
>
> logansan25 wrote:Any progress? I need the new cool characters.
Try new version of Unity Studio :
https://ci.appveyor.com/project/Perfare ... /artifacts
 Tutorial (just in case) :
https://www.vg-resource.com/thread-3114 ... #pid634545

Thanks a lot. I had tried, however when i try import file fbx in 3D Max dont happen nothing.
## Post #46
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-09-19T05:50:42+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from logansan25
>
> 
Thanks a lot. I had tried, however when i try import file fbx in 3D Max dont happen nothing.

Try converting that fbx in noesis as either fbx again or any other format with bone+weight support then import in Max. Either that or you need to update your 3DSMax.
## Post #47
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-09-22T12:13:38+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from artworkplay
>
> logansan25 wrote:
Thanks a lot. I had tried, however when i try import file fbx in 3D Max dont happen nothing.

Try converting that fbx in noesis as either fbx again or any other format with bone+weight support then import in Max. Either that or you need to update your 3DSMax.
[http://prntscr.com/gobdrg](http://prntscr.com/gobdrg)

Help me please!
## Post #48
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2017-09-23T22:30:57+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from logansan25
>
> Help me please!
Don't use DisUnity. Unity Studio  (the latest one linked to this thread) is the only tool you'll need since it can open assetbundle files already.

EDIT I checked that hulk_red_odr file from the latest COC version I had (v15). Unity Studio works, its just that particular file doesn't have any meshes at all. Best guess would be to try looking for older COC versions.

EDIT EDIT sorry I take it back. It has the Red Hulk mesh in Hulk_Red and not Hulk_Red_LW
## Post #49
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2017-09-25T22:07:43+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

> Reply from artworkplay
>
> logansan25 wrote:Help me please!
Don't use DisUnity. Unity Studio  (the latest one linked to this thread) is the only tool you'll need since it can open assetbundle files already.

EDIT I checked that hulk_red_odr file from the latest COC version I had (v15). Unity Studio works, its just that particular file doesn't have any meshes at all. Best guess would be to try looking for older COC versions.

EDIT EDIT sorry I take it back. It has the Red Hulk mesh in Hulk_Red and not Hulk_Red_LW
Very thanks mate! I got it. The mesh is in .obj and fine.
Now i only have problem with the textures. That don´t export. Why?
## Post #50
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2018-03-01T13:27:06+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

How to export the files in this new version from game?
## Post #51
- Username: SSingh511
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Sep 23, 2015 12:52 pm
- Post datetime: 2020-10-08T04:18:47+00:00
- Post Title: Re: [iOS] Marvel Contest of Champions import maxscript

New updates of game doesn't allow login and downloading files on emulators, which makes it impossible to get data files, if anyone has access to those files, please respond
