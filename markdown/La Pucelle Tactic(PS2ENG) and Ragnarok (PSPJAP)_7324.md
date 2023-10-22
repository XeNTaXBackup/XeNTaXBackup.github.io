## Post #1
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-09-08T17:59:11+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

Hello, newbie here and i want to learn a few things but i have no idea on how to extract or unpack files.Plus i got lost in the Tutorials trying to learn.
so heres what i want to do. i want to get the scripts off the Ps2 verison and place them in the psp version. how would i go about extracting and how would i know what file to get the scripts from and ect.
## Post #2
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-15T03:07:51+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

PS2 ad PSP are built on completely separate operating systems, and it's likely that La Pucelle Tactics and LP: Ragnarok are not even compatible.

Just because the games seem the same, and are in the same series from the same company, doesn't mean they will be in any way alike in their data.

Final Fantasy 7 for the PC and FF7 for PSX, while being technically the same game, are wildly different in a few very important ways, for instance, their files are stored in different ways. The models are in a form of archive in the PC version, and as I recall, have not been even found in the PSX original disc yet.

Another example, Metal Gear Solid 2 XBox and MGS2 PS2, are very different, in fact, the graphics engines are wildly different, having had to be completely rebuilt for the Xbox port, due to the same settings looking very different between PS2 and Xbox, this information came directly from the games' creator himself in an interview.

All that aside, assuming the games were in fact compatible, what you want to do is not a simple task by any means. One thing I've learned since coming here ages I can't even remember ago, is that you'll have to be competent at file examination and do a lot of the work yourself before anyone here will be able to help you, unless you're very lucky.

Another thing I've learned is that games with a very small or very obscure fanbase, are not likely to get noticed. It's for this reason .hack, Megaman Legends 2, and several others in which I am interested in getting models from, are still largely unexplored. .hack being the more popular of them, was researched partially by TWO ENTIRE PEOPLE, one of them being me, long ago (and likely again in the future). MML2 has been looked into by me on numerous occasions, but due to my lack of experience in comparison to people like MrAdults, MarioKart64, and chroxx, I've discovered very little.

Scripts are likely compressed, archived, and encrypted, OR they may be right out in the open, and are in some proprietary bytecode format that you'll never even realize they are what you're looking for.

The sad truth of the matter is that no matter how much you love a game, it's the number of people that love it that aren't you that will affect how much help you get.

I suggest looking for a rather large community of La Pucelle fans and trying to find people in that group that has file exploration experience. I'm not saying you won't find help here, but you -probably- won't. Your goals are pretty ambitious, and you're not exuding confidence in your ability to succeed...
## Post #3
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-09-15T14:45:10+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

Thanks for the information. i was told to read this forum to learn on to file hacking.  i know its  sounds simple, but its hard in reality. well i have learn somewhat here but will come here for often and see if i can actually can do this
## Post #4
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-15T18:10:15+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

Good to see your drive isn't dampened.

I suggest looking at an ISO of La Pucelle Ragnarok to see if you can find any files. There's likely an archive containing game assets inside the User folder. That's how it was with Star Ocean First Departure anyway.

Once you find a file, get yourself a hex editor like Cygnus, XVI32, or whatever, and look through the data to see if you can find things like RIFF, BMP, MDL, or generally any kind of text that seems to make sense. 

Maybe you'll luck out and find something like SCR  or  RCS (representing script) but it's unlikely.

The process is similar for PS2 games, but the files are probably in a very different file format.

I certainly hope you succeed, though it may take a while. Xentax is a good place to learn, and to find some help, but you'll have to show a bit of work before anyone will be able to do much.
You have to give us a springboard into the files essentially.

Best of luck.
## Post #5
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-09-15T20:15:40+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

I been told to use an Hex editor but no one told me which one is good. well most people told me most of the archive files are in the eboot.bin. i haven't thought of checking the USDIR file. What  i found under the  USDIR folder is 
MODULE file
 ->USBPSPCM.PRX
DUMMY DATA
START_JP.LZS
SCRIPTPACK.DAT
NSAVEICON.PNG
SAVE000.PNG
SAVE001.PNG
SOUND_01_JP.DAT
SOUND_02_JP.DAT
ANMPACK.DAT
MAPPACK.DAT
BGPACK.DAT
 I have an iso of Tactics and haven't looked at it much yet. i been trying to understand hex code but haven't learned much.
As for Tactics ISO i have found
SOUND
 ->SND.PACK
SYSTEM
 ->IOPRP.280.IMG
 ->LIBSD.IRX
 ->MCMAN.IRX
 ->MCSERV.IRX
 ->MODHSYN.IRX
 ->MODMIDI.IRX
 ->NIS.IRX
 ->PADMAN.IRX
 ->SIO2MAN.IRX
 ->USBD.IRX
DATA.DAT
SECTOR.H
SLUS_208.47
SYSTEM.CNF
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-09-16T09:45:06+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

This tool extracts DATA.DAT from the ps2 version. You need SECTOR.H and DATA.DAT in the same dir as the tool. if it gives you a dll error just install vc++2010 and/or .net framework 4

