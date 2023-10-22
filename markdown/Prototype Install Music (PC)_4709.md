## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-04T12:25:22+00:00
- Post Title: Prototype Install Music (PC)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-07-04T20:56:43+00:00
- Post Title: Prototype Install Music (PC)

[http://blog.gib.me/2009/06/21/prototype/#comments](http://blog.gib.me/2009/06/21/prototype/#comments)

Rick's blog comments contain useful stuff for the rcf and contained p3d files.  thats how i decoded a few files.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-04T22:45:56+00:00
- Post Title: Prototype Install Music (PC)

> Reply from Pepper
>
> http://blog.gib.me/2009/06/21/prototype/#comments

Rick's blog comments contain useful stuff for the rcf and contained p3d files.  thats how i decoded a few files.Sorry but I didn't upload files to get comments about a possible solution to another problem!
read the post
download the files
look at the filesIs that really too much to ask? Sorry for sounding harsh but it's really annoying to get off-topic answers to half of my posts...
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2010-07-05T00:29:13+00:00
- Post Title: Prototype Install Music (PC)

... the rcf files contain .p3d files, some of which are music and sound effects.  it's not off topic, the blog has tools that help you get them out and convert them.

are you saying you can't find them?  they're in frontend_sounds.p3d (within 01audio.rcf)

yeah found the exact file, frontend_surround.radp, exports fine using radp2wav, and plays fine in WMP.
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-05T02:55:55+00:00
- Post Title: Prototype Install Music (PC)

Maybe I haven't been clear enough in my first post: I want the EXACT file that plays during the pre-install routine. It's contained somewhere inside the files I've uploaded because it plays when prototype.exe is executed. How can I extract the file out of the installation files?
There are no *.rcf or *.p3d files among the files I've uploaded, so of course it's off-topic. These are the files I uploaded:

```
18.02.2009  00:46               370 AUTORUN.INI
23.04.2009  06:22         1.563.018 Data.CAB
11.04.2009  00:00            32.528 Install.exe
21.04.2009  00:39         7.175.680 Prototype.exe
25.10.2008  06:10               610 Prototype.exe.manifest
21.02.2009  00:48           216.358 Prototype.ico
22.12.2008  20:24            33.040 Uninstall.exe
```
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-07-08T15:07:27+00:00
- Post Title: Prototype Install Music (PC)

I can't help you more than that you will probably need to extract the files to get other sets of files to extract to get the music.

The .cab is an archive, containing more archives that contain the music 

So you must install the game to first the the files from the cab or maybe you can just open the cab and find the right audio archive and extract just that.

Logic?
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-08T15:50:05+00:00
- Post Title: Prototype Install Music (PC)

I'm only searching a way to extract only this particular cab file that's inside the installation folder! Am I writing this cryptic?
Installing the game won't help because the file is included in the installation folder and won't be installed!
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-17T14:03:37+00:00
- Post Title: Prototype Install Music (PC)

Ok, found out how to get hands on that file. When running the setup, a file named "~swd1.dat" is placed in the temporary folder. Rename it to *.swf and open with SWF Decompiler to get the music.mp3. I hope you know now what I meant.
I wonder why nobody could give me that info... Well, never mind, will try around more next time.
