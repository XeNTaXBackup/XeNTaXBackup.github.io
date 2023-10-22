## Post #1
- Username: T0M099
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-12T18:32:11+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Shadow of the Tomb Raider - [TR11] - [PC]/b]


fmt_TR11_mesh_1_2.py - Version 1.2 - 07/11/18

Supported:
1. Meshes, UVs, Normals, Skin Weights, Skin Indices, Skeleton (*.tr11mesh)

Unsupported:
1. Auto texturing/Material parsing. (relationship is unknown)

Bigfile Unpacker:
> Download <
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-09-13T13:41:28+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

```
{
   uint32_t   dwID; //TAFS
   uint32_t   dwVersion; //5
   uint32_t   dwPartsCount;
   uint32_t   dwTotalFiles;
   uint64_t   dwUnknown;
   uint8_t    m_Platform[32]; //pcx64-w for PC
};

struct TigerEntry
{
   uint64_t   dwNameHash; // Fnv64
   uint64_t   dwLanguageID;
   uint32_t   dwSize;
   uint32_t   dwUnknown1; // ???
   uint32_t   dwUnknown2; // ???
   uint32_t   dwOffset;
};
```


example of a hash

```
331F339BC3DB8E80 - pcx64-w\local\locals.bin
```
## Post #3
- Username: BadBoy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 24, 2016 10:17 pm
- Post datetime: 2018-09-14T15:14:47+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Code: Select allstruct TigerHeader
{
   uint32_t   dwID; //TAFS
   uint32_t   dwVersion; //5
   uint32_t   dwPartsCount;
   uint32_t   dwTotalFiles;
   uint64_t   dwUnknown;
   uint8_t    m_Platform[32]; //pcx64-w for PC
};

struct TigerEntry
{
   uint64_t   dwNameHash; //Fnv64
   uint64_t   dwLanguageID;
   uint32_t   dwSize;
   uint32_t   dwUnknown1; // ???
   uint32_t   dwUnknown2; // ???
   uint32_t   dwOffset;
};

example of a hash
Code: Select all331F339BC3DB8E80 - pcx64-w\local\locals.bin
Can you make Unpacker and Packer?  How do we find the names and Hash?
## Post #4
- Username: serkandogan12345
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-14T16:25:44+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from BadBoy
>
> Ekey wrote:Code: Select allstruct TigerHeader
{
   uint32_t   dwID; //TAFS
   uint32_t   dwVersion; //5
   uint32_t   dwPartsCount;
   uint32_t   dwTotalFiles;
   uint64_t   dwUnknown;
   uint8_t    m_Platform[32]; //pcx64-w for PC
};

struct TigerEntry
{
   uint64_t   dwNameHash; //Fnv64
   uint64_t   dwLanguageID;
   uint32_t   dwSize;
   uint32_t   dwUnknown1; // ???
   uint32_t   dwUnknown2; // ???
   uint32_t   dwOffset;
};

example of a hash
Code: Select all331F339BC3DB8E80 - pcx64-w\local\locals.bin
Can you make Unpacker and Packer?  How do we find the names and Hash?

Game must be played through to dump all filenames.
## Post #5
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-15T14:03:25+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> BadBoy wrote:Ekey wrote:Code: Select allstruct TigerHeader
{
   uint32_t   dwID; //TAFS
   uint32_t   dwVersion; //5
   uint32_t   dwPartsCount;
   uint32_t   dwTotalFiles;
   uint64_t   dwUnknown;
   uint8_t    m_Platform[32]; //pcx64-w for PC
};

struct TigerEntry
{
   uint64_t   dwNameHash; //Fnv64
   uint64_t   dwLanguageID;
   uint32_t   dwSize;
   uint32_t   dwUnknown1; // ???
   uint32_t   dwUnknown2; // ???
   uint32_t   dwOffset;
};

example of a hash
Code: Select all331F339BC3DB8E80 - pcx64-w\local\locals.bin
Can you make Unpacker and Packer?  How do we find the names and Hash?

Game must be played through to dump all filenames.

If you play the game, can you make a tool ? I need just language files for this game.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-15T15:16:45+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from serkandogan12345
>
> 

If you play the game, can you make a tool ? I need just language files for this game.

I usually just work on the meshes. Ekey is usually the one who writes the tiger unpacker and drm dumper. Also I don't have the PC version.

Can someone upload Lara's model? I will have the meshes out in minutes.
## Post #7
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-15T17:13:45+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> serkandogan12345 wrote:

If you play the game, can you make a tool ? I need just language files for this game.

I usually just work on the meshes. Ekey is usually the one who writes the tiger unpacker and drm dumper. Also I don't have the PC version.

Can someone upload Lara's model? I will have the meshes out in minutes.

Im downloading game. Status %55. But i dont have steam game. Im downloading "Shadow.of.the.Tomb.Raider.Croft.Edition" from 3DMGAME.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-16T22:48:03+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hmm tiger archive has no visible CDRM headers? Possibly encrypted?
## Post #9
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-09-17T00:05:33+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Hmm tiger archive has no visible CDRM headers? Possibly encrypted?
Don't think so? CDRM can be read many times in hex editor. The bms script posted on zenhax doesn't work with the main bigfiles though.
## Post #10
- Username: Faithfullfaun
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-17T10:42:56+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

First mesh is out, normals data looks weird though, not same method used to compress on earlier games :/
## Post #11
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-17T11:00:41+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 


First mesh is out, normals data looks weird though, not same method used to compress on earlier games :/

Nice. Im waiting tiger Unpacker and Repacker.  @Gh0stBlade and @Ekey Thank you for helping. Im waiting. I need just language files.
## Post #12
- Username: Streetx2007
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 08, 2016 4:10 am
- Post datetime: 2018-09-17T17:28:14+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from serkandogan12345
>
> 
Nice. Im waiting tiger Unpacker and Repacker.  @Gh0stBlade and @Ekey Thank you for helping. Im waiting. I need just language files.

Mee too. I want to make a translate (from my home language) for this game. Thanks for the help!
## Post #13
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-17T17:48:55+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Streetx2007
>
> serkandogan12345 wrote:
Nice. Im waiting tiger Unpacker and Repacker.  @Gh0stBlade and @Ekey Thank you for helping. Im waiting. I need just language files.

Mee too. I want to make a translate (from my home language) for this game. Thanks for the help!

Do you have this game?
## Post #14
- Username: Streetx2007
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 08, 2016 4:10 am
- Post datetime: 2018-09-17T17:58:04+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from serkandogan12345
>
> Streetx2007 wrote:serkandogan12345 wrote:
Nice. Im waiting tiger Unpacker and Repacker.  @Gh0stBlade and @Ekey Thank you for helping. Im waiting. I need just language files.

Mee too. I want to make a translate (from my home language) for this game. Thanks for the help! 

Do you have this game?

Yes. On Steam (Croft Edition).
## Post #15
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-17T18:48:56+00:00
- Post Title: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Streetx2007
>
> 
Yes. On Steam (Croft Edition).

