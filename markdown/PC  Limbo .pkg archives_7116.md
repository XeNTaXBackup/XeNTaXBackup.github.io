## Post #1
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-08-04T19:39:21+00:00
- Post Title: *PC | Limbo .pkg archives

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-08-04T20:07:21+00:00
- Post Title: *PC | Limbo .pkg archives

Do you know what this archive includes?
Textures, texts, etc..?
## Post #3
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-08-04T21:06:15+00:00
- Post Title: *PC | Limbo .pkg archives

Yup. There are 2 archives/

limbo_boot and limbo_runtime

They contain everything for the game (textures, texts, models, images...).
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-04T21:41:21+00:00
- Post Title: *PC | Limbo .pkg archives

just run offzip on them then inside the extracted files is a simple to extract archive.

c:\offzip.exe -a c:\file.pkg c:\extract 0x0
## Post #5
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-08-04T22:01:37+00:00
- Post Title: *PC | Limbo .pkg archives

I do something wrong or what?

The archive is in C:\. The output folder is 'extracted'.

Sorry but i'm ultra noob
## Post #6
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-04T22:18:25+00:00
- Post Title: *PC | Limbo .pkg archives

```
entry[entryCount] entries

entry:
  uint32 nameHash // crc32 of file name
  uint32 offset // relative to end of entry table, ie, 4 + (entryCount * 12)
  uint32 size
```


Some files will have an extension ".d" which generally indicates it's compressed with zlib. ie: derived/pc/data/animation/boy/death/death.anim.d is compressed
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-04T22:30:15+00:00
- Post Title: *PC | Limbo .pkg archives

this is the command i ran

c:\offzip\offzip.exe -a c:\limbo_boot.pkg "c:\extracted" 0x0
## Post #8
- Username: Teryal5532
- Rank: beginner
- Number of posts: 27
- Joined date: Wed May 11, 2011 7:10 am
- Post datetime: 2011-08-04T23:20:19+00:00
- Post Title: *PC | Limbo .pkg archives

Okay, i extracted the files but every file is with .dat extension...   

Where i can find the textures, models and the text for the game and how i can open those .dat files?

I need help
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-05T02:57:48+00:00
- Post Title: *PC | Limbo .pkg archives

I think that's as much as offzip can do in terms of filenames lol

Though from rick's post it seems there aren't any useful filenames anyways.
## Post #10
- Username: get8p
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2011 11:24 pm
- Post datetime: 2011-08-18T17:14:13+00:00
- Post Title: *PC | Limbo .pkg archives

Heya, Ive got the same trouble, I unpacked files good, but I only got .dat files, plus to that, my target is to change a model(texture?) of protagonist in the game, so I need a way to pack it back after I edit it in some way =\
## Post #11
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-08-19T06:18:02+00:00
- Post Title: *PC | Limbo .pkg archives

Here is my code and file lists:

[http://svn.gib.me/public/limbo/trunk/](http://svn.gib.me/public/limbo/trunk/)

I have no further plans to work on LIMBO further, sorry.
## Post #12
- Username: get8p
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2011 11:24 pm
- Post datetime: 2011-08-19T09:31:42+00:00
- Post Title: *PC | Limbo .pkg archives

Guys, any chance somebody here can make an upnpack/pack tool? Cuz I dont know anything about it... 
Or perhaps somebody knows somebody who can? I guess I shouldnt say obvious things like I would b supermega grateful and incredibly happy
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T15:05:35+00:00
- Post Title: *PC | Limbo .pkg archives

From the unpacking code, it would seem pretty hard to pack it...
## Post #14
- Username: get8p
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2011 11:24 pm
- Post datetime: 2011-08-19T18:15:39+00:00
- Post Title: *PC | Limbo .pkg archives

Turns out, pkg is...[Mac OS X Installer Package](http://www.macupdate.com/app/mac/16357/unpkg), aint it?
Or its some kind of other .pkg?
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T18:31:42+00:00
- Post Title: *PC | Limbo .pkg archives

pkg is just an extension. Microsoft decided that it would be cool to associate certain extensions with certain applications, but you don't have to follow it.
## Post #16
- Username: get8p
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2011 11:24 pm
- Post datetime: 2011-08-20T08:36:12+00:00
- Post Title: Re: *PC | Limbo .pkg archives

With the help of [this unpacker from other forum](http://rghost.ru/17930891), some guy made it, I successed to extract files. But they got no extension and I cant open them.

Also, bfore that I grabbed texture files with 3D Ripper DX, which appears to be grabbed all the textues while I was playing. 
Example of a biggest texture file 9e42bb64.dds which weights around 42Mbs
[http://i.piccy.info/i5/52/33/1873352/11.jpg](http://i.piccy.info/i5/52/33/1873352/11.jpg)

So the point is, some extracted files of first unpacker has identical weight to a textures that I grabbed with 3D Ripper DX, exept I cant open them.
Mah m8 sas that  its probably a png with modificated header. So we need to know how it was modified. Can somebody help?
[Here is this 2 files](http://www.mediafire.com/download.php?5tjqwj9ud7btkdu), texture and identical unpacked file. They weight 85Mb together, but packed they weight 5Mb.
## Post #17
- Username: get8p
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Aug 18, 2011 11:24 pm
- Post datetime: 2011-09-02T21:37:07+00:00
- Post Title: Re: *PC | Limbo .pkg archives

BumP
## Post #18
- Username: GARID
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Apr 06, 2011 8:29 pm
- Post datetime: 2011-12-25T15:03:44+00:00
- Post Title: Re: *PC | Limbo .pkg archives

> Reply from get8p
>
> 
Here is this 2 files

Inside that archive one file have dds format its can be edited by gimp or DDS Converter 2.1 ( It's a image format )

U can convert it to png
[conver.JPG](https://xentaxbackup.github.io/file/4927_conver.JPG)
## Post #19
- Username: Markercreed
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 11, 2016 4:11 am
- Post datetime: 2016-01-10T20:38:15+00:00
- Post Title: Re: *PC | Limbo .pkg archives

Can you make a YouTube video in how to change texture file on limbo? 
if not can"t, can you guys upload make a how to video about Limbo pkg archives : ]
## Post #20
- Username: IT IS ME1987
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jul 12, 2018 2:34 pm
- Post datetime: 2018-07-12T06:37:31+00:00
- Post Title: Re: *PC | Limbo .pkg archives

> Reply from Rick
>
> Here is my code and file lists:

http://svn.gib.me/public/limbo/trunk/

I have no further plans to work on LIMBO further, sorry.
\\\\\how to compile that code? I have code, but I still can't unpack limbo_boot.pkg!