[Download](http://vash.romhacking.it/index.php?sdmon=Downloads/pucelle_extractor_v1.0_by_vash.rar)

bye

[edit]If someone downloaded it, there was a little bug. Pleasr redownload it
## Post #7
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-09-16T16:59:00+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

Thanks Vash  for the extractor. it was able to get all the files inside data.dat. so what programs would i need to use to view anm??.dat,at??.tx2,bg???.km2.mi??.dat,mp?????.mpd. start.dat,script.dat,sys1.tx2 and the talk.dat.
 I have been looking in the Scriptpack.dat of the psp verison in the hex editor and found it contains more script.dat, talk_jp.dat and NIS pack and the Mappack.dat has LZS files so how would i extract the LZS files and the DAT files and extract the text if possible
## Post #8
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-09-16T17:21:15+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-09-20T17:58:30+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-09-26T04:55:50+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

You can use NISDecmp for LZS. and NISUnpack.jar for the Scriptpak.dat
You'll need to install Java to use the NISunpack one. As for the script files in "Scriptpack.dat", you'll have to find someone to unpack the script files in Scriptpak.dat to txt or whatever.

[http://www.propl.nl/javaprogs/NISUnpack.jar](http://www.propl.nl/javaprogs/NISUnpack.jar)
[http://www.propl.nl/random/NISDecmp.zip](http://www.propl.nl/random/NISDecmp.zip)
## Post #11
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-10-07T01:30:01+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

well i haven't been able to unpack the start_jp.lzs. i have tried to update my java but it stated that its the old one. also are there any thing i need to do to unpack the scriptpack.dat or do i have to find an skilled person to unpack it
## Post #12
- Username: Dudethunder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 18, 2011 6:16 am
- Post datetime: 2011-11-17T22:27:34+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

I came across this website while looking for how to do this myself, and while I have managed to get at the script (it's in scriptpack.dat and the text is apparently in SHIFT-JIS, along with all the pointers and other required instructions), I wanted to know if there was a preexisting utility to repack NISPACK files, as step one of my plan of action is to arbitrarily swap out some text and repack the ISO to see if it works. Then comes translating the menu properly.
## Post #13
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-11-21T00:08:22+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

can we join forces. i have the scripts from the PS2. so half of the work would be done or most of it.
## Post #14
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-11-21T09:22:46+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

How did you obtain them? I have almost all formats cracked but the scripts, I'd be very interested in that..
## Post #15
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-11-22T00:14:13+00:00
- Post Title: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

i didn't crack it. i viewed it on an hex editor and view it under SHIFT-JIS encoding and was able to view the Dialog,story text, items names and descriptions and ect.  i found each of this under Script.dat, Talk.dat and Start.dat of the ps2
## Post #16
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-22T00:33:59+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

It's my understanding that Ragnarok used the Granny System at lest on the PC version.
I would expect the same but with adjustments for other systems.
I'd be interested to see some extracted files.
## Post #17
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-11-22T02:54:24+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

which files would you like to see.
## Post #18
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2011-11-22T03:01:18+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

An example of anything you have extracted would be a good start.
## Post #19
- Username: Dudethunder
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 18, 2011 6:16 am
- Post datetime: 2011-11-22T06:07:13+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

Here is an example from the psp version. The text is in Shift-JIS and is interspersed with whatever they're using it to put it on the screen properly. The first text is Culotte introducing himself, probably in the opening cutscene.

[http://www.mediafire.com/download.php?320jowyi3y3q3ag](http://www.mediafire.com/download.php?320jowyi3y3q3ag)
## Post #20
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2011-11-22T17:36:15+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

The contents of this post was deleted because of possible forum rules violation.
## Post #21
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2012-02-02T22:16:40+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

Progress update. i have been able to decompress the Start_JP.LZS file into an Start_JP.Dat which showed me these files in HEX editor. also i haven't been able to use the NISUnpack.jar. i even updated my java and i haven't been able to get it to work. can any one give me tips on how to make it work. also how can i extract this files form Start_JP.dat?

anm000.dat
attach.dat
char.dat
com.dat
face.dat
kis.dat
magic.dat
mapinfo.dat
name.dat
ritem.dat
script00.dat
skill.dat
takara.dat
talk00.dat
fontB.fnt
fontB.ftd
BASE.km2
h600.km2
mgate.km2
muki.km2
effect.km2
item.txp
sys2.txp
sys3.txp
sys4.txp
sys5.txp
sys6.txp
sys7.txp
waku.txp
wbg01.txp
wbg.txp
fontB0000.tx
fontB0001.tx
panel.txp
waku2.txp
waku2bg.txp
## Post #22
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2012-02-03T17:50:58+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

after some searching i was able to find out how to unpack the scriptpack.dat and the start_jp.dat. Now what type of file is TXP and KM2, and also is it possible to open them ??? sorry if its an NOOB question
## Post #23
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2012-02-07T17:32:33+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

is there any way to repack the scriptpack.dat and recompress the Start_JP.dat back to an Start_JP.LZS????
## Post #24
- Username: Dragon'sRagnarok
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Sep 09, 2011 1:34 am
- Post datetime: 2012-02-11T19:02:53+00:00
- Post Title: Re: La Pucelle Tactic(PS2/ENG) and Ragnarok (PSP/JAP)

The contents of this post was deleted because of possible forum rules violation.