Good. Can you try this translated files ? I translated this screen. Download Link : [https://yadi.sk/d/S8-AVxOwBeiG9A](https://yadi.sk/d/S8-AVxOwBeiG9A)
## Post #16
- Username: Streetx2007
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 08, 2016 4:10 am
- Post datetime: 2018-09-17T19:05:25+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from serkandogan12345
>
> Streetx2007 wrote:
Yes. On Steam (Croft Edition).

Good. Can you try this translated files ? I translated this screen. Download Link : https://yadi.sk/d/S8-AVxOwBeiG9A

Sadly, but not working.


Error message:
TigerArchive header mismatch in bigfile.update1.002_english_allvo_allplt.000.tiger!
## Post #17
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-17T19:19:21+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Streetx2007
>
> 
Sadly, but not working.


Error message:
TigerArchive header mismatch in bigfile.update1.002_english_allvo_allplt.000.tiger!

Ohhh bad.

I dont know how to reimport .dat file to .tiger

Do you know how to reimport ?
## Post #18
- Username: Streetx2007
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Feb 08, 2016 4:10 am
- Post datetime: 2018-09-17T19:23:41+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from serkandogan12345
>
> Streetx2007 wrote:
Sadly, but not working.


Error message:
TigerArchive header mismatch in bigfile.update1.002_english_allvo_allplt.000.tiger!

Ohhh bad.

I dont know how to reimport .dat file to .tiger

Do you know how to reimport ?

No. Sadly I not have any tools for this game. So, I need waiting.
## Post #19
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-17T19:31:42+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Streetx2007
>
> 
No. Sadly I not have any tools for this game. So, I need waiting.

Yes, me too. We need just reimport .dat to .tiger Hellppppp
## Post #20
- Username: sydie
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Nov 30, 2016 6:45 am
- Post datetime: 2018-09-19T15:47:21+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hey guys!
@Gh0stBlade, @Ekey and @aluigi
I've tried unpacking bigfile.000.tiger with Aluigi's tomb_raider_tafs.bms, but got only 75% extracted and the files are without names and most of the extensions are .dat
@Ekey - I've tried using ROTR TIGER Unpacker, but I guess we'll need a new FileNames.list for that.
@Gh0stBlade - How did you get that model into Noesis - did you try all the the scrambled .dat files in Noesis or is there a method to this madness
## Post #21
- Username: sydie
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-09-19T18:02:16+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from sydie
>
> Hey guys!
@Gh0stBlade - How did you get that model into Noesis - did you try all the the scrambled .dat files in Noesis or is there a method to this madness
I used offzip to decompress the CDRM sections inside the Bigfile... Then updated rise of the tomb raider's mesh importer to work with Shadow of the Tomb Raider's files.

Waiting patiently for the bigfile unpacker. Is EKey working on this or not?
## Post #22
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-19T19:27:41+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
I used offzip to decompress the CDRM sections inside the Bigfile... Then updated rise of the tomb raider's mesh importer to work with Shadow of the Tomb Raider's files.

Waiting patiently for the bigfile unpacker. Is EKey working on this or not?
I hope, Ekey is working .bigfile unpacker and repacker. we need just language files  

Ekey ?
## Post #23
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-09-20T19:32:22+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from serkandogan12345
>
> I hope, Ekey is working .bigfile unpacker and repacker. we need just language files  

Ekey ?
No sorry, I'm not working on this game, cause not enough time
## Post #24
- Username: sydie
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Nov 30, 2016 6:45 am
- Post datetime: 2018-09-20T19:39:37+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> serkandogan12345 wrote:I hope, Ekey is working .bigfile unpacker and repacker. we need just language files  

Ekey ?
No sorry, I'm not working on this game, cause not enough time

That's sad 
But thank you for your work on ROTR!
Can you point me in the right direction - how to get the file list at least?
## Post #25
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-09-20T20:47:28+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

The filelist was generated by using a hook (detouring)
## Post #26
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2018-09-20T21:36:43+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

what could a mortal being like me, with no coding skills, do to help?
those assets look so nice! especially the static meshes.
## Post #27
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-20T21:52:07+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> serkandogan12345 wrote:I hope, Ekey is working .bigfile unpacker and repacker. we need just language files  

Ekey ?
No sorry, I'm not working on this game, cause not enough time

ohh. sad   But you are my hero.

if you have any free time in the future, do you think ?

actually we need just language files import and reimport. I don't need other files. Just English Lanugage Files.

(sorry my bad english   )
## Post #28
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-09-21T22:06:25+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from serkandogan12345
>
> 
if you have any free time in the future, do you think ?
probably yes
## Post #29
- Username: serkandogan12345
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Jan 22, 2018 9:58 pm
- Post datetime: 2018-09-21T22:57:24+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> serkandogan12345 wrote:
if you have any free time in the future, do you think ?
probably yes

 I'm waiting impatiently.
## Post #30
- Username: yusuf0808
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 30, 2017 12:33 am
- Post datetime: 2018-09-29T14:47:52+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> serkandogan12345 wrote:
if you have any free time in the future, do you think ?
probably yes

Hey Ekey. Can't you make a quick tutorial for how we use the detouring to get the filenames? I'd really like to help this but I don't have enough knowledge to do so.

Thanks in advance.
## Post #31
- Username: BadBoy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Apr 24, 2016 10:17 pm
- Post datetime: 2018-10-02T04:20:04+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> The filelist was generated by using a hook (detouring)
Ekey, Can a filelist be created with Procmon or API Monitor? Or is it impossible?
## Post #32
- Username: adrianna
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Oct 07, 2018 7:54 am
- Post datetime: 2018-10-09T10:57:15+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> serkandogan12345 wrote:
if you have any free time in the future, do you think ?
probably yes

Hello! Sorry to write in this topic, your PM closed. And sorry for very bad english.

You uploaded your 11 Bit Studios Games .DAT unpacker [here](http://forum.xentax.com/viewtopic.php?f=10&t=11378), do you still have it? Link is dead now.
## Post #33
- Username: Darksyde
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-09T15:22:02+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from adrianna
>
> Ekey wrote:serkandogan12345 wrote:
if you have any free time in the future, do you think ?
probably yes 

Hello! Sorry to write in this topic, your PM closed. And sorry for very bad english.

You uploaded your 11 Bit Studios Games .DAT unpacker here, do you still have it? Link is dead now.
Stay on topic.
## Post #34
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2018-10-10T17:19:24+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Any news? It'd be so great to see assets exported from the game.
## Post #35
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-12T10:24:20+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from kotn3l
>
> Any news? It'd be so great to see assets exported from the game.
I have a work in progress mesh importer. Stopped working on it though, need a bigfile unpacker and DRM dumper.
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-22T02:27:17+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I have some time to work on this game. Here's a small the patcher (see attach). Usage as usual - just copy in game folder.
Tested only on latest patch (1.0.235.5). I do not know whether it will work on previous versions.

What this patcher to does:
Just check log file with file names 

Log location:

```
C:\Users\XXXX\Documents\Shadow of the Tomb Raider\
```


You can see something like:

```
04:30:59:649 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\wwise\TOC.dat
04:30:59:852 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\objectlist.txt
04:30:59:892 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\zonelist.ids
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\generalbank.drm
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\globalsoundinfo.drm
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\globalaniminfo.drm
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\globaluiinfo.drm
```


and etc.

Warning: If you restart game, previous log file will be overwritten. Therefore, make copies!

Interact with Npc, objects, complete challenge tombs, main missions, side missions, puzzles and etc. This is need for collect more file names. You can send links your log file to me in PM or share in this thread.
[SOTTRPatcher_0.0.1_r1.rar](https://xentaxbackup.github.io/file/15071_SOTTRPatcher_0.0.1_r1.rar)
## Post #37
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2018-10-23T12:24:52+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Logs, mainly taken from late game areas

[https://www57.zippyshare.com/v/3ihvNlGy/file.html](https://www57.zippyshare.com/v/3ihvNlGy/file.html)
## Post #38
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-23T12:34:54+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from YourImaginaryFriend
>
> Logs, mainly taken from late game areas

https://www57.zippyshare.com/v/3ihvNlGy/file.html
Thanks. I will merging this log with my list
## Post #39
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-23T20:37:22+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Almost done. I will share tools later after few tests on different drm types 



PS: Dumped mesh for reversing format: [here](https://www.sendspace.com/file/suqhem)
## Post #40
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-23T21:19:01+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Almost done. I will share tools later after few tests on different drm types 



PS: Dumped mesh for reversing format: here
Can you get me Lara (tr11_lara.drm)?

Edit:
## Post #41
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-23T21:34:51+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

[Here](https://dropmefiles.com/XuQcw) full dump of tr11_lara. Also they added new file type with id > 4. Idk what this
## Post #42
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-23T22:12:34+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Here full dump of tr11_lara. Also they added new file type with id > 4. Idk what this
Odd, Lara's mesh not included in this dump.  

Edit: You sure it's unpacking correctly?
## Post #43
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-23T23:16:19+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Edit: You sure it's unpacking correctly?
All that tr11_lara.drm contains was unpacked. Perhaps the Lara model is somewhere else. For example in this file laracroft.drm > [check it here](https://dropmefiles.com/RRtLK)
## Post #44
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-24T12:38:10+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Excellent! Working on it now.

Some new changes to the mesh format, all is figured out, just need to piece the code back together and check bones plus textures.
## Post #45
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-24T17:06:29+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Here are the stable versions, maybe after the release of The Forge DLC, some changes will be needed.

SOTTR_TIGERUnpacker_0.0.1_r1: [here](https://www.sendspace.com/file/q3ko6h)
SOTTR_DRMDumper_0.0.1_r1: [here](https://www.sendspace.com/file/fl9q7u)
## Post #46
- Username: volfin
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-24T20:28:29+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Some textures working.
## Post #47
- Username: pineapples721
- Rank: advanced
- Number of posts: 58
- Joined date: Wed Sep 06, 2017 1:39 am
- Post datetime: 2018-10-24T22:30:28+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Can we have the source code to the Tiger Unpacker and/or DRM Dumper? Thanks!
## Post #48
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2018-10-25T01:11:41+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

thanks for your tool(s)!
but for me, SOTTRPatcher_0.0.1_r1 is crashing the game. therefore i can't collect filenames.
game version at this point is still:

v1.0 build 235.5_64

any ideas?
## Post #49
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-25T09:59:34+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from TheMask85
>
> thanks for your tool(s)!
but for me, SOTTRPatcher_0.0.1_r1 is crashing the game. therefore i can't collect filenames.
game version at this point is still:

v1.0 build 235.5_64

any ideas?
Try to unlock dll like this
## Post #50
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-10-25T13:18:20+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I'd love to contribute to filelists but my game doesn't start when i have the dll in the folder. Does it not work with Steam version or is it a problem only i have? (Tried previous suggested solution without success)
## Post #51
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-25T13:45:12+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I do not even know what could be the matter.
## Post #52
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2018-10-25T15:07:39+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey
>
> Try to unlock dll like this

hmm, i don't have such an unlock button in the properties window. never had one, tbh.
that's weird. with the dll in the game files it just won't run the game. basically exact same issue as o0Crofty0o.
i'm using Windows 7, if that's a useful information for you.
## Post #53
- Username: T0M099
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Apr 02, 2013 1:12 am
- Post datetime: 2018-10-25T19:53:31+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Same issue as Crofty and TheMask have.
I see in TaskManager SOTTR.exe running, but nothing happens. (It's stuck with 43 832 KB of RAM)
I also unblocked the DLL as Ekey suggested.

Now I even can't kill the process via TaskManager.

Running on Windows 7 EN x64 SP1 (updated till September)
## Post #54
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-10-26T20:51:51+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

yeah Steam won't even get past the bootstrap loader with that dll in the folder. I think it knows it shouldn't be there.
## Post #55
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2018-10-27T10:08:32+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Sadly but this works not for everyone, I do not know what the problem is.
## Post #56
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2018-10-27T20:17:58+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Some textures working.

This is so exciting.  Finally some extracted 3D models soon.
Can you share the Noesis plugin please?
## Post #57
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-27T20:59:18+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from kotn3l
>
> Gh0stBlade wrote:Some textures working.


This is so exciting.  Finally some extracted 3D models soon.
Can you share the Noesis plugin please?
Not with that attitude
## Post #58
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2018-10-28T10:25:07+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> kotn3l wrote:Gh0stBlade wrote:Some textures working.


This is so exciting.  Finally some extracted 3D models soon.
Can you share the Noesis plugin please? 
Not with that attitude

I meant no disrespect.
I'm sorry if my "finally" sounded rude and inappropriate, I was just really excited to see progress in this matter. (Also, I didnt mean my roll smilie as a provoking one.)
## Post #59
- Username: kotn3l
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-28T14:41:18+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Noesis script is almost done, just applied a few optimisations. Still running a little bit slow...

Todo:
Textures - Some types are still unsupported.
Models - Skeleton needs to be found to test rig.
## Post #60
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-28T21:21:33+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Any updated file list?

Can someone go to a campsite switch to all outfits then update the file listing?

Need more character model references, can only find default Lara. No jonah, young lara or costumes... hmm....

Thanks.
## Post #61
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2018-10-28T23:18:46+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Strange, I have many files referencing lara, jonah and others. At least texture wise their assets seems to be stored in archives starting with paperdoll_piece e.g. paperdoll_piece_tr11_lara_crimson_huntress_torso or paperdoll_piece_jonah_head
## Post #62
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2018-10-29T11:40:43+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Any updated file list?

Can someone go to a campsite switch to all outfits then update the file listing?

Need more character model references, can only find default Lara. No jonah, young lara or costumes... hmm....

Thanks.
[Here](https://drive.google.com/file/d/1gseZa5vv4bqf0E0mRxInvqZ3YIbjmZ7Y/view?usp=sharing), I was in Cozumel, the big room, in the Explorer outfit, then switched to the default blue one. Then I fast traveled to Kuwaq Yaku and talked to the merchant. I also killed a spider.
## Post #63
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-29T18:54:31+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Bones, skinning works fine.


Some characters are indeed split into "paperdoll" pieces. Good luck piecing them all back together.... I guess...
## Post #64
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2018-10-30T10:29:04+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

@Gh0stBlade
Out of curiosity, do they by any chance use hashes as bone names inside the file? If they do could the script read them? Would make joining models a little easier. Not a big deal tho.
## Post #65
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-10-30T11:01:27+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from o0Crofty0o
>
> @Gh0stBlade
Out of curiosity, do they by any chance use hashes as bone names inside the file? If they do could the script read them? Would make joining models a little easier. Not a big deal tho.
Bone names are not hashed, there are no bone names.

Tomb Raider: Underworld had a separate DTP file that stored bone names but I'm unsure if it's present in later games. If it is then I'd have to write a full DRM parser and the process of parsing the DRM plus all sections dynamically is unfortunately complicated and unknown.

Cheers.
## Post #66
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2018-10-30T19:40:00+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

>> Ekey
There are a lot of containers with resources, and according to the utility case, only 5 indices
## Post #67
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2018-10-31T17:18:10+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 

Bones, skinning works fine.


Some characters are indeed split into "paperdoll" pieces. Good luck piecing them all back together.... I guess...

Well done, can't wait for the plugin
## Post #68
- Username: sydie
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-01T16:22:51+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Mesh importer is available in the first post of this topic.

Please report bugs here, I will fix them but there probably aren't any.

If someone finds Lara's skeleton in (laracroft.drm DTPData folder) let me know. Skeletons are located in the DTPData. Reason: I'm not certain my code will load all skeletons, I only tested it on one. If it helps skeleton files usually start with 0x0B000000. I don't have the time to go through all sections unfortunately.

Cheers.
## Post #69
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-11-01T19:01:39+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hi, i extract laracroft.drm
in the DTPData folder i found - Section 5651.dtp
rename Section 5651.dtp to skeleton.skl and drop to RenderMesh folder
open in Noesis - Section 5648.tr11mesh
all bones work fine
[image.jpg](https://xentaxbackup.github.io/file/15108_image.jpg)
## Post #70
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-01T19:08:46+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Good find, thank you.
## Post #71
- Username: sydie
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Nov 30, 2016 6:45 am
- Post datetime: 2018-11-01T19:15:50+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Yo, guys! I can't thank you enough!
Ekey and Gh0stBlade did some amazing coding magic and everything works!
Just out of curiosity - is it possible to dump the morph targets (a.k.a. blend shapes)?
ROTR's rig was based entirely on blend shapes and even had 3 sets of face-region normal and mask maps.

Thank you again!
## Post #72
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-11-01T19:19:49+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

If someone extracted laracroft.drm from bigfile.update2 - the skeleton is "Section 5372.dtp".

Badass Lama's skeleton (same bigfile) is "Section 315.dtp".
## Post #73
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-11-01T19:25:10+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

i don't understand how get hair
only find - lara_hair_braid_rig
## Post #74
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-11-01T19:54:57+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Crazy31139
>
> i don't understand how get hair
only find - lara_hair_braid_rig

From what I can tell, even on low settings you get PureHair, meaning it's not like in RotTR where you'd get a "conventional" mesh for the hair when choosing the lowest setting.

There's also "lara_hair_all.drm" which should contain (in the dtp folder) the PureHair but I hadn't had any luck extracting it with daemon1's tools.

Edit: The hair-mesh for the survivor skin is in "paperdoll_piece_tr11_lara_tr9_yamatai_head".
## Post #75
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-01T21:10:57+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from sydie
>
> Yo, guys! I can't thank you enough!
Ekey and Gh0stBlade did some amazing coding magic and everything works!
Just out of curiosity - is it possible to dump the morph targets (a.k.a. blend shapes)?
ROTR's rig was based entirely on blend shapes and even had 3 sets of face-region normal and mask maps.

Thank you again!
If there are morph targets then it's probably in the dtp data. I'd say impossible to extract since there's hundreds of dtp files
## Post #76
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-11-02T01:58:10+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Will the tool also work with Environment meshes that don't contain skeletons.

I'm guessing yes, but sometimes the skeletal mesh format is very different from the normal meshes.
## Post #77
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-11-02T08:18:42+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Is it possible to extract the voice and music files?

Back in RotTR one would get - after dumping a corresponding *.drm - a selectin of .mul files, which contained .fsb 
Now when I dump for example "017_storyteller_fountain_woman.drm" (audio/dialogue.../stroy/...) I only get one .dtp file.
Then there's the folder "wwise" in the unpacked bigfile and if I dump one of the .drm found there I get a .sound file, which doesn't seem to be an ordinary wwise - at least I failed converting it (with ww2ogg024).
## Post #78
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2018-11-02T09:22:03+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

>> I'd say impossible to extract since there's hundreds of dtp files
laracroft.drm->id->4067A->"RenderMesh"->data:

```

```

this "RenderMesh"????))
ok. goto->
laracroft.drm->id->4062B->this "Material"!!!! pointers to id graphics in this container
EKey instead of the ordinal section, it is necessary to write the resource ID, a lot of files, search for content for a very long time.
in subdrm the first three bytes are the resource id, offset, id, and the ordinal of the container is still reading.))
---------
and there are files of objects Mesh in the *.tiger from one block, as a result, the block is not unpacked.
---------
Squish for graphics decompression is no longer suitable. 
except Noesis, there are libraries newer???(C# or C++)???
## Post #79
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-02T11:03:12+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from lionheartuk
>
> Will the tool also work with Environment meshes that don't contain skeletons.

I'm guessing yes, but sometimes the skeletal mesh format is very different from the normal meshes.
No, scene mesh will require a separate importer since the format is different.
## Post #80
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-11-02T16:35:46+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from lionheartuk
>
> Will the tool also work with Environment meshes that don't contain skeletons.

I'm guessing yes, but sometimes the skeletal mesh format is very different from the normal meshes.

if you mean simple props with no skeletons, then yes, it works. I've done several already. Level data is another matter.
## Post #81
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2018-11-03T03:52:44+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from volfin
>
> lionheartuk wrote:Will the tool also work with Environment meshes that don't contain skeletons.

I'm guessing yes, but sometimes the skeletal mesh format is very different from the normal meshes.

if you mean simple props with no skeletons, then yes, it works. I've done several already. Level data is another matter.

Yup, just props and general assets.
Not the actual level data itself.
More like, X number of levels use a wall, but that wall is just a referenced static mesh, wondered if it'd open that wall, for example.
## Post #82
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-11-03T04:48:07+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from lionheartuk
>
> 
Yup, just props and general assets.
Not the actual level data itself.
More like, X number of levels use a wall, but that wall is just a referenced static mesh, wondered if it'd open that wall, for example.

Well for instance I know it does relics from the collectible screen. They don't have a skeleton. I did a few other props too. So I assume stuff like that should work.
## Post #83
- Username: PaulPhoenix31139
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 09, 2018 4:38 pm
- Post datetime: 2018-11-03T05:27:13+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hello, need help
i can't find skeleton in the DTPData folder to "paperdoll_piece_tr11_lara_child_torso.drm"
how i can find, in the folder i see .dtp (start with 0x0B000000) but their size 1kb
after rename .dtp to skeleton.skl i try open in noesis, but open model without skeleton 
I see in bigfile/update1/update2.tiger and weapon skeleton too interest.
Maybe i do it wrong.
Please help me, if you have info how get this.
## Post #84
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2018-11-03T10:23:25+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Crazy31139
>
> Hi, i extract laracroft.drm
in the DTPData folder i found - Section 5651.dtp
rename Section 5651.dtp to skeleton.skl and drop to RenderMesh folder
open in Noesis - Section 5648.tr11mesh
all bones work fine

Thanks! Any way to view animations like this? Like renaming one of them in the Animations folder then dropping it to RenderMesh folder like the skeleton? Question is, what to rename the animation files? Or is it not possible this way?
## Post #85
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-03T14:35:13+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Raban
>
> I hadn't had any luck extracting it with daemon1's tools.

i will modify my purehair tool to support it later
for now, use this "converter" that will modify this new version headers so they will be compatible with old tool
[PureHair_2c.rar](https://xentaxbackup.github.io/file/15116_PureHair_2c.rar)
## Post #86
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-11-03T20:02:14+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from daemon1
>
> 
i will modify my purehair tool to support it later
for now, use this "converter" that will modify this new version headers so they will be compatible with old tool

Thank you very much!
## Post #87
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2018-11-04T23:12:28+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I have difficulties finding skeletons for characters other than Lara. Anyone had any luck with them?
## Post #88
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2018-11-05T12:30:06+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

is there a way to have correct mesh-/texture names instead of "section #"?
eyeballing by uv sheet for applying textures works but is pretty tedious.
## Post #89
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-05T17:04:59+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from TheMask85
>
> is there a way to have correct mesh-/texture names instead of "section #"?
eyeballing by uv sheet for applying textures works but is pretty tedious.
There is no such thing as correct "mesh and texture names". Each DRM section has only an ID number to identify it. All names are stripped out during the cooking process, it has been like this since Tomb Raider: Legend.
## Post #90
- Username: Anthony78800
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Nov 06, 2018 9:05 pm
- Post datetime: 2018-11-06T13:15:14+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hello, how to get the Mesh file for the game Shadow of Tomb Raider because I extracted the files laracroft.drm I would like to get the characters
## Post #91
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-11-07T05:05:06+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Mesh importer is available in the first post of this topic.

Please report bugs here, I will fix them but there probably aren't any.

If someone finds Lara's skeleton in (laracroft.drm DTPData folder) let me know. Skeletons are located in the DTPData. Reason: I'm not certain my code will load all skeletons, I only tested it on one. If it helps skeleton files usually start with 0x0B000000. I don't have the time to go through all sections unfortunately.

Cheers.

Hi, can you see in bigfile.000, paperdoll_piece_redqueen_head.drm
i extract paperdoll_piece_redqueen_head.drm in DTPData folder i find Section 24.dtp ( 0x0B000000)
rename Section 24.dtp to skeleton.skl
in the noesis open and see this error
[image.png](https://xentaxbackup.github.io/file/15140_image.png)
## Post #92
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-07T07:45:57+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Crazy31139
>
> Gh0stBlade wrote:Mesh importer is available in the first post of this topic.

Please report bugs here, I will fix them but there probably aren't any.

If someone finds Lara's skeleton in (laracroft.drm DTPData folder) let me know. Skeletons are located in the DTPData. Reason: I'm not certain my code will load all skeletons, I only tested it on one. If it helps skeleton files usually start with 0x0B000000. I don't have the time to go through all sections unfortunately.

Cheers.

Hi, can you see in bigfile.000, paperdoll_piece_redqueen_head.drm
i extract paperdoll_piece_redqueen_head.drm in DTPData folder i find Section 24.dtp ( 0x0B000000)
rename Section 24.dtp to skeleton.skl
in the noesis open and see this error

I'll check it when I get home. Very likely a format error.
## Post #93
- Username: volfin
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-07T13:31:01+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Updated script available in first post, should fix issues loading certain skeletons.
## Post #94
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-11-07T19:17:18+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Thanx, now support many other skeleton
If you have free time can see paperdoll_piece_redqueen_lowerbody.drm 
in the DTPData folder - Section 31.dtp

paperdoll_piece_abby_top.drm (Section 32.dtp)
[image_1.jpg](https://xentaxbackup.github.io/file/15142_image_1.jpg)
## Post #95
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-11-08T08:14:39+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Upon trying to load the explorer-outfit I'm getting the following error:

```
Skeleton file detected!
Building Skeleton....
Traceback (most recent call last):
  File "E:\Noesis v4296\plugins\python\fmt_TR11_mesh_1_2.py", line 428, in meshLoadModel
    mesh.buildSkeleton()
  File "E:\Noesis v4296\plugins\python\fmt_TR11_mesh_1_2.py", line 194, in buildSkeleton
    sd.seek(0xC, NOESEEK_REL)
  File "E:\Noesis v4296\plugins\python\inc_noesis.py", line 165, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "E:\Noesis v4296\plugins\python\inc_noesis.py", line 161, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "E:\Noesis v4296\plugins\python\inc_noesis.py", line 78, in setOffset
    noesis.bsSetOfs(self.h, ofs)
RuntimeError: Tried to set offset beyond buffer size. (516 > 512)
Detected file type: Shadow of the Tomb Raider 3D Mesh [PC]
Skeleton file detected!
Building Skeleton....
Traceback (most recent call last):
  File "E:\Noesis v4296\plugins\python\fmt_TR11_mesh_1_2.py", line 428, in meshLoadModel
    mesh.buildSkeleton()
  File "E:\Noesis v4296\plugins\python\fmt_TR11_mesh_1_2.py", line 194, in buildSkeleton
    sd.seek(0xC, NOESEEK_REL)
  File "E:\Noesis v4296\plugins\python\inc_noesis.py", line 165, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "E:\Noesis v4296\plugins\python\inc_noesis.py", line 161, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "E:\Noesis v4296\plugins\python\inc_noesis.py", line 78, in setOffset
    noesis.bsSetOfs(self.h, ofs)
RuntimeError: Tried to set offset beyond buffer size. (516 > 512)

```


What am I doing wrong? Is it possible to increase the buffer size?

Edit: Just saw whose birthday it is today.
Happy birthday Ekey!
## Post #96
- Username: Crazy31139
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-08T12:08:04+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Crazy31139
>
> Thanx, now support many other skeleton
If you have free time can see paperdoll_piece_redqueen_lowerbody.drm 
in the DTPData folder - Section 31.dtp

paperdoll_piece_abby_top.drm (Section 32.dtp)

The correct skeleton file is Section 22.dtp... For some reason the model has out of range bone indices.

> Reply from Raban
>
> Upon trying to load the explorer-outfit I'm getting the following error: Detected file type: Shadow of the Tomb Raider 3D Mesh [PC]

It would help if you told me the exact DRM file name.
## Post #97
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-11-08T12:33:40+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> It would help if you told me the exact DRM file name.

Sorry, I thought the problem was at my end.

It's about "paperdoll_piece_tr11_lara_explorer_legs" (skl:Section 387) and "paperdoll_piece_tr11_lara_explorer_torso" (skl:Section 388).
## Post #98
- Username: Raban
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-08T13:33:27+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Raban
>
> Gh0stBlade wrote:It would help if you told me the exact DRM file name.

Sorry, I thought the problem was at my end.

It's about "paperdoll_piece_tr11_lara_explorer_legs" (skl:Section 387) and "paperdoll_piece_tr11_lara_explorer_torso" (skl:Section 388).
It's because you are loading the wrong section as the skeleton file.

paperdoll_piece_tr11_lara_explorer_legs is Section 955.dtp
paperdoll_piece_tr11_lara_explorer_torso is Section 960.dtp
## Post #99
- Username: Raban
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 10, 2017 8:23 pm
- Post datetime: 2018-11-08T13:59:37+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
It's because you are loading the wrong section as the skeleton file.

paperdoll_piece_tr11_lara_explorer_legs is Section 955.dtp
paperdoll_piece_tr11_lara_explorer_torso is Section 960.dtp
Thanks, it's working!


The strange thing is that when I load for example 960.dtp in a hexeditor, I get in the first line:

```
2F 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```


When I previously looked for and found skeletons they always began like this:

```
0B 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```


I thought the "0B" is the "0x0B000000" you were refering to earlier. And it also worked until the issue with lara-explorer: I got several skeletons for the various animals by looking for said "0B". 
Has something changed or is "0B" just not the dead-sure way of identifying the skeleton that I thought it is?
## Post #100
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-08T14:13:27+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Raban
>
> Gh0stBlade wrote:
It's because you are loading the wrong section as the skeleton file.

paperdoll_piece_tr11_lara_explorer_legs is Section 955.dtp
paperdoll_piece_tr11_lara_explorer_torso is Section 960.dtp
Thanks, it's working!


The strange thing is that when I load for example 960.dtp in a hexeditor, I get in the first line:
Code: Select all2F 01 00 00 00 00 00 00 00 00 00 00 00 00 00 00

When I previously looked for and found skeletons they always began like this:
Code: Select all0B 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00

I thought the "0B" is the "0x0B000000" you were refering to earlier. And it also worked until the issue with lara-explorer: I got several skeletons for the various animals by looking for said "0B". 
Has something changed or is "0B" just not the dead-sure way of identifying the skeleton that I thought it is?
Because 0xB isn't really the magic. Most skeletons start with it though.

The real way to do it is looking for bones in a hex editor. Quite tedious if you ask me.
## Post #101
- Username: Nihyaku
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 08, 2017 7:06 pm
- Post datetime: 2018-11-08T21:21:56+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hi! Many thanks for the tools! Your work is highly appreciated!!  

Sorry for bothering you, but I don't understand how daemon1's Purehair tool works... Could someone help me, please? Thank you.
## Post #102
- Username: PaulPhoenix31139
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Oct 09, 2018 4:38 pm
- Post datetime: 2018-11-09T07:07:55+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Nihyaku
>
> Hi! Many thanks for the tools! Your work is highly appreciated!!  

Sorry for bothering you, but I don't understand how daemon1's Purehair tool works... Could someone help me, please? Thank you.

Sample - tr11_larachild_hair.drm in the DTPData folder choose biggest file.dtp and drop to PureHair_2c.exe and you receive file

received file drop to DXMDmodel (PureHair.exe) and receive complete files .ascii and .obj (PureHair for SOTTR)

Cheers.
## Post #103
- Username: Nihyaku
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Dec 08, 2017 7:06 pm
- Post datetime: 2018-11-09T15:09:19+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from PaulPhoenix31139
>
> Nihyaku wrote:Hi! Many thanks for the tools! Your work is highly appreciated!!  

Sorry for bothering you, but I don't understand how daemon1's Purehair tool works... Could someone help me, please? Thank you.

Sample - tr11_larachild_hair.drm in the DTPData folder choose biggest file.dtp and drop to PureHair_2c.exe and you receive file

received file drop to DXMDmodel (PureHair.exe) and receive complete files .ascii and .obj (PureHair for SOTTR)

Cheers.

Many thanks for your prompt and clear reply!   
I followed your instructions attentively, however when I try to import the model in Noesis, the following errors appear:

[http://i67.tinypic.com/wamvpc.png](http://i67.tinypic.com/wamvpc.png)

I tried other files (for example "tr11_lara_hair_swampthing_loose") and I receive the same message.
Thank you
(Is "PureHair for SOTTR" [this tool](http://forum.xentax.com/viewtopic.php?f=16&t=18534), isn't it?)
## Post #104
- Username: doppel
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 20, 2013 1:09 am
- Post datetime: 2018-11-09T22:41:24+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hi everyone!
i'm having some issues with DRMDumper
when i try to open a DRM this message appears:

is anyone can help me please to fix this? 
Thanks in advance
## Post #105
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T12:23:27+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hello, how to fix this problem
[help_shadow_of_the_tomb_raider_lara_hair_by_anthony7880-dcrmdly.jpg](https://xentaxbackup.github.io/file/15150_help_shadow_of_the_tomb_raider_lara_hair_by_anthony7880-dcrmdly.jpg)
## Post #106
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-10T12:46:02+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

And what is the problem ?
## Post #107
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T13:24:23+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I can not open it on the software Noesisv Car it makes me an error message and when I open it on another software it does not appear And I can not put a texture on it
## Post #108
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-10T13:35:06+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

if you want a texture, use ascii file,

or build a mesh from OBJ file which contains only edges, which was specifically made for that purpose
## Post #109
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T13:42:50+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Here is a small example that I was told to put in this program PureHair_2c Then I get this file here Section 1.dtp.c This file there I put it in the program DXMDmodel PureHair I get the file Section 1 .dtp OBJ and this is where I have the problem after I have an ascii file but there is nothing in it So I only have the OBJ file
## Post #110
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-10T14:02:34+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Anthony789000
>
> Here is a small example that I was told to put in this program PureHair_2c Then I get this file here Section 1.dtp.c This file there I put it in the program DXMDmodel PureHair I get the file Section 1 .dtp OBJ and this is where I have the problem after I have an ascii file but there is nothing in it So I only have the OBJ file
ascii file has a model in it
you must have it too
## Post #111
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T14:10:25+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Yes I have it but when I want to open it on my Noesisv I have an error message
## Post #112
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-10T14:31:48+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Anthony789000
>
> Yes I have it but when I want to open it on my Noesisv I have an error message
i can't help you without files, and without error messages
## Post #113
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T14:34:06+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Ok wait, I'll send it to you
## Post #114
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T14:38:15+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I send it to you if you have succeeded, please tell me how did you do [https://mega.nz/#!ymgjkCxZ!ZAjmrGMK2SHM ... K9UkOLI8pw](https://mega.nz/#!ymgjkCxZ!ZAjmrGMK2SHMoQEkwCevxCR9JEs64HR4eK9UkOLI8pw)
## Post #115
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-10T14:45:13+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

this ascii file loads fine without errors

i use noesis 4.2.3.1 with ascii XNALara/XPS plugin
and blender with XNALaraMesh plugin from john zero
## Post #116
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T14:49:57+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Ok can you send me a link and give me the noesis 4.2.3.1 software with the XNALara / XPS ascii plugin
## Post #117
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-10T14:52:59+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

ascii plugin here:
[viewtopic.php?f=16&t=18226](http://forum.xentax.com/viewtopic.php?f=16&t=18226)

must work with any noesis version
## Post #118
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T14:54:59+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I can not find the plugin
## Post #119
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T15:07:11+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I'm sorry I do not find the plugin is it possible to give me a link to be able to download it directly
## Post #120
- Username: Anthony789000
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 09, 2018 6:58 pm
- Post datetime: 2018-11-10T15:22:19+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I found the plugin but the file Section 1.dtp.ascii Does not appear in Noesis The plugin I downloaded this one is it good fmt_xps_ascii.py
## Post #121
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-11T22:50:59+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Noesis importer is also a big problem. I think there's four bone boundaries. 
So a vetex is supported up to 4 bones. And this also causes Bone-weight errors.   ([https://answers.unrealengine.com/questi ... -maya.html](https://answers.unrealengine.com/questions/564898/fbx-imported-to-ue4-behave-differently-from-maya.html))
[https://comments.deviantart.com/1/730852304/4613196632](https://comments.deviantart.com/1/730852304/4613196632)  I thought the reason for the problem could be the plug-in for ascii. But ascii importer was working properly. I thought the source of the problem could be the importer.
[Limit.jpg](https://xentaxbackup.github.io/file/15158_Limit.jpg)
## Post #122
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-11-12T06:39:44+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Crazy31139 wrote:Thanx, now support many other skeleton
If you have free time can see paperdoll_piece_redqueen_lowerbody.drm 
in the DTPData folder - Section 31.dtp

paperdoll_piece_abby_top.drm (Section 32.dtp)

The correct skeleton file is Section 22.dtp... For some reason the model has out of range bone indices.

Sorry i don't understand Section 22.dtp for which model paperdoll_piece_abby_top.drm or  paperdoll_piece_redqueen_lowerbody.drm
i don't find in DTPData folders of their .drm
## Post #123
- Username: junkymana
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 05, 2017 11:01 am
- Post datetime: 2018-11-15T06:52:36+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

First of all I want to say thank you for this tool. I found this a few days ago and I am happy that I can finally extract from this game.

Second, I just have a question. Are the textures from this game lower?
I remember when extracting from ROTTR the textures were in 4k but here it looks like they are in 2K.

Not criticising at all, just wondering if it's the tool extracting the textures at this resolution (as it happened with the TOMB RAIDER 2013 tool at the time), or if they are like this in the actual game.
When I played I didn't pay that much attention as I was more focused on playing, but it did look a bit less visually attractive compared with ROTTR.

And again, thanks for this tool. My question is just out of curiosity.
Thanks!
## Post #124
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-11-15T09:11:19+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Noesis does not have a bone weight limit.
I have imported models with 12 weights per bone before.
## Post #125
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-15T13:56:05+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

It's likely it's just a bad model if you ask me... Each model I've seen (the engine only supports also...) 4 bone influences per vertex. This is what has been implemented, been the same since Legend.
## Post #126
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-15T15:13:01+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from chrrox
>
> Noesis does not have a bone weight limit.
Yeah, I'm sure the problem is not with Noesis. I think the source of the problem is in "fmt_TR11_mesh_1_2.py".

> Reply from Gh0stBlade
>
> It's likely it's just a bad model if you ask me... Each model I've seen (the engine only supports also...) 4 bone influences per vertex. This is what has been implemented, been the same since Legend.

But as you can see, there are problems. I haven't seen a 5 bone influences per vertex that refutes my guess.
Already only when exporting in .ascii format, the problems are minimized.  (  [https://sta.sh/01ekgyx6cp61](https://sta.sh/01ekgyx6cp61) / [https://sta.sh/0i3owijio1d](https://sta.sh/0i3owijio1d)  Same problem.Problem solved)
( --> [https://sta.sh/comments/61/1ekgyx6cp61/4644879812](https://sta.sh/comments/61/1ekgyx6cp61/4644879812)  "The bone index '2' is assigned 2 times. XPS add this values. The maxscript and the Blender importer use just the latest (small) value. This caust your "weight error"." )
## Post #127
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-15T15:50:37+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from TSelman61X
>
> chrrox wrote:Noesis does not have a bone weight limit.
Yeah, I'm sure the problem is not with Noesis. I think the source of the problem is in "fmt_TR11_mesh_1_2.py".
Gh0stBlade wrote:It's likely it's just a bad model if you ask me... Each model I've seen (the engine only supports also...) 4 bone influences per vertex. This is what has been implemented, been the same since Legend.

But as you can see, there are problems. I haven't seen a 5 bone influences per vertex that refutes my guess.
Already only when exporting in .ascii format, the problems are minimized.  (  https://sta.sh/01ekgyx6cp61 / https://sta.sh/0i3owijio1d  Same problem.Problem solved)
( --> https://sta.sh/comments/61/1ekgyx6cp61/4644879812  "The bone index '2' is assigned 2 times. XPS add this values. The maxscript and the Blender importer use just the latest (small) value. This caust your "weight error"." )
Which DRM file, which mesh file?
## Post #128
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-15T18:35:05+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> 
Which DRM file, which mesh file?
In fact, all models have this problem. But the model I'm showing you as an example above is "paperdoll_piece_tr11_lara_child_torso.drm" . 

The same bone of a different model. (This problem is not only a problem with this bone. There's this problem with all the mesh.)
[paperdoll_piece_tr11_lara_classic_torso.jpg](https://xentaxbackup.github.io/file/15180_paperdoll_piece_tr11_lara_classic_torso.jpg)
## Post #129
- Username: volfin
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2018-11-15T19:13:21+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Not an issue with the script, this is just how the models are rigged.
## Post #130
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-11-15T20:51:10+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Not an issue with the script, this is just how the models are rigged.

Yeah, as someone who's rigged a lot of models and seen a lot of rigged models, it's pretty clear it's just some sloppy weighting work. You'd be surprised how bad AAA studios can be with weighting, especially when crunch time hits. I've seen some really atrocious examples.
## Post #131
- Username: Paliha
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Nov 12, 2015 8:10 pm
- Post datetime: 2018-11-17T06:24:36+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hi!
waiting for advice. In the archives of the game there are graphics DXGI_FORMAT_BC5_UNORM, console utilities from Microsoft and Nvidia convert them to DXGI_FORMAT_R8G8B8A8_UNORM, with a green tint, the DevIL and plugins Noesis, with blue. where is right? ))
public enum DDS_CAPS2
        {
               CUBEMAP    = 0x00000200,
               POSITIVE_X = 0x00000400,  
               POSITIVE_Y = 0x00000A00,
               POSITIVE_Z = 0x00004000,
               NEGATIVE_X = 0x00000600, 
               NEGATIVE_Y = 0x00002000,  
               NEGATIVE_Z = 0x00008000,
               VOLUME     = 0x00200000, 
        };
flags DDS_CAPS2 do not affect decompression or conversion.
## Post #132
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-17T12:41:07+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Not an issue with the script, this is just how the models are rigged.
Probably...   I'm sure you're right. But the error I am talking about cannot be ignored. 
I hope we find the source of the problem. 
[Not normal.jpg](https://xentaxbackup.github.io/file/15196_Not normal.jpg)
## Post #133
- Username: Wasi78
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 19, 2018 12:44 pm
- Post datetime: 2018-11-19T05:27:09+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from junkymana
>
> First of all I want to say thank you for this tool. I found this a few days ago and I am happy that I can finally extract from this game.

Second, I just have a question. Are the textures from this game lower?
I remember when extracting from ROTTR the textures were in 4k but here it looks like they are in 2K.

Not criticising at all, just wondering if it's the tool extracting the textures at this resolution (as it happened with the TOMB RAIDER 2013 tool at the time), or if they are like this in the actual game.
When I played I didn't pay that much attention as I was more focused on playing, but it did look a bit less visually attractive compared with ROTTR.

And again, thanks for this tool. My question is just out of curiosity.
Thanks!

Can you please give me the link of tools to unpack and pack the bigfile.tiger ..
## Post #134
- Username: junkymana
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Mar 05, 2017 11:01 am
- Post datetime: 2018-11-19T21:08:51+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Wasi78
>
> Can you please give me the link of tools to unpack and pack the bigfile.tiger ..

In the first page you can find the links
## Post #135
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-11-20T23:29:56+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Be careful of this newest Patch that just came out a few minutes ago, Patch #7:

"Restructuring of game-data to reduce disc space usage and to allow for a smaller download size for new players. This does make the patch download for this specific patch a bit larger than usual."

I'm betting this will break the *.tiger exporter.
## Post #136
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-11-21T19:36:42+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Gh0stBlade
>
> Updated script available in first post, should fix issues loading certain skeletons.
Can you see paperdoll_piece_tr11_lara_outsider_torso.dtp
DTPData - Section 488.dtp  ( 0x0B000000) or Section 39.dtp
[image.jpg](https://xentaxbackup.github.io/file/15213_image.jpg)
## Post #137
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2018-11-21T20:28:18+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Crazy31139
>
> Gh0stBlade wrote:Updated script available in first post, should fix issues loading certain skeletons.
Can you see paperdoll_piece_tr11_lara_outsider_torso.dtp
DTPData - Section 488.dtp  ( 0x0B000000) or Section 39.dtp

I don't think this file has bone information.
For "paperdoll_piece_tr11_lara_outsider_torso.dtp" it is either "Section 39.dtp" or "Section 406.dtp". 
But I think it is Section 431.dtp. But it doesn't work.

Section 431.dtp
[Noesis Pythhon Error.png](https://xentaxbackup.github.io/file/15215_Noesis Pythhon Error.png)
## Post #138
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2018-12-12T16:34:37+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hey guys. When I want to open a DRM with the DRMDumper, it errors, and says: invalid CDRM data. Why is that? It worked before. Is it because I updated my game?
## Post #139
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2018-12-12T17:04:55+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from kotn3l
>
> Hey guys. When I want to open a DRM with the DRMDumper, it errors, and says: invalid CDRM data. Why is that? It worked before. Is it because I updated my game?

Probably, the last update changed the data format.
## Post #140
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2018-12-13T04:36:27+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Does someone know where lara's skeleton is in the demo files??
## Post #141
- Username: therussian
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 05, 2015 6:46 pm
- Post datetime: 2018-12-29T19:47:22+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

By combining multiple "Paperdoll" segments I got the reference nude body of Lara.The upper limbs are from paperdoll_piece_tr11_lara_assault_02_torso", the torso and legs are from "paperdoll_piece_tr11_lara_outsider_...." and the head is from "paperdoll_piece_tr11_lara_highpriest_head". The pieces fit together perfectly, I weld them together before making the test render. Each of these meshes had 4 LOD's and I kept the one with the highest polygon count. I also found another reference nude body (paperdoll_piece_tr11_lara_priest_legs) with a more detailed pelvic region but it was missing a section of the breasts and lower abdomen, and it didn't match with the "Outsider" torso section to fill the gaps..
[Paperdoll_.jpg](https://xentaxbackup.github.io/file/15399_Paperdoll_.jpg)
## Post #142
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2018-12-30T02:17:07+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Good work on combing the parts...however if I may input a little bit of a rant here

What happened to the Lara Croft I grew up with and fell in love with..Ya know the Massive boobs and sexy curves, I mean I understand making her more realistic and even reducing the breast size but look at her now...she is very very plain ..just an average body nothing unique or different the girl next door really

Not An Iconic figure at all in  my opinion

Sorry but I needed to put my worthless 2 cents in about that,..lol
## Post #143
- Username: therussian
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 05, 2015 6:46 pm
- Post datetime: 2018-12-30T22:05:44+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

For the mesh discussed in the previous posts (Desert Tanktop?) the facial rig is not working for LOD0 (highest polygon count).
I checked the meshes from Crazy31139 (Deviant Art) and for "Lara Explorer", "Lara Poncho", "Lara Tactical" and "Lara Tactical Black" the facial rig is not working.

Found the skeleton for: 
paperdoll_piece_tr11_lara_highpriest_head ---> "Section 928.dtp" and the rig is working for all LODs except for the highest polygon density; the mesh is Section 927
paperdoll_piece_tr11_lara_outsider_legs ----> "Section 25.dtp" and the rig is working for all LODs; the mesh is Section 23
paperdoll_piece_tr11_lara_assault_02_torso ---> "Section 1009.dtp" and the rig is working for all LODs; the mesh is Section 1007
paperdoll_piece_tr11_lara_menu_body --->"Section 823.dtp"; the mesh is Section 821

I also found skeletons that do not work, with the error "Weight contains an out of range bone index".Here is a list:
paperdoll_piece_tr11_lara_crimson_huntress_torso ---> "Section 1001.dtp"
paperdoll_piece_tr11_lara_outsider_torso ---> "Section 39.dtp
paperdoll_piece_tr11_lara_priest_legs ---> "Section 989.dtp"
paperdoll_piece_tr11_lara_priest_torso ---> "Section 983.dtp"

The skeleton is in a section close as number to the section number of the mesh itself: [skeleton section number] = [mesh section number] + 1 (or 2)
In my text viewer the content of skeleton file look like a series of slopes ascending from left to right, as in the attached image, and this way was easier to spot them.
[skeleton.jpg](https://xentaxbackup.github.io/file/15410_skeleton.jpg)
## Post #144
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2019-01-04T14:41:00+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Any way to extract music from this game? 
EDIT: Found a way: the .wem files in the wwise folder. Use this tool to convert them. Not by me, found it on reddit, by _Homesalad [Link.](https://drive.google.com/file/d/0B4eUybNL3QcwZDAxYWxPY05mdXc/view) The [reddit post link](https://www.reddit.com/r/NoMansSkyMods/comments/4xrxvv/tool_extract_wem_audio_files/).
## Post #145
- Username: Maron19
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Nov 05, 2017 10:22 pm
- Post datetime: 2019-02-01T19:31:58+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I wrote in other topics, but unfortunately they are already archived. I need help with bigfile.000.tiger files in Lara Croft ToO. I want to translate this game, but Ekey's unpacker aurora is no longer working (unknown folders are created), and there is no translatr tool here. Unfortunately, I can not write a private message to the author of the script, so I leave it here in the hope that it will not be removed before @Ekey sees it.
## Post #146
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2019-04-02T20:39:10+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hey guys, I'm desperately trying to open the stupid DRM files from Tomb Raider 2013 for a project, and the stupid DRM Dumper is giving me an error, looks like this: ERROR: Can't open file TIGER archive

Its incredibly frustrating, because I set up the tool correctly, did everything as instructed, and other people are able to do this just fine, all except for me. I tried posting in the TR 2013 thread, but no one has posted in that for a long time. Please help me figure this out.
## Post #147
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2019-04-03T01:43:58+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Several people are having issues with the tool.
Its mentioned somewhere in, I believe, this thread, that the game received a number of updates, the most updated versions of the game, and the rereleaes (definitive edition, game of the year edition, PS4 re-release etc etc) are not compatible with this tool as the updates and patches have changed the way the files work slightly, the tool could potentially be updated for that, but it may be a considerable amount of work, which is why nobody has done it.

I'd recommend getting one of the original releases of the game and using that to rip from instead.
## Post #148
- Username: CrashAngel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 21, 2012 4:55 am
- Post datetime: 2019-07-06T08:27:09+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

.....
## Post #149
- Username: CrashAngel
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 21, 2012 4:55 am
- Post datetime: 2019-07-06T08:34:09+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

thanks....
## Post #150
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2019-11-05T18:34:49+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey ↑Mon Oct 22, 2018 10:27 am at Mon Oct 22, 2018 10:27 am
>
> 
I have some time to work on this game. Here's a small the patcher (see attach). Usage as usual - just copy in game folder.
Tested only on latest patch (1.0.235.5). I do not know whether it will work on previous versions.

What this patcher to does:
Just check log file with file names 

Log location:
Code: Select allC:\Users\XXXX\Documents\Shadow of the Tomb Raider\

You can see something like:
Code: Select all04:30:59:112 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\symbol.ids
04:30:59:649 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\wwise\TOC.dat
04:30:59:852 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\objectlist.txt
04:30:59:892 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\zonelist.ids
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\generalbank.drm
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\globalsoundinfo.drm
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\globalaniminfo.drm
04:30:59:935 (00002864) > [ASSERT] Fatal error: Can't open file pcx64-w\globaluiinfo.drm

and etc.

Warning: If you restart game, previous log file will be overwritten. Therefore, make copies!

Interact with Npc, objects, complete challenge tombs, main missions, side missions, puzzles and etc. This is need for collect more file names. You can send links your log file to me in PM or share in this thread.
i'm trying to get filenames for the DLCs, but SOTTR won't launch with the dll file inside. Any solution? i've read about the unblock thing, i did it, still not working. I tried registering the dll, still nothing. The game doesn't crash though, the log files doesn't say any errors. Win10.
## Post #151
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2019-11-05T19:13:13+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from kotn3l ↑Wed Nov 06, 2019 2:34 am at Wed Nov 06, 2019 2:34 am
>
> 
i'm trying to get filenames for the DLCs, but SOTTR won't launch with the dll file inside. Any solution? i've read about the unblock thing, i did it, still not working. I tried registering the dll, still nothing. The game doesn't crash though, the log files doesn't say any errors. Win10.
Outdated. There are no plans to update it.
## Post #152
- Username: kotn3l
- Rank: veteran
- Number of posts: 90
- Joined date: Thu Mar 16, 2017 9:48 pm
- Post datetime: 2019-11-05T20:45:07+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey ↑Wed Nov 06, 2019 3:13 am at Wed Nov 06, 2019 3:13 am
>
> 
kotn3l wrote: ↑Wed Nov 06, 2019 2:34 am
i'm trying to get filenames for the DLCs, but SOTTR won't launch with the dll file inside. Any solution? i've read about the unblock thing, i did it, still not working. I tried registering the dll, still nothing. The game doesn't crash though, the log files doesn't say any errors. Win10.

Outdated. There are no plans to update it.

That's sad to hear. Thanks anyway for the clarification!
## Post #153
- Username: r00t0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 24, 2017 7:20 am
- Post datetime: 2019-11-15T22:35:07+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

On attach i post logger for getting name hash lists for new updated SotTR.


[SotTR_SOTTRLogger.7z](https://xentaxbackup.github.io/file/17063_SotTR_SOTTRLogger.7z)
## Post #154
- Username: beelzebub2063
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 01, 2019 3:37 am
- Post datetime: 2019-11-19T11:38:36+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from r00t0 ↑Sat Nov 16, 2019 6:35 am at Sat Nov 16, 2019 6:35 am
>
> 
On attach i post logger for getting name hash lists for new updated SotTR.

I have a few questions.
How exactly do I use the logger?
Simply copy the DLL's into the game directory, then start the game does not work for me.
I have this error message.
[](https://abload.de/image.php?img=error59jrr.jpg)]
Does that mean the version of the game or the version of the DLL?
## Post #155
- Username: r00t0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 24, 2017 7:20 am
- Post datetime: 2019-11-21T18:12:40+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from beelzebub2063 ↑Tue Nov 19, 2019 7:38 pm at Tue Nov 19, 2019 7:38 pm
>
> 
Does that mean the version of the game or the version of the DLL?

This only check version of game, did you update it to the new version on Steam?
## Post #156
- Username: beelzebub2063
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 01, 2019 3:37 am
- Post datetime: 2019-11-21T20:33:24+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from r00t0 ↑Fri Nov 22, 2019 2:12 am at Fri Nov 22, 2019 2:12 am
>
> 
This only check version of game, did you update it to the new version on Steam?

Has there been any recent updates?
The version of my game is V1.0 build 292.0_64.
## Post #157
- Username: ZacharyS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 21, 2019 4:52 am
- Post datetime: 2019-11-21T22:38:27+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I know this looks pretty dead but is anyone able to help? I think I'm missing something

I've managed to get the models I want but they're exporting with no UV co-ordinates meaning textures don't work!
## Post #158
- Username: beelzebub2063
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 01, 2019 3:37 am
- Post datetime: 2019-11-22T01:54:48+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from ZacharyS ↑Fri Nov 22, 2019 6:38 am at Fri Nov 22, 2019 6:38 am
>
> 
I know this looks pretty dead but is anyone able to help? I think I'm missing something

I've managed to get the models I want but they're exporting with no UV co-ordinates meaning textures don't work!

The UV are there.
Just not as they should be ...

3ds Max 2012 with Unwrap UV Modifier.
Looks like Uv isn't there

[](https://abload.de/image.php?img=1btj19.jpg)

Zoom out aaaand

Taadaaaaa
[](https://abload.de/image.php?img=2xek5k.jpg)
## Post #159
- Username: r00t0
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 24, 2017 7:20 am
- Post datetime: 2019-11-22T12:25:16+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I have version 1.0.296, and was compiled for this, update game on Steam.
## Post #160
- Username: ZacharyS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Nov 21, 2019 4:52 am
- Post datetime: 2019-11-23T20:20:41+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from beelzebub2063 ↑Fri Nov 22, 2019 9:54 am at Fri Nov 22, 2019 9:54 am
>
> 
The UV are there.
Just not as they should be ...

3ds Max 2012 with Unwrap UV Modifier.
Looks like Uv isn't there



Zoom out aaaand

Taadaaaaa

Thank you so much!! This worked perfectly!!
## Post #161
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-06-12T22:54:10+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

What am I doing wrong here? I unpacked the laracroft.drm file but I can't even open anything with the Noesis script.
## Post #162
- Username: monera
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 08, 2020 10:18 am
- Post datetime: 2020-08-08T02:23:02+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Probably a dumb question, but how do I repack the .tiger file? I unpacked it and changed some meshes, now I'd like to repack it so that the game can read the stuff I changed.
## Post #163
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2020-08-09T22:32:16+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hi! It's possible from DRMDumper to load several DRM at the same time to unpack?
## Post #164
- Username: beelzebub2063
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Feb 01, 2019 3:37 am
- Post datetime: 2020-10-23T09:54:36+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from monera ↑Sat Aug 08, 2020 10:23 am at Sat Aug 08, 2020 10:23 am
>
> 
Probably a dumb question, but how do I repack the .tiger file? I unpacked it and changed some meshes, now I'd like to repack it so that the game can read the stuff I changed.

Not possible yet
## Post #165
- Username: ImOK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 25, 2020 9:22 pm
- Post datetime: 2020-10-29T08:49:41+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hi, Gh0stBlade. 
I saw [on another forum](https://www.tombraiderforums.com/showpost.php?p=8221714&postcount=276) you`ve figured out how to extract ingame animation of Lara. 
Are there any news how to achieve it? Does it require some additional scripts, or it can be done without it?
## Post #166
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-02-21T11:37:47+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Could someone get Lara's loose hair when she covers herself in mud later in the game? I can provide the necessary files

> 

Also, I can't seem to find the Tunic of the Exiled Fox outfit anywhere from the 000.tiger archives. I'm assuming the tool hasn't been updated so it lists that particular outfit as an unknown file, shame :/ I could just rip the outfit from the game but unfortuntly the UVs come completely warped as well as the textures have this strange red hue on them, even Lara's head's diffuse texture.

Edit: Nevermind, got it
## Post #167
- Username: Inconnuxdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 14, 2019 9:12 pm
- Post datetime: 2021-04-08T14:55:42+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Hello everyone, I would have a question about the bow failing to find in the shadow files of the tomb raider, I wanted to know where could it be located in the files ? (or if someone already has obj ?)
## Post #168
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2021-04-21T15:41:45+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Inconnuxdark ↑Thu Apr 08, 2021 10:55 pm at Thu Apr 08, 2021 10:55 pm
>
> 
Hello everyone, I would have a question about the bow failing to find in the shadow files of the tomb raider, I wanted to know where could it be located in the files ? (or if someone already has obj ?)

Check wp_tr11_bow_XXXX from bigfile.000

The tools provided in this thread do not work at all on any of the DLC assets, you're going to have to rip them from the game with NinjaRipper like I did the Tunic of the Exiled Fox outfit:
[https://www.deviantart.com/m4zter/art/S ... -871609216](https://www.deviantart.com/m4zter/art/Shadow-of-the-Tomb-Raider-Lara-Croft-Exiled-Fox-871609216)

However, Ninjaripper screws up the UVs so you have to line them up. Use an extracted asset as a reference when adjusting the UVs.
## Post #169
- Username: Kabox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 01, 2019 8:18 pm
- Post datetime: 2021-08-04T11:43:05+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

> Reply from Ekey ↑Thu Oct 25, 2018 1:06 am at Thu Oct 25, 2018 1:06 am
>
> 
Here are the stable versions, maybe after the release of The Forge DLC, some changes will be needed.

SOTTR_TIGERUnpacker_0.0.1_r1: here
SOTTR_DRMDumper_0.0.1_r1: here

Hi Ekey, your tool so well so far.
But how to repack them to file .tiger.
example, I modded one file session 1.dtp, now how to re-pack all of them to .tiger

Any hope ?
## Post #170
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-08-06T13:16:05+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Nope, these tools are only for unpack assets.
## Post #171
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-01-01T03:33:15+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

Does anyone know how to fix the weight contains an out of range bone index issue?  I ran into it with these two models:

[https://www.mediafire.com/file/set2legy ... s.zip/file](https://www.mediafire.com/file/set2legyuz2eeqg/lara_priest_legs.zip/file)
[https://www.mediafire.com/file/kvy2c099 ... o.zip/file](https://www.mediafire.com/file/kvy2c099tepjcw5/lara_priest_torso.zip/file)

Would appreciate any help I can get with this
## Post #172
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2022-01-06T08:02:17+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

I did it, I figured out a fix for the weight contains an out of range bone index issue! 



test1.png (160.31 KiB) Viewed 172 times



I updated the python script from the beginning of this thread (all credit to Gh0stBlade!), every model I've tested so far loads without issue!

[https://www.mediafire.com/file/doz9cau2 ... 3.zip/file](https://www.mediafire.com/file/doz9cau24omyt8j/fmt_TR11_mesh_1_3.zip/file)
## Post #173
- Username: NSIJ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 26, 2022 7:23 pm
- Post datetime: 2022-06-26T11:28:56+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

THANKS
## Post #174
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2023-08-07T13:54:44+00:00
- Post Title: Re: [PC] Shadow of the Tomb Raider Bigfile.000.tiger

How do you load models with skeletons from that game?
