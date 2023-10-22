## Post #1
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2007-07-12T15:20:20+00:00
- Post Title: Transformers *.DAT

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-12T17:38:05+00:00
- Post Title: Transformers *.DAT

Pretty simple format. Directory at the end of the file.
But I have no time to fully investigate it.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-12T20:26:35+00:00
- Post Title: Transformers *.DAT

The second uint32 is the size of the tail section. 

At the tail section there are a number of tables:

1. Resource offset and size table 
    The resources are padded into blocks of 256 bytes, the offset is in blocks
2. String pointer table
    Points to the filenames in the next table, there's however a little more than meets the eye to this table. Needs some investigation. 
3. String table 
    all the folder names and filenames
4. Unknown 
    compressed? encrypted? junk? other?
## Post #4
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-12T22:09:57+00:00
- Post Title: Transformers *.DAT

Mr.Mouse said true but last table seems encrypted, when ill get a bit of free time ill write unpacker.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-13T06:46:43+00:00
- Post Title: Transformers *.DAT

hehe. 

By the way, INFINITY/KORNET check your PM.
## Post #6
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-13T09:37:07+00:00
- Post Title: Transformers *.DAT

thx Mr.Mouse  

2 itg - I waiting your unpacker
## Post #7
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-16T06:27:34+00:00
- Post Title: Transformers *.DAT

4. - hash table ( size = Files count * 4 ) some CRCs of file names, game searches for that hash in table and then know file number in the first table.

Also i have found that some files are compressed with LZ2K algorithm, which is possible to rip  File is splitted to 16kb blocks where each block compressed with that LZ2K algo.
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-16T09:07:40+00:00
- Post Title: Transformers *.DAT

LZ2K? Never heard
## Post #9
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-16T13:24:27+00:00
- Post Title: Transformers *.DAT

> Reply from Rheini
>
> LZ2K? Never heard

Ye me too, some LZ modification I assume, googled for it and found nothing related with this compression algorithm.

Header:

```
DWORD: Unpacked size ( 0x4000 - for transformers )
DWORD: Packed size

```
## Post #10
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-07-16T17:35:52+00:00
- Post Title: Transformers *.DAT

Seems to be LZW based.
## Post #11
- Username: CVROY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 30, 2007 11:17 pm
- Post datetime: 2007-07-30T19:13:48+00:00
- Post Title: Transformers *.DAT

I too am trying to extract the content from this game. Using multiex, I cannot seem to get any of the DAT file types to work with the transformer DAT files.

Is there a way to extract the content from the files posted in the first post?
## Post #12
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-30T19:45:04+00:00
- Post Title: Transformers *.DAT

> Reply from CVROY
>
> I too am trying to extract the content from this game. Using multiex, I cannot seem to get any of the DAT file types to work with the transformer DAT files.

Is there a way to extract the content from the files posted in the first post?

Yes it is, I worked on it, haven't enough of time atm :/
Thing is, need to figure out hashing algorithm and this LZ2K compression, this will take a while...
## Post #13
- Username: CVROY
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 30, 2007 11:17 pm
- Post datetime: 2007-07-30T20:01:09+00:00
- Post Title: Transformers *.DAT

OKEE 

Thanks for the update, appreciate it. I don't know anything about programming other than making mods for Unreal Tournament 2004. If you need any files from me for the transformers game, let me know.
## Post #14
- Username: itg
- Rank: beginner
- Number of posts: 31
- Joined date: Sat May 12, 2007 10:11 pm
- Post datetime: 2007-07-30T20:19:08+00:00
- Post Title: Transformers *.DAT

> Reply from CVROY
>
> OKEE 

Thanks for the update, appreciate it. I don't know anything about programming other than making mods for Unreal Tournament 2004. If you need any files from me for the transformers game, let me know.

Hehe, no need I have the game, thanks anyway.

UT2004 FTW
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-07-30T21:35:50+00:00
- Post Title: Transformers *.DAT

One problem with UT2K4 is that there is only a player handler that assigns the model and it makes adding stuff a bit more difficult and adding player classes.
## Post #16
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2007-07-30T23:03:27+00:00
- Post Title: 

itg - We waiting your tool for work DAT file
## Post #17
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2007-11-27T23:28:42+00:00
- Post Title: 

Just wanted to point out that LEGO Star Wars: The Complete Saga (also made by Traveler's Tales) uses the same .dat archives.  They're huge though  - they're two different archives, one for the prequels, one for the old trilogy.  They have all the same attributes as ya'll have described.  So I'd really like to see support for this archive too.
## Post #18
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-12-17T07:42:56+00:00
- Post Title: 

I'm so lost. lol  Perhaps I'll go read a book on C++ or C# for games programming lol.
## Post #19
- Username: cookiecutter
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 21, 2007 4:08 pm
- Post datetime: 2008-01-04T15:17:40+00:00
- Post Title: 

> Reply from itg
>
> 
Header:
Code: Select allDWORD: LZ2K
DWORD: Unpacked size ( 0x4000 - for transformers )
DWORD: Packed size

could someone tell me how this info was found?
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-17T16:42:24+00:00
- Post Title: 

although the topic is old this type of archives and compression is continued to be used in the games developed by Traveller's Tales like the LEGO series.
the update is that I have been able to dump (so no source code) the [lz2k decompression function](http://aluigi.org/papers/unlz2k.h) and I have implemented it natively in quickbms.
## Post #21
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2009-10-17T18:29:57+00:00
- Post Title: 

Awesome, thanks!
## Post #22
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-20T13:11:44+00:00
- Post Title: 

and that's it:
[http://aluigi.org/papers/bms/ttgames.bms](http://aluigi.org/papers/bms/ttgames.bms)
