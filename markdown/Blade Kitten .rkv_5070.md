## Post #1
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-09-22T19:32:02+00:00
- Post Title: Blade Kitten .rkv

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: jooped
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jun 25, 2010 3:30 am
- Post datetime: 2010-09-23T03:46:57+00:00
- Post Title: Blade Kitten .rkv

you might be able to use something from this thread since it is the same file type and both games were made by the same company

[viewtopic.php?f=10&t=3921&p=33720&hilit=rkv#p33720](http://forum.xentax.com/viewtopic.php?f=10&t=3921&p=33720&hilit=rkv#p33720)
## Post #3
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-09-23T14:08:49+00:00
- Post Title: Blade Kitten .rkv

Hah, thanks. It works. But now I have a lot of .min.bin , .ast.ads , .mktx.tex files and so on.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-24T16:22:34+00:00
- Post Title: Blade Kitten .rkv

That program does not appear to extract the files correctly.
It is just extracting war files not decompressing them.
this is a bms script that does the same thing only much faster.

```
getdstring name1 0x40
get null long
get tableoff long
get null2 long
get files long
goto tableoff
#comtype lzss
for i = 0 < files
getdstring name 0x40
get unk01 long
get unk02 long
get unk03 long
get offset long
get unk05 long
get size long
get zsize long
get unk08 long
log name offset zsize
next i
```

anyone know what this text compression is?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-09-25T18:52:19+00:00
- Post Title: Blade Kitten .rkv

the compression for the type 2 (the only one I have found and also the only one accepted in the executable of the games that use this format) is LZF, script here:
[http://aluigi.org/papers/bms/rkv.bms](http://aluigi.org/papers/bms/rkv.bms)

seems that this RKV format is used for Windows Live games, so it could be used even more in future
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-25T20:11:18+00:00
- Post Title: Blade Kitten .rkv

Great job 
any chance on updating the tools soon to support greater then 4GB files?
its good to see you back.
## Post #7
- Username: Nexus Elite ns
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2009 1:11 am
- Post datetime: 2010-09-25T20:41:46+00:00
- Post Title: Blade Kitten .rkv

> Reply from chrrox
>
> Great job 
any chance on updating the tools soon to support greater then 4GB files?
its good to see you back.
Well the full archive file for this game is only 700mb actually.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-26T01:15:29+00:00
- Post Title: Blade Kitten .rkv

I have the game file i mean his tools in general.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-09-26T09:35:46+00:00
- Post Title: Blade Kitten .rkv

in quickbms it's needed to enable a thing in the source code (a #define) and recompiling it to allow the usage of 64bit numbers obviously with all the downsides of slowness and possibly lack of compatibility in some things.

anyway quickbms will remain ever at 32bit because there is absolutely no need ot using 64bit numbers and the 99,9% of the files in the world is ever under 4 gigabytes (both archives and files contained in them)
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-26T18:14:34+00:00
- Post Title: Blade Kitten .rkv

this model format is so chaotic its crazy.
[http://img693.imageshack.us/img693/7884/catgirld.png](http://img693.imageshack.us/img693/7884/catgirld.png)
## Post #11
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2010-10-02T15:33:25+00:00
- Post Title: Blade Kitten .rkv

Thanks for the bms script aluigi.

Now when the second installment of blade kitten comes out, I can get the rip done much quicker.
## Post #12
- Username: LoneTiger
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Sep 16, 2010 3:51 am
- Post datetime: 2010-10-24T19:30:45+00:00
- Post Title: Blade Kitten .rkv

Since it is Blade Kitten related...

The .fsb files are the Music/Voices/SFX

But what are the:
.mktx.tex
.uiss.raw
.mkmesh.mdg
.ent.bin
.min.bin
.ast.ads

What I am looking for is the game textures and the game artwork (Which I missed to see at the end of the game ) I assume .mkmesh is the 3d model mesh itself but not sure about that.

Thanks in advance.
LT.
## Post #13
- Username: lapdragon
- Rank: beginner
- Number of posts: 30
- Joined date: Tue Dec 28, 2010 4:24 am
- Post datetime: 2010-12-27T21:50:31+00:00
- Post Title: Blade Kitten .rkv

Well, your mktx are the textures - but I haven't done any poking at them yet to see what's been done to them.
