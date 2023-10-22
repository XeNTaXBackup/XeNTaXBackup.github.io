## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-07T04:31:49+00:00
- Post Title: ghost recon (online) phantoms help

can someone help me with these models please?

the game runs under yeti engine the same that Ghost recon future soldier, the problem is all models looks weird (in ninja ripper and hex2obj) maybe the normal values for the mesh are in negative .

torso mesh.



maybe someone can create a 3ds max script or noesis script for import in correct form the models.

here some files

[http://www.mediafire.com/download/r41rj ... object.rar](http://www.mediafire.com/download/r41rjrsh0611qg1/Graphic+object.rar)

thanks
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-08-07T22:33:03+00:00
- Post Title: ghost recon (online) phantoms help

Same issue I've run into.  I can get a close resemblance to the shape, but there are always quite a number of verts that are all over the place.

I haven't had much time recently to get back into this, but I also haven't figured out what's causing the problem.

It would be great if someone else could maybe tell us what's going on.

--MDA
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-08-07T22:53:43+00:00
- Post Title: ghost recon (online) phantoms help

it looks like the data is not 16 byte aligned. are these files extracted properly?
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-07T23:01:08+00:00
- Post Title: ghost recon (online) phantoms help

I used the bms script from aluigi for extract the yeti.big file.
if I use ninja ripper or intel gpa the models looks in the same form

[http://aluigi.altervista.org/papers/bms/yeti_ybig.bms](http://aluigi.altervista.org/papers/bms/yeti_ybig.bms)


a guy called rarefacer has modify the max script for import ninjaripper *.rip files with normal values in negative but he lost the script

[http://th02.deviantart.net/fs70/PRE/f/2 ... 7r4rhi.jpg](http://th02.deviantart.net/fs70/PRE/f/2014/198/d/6/rarefacer_ghostreconfuturesoldier_30kdesierto__ren_by_rarefacer-d7r4rhi.jpg)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-08T10:07:06+00:00
- Post Title: ghost recon (online) phantoms help

this format will require some fiddling, I guess. This is what I got from m_GRO-COM01-Helm03_PC_00000001:



GhostRec.JPG (123.56 KiB) Viewed 608 times


The point cloud (button noPtC -> PtCld) is giving flat shapes only so the parameters I chose (or the cutting done by hex2obj) may be wrong.
("cutting" means getting the maximum vertex value and subtracting its half value from all vertices of an axis, iirc)

edit: well, this is a strange proceeding, admitted, but it worked fine on Ratchet&Clank models, iirc.
But it should be replaced by some decent short conversion (view my next post).

The vertex count (4625) and the face index count (12441) might be stored at
0x002B: 11 12 00 00 and 0x0033: 99 30 00 00
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-09T06:31:05+00:00
- Post Title: ghost recon (online) phantoms help

You should ask this guy what he did with "vertex" values! They are shorts, which from what I've seen should be divided /32767.0 and something more I guess.

EDIT: Can you provide few NinjaRipper files/rips?
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-08-18T12:26:10+00:00
- Post Title: ghost recon (online) phantoms help

Luxox18, have you tried to rip models Tom Clancy's Ghost Recon: Future Soldier? If yes, are they corrupted in the same way as from Ghost Recon Online?
## Post #8
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2014-08-18T16:16:38+00:00
- Post Title: ghost recon (online) phantoms help

sorry!

here are some models from Ghost Recon Future Soldier ripped with ninjaripper

[http://www.mediafire.com/download/fm3u4 ... ripper.rar](http://www.mediafire.com/download/fm3u4pv63orpnlt/GRFS_ninjaripper.rar)

Edit----

here are models from ghost recon online ripped with ninjaripper


[http://www.mediafire.com/download/z5kdo ... online.rar](http://www.mediafire.com/download/z5kdo38aaa6vadm/Ghost_Recononline.rar)
## Post #9
- Username: Rarefacer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 14, 2014 8:26 am
- Post datetime: 2014-09-15T01:36:26+00:00
- Post Title: ghost recon (online) phantoms help

Hi guys! I founded this forum and my experience with Ghost Recon: Future Soldier, was dissapointing in the extractions process. I'm not a script, codding or development expert, but triying and triying, i founded a way, not to extract entirely models, but yes to reconstruct them (only character models).

I had a little modified Ninja Ripper script (i lost it a year ago formatting my pc), result of that triying and triying with the extracted Ninja ripper files, but it just could return to a manipulable shape the "squizzed" meshes.



Then, i start a rebuilding process manually working purely with 3ds Max skills.









And so...  This is my final results





(Photo album link [https://www.facebook.com/media/set/?set ... 260&type=3](https://www.facebook.com/media/set/?set=a.690904467629932.1073741829.223361234384260&type=3))


I just need a better resolution textures, Ninja Ripper can't extract high resolutions, just the two main characters (Jhon Kozak and Ramírez from the initial mission) have highg resolution, and have a decent look. the other models have low resolutions like 512x512 and 1024x512 for full body and looks ugly in detail.

Luxox, i go to work in the online models published in the mf link, and please, continue extractions in Ninja Ripper formats, and xentax members, maybe, exist any way to extract the full resolution textures from yeti files? i tried with bms without results.
## Post #10
- Username: jakkrit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 14, 2014 8:08 pm
- Post datetime: 2014-11-13T08:44:37+00:00
- Post Title: ghost recon (online) phantoms help

How can I rip some models with ninjaripper?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-13T11:48:15+00:00
- Post Title: ghost recon (online) phantoms help

after having had a look at this again I'm not sure whether we have mesh data here.
For me it looks more like some kind of cubemapped uv data (just a wild guess):



head_uvmap_maybe.jpg (221.56 KiB) Viewed 437 times
## Post #12
- Username: jakkrit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 14, 2014 8:08 pm
- Post datetime: 2014-11-14T02:43:23+00:00
- Post Title: ghost recon (online) phantoms help

Yeah, I got like this too when I use hex2obj or ninjaripper.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-15T02:53:11+00:00
- Post Title: ghost recon (online) phantoms help

On another try I got this:



m_GRO-COM01_PC_0.JPG (247.87 KiB) Viewed 414 times



How to expand these flattened coordinates?
For me it seems to be impossible without additional data - but where to search for it?

In the VB block of 32 bytes or in another file? - Guess: no.

The only possibility I could think of is that they use some kind of compression.
But I don't have a clue how to decompress the 2D vertices (on each plane of the cube) into 3D ones.

So a maybe solution is burried in Rarefacer's lost script, whatever.

Perhaps someone gets an idea from viewing the wavefront obj data:
[http://www.uploadmb.com/dw.php?id=1416019776](http://www.uploadmb.com/dw.php?id=1416019776)
## Post #14
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-03-21T15:44:46+00:00
- Post Title: ghost recon (online) phantoms help

Some good news, I figured out Ghost Recon Phantoms and Future Soldier meshes   I'm going to post script soon, just will do some tests to bring weights right
## Post #15
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2015-03-21T20:12:47+00:00
- Post Title: ghost recon (online) phantoms help

thanks for this and for your effort
## Post #16
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-03-22T14:25:29+00:00
- Post Title: Re: ghost recon (online) phantoms help

No problem   Soon I'll release maxscript which will import NinjaRipper rips (.rip) with weights for YETI engine games (tested Ghost Recon Series and Lost: Via Domus)
## Post #17
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2015-03-25T16:07:18+00:00
- Post Title: Re: ghost recon (online) phantoms help

If you release your script, you'll be my biggest reverse engineer hero!!!  
I tried literally hundreds of ways to RE grp, without any luck.
## Post #18
- Username: jakkrit
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 14, 2014 8:08 pm
- Post datetime: 2015-04-08T09:19:03+00:00
- Post Title: Re: ghost recon (online) phantoms help

Anything update? I really want to try to rip models from the ghost recon phantom.
## Post #19
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-04-26T17:37:43+00:00
- Post Title: Re: ghost recon (online) phantoms help

Okay guys, sorry for such huge delay! Here's script to import NinjaRipper .rips of YETI Engine game (Ghost Recon: Phantoms/Lost: Via Domus/ Beawulf). You will get game rig - just bones misplaced, but skin weights will be original. I will post script for original in-game files of Ghost Recon:Phantoms soon

P.S. Report bugs and problems
[Yeti_Ninja_Import.7z](https://xentaxbackup.github.io/file/9111_Yeti_Ninja_Import.7z)
## Post #20
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2015-04-27T06:16:01+00:00
- Post Title: Re: ghost recon (online) phantoms help

> Reply from zaramot
>
> Okay guys, sorry for such huge delay! Here's script to import NinjaRipper .rips of YETI Engine game (Ghost Recon: Phantoms/Lost: Via Domus/ Beawulf). You will get game rig - just bones misplaced, but skin weights will be original. I will post script for original in-game files of Ghost Recon:Phantoms soon

P.S. Report bugs and problemsHi zaramot My friend. The script is very good, thanks for your great work
[BaiduShurufa_2015-4-27_14-13-27.jpg](https://xentaxbackup.github.io/file/9113_BaiduShurufa_2015-4-27_14-13-27.jpg)
## Post #21
- Username: kapul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 12, 2015 1:42 am
- Post datetime: 2015-09-13T09:49:00+00:00
- Post Title: Re: ghost recon (online) phantoms help

Hi guys

Little question here. How you run Ghost recon online from Ninja Ripper? I mean, every time I try to run the main .exe from ninja ripper, it says "please, run Ghost Recon from Ubi Launcher" and when I load from there, it says "run from steam" and... common       

So, what's the correct way to run this?
## Post #22
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-09-13T19:10:35+00:00
- Post Title: Re: ghost recon (online) phantoms help

You should use wrapper not injector method (buy choosing wrapper and clicking "run" button NinjaRipper will copy d3d9.dll into folder with .exe, it's important to have this file in the same place as .exe of GR:Phantoms) then just run game from launcher

Also, you can get here my script to import models directly into 3d max without NinjaRipper, textures are headerless .dds files
[http://zenhax.com/viewtopic.php?f=5&t=1332](http://zenhax.com/viewtopic.php?f=5&t=1332)
## Post #23
- Username: kapul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 12, 2015 1:42 am
- Post datetime: 2015-09-14T15:59:37+00:00
- Post Title: Re: ghost recon (online) phantoms help

Okay, now it's working fine, thanks @zaramot for the help and for the script.
## Post #24
- Username: kapul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 12, 2015 1:42 am
- Post datetime: 2015-12-08T19:53:00+00:00
- Post Title: Re: ghost recon (online) phantoms help

Hi all again

I have another little question. I've extracted the hole yeti.big file from the Ghost Recon Phantoms, and it seems to have pretty cool thins inside. Nevermind, files are extracted as ".File" and the crappy way of renaming the file as ".obj" or something, doesn't work.

Has anyone an idea or suggestion of what can I do?

Thanks in advance
## Post #25
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-30T02:18:53+00:00
- Post Title: Re: ghost recon (online) phantoms help

zaramot, so the solution to the square mesh problem was the vw part right?

```
	getPos = ftell f + 32
	vx = ((readshort f))	
	vy = ((readshort f))
	vz = ((readshort f))
	vw = ((readshort f))	
	tu = ((readshort f))
	tv = ((readshort f)*-1)	
	append vertArray ([(vx * vw), (-vy * vw), (vz * vw)] / 655350) --??	
	append UV_array ([tu, tv, 0] / 1024)	--??
)

```

also, what is the reason behind dividing by 655350 and 1024?
## Post #26
- Username: kapul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 12, 2015 1:42 am
- Post datetime: 2017-11-24T14:50:29+00:00
- Post Title: Re: ghost recon (online) phantoms help

Hi there!

Is there any chance to get the links alive? The original ones are deleted by mediafire.

Thanks in advance
