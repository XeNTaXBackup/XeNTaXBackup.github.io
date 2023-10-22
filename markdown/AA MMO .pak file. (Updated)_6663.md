## Post #1
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-05-22T15:49:47+00:00
- Post Title: AA MMO .pak file. (Updated)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-05-23T16:14:40+00:00
- Post Title: AA MMO .pak file. (Updated)

Not sure who changed the thread title, a mod obviously, but I was trying to keep the name of the game obfuscated to avoid this thread being spammed by a million Russian hackers with hardons for piracy, which is what happened with the last thread I made for a popular MMO (Aion). Kinda wanted to avoid that happening again, since it didn't help the game.
## Post #3
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-05-31T04:16:09+00:00
- Post Title: AA MMO .pak file. (Updated)

Bump and update!

I've figured out what files are involved in opening game.pak and mounting it by examining the patcher client.

The patcher calls xlcommon.dll to do all the operations necessary to modify the files inside game.pak, so I've put the two files together into a single .zip for you to download and examine.
## Post #4
- Username: iaw
- Rank: advanced
- Number of posts: 52
- Joined date: Wed Oct 21, 2009 7:52 pm
- Post datetime: 2011-05-31T06:13:37+00:00
- Post Title: AA MMO .pak file. (Updated)

Example: [http://cdn.archeage.com/50374to50399.pak](http://cdn.archeage.com/50374to50399.pak)
## Post #5
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-06-01T17:54:22+00:00
- Post Title: AA MMO .pak file. (Updated)

Yeah, that's a much more manageable file, lol. Thanks for finding it.
## Post #6
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-06-10T18:19:41+00:00
- Post Title: AA MMO .pak file. (Updated)

Long overdue bump.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T10:04:17+00:00
- Post Title: AA MMO .pak file. (Updated)

the content of the pak files can be easily taken with any ripper, they are just dlls, dds and so on.

the index informations are probably those available at the end (-0x200 and the block before) but they are encrypted probably with aes so no key no party.

anyway there is no reason to waste time finding a key for a job that can be done by a ripper
## Post #8
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-06-13T03:22:07+00:00
- Post Title: AA MMO .pak file. (Updated)

So something like Jaeder Naub, huh? Yeah, it seems to work for the DDS files in the smaller PAK. I'm having trouble opening the larger PAK file, though. Pretty sure it's for the obvious reason: the file's too damn big. :L

EDIT: The specific error I get is "run time error 52" which I see at least one other person has also run into here (and got no response in the troubleshooting forum).

Sent an email to Strobe, maybe he can help. Thanks for your help, aluigi. 

EDIT: JN can take 1gb files so far. Checking 2, then 4.

EDIT: It seems that 4gb is the limit for JN. 

3gb files give an interesting error too (but doesn't crash the program): "Information: Length Error. (bug!)" That's literally what it says.
## Post #9
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-06-15T04:33:19+00:00
- Post Title: AA MMO .pak file. (Updated)

Hmm, Jaeder Naub can't extract FSB sound files. That's what I was really hoping for.
## Post #10
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-06-15T04:54:08+00:00
- Post Title: AA MMO .pak file. (Updated)

Just use [http://hcs64.com/files/fsbii07.zip](http://hcs64.com/files/fsbii07.zip) to extract embedded FSB files assuming they are as is in the file (not compressed)
## Post #11
- Username: Mark
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 27, 2007 12:57 pm
- Post datetime: 2011-06-15T18:22:01+00:00
- Post Title: AA MMO .pak file. (Updated)

> Reply from Apollo
>
> Just use http://hcs64.com/files/fsbii07.zip to extract embedded FSB files assuming they are as is in the file (not compressed)
Thanks for the tip, trying it now.

It doesn't seem to want to open the large file, but I'm testing it on split versions of file (2gb each) and it seems to not be complaining. Taking it's time, though.

I'm thinking about just doing everything the hard way if this doesn't work, via hex editing.

Last night I tried the brute-force FSB-finding quickbms script that aluigi made for a different game and it didn't seem to work (churned out some really huge files that caused fsbext to crash when I tried to convert them).

EDIT: fsbii doesn't seem to like large files at all. "error getting file size: No error" Oh well. Thanks for the help anyhow. 

EDIT2: I've got a couple files out by manually copy and pasting hex values. This isn't too difficult, the hardest part is finding the music I want between all the other random sound effects.

Thanks for your help, guys. The quickBMS script would have worked if there weren't false positives way early in the file. aluigi, is there a way to make the script less error-prone? Is there any way I can implement a maximum file size check or something?

I'm considering programming a tool to rip FSBs now that I went through all this trouble to do things myself.
## Post #12
- Username: xyzwrgba
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jun 21, 2011 8:39 pm
- Post datetime: 2011-06-25T12:55:24+00:00
- Post Title: AA MMO .pak file. (Updated)

bump 
Anyone have any success with this yet?
## Post #13
- Username: ABANDONGFX
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 20, 2010 9:38 pm
- Post datetime: 2011-08-20T14:41:38+00:00
- Post Title: AA MMO .pak file. (Updated)

HI THERE ! ANyone help please to Find CRYENGINE formats Inside that ARCHEAGE 24gb 50374to50374.pak please ...

I downloaded and tried with JaederNaub2.2.4g File ripper But it crashes the program ...

I tryied on the Littler file and i just finded .Raw and .bmp files ...


ANyone knows any other file ripper than Jaeder ? ...

Or ALUIGI PLEASE CAn yu Make a QUICKBMS Script for this !? Please ...


I'm Looking for the CRYENGINE 2 Files inside this pack 

But i need them with proper directories ...


This is the Files list that This .pack Should have inside And i'm looking for !

THANK YU SO MUCH !

 

List of File formats inside cryengine encoded .pack
.cry
.cfg
.txt
.lyr
.lua
.tif
.pak
.xml
.Settings
.animevents
.tod
.cal
.chr
.caf
.mp2
.ogg
.cga
.cgf
.ag
.anm
.bai
.ccc
.cba
.cdf
.cfi
.cfib
.cfx
.cfxb
.cnd
.ctc
.dat
.dba
.dds
.dlg
.dsw
.ent
.ext
.fdp
.fev
.fsb
.fsq
.fxcb
.fxl
.gfx
.h
.joy
.lmg
.lng
.lua
.lut
.lyr
.mtl
.node
.sfd
.tga
.vcproj
.veg
.vspscc
.vssscc
.grp
.bmp
.sln
.xml
.swf
.tmd
## Post #14
- Username: xennasolo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 16, 2015 6:54 pm
- Post datetime: 2015-11-16T11:03:59+00:00
- Post Title: AA MMO .pak file. (Updated)

beware on the extensions list! ccc may refer to cryptic trojan !!! [http://nabzsoftware.com/types-of-threats/ccc-file](http://nabzsoftware.com/types-of-threats/ccc-file)
## Post #15
- Username: Prometeus))
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 30, 2016 3:55 am
- Post datetime: 2016-11-29T20:01:17+00:00
- Post Title: AA MMO .pak file. (Updated)

Guys! thanks for the links and useful information
