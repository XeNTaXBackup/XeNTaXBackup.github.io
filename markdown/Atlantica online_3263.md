## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-12-21T02:28:53+00:00
- Post Title: Atlantica online

Can anyone de swizzle the atlantica online dds files?
This would be a great find as the models of this game are in .nif format and can be viewed with nifskope or imported into max.


Edit* I just saw pixle's thread so if this is not allowed please delete this.
[BOOTS140_MAP00.rar](https://xentaxbackup.github.io/file/1790_BOOTS140_MAP00.rar)
## Post #2
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2008-12-21T21:46:51+00:00
- Post Title: Atlantica online

I'm no good at programming, but I was able to convert most of these using a batchfile I wrote for use with Hex Editor XVI32.

Basically, I just replaced the first part of each atlantica .dds file with the first bytes of a corresponding size/shape normal .dds file and I can open them all ok.  

For example here's the Hex Editor XVI32 script I used for the 512x512 342 kb .dds files:

ADR 0
OVERWRITE 44 44 53 20 7C 00 00 00 07 10 02 00 00 02 00 00 00 02 00 00 00 00 00 00 00 00 00 00 0A 00 00 00

some of the mip maps are messed up, but that's easy to fix.

I copied all the monster dds files into a directory on my c drive called c:\atex\monster, then created a windows batchfile to convert all the dds files:

XVI32.exe JAGWARRIORF3_MAP01.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANF3_MAP01.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANF3_MAP00.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANF2_MAP01.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANF2_MAP00.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANF1_MAP01.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANF1_MAP00.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANB1_MAP01.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe REMODELMANB1_MAP00.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe LEECHESF2_MAP00.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe LEECHESF1_MAP01.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc
XVI32.exe RATMANF2_MAP00.dds /S=C:\ATEX\MONSTER\SCRIPT342.xsc, etc, etc,

Sigh, this is why I should've stayed in school and learned to write a proper program
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2008-12-22T01:15:31+00:00
- Post Title: Atlantica online

cool thanks a million trying it now 
edit it works perfectly 

I will attempt to build a converter in vb it should not be to hard.
## Post #4
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2008-12-22T03:55:26+00:00
- Post Title: Atlantica online

Cool, glad we're getting somewhere. Here are all the hex codes I used in the scripts and the file sizes I used them on. Some of the smaller ones are giving me trouble, I think it has something to do with wether the image is square or rectangular, and like I said the mip maps are messed up on some of them, at least in nifskope, but I'd say at least 90% of them are working:

1366kb .dds 1024x1024
44 44 53 20 7C 00 00 00 07 10 02 00 00 04 00 00 00 04 00 00 00 00 00 00 00 00 00 00 0B 00 00 00


613kb .dds  512x512
44 44 53 20 7C 00 00 00 07 10 0A 00 00 04 00 00 00 02 00 00 00 00 08 00 00 00 00 00 0B 00 00 00


513kb .dds
44 44 53 20 7C 00 00 00 07 10 08 00 00 02 00 00 00 08 00 00 00 00 08 00 00 00 00 00 00 00 00 00


342kb
44 44 53 20 7C 00 00 00 07 10 02 00 00 02 00 00 00 02 00 00 00 00 00 00 00 00 00 00 0A 00 00 00


257kb
44 44 53 20 7C 00 00 00 07 10 08 00 00 02 00 00 00 02 00 00 00 00 04 00 00 00 00 00 00 00 00 00


171kb
44 44 53 20 7C 00 00 00 07 10 0A 00 00 02 00 00 00 02 00 00 00 00 02 00 00 00 00 00 0A 00 00 00


129kb
44 44 53 20 7C 00 00 00 07 10 08 00 80 00 00 00 00 04 00 00 00 00 02 00 00 00 00 00 00 00 00 00


86kb
44 44 53 20 7C 00 00 00 07 10 02 00 00 01 00 00 00 01 00 00 00 00 00 00 00 00 00 00 09 00 00 00


65kb
44 44 53 20 7C 00 00 00 07 10 08 00 00 01 00 00 00 01 00 00 00 00 01 00 00 00 00 00 00 00 00 00


43kb
44 44 53 20 7C 00 00 00 07 10 0A 00 80 00 00 00 00 01 00 00 00 80 00 00 00 00 00 00 09 00 00 00


33kb
44 44 53 20 7C 00 00 00 07 10 08 00 80 00 00 00 00 01 00 00 00 80 00 00 00 00 00 00 00 00 00 00


22kb
44 44 53 20 7C 00 00 00 07 10 0A 00 80 00 00 00 80 00 00 00 00 40 00 00 00 00 00 00 08 00 00 00


11kb
44 44 53 20 7C 00 00 00 07 10 0A 00 80 00 00 00 80 00 00 00 00 20 00 00 00 00 00 00 08 00 00 00


6kb
44 44 53 20 7C 00 00 00 07 10 0A 00 40 00 00 00 40 00 00 00 00 10 00 00 00 00 00 00 07 00 00 00


3kb
44 44 53 20 7C 00 00 00 07 10 0A 00 80 00 00 00 20 00 00 00 00 08 00 00 00 00 00 00 08 00 00 00
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-22T07:37:20+00:00
- Post Title: Atlantica online

i totally missed this thread, i thought i searched for it before posting  im on a holiday break but want to try it out later on
## Post #6
- Username: citizenx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 03, 2009 8:51 am
- Post datetime: 2009-02-04T19:23:41+00:00
- Post Title: Atlantica online

I am trying to work with the .nif's and .dds' in this game but seem to be running into issues when trying to render. What I was hoping to do was export the models to resized gif's using 3D Max. Issues seem to be that I can get the body textures but the head texture is missing (or sometimes no textures at all). Anyone have any further work on this games models? I appreciate what has already been done as it has helped me get this far.

Thank You
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-04T21:07:09+00:00
- Post Title: Atlantica online

just re apply the textures.
## Post #8
- Username: citizenx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 03, 2009 8:51 am
- Post datetime: 2009-02-05T03:06:21+00:00
- Post Title: Atlantica online

[http://atlantica.wikia.com/wiki/Forum:N ... dissection](http://atlantica.wikia.com/wiki/Forum:Ndoors_DDS_image_format_dissection)

Some good information if anyone wants to look.

Thank You
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-02-05T03:52:45+00:00
- Post Title: Atlantica online

What file are you trying to view?
if you post the file I can look at it I have extracted 99% of the files from this game with no problem.
## Post #10
- Username: citizenx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 03, 2009 8:51 am
- Post datetime: 2009-02-05T05:19:30+00:00
- Post Title: Atlantica online

I appreciate the offer chrrox, but what I am attempting to do is a bit ambitious in that I want to be able to manipulate (import to 3D Max) all the Monster / NPC "wait" animation and export them to a .gif format.

Thank You
## Post #11
- Username: Kilandor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 05, 2009 7:15 pm
- Post datetime: 2009-02-07T04:40:35+00:00
- Post Title: Atlantica online

I will very soon try to post up a tool that will autmatically convert all the DDS for you. Or, allow input maybe for a specific one.
## Post #12
- Username: citizenx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Feb 03, 2009 8:51 am
- Post datetime: 2009-02-13T21:34:24+00:00
- Post Title: Atlantica online

Kilandor, That would be great!

Thank You
## Post #13
- Username: Yorick
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 10, 2009 12:45 pm
- Post datetime: 2009-03-11T00:23:29+00:00
- Post Title: Atlantica online

I've created a Python program that will convert these .DDS files, and tested it on a copy of my game folder. Works great. Some Korean filenames made the "file has been converted" output unhappy, so now I don't output the filename for those. Feel free to teach this thing Korean though. 

It is clever enough to not touch regular DDS files or ones that have already been converted.
It also does a basic sanity check on values - doesn't mean it'll catch itself if NDOORS ever changes the encode, but it might be able to tell you "not touching that one", depending on how the encode's changed.

This will need Python 3.x, I've used 3.01.

It's pretty self-explanatory - here's the usage screen:

This program will convert Atlantica Online .dds files to regular .dds files
by de-obfuscating the header.
It will in the process overwrite the original source file. DO NOT run this
on your original game files, use a copy.

This program's options are:

ndoordds.py [-rsvh] [--recursive|silent|verbose|help] filename(s)...

-r      Recurse into subdirectories, change all .dds files found within
Use that one carefully 
[ndoordds.zip](https://xentaxbackup.github.io/file/1914_ndoordds.zip)
## Post #14
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-05-01T22:38:18+00:00
- Post Title: Atlantica online

thanks for the converting tool!
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-04T02:14:59+00:00
- Post Title: Atlantica online

if anyone needs to know how to use this script it is C:\Python30>python.exe ndoordds.py -r C:\nDoors\Atlantica
if everything is installed in its default locations.
## Post #16
- Username: Vorick
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 01, 2009 5:06 am
- Post datetime: 2009-08-01T07:34:42+00:00
- Post Title: Re: Atlantica online

Hi there,

I'm currently building a fansite for the upcoming german release of Atlantica. So I was really excited to find this thread in here. It would really help me in content creation if it worked. Sadly, for me - it doesn't. I tried the xvi-script as well as the python one and never ended up with a usable dds file which I could open in irfanview or gimp. irfanview states a decode error and gimp says "unexpected EOF". I tried numerous files, but to give an example I tried the atlantica\NMap\DeathCastle1\DeathCastle1.dds file since I am mostly interested in usable map data. Model DDS-Texture didn't work either.

I also noticed that my file sizes differed from the ones given in the xvi-script-post.

Can anyone help me out with this?

Thanks in advance,

Vorick

Edit: For easier analysis, I've uploaded my unmodified version of the DDS-File: [http://www.atlantica-mmorpg.de/temp/DeathCastle1.zip](http://www.atlantica-mmorpg.de/temp/DeathCastle1.zip)
## Post #17
- Username: Yorick
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 10, 2009 12:45 pm
- Post datetime: 2009-08-01T10:36:44+00:00
- Post Title: Re: Atlantica online

"It works here" ?

Here's what I can suggest:
- Open your converted file with WTV, The Compressonator or ddsview, see whether it displays okay there. If it does, the issue is not with the decode.
- Run ndoordds.py with the -v flag and compare to the output of my run, which created a file that was readable by WTV:

```
Header values for DeathCastle1.dds
Length: 0000007C
Flags: 000A100F
Header field at 12: 0000018E
Header field at 16: 00000200
Header field at 20: 000C7000
Header field at 24: 00000000
Header field at 28: 00000003
DeathCastle1.dds has been converted
```
## Post #18
- Username: Vorick
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 01, 2009 5:06 am
- Post datetime: 2009-08-01T12:39:32+00:00
- Post Title: Re: Atlantica online

You are right. It is working. I just wonder why both Irfanview and Gimp refused to open the files. They used to work with oder dds-images. 

Thanks for your help.
## Post #19
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-09-30T01:37:19+00:00
- Post Title: Re: Atlantica online

Sorry for the thread necromancy, but I can't get the tool to work...

Is there any way that someone could upload the converted dds textures up? I'm really curious to see how they're made up.
## Post #20
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-01-13T15:09:58+00:00
- Post Title: Re: Atlantica online

Sorry to necro, but I am unable to get the Script running (most likely, doing something wrong in the commands).

Could anyone give me a dummies outline as how to use it.
## Post #21
- Username: Yorick
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 10, 2009 12:45 pm
- Post datetime: 2010-01-13T22:38:06+00:00
- Post Title: Re: Atlantica online

> Reply from AceAngel
>
> Sorry to necro, but I am unable to get the Script running (most likely, doing something wrong in the commands).

Could anyone give me a dummies outline as how to use it.

It should be as simple as installing Python 3 and running the script from command line.

What version of Python do you have installed? And copy/paste the relevant bits from your command line window, please, so we can see the way you invoke the script and the error message you get back.

Another alternative is to say "this whole Python business is silly", take the code, and port to language-of-choice.
## Post #22
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-01-14T14:32:05+00:00
- Post Title: Re: Atlantica online

the only thing I do when doing python things is copy the python exe to the folder and make a .bat with:

sctipt.py command input output
pause

The pause can be good because the window stays and doesnt close so you see what actually happens
## Post #23
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-01-14T15:26:43+00:00
- Post Title: Re: Atlantica online

OK, well, here is what I did:

-Downloaded ndoordds.py
-Extracted to 'C:\Python30\Tools\Scripts', 'C:\Python30' and 'C:\nDoors\Atlantica\NChar3D\Texture'
-Double-Click 'Python.exe'
-Type in the CMD window: 'ndoordds.py -r C:\nDoors\Atlantica\NChar3D\Texture'

Here is what I get:

```
  File "<stdin>", line 1
    ndoordds.py -r C:\nDoors\Atlantica\NChar3D\Texture

Invalid Syntax
```


I'm pretty sure it's me, I'm doing something wrong.
## Post #24
- Username: Yorick
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 10, 2009 12:45 pm
- Post datetime: 2010-01-14T23:48:09+00:00
- Post Title: Re: Atlantica online

Yeah, you can just run the script from your windows command line. I have no idea how it would behave inside python.exe, I never tried that. If python is in your path and was allowed to bind itself to .py - which is the default install - then you can just run the script itself. If that's not the case, then "python ndoordds.py <parameters>" should do the trick.
## Post #25
- Username: Makina
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jan 10, 2013 10:06 am
- Post datetime: 2013-01-11T15:16:34+00:00
- Post Title: Re: Atlantica online

This script does not work, upload one better, Donate this forum for this script and does not work :S:S

anyone can explain?

Thanks.
## Post #26
- Username: Yorick
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Mar 10, 2009 12:45 pm
- Post datetime: 2013-01-11T23:50:15+00:00
- Post Title: Re: Atlantica online

You know, I'd love to help. But I have no idea what "does not work" is supposed to mean. A bit more information would be awesome, such as "I get this error message when I do that".

Donate the forum - you lost me, buddy.

May I also point out: It is a Python script. Which means it isn't just useful, it's also source code. Nifty! If your "doesn't work" isn't just caused by "I don't know how to run a Python script" (please do Google), then having the source right there does allow you to tweak it to be just what you always wanted it to be, rather than the ungainly, ugly thing you received in the forum.
## Post #27
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-14T11:30:18+00:00
- Post Title: Re: Atlantica online

[http://www.progamercity.net/game-files/ ... 014-a.html](http://www.progamercity.net/game-files/10965-release-nexon-atlantica-ndt-file-unpacker-packer-all-3-version-formats-2014-a.html)

Anyone can repost here this converter ?
