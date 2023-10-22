## Post #1
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-09-03T21:55:16+00:00
- Post Title: Manhunt mls/ifp

The PS2 version has ini files, which do change the game functions, but whenever the iso is rebuilt, it never boots up.

The PC version doesn't have any ini files, and I assume it just uses the mls scripts for all functions. There was originally Wire that was supposed to be used on Piggsy. The icon, and the animation for the execution still exists in the ifp file. The animations can be swapped in the ENTTDATA of the PS2 version, but it won't boot after a rebuild. And when anything is changed in the mls, it crashes.

Here's the attic (Deliverance level) folder: [http://www.mediafire.com/folder/pb1mu7iwp7bc1/attic](http://www.mediafire.com/folder/pb1mu7iwp7bc1/attic)
## Post #2
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-09-04T21:14:14+00:00
- Post Title: Manhunt mls/ifp

I located all the ini files, they're inside the levels>global>data>Manhunt.pak file. [http://www.mediafire.com/download/736n1 ... anHunt.pak](http://www.mediafire.com/download/736n1k4qanl5f49/ManHunt.pak)
Opening the pak file with a hex editor or notepad shows the ini's in there. The ini's can make modding a lot easier. I don't know how to extract them from the pak file.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-04T22:46:03+00:00
- Post Title: Manhunt mls/ifp

Here script for PAK files.. Files seems obfuscated / xored

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "MHPK"
goto 0x8
get FILES long

for i = 0 < FILES
	getdstring NAME 260
	get SIZE long
	get OFFSET long
	get TYPE long
	get CRC32 long
	log NAME OFFSET SIZE
next i
```
## Post #4
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-09-04T22:57:25+00:00
- Post Title: Manhunt mls/ifp

Thank you for that script. The pak file is actually from the PC version. That did extract all the ini's, but when they're opened, they come out like this:

Edit: Figured out how to extract the ini's from the .pak. [http://www.mediafire.com/folder/cww1phy6jrfgx/Ramirez](http://www.mediafire.com/folder/cww1phy6jrfgx/Ramirez) But how do you repack the ini's after editing?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-05T06:18:50+00:00
- Post Title: Manhunt mls/ifp

Read section 3 in QBMS Readme.
## Post #6
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-09-06T19:52:36+00:00
- Post Title: Manhunt mls/ifp

I did repack it, but it gives this error in game:
## Post #7
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2013-09-07T00:51:05+00:00
- Post Title: Manhunt mls/ifp

> Reply from 41hc1
>
> I did repack it, but it gives this error in game:
Maybe the file you repacked is larger than the original? that normally causes tons of trouble with how files are stored.
## Post #8
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-09-08T17:05:47+00:00
- Post Title: Manhunt mls/ifp

I figured it out. I had to place all ini's in the level folder's, then replace the .pak with a blank one, then the ini's can be edited.
[http://www.youtube.com/watch?v=avJ5djSXIk8](http://www.youtube.com/watch?v=avJ5djSXIk8)

How can clumps be added to different dff files? Like taking one hunter model, and just inserting it into another dff? [http://www.mediafire.com/download/ipxmk ... delspc.dff](http://www.mediafire.com/download/ipxmk7cxc4b5d8l/modelspc.dff) 
It doesn't have to replace an existing one, because the ini can change that.

The mls files can be opened with notepad, or a hex editor, but how can they be modified? Like changing a hunter's voice without crashing?
## Post #9
- Username: Skull Kid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 22, 2015 10:34 pm
- Post datetime: 2015-08-22T14:39:33+00:00
- Post Title: Manhunt mls/ifp

Dear Ekey and 41hc1,

Would any of you please tell me how I can properly, with your script, extract the ManHunt.pak file?

Thanks in advance!
## Post #10
- Username: Skull Kid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 22, 2015 10:34 pm
- Post datetime: 2015-08-23T12:12:15+00:00
- Post Title: Manhunt mls/ifp

*BUMP* I am indeed very interested in extracting the ManHunt.pak
