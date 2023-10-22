## Post #1
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-04-13T07:35:51+00:00
- Post Title: Assassins Creed PC .forge files

hey guys, im trying to un/repack the bigfiles of assassins creed   

each .forge file starts with "7363696D697461720019000000160400" -> scimitar header

then lots of zeros before the actually content

however the file seems to be compressed somehow cause there are no files directly accesseble(looked for .dds .mpeg etc)

i have uploaded 2 of the smaller .forge files (DataPC_LoadingRoom2.forge & DataPC_Map_Menu.forge) to speedyshare here: 

[http://www.speedyshare.com/616390380.html](http://www.speedyshare.com/616390380.html) (10.35 MB)

would be cool if someone could take a look at it
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-04-13T10:56:36+00:00
- Post Title: Assassins Creed PC .forge files

It wouldn't make sense to compress dds and mpg since they are already compressed.
They might use an encryption though.
## Post #3
- Username: Razor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 10, 2008 5:55 pm
- Post datetime: 2008-04-15T22:57:18+00:00
- Post Title: Assassins Creed PC .forge files

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2008-04-19T06:47:38+00:00
- Post Title: Assassins Creed PC .forge files

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: grimdoomer
- Rank: advanced
- Number of posts: 70
- Joined date: Sat Mar 22, 2008 3:11 am
- Post datetime: 2008-04-19T23:48:30+00:00
- Post Title: Assassins Creed PC .forge files

Ill take a look now......
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-04-20T09:08:48+00:00
- Post Title: Assassins Creed PC .forge files

Some kind of ADPCM, (probably XBOX ADPCM), however, not a known header.
could probably attach the soundata over a forged RIFF header and it would be playable.
## Post #7
- Username: Delphy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 21, 2008 1:36 am
- Post datetime: 2008-04-20T18:22:34+00:00
- Post Title: Assassins Creed PC .forge files

I've been working on the .forge files this afternoon, and so far they are fairly easy.  I started on a preliminary file format which needs a lot of fleshing out.  Currently it's on my own wiki till I get more details then I'll create an entry on the GFFC.

You can view it here: [http://www.fluffy-demons.net/index.php? ... ile_format](http://www.fluffy-demons.net/index.php?title=.forge_file_format)

Regards
Delphy
## Post #8
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2008-04-26T21:46:40+00:00
- Post Title: Assassins Creed PC .forge files

Doing some work on this format, since Assassin's creed runs on an updated JADE engine.
Hope to have a first data file unpacker done by tomorrow.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-26T21:51:40+00:00
- Post Title: Assassins Creed PC .forge files

Interesting to see that old and new here at the forum combine to tackle this format from a hot new game.  Loverly!!!

Perhaps I should join the fun!
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-04-26T22:09:56+00:00
- Post Title: Assassins Creed PC .forge files

Hey we aren't old 
Just experienced
## Post #11
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2008-04-27T01:51:06+00:00
- Post Title: Assassins Creed PC .forge files

Ok, try this [very, very early beta](http://turvy.dommel.be/Assassin/Animus.rar) of Animus.
Most of the datafiles should be extracted and unpacked successfully (except the ones that state "Hacked patch" and don't match my quick file format writeup, those are prolly screwed  This includes sound files at the moment).
Haven't done any work on the datafiles themselves (they look like what PoP bin files should have looked like, which is a LOT less chaotic) yet (there's only so much work you can do in one night starting from pretty much nothing, after all), but I've already recognised some raw texture data, so texture extraction might be happening soon if I have some more free time.

Checking "dump mode" dumps the original file data, including most of the second header (minus the filename), not checking it extracts and unpacks the datafile.

When I'm slightly more awake, I'll decant my scribbles into something legible and put it up on Delphy's wiki page I guess.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-27T06:30:23+00:00
- Post Title: Assassins Creed PC .forge files

...lol,slightly more awake... Oh, and put it up at the Game File Format Central as well ? 

Well, seems you have "first release" of a tool here, Turfster! (Like we said in them c64-scene days  )

And Rheini, indeed, I meant old as in time at the forum
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-04-27T13:16:40+00:00
- Post Title: Assassins Creed PC .forge files

> Reply from Mr.Mouse
>
> Well, seems you have "first release" of a tool here, Turfster! (Like we said in them c64-scene days  )
First blood! 
Good work, dude.
## Post #14
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2008-04-27T21:43:15+00:00
- Post Title: Assassins Creed PC .forge files

Tadaa!


[New build up](http://assassin.turfster.be/), with updated and fixed file extraction from forge files and texture extraction from the extracted datafiles.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-27T22:10:31+00:00
- Post Title: Assassins Creed PC .forge files

Okay, good. I've got the game, so I tried it on some archives. The stuff Animus extracts is basically some custom game file that in itself is another format.

Image tag:


Hmm, this image does show up. What url and bbcode do you use?
## Post #16
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2008-04-27T22:20:12+00:00
- Post Title: Re: Assassins Creed PC .forge files

[http://www.turfster.be/Assassin/Defend.jpg](http://www.turfster.be/Assassin/Defend.jpg), surrounded by img /img bbcodes
## Post #17
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2008-04-28T01:42:35+00:00
- Post Title: Re: Assassins Creed PC .forge files

[New final build](http://assassin.turfster.be/) for the night (280408-0335) has more bugs fixed and should extract pretty much every texture correctly (as far as I've been able to test anyway).

I could use some betatesters and comments.
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-28T06:13:03+00:00
- Post Title: Re: Assassins Creed PC .forge files

@Image: i think you have configured your server to prevent linking of images by other sites.
## Post #19
- Username: mikehood
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Jun 20, 2006 1:45 pm
- Post datetime: 2008-04-28T06:54:51+00:00
- Post Title: Re: Assassins Creed PC .forge files

but sound ??
## Post #20
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2008-04-28T14:47:26+00:00
- Post Title: Re: Assassins Creed PC .forge files

awesome work turfster!   

i hope you'll manage to extend this to all files and add repacking... i wanna replace every character with the bellydancers
## Post #21
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2008-04-29T23:46:01+00:00
- Post Title: Re: Assassins Creed PC .forge files

Added my writeup for the forge format to the [wiki](http://wiki.xentax.com/index.php?title=Assassin%27s_Creed).
Hope I didn't mess up the copypasting and the bytecount, it pretty much took more time to write than to code the basic extractor
## Post #22
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-04-29T23:58:19+00:00
- Post Title: Re: Assassins Creed PC .forge files

Great work, hope you'll keep creating such tools for the community
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-04-30T08:16:05+00:00
- Post Title: Re: Assassins Creed PC .forge files

Excellent work Turfster!
## Post #24
- Username: BhaaL
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 14, 2008 7:29 pm
- Post datetime: 2008-05-14T14:36:48+00:00
- Post Title: Re: Assassins Creed PC .forge files

Evenin' folks!

I just found this topic at google, trying to poke around the files of Assassins Creed 

First off, great job @ Turfster for Animus, aswell as for Delphy for the first few insights to the .forge format.
I'd like to help a bit there, as I want to get some files out there (and probably back in later). For that matter, is there any IRC Server or anything you guys hang around? If not, any IM Address I could reach you for your current research status?
I am currently analyzing the game's executable, I'm pretty sure we can get some additional info out there 

A short note about myself probably, I started off back with GTA 3, where the game was just out yet, to fiddle around with all its files. Along with a few others, I was amongst the first to build custom maps, after some research custom models, and even custom missions. Then I too a rather long time off game modding, until a friend dragged me into Rush On Seven Episodes, an unofficcial successor to Ragnarok Online long since RO2 was even announced. Prior to the end of the open beta, I found a few others to start off with a PServer for it (AuRose, for those who heard of it probably). Mainly involved in Core development and reverse engineering of the game mechanics, we pretty much reversed and documented every file format used, and wrote tools for most of them. If anyone is interrested, I could possibly put them up in the GFFC some day.
For now, I work as software developer utilizing the latest .NET Technologies with occasional jumps over to unmanaged coding using C++ and Delphi.

Greetings, BhaaL

Edit:
Probably interresting for all those who want the sounds. It seems they use Ogg Vorbis media for that.
Apart from that, they use SQLite, and for whatever reason, they even included the UBISoft MatchMaking system (at least it references their server, with URLs and such).
More on that as I advance.
## Post #25
- Username: plaksnor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 18, 2008 2:37 am
- Post datetime: 2008-05-18T14:13:57+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from BhaaL
>
> Evenin' folks!
...
Edit:
Probably interresting for all those who want the sounds. It seems they use Ogg Vorbis media for that.
Apart from that, they use SQLite, and for whatever reason, they even included the UBISoft MatchMaking system (at least it references their server, with URLs and such).
More on that as I advance.

This topic contains a link to 50 songs ripped from the game (recorded, cause I heard some in-game action sounds), but the quality is pretty good though.
link: [http://forums.ffshrine.org/showthread.php?t=49941](http://forums.ffshrine.org/showthread.php?t=49941)
However, I'm also curious how we're able to extract and convert the sounds from the datafiles.
## Post #26
- Username: BhaaL
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 14, 2008 7:29 pm
- Post datetime: 2008-05-18T15:10:44+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from plaksnor
>
> This topic contains a link to 50 songs ripped from the game (recorded, cause I heard some in-game action sounds), but the quality is pretty good though.
link: http://forums.ffshrine.org/showthread.php?t=49941
However, I'm also curious how we're able to extract and convert the sounds from the datafiles.

Nice catch, but the first post states they are Line In rips from a console. Also states that they are still waiting for the PC release (note the first post was made in January).
## Post #27
- Username: chag
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 20, 2008 6:19 am
- Post datetime: 2008-05-23T05:34:56+00:00
- Post Title: Re: Assassins Creed PC .forge files

hello.  i'm was also working on disassembling the forge files at [http://www.fluffy-demons.net/index.php? ... ile_format](http://www.fluffy-demons.net/index.php?title=.forge_file_format) before turfster released his tool and info.  unfortunately i have not made any progress decompressing the FILEDATA chunks once they are extracted.  i'm wondering if turfster or anyone else would be willing to release their source code and/or some explanations?  i'm trying to disseminate some information from [http://wiki.xentax.com/index.php?title= ... %27s_Creed](http://wiki.xentax.com/index.php?title=Assassin%27s_Creed) but there seems to be a some errors somewhere.

i have a (huge) output dump of my first exploration tool, even though i dont use it anymore, it might possibly be of use.  it covers all the forge files for PC.  uncompressed it's 21.4MB.  message me if you want it.  uggh, how do i attach a text or zip file?????? lame.

================ FORGE: DataPC_Map_Menu.forge ================
file_index_chunk_file_offset: 0x00000416
==== file index chunk ====
number of records: 2
GUESS 0x0000041a: 0x00000001           1 [    1     0] [  1   0   0   0] FP?
GUESS 0x00000426: 0xffffffff          -1 [65535 65535] [255 255 255 255]
GUESS 0x0000042a: 0xffffffff          -1 [65535 65535] [255 255 255 255]
GUESS 0x00000432: 0x00000002           2 [    2     0] [  2   0   0   0] FP?
GUESS 0x00000436: 0x0000043e        1086 [ 1086     0] [ 62   4   0   0] FP?
GUESS 0x0000043a: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
GUESS 0x0000043e: 0x00000002           2 [    2     0] [  2   0   0   0] FP?
GUESS 0x00000442: 0x00000001           1 [    1     0] [  1   0   0   0] FP?
GUESS 0x0000044a: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
GUESS 0x0000044e: 0x00000a62        2658 [ 2658     0] [ 98  10   0   0] FP?
GUESS 0x00000452: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
GUESS 0x00000456: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
GUESS 0x0000045a: 0x00000001           1 [    1     0] [  1   0   0   0] FP?
file_info_chunk_file_offset: 0x0000048e
GUESS 0x00000462: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
fruity_pebbles_chunk_file_offset: 0x00000606
GUESS 0x0000046a: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
data_chunk_file_offset: 0x00000800
GUESS 0x00000472: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
GUESS 0x00000476: 0x00000010          16 [   16     0] [ 16   0   0   0] FP?
GUESS 0x0000047a: 0x000000aa         170 [  170     0] [170   0   0   0] FP?
GUESS 0x0000047e: 0x00001000        4096 [ 4096     0] [  0  16   0   0] FP?
GUESS 0x00000482: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
GUESS 0x00000486: 0x1e3889fe   507021822 [35326  7736] [254 137  56  30]
GUESS 0x0000048a: 0x0018635a     1598298 [25434    24] [ 90  99  24   0] FP?
                 END OF FILE INDEX CHUNK: TELL 0x0000048f
==== Resource Directory Chunk ====
---> RESOURCE 0
        Resource Directory 1 Index 0 offset: 0x0000048f
        GUESS 0x0000048f: 0x74000000  1946157056 [    0 29696] [  0   0   0 116]
        GUESS 0x00000493: 0x17153eae   387268270 [16046  5909] [174  62  21  23]
        GUESS 0x00000497: 0x00664856     6703190 [18518   102] [ 86  72 102   0]
        GUESS 0x0000049b: 0x00000000           0 [    0     0] [  0   0   0   0] FP?
        Resource Directory 2 Index 0 offset: 0x0000048e
        size: 0x000000aa  170
        GUESS 0x00000492: 0x153eae74   356429428 [44660  5438] [116 174  62  21]
        GUESS 0x00000496: 0x66485617  1716016663 [22039 26184] [ 23  86  72 102]
        timestamp: 2008-03-01 07:03:53
        filename: 'GlobalMetaFile'
        DATA OFFSET at 0x00000800
        GUESS 0x00000987: 0x00000010          16 [   16     0] [ 16   0   0   0] FP?
        GUESS 0x0000098f: 0x153eae74   356429428 [44660  5438] [116 174  62  21]
        GUESS 0x00000993: 0x66485617  1716016663 [22039 26184] [ 23  86  72 102]
        TIMESTAMP 2008-03-01 07:03:53
        IDENT?SURE? 00010000000400000001000000000000
        GUESS 0x000009c7: 0x0000     0 [0 0]
        GUESS 0x000009c9: 0x00000005           5 [    5     0] [  5   0   0   0] FP?
        GUESS 0x000009cb: 0x00010000       65536 [    0     1] [  0   0   1   0] FP?
        Counter 0:
        IDENT?SURE? 00000000000003000000010000000000
## Post #28
- Username: BhaaL
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 14, 2008 7:29 pm
- Post datetime: 2008-05-23T13:23:27+00:00
- Post Title: Re: Assassins Creed PC .forge files

Looks interresting. Check my PM for that.

By the way, some of the files (particularly noticed at Present_Room) look like GZip archives. At least they contain some familiar stuff that brings up quite a few GZipped files as result on google - worth a try I'd say.
## Post #29
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-06-10T07:35:41+00:00
- Post Title: Re: Assassins Creed PC .forge files

umm stupid question...i want these files too but i don't have AC for the pc, i can rent it for the 360 though...but the pc can't display xbox 360 game stuff, it treats 360 games as movies so is there any way or any tool i can download freely that will enable me to see 360 game files? any driver or something? anything? i've already tried with mass effect and oblivion but nothing...and since they use the same engine for both the pc and 360 versions of AC they are the same files right?
## Post #30
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-07-26T22:07:37+00:00
- Post Title: Re: Assassins Creed PC .forge files

The sounds are Dialogic VOX ADPCM at 11025hz,  at least the ones linked to earlier in the thread are. 
Here, I converted one: 

[http://www.antiup.net/view/11745/](http://www.antiup.net/view/11745/)


Sorry if this is a bump, But I'd like to know how to extract the sound files so I can convert and use them.  I hope my information was helpful too.
## Post #31
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2008-07-28T00:34:50+00:00
- Post Title: Re: Assassins Creed PC .forge files

Nevermind that, Dump mode does it.

Wow.  this is confusing, Dialogic vox works perfectly for a bunch of them (some vocals and music)  but there are a ton that aren't imported right.   It doesnt make sense to me to use multiple audio formats in one game, but when I try to import a good deal of them I get a two or more incompatible streams error.

and even more, alot of the music imports without me specifying a codec/sample rate, like it's just a standard mp3 file.

It appears alot of the sound files are ogg, but all except for the music aren't recognized.
## Post #32
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2008-12-28T18:38:42+00:00
- Post Title: Re: Assassins Creed PC .forge files

just saw that the new prince of persia is in .forge files too. Tried it on animus but get files that are 0kb big.

I never tried animus on assassins creed but do you get character 3d files from it?
## Post #33
- Username: Shaddy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 08, 2008 7:11 pm
- Post datetime: 2009-05-12T18:34:14+00:00
- Post Title: Re: Assassins Creed PC .forge files

Has anyone made any progress with the .forge files?
## Post #34
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2009-05-13T22:53:43+00:00
- Post Title: Re: Assassins Creed PC .forge files

Try [Maki](http://maki.turfster.be/) with the Animus plugin.
Replacement of datafiles in forge files doesn't work correctly yet.
## Post #35
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2009-05-15T00:47:29+00:00
- Post Title: Re: Assassins Creed PC .forge files

Updated the Animus plugin to also convert (some kinds of) meshes to OBJ files.
## Post #36
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-05-27T17:18:49+00:00
- Post Title: Re: Assassins Creed PC .forge files

Why all these? To make some MODs of the game?

Then what a MOD makin if I can't find in those damned .forge files which is FONT and TEXTs to extract and edit font and text and menu names in the game and pack them again?
## Post #37
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-05-29T13:23:32+00:00
- Post Title: Re: Assassins Creed PC .forge files

Here what I have made out, defined and specified:

Here is two texture file Screenshots from the Russian version of the game (one big table, one small table), which I made by 'TexMod' (which doesn't supports repacking back edited textures of the game).


[http://rapidshare.com/files/238528256/AC_Out.rar](http://rapidshare.com/files/238528256/AC_Out.rar)

Textures definitely are  in one of these:
DataPC.forge
DataPC_Common.forge
DataPC_LoadingRoom2.forge
DataPC_Map_Menu.forge

(I want than ever to find the text of the game, menu text, subtitle text and so on)
Can anyone work it out?
## Post #38
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-06-01T06:28:50+00:00
- Post Title: Re: Assassins Creed PC .forge files

I discovered that in file 'DataPC.forge' exists container 'Game Fix' [178mb], which one contains some texture files.

Maki 1.2 by Turfster, doesn't opens it.

As I've explored extracted files by Maki 1.2, I think textures for font file has to be in 'Game Fix', I hope someone will defeat that
## Post #39
- Username: fedeita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 22, 2009 12:49 am
- Post datetime: 2009-06-04T11:26:01+00:00
- Post Title: Re: Assassins Creed PC .forge files

Turfster i sent to you some pm's take a look at them i need you help please.
## Post #40
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-06-10T15:09:03+00:00
- Post Title: Re: Assassins Creed PC .forge files

Has anyone made any progress with the .forge files?
## Post #41
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-06-10T18:27:33+00:00
- Post Title: Re: Assassins Creed PC .forge files

don't hink so, the only thing i discovered is that if you look at .forge in a mirror it becomes egrof.


....i am tired
## Post #42
- Username: The Mauler
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 21, 2009 1:25 am
- Post datetime: 2009-10-20T19:13:47+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hi !

I've worked on this file format a few months ago (with your well known member Turfster) and i would like to share this because I don't have the time anymore to continue my research.

I've written an application (called Elika like the Turfster's plugin for Maki ) in C# to analyse/extract or create forge archives but it's incomplete. Unfortunately, my code sucks and lacks of optimisations  
You can grab the binaries and sources here (sorry for the comments, they are in french...) : [http://www.mediafire.com/file/4trtqznm4 ... v0.5.1.zip](http://www.mediafire.com/file/4trtqznm4dy/ELIKA_v0.5.1.zip)

Finally, I post here again the structure of the forge archives (my thread on the official Ubisoft's forum hadn't any kind of succes). All of this is based on the published work by Turfster on your wiki and here : [http://www.fluffy-demons.net/index.php? ... ile_format](http://www.fluffy-demons.net/index.php?title=.forge_file_format).

I hope this will be useful for some coders here 

```
Forge Archive
========================================================================

Global structure :
- File header
- Archive header
- One or more fragments

Fragment structure :
- fragment header
- index 1
- index 2
- index 3
- Datablocks (aligned on 2048 bytes to match DVD sector size)

REMS :
- Null padding between Special index and first datablock can be null. If it's not null, it's first byte have a not null random value (unknown). If the archive has multiple fragments, there will be the same byte values for each padding.
- Values are little-endian for all plateform (Verified for PC and Xbox360)

------------------------------------------------------------------------
File Header (29 bytes = 0x1D bytes)
------------------------------------------------------------------------

0000	byte[8]	"scimitar" string
0008	byte	0x00 (probably null character of scimitar string)
0009	int32	engine version (AC : 0x19, PoP : 0x1A)
0013	int64	Archive header pointer
0021	int32	0x00000010 (unknown)
0025	int32	0x00000001 (unknown)

------------------------------------------------------------------------
Archive Header (40 bytes = 0x28 bytes)
------------------------------------------------------------------------

0000	int32	file number in the whole archive
0004	int32	number of records used in index 3 (in all fragments)
0008	int64	0x0000000000000000 (unknown)
0016	int64	0xFFFFFFFFFFFFFFFF (unknown)
0024	int32	maximum files which can be stored in one fragment (in PoP forge archives, this value is always 5000 = 0x00001388 files, in AC this value is exactly the number of file in the archive)
0028	int32	fragment number in the archive
0032	int64	offset of the first fragment

------------------------------------------------------------------------
Fragment header (48 bytes = 0x30 bytes)
------------------------------------------------------------------------

0000	int32	file number in the fragment (can be null)
0004	int32	number of records used in index 3 (in this fragment only)
0008	int64	index 1 pointer
0016	int64	pointer to next fragment or 0xFFFFFFFFFFFFFFFF if this fragment is the last fragment of the archive
0024	int32	index of the first file in the fragment. Each file in the archive have an index : 1st file, index 0, second file index 1 etc... Therefore this value will always be zero in the first fragment and will be equal to 5000 in the second fragment if the fragment capacity is 5000... (we assume all indexes are consecutives values)
0028	int32	index of the last file in the fragment. Therefore, this value will be equal to c*f-1 with c the capacity of one fragment and f the position of the fragment in the archive with a starting by f=1.
0032	int64	index 2 pointer
0040	int64	index 3 pointer

------------------------------------------------------------------------
Index 1 record (16 bytes = 0x10 bytes), one record per datablock
------------------------------------------------------------------------

0000	int64	datablock pointer
0008	int32	identifier 1 (unknown, this value is always 0x000000010 in the first file of any archive named GlobalMetaFile, the game will crash if you change this value, it's probably an identifier used to retrieve the ressources)
0012	int32	length of the datablock

------------------------------------------------------------------------
Index 2 record (188 bytes = 0xBC bytes), one record per datablock
------------------------------------------------------------------------

0000	int32	length of the datablock
0004	int64	identifier 2 (unknown, maybe a checksum, the game still work if we change this value)
0012	int64	0x0000000000000000 (unknown)
0020	int64	0x0000000000000000 (unknown)
0028	int32	next file index value or 0xFFFFFFFF if this is the last record of the archive
0032	int32	previous file index value or 0xFFFFFFFF if this is the first record of the archive
0036	int32	0x00000000 (unknown)
0040	int32	unix style timestamp
0044	byte[128]	ressource name (unused bytes are set to zero), some files are unamed
0172	int64	flag 1 (unknown). Always 0x0000000000000002 for the first record in the archive and 0x0000000000000004 for the other files (except in AC where all files have 0x0000000000000004)
0180	int32	flag 2 (unknown). Always 0x00000002 for the first record in the archive and 0x00000004 for the other files (except in AC where all files have 0x00000004)
0184	int32	flag 3 (unknown). Always 0x00000001 for the first record in the archive and 0x00000000 for the other files (except in AC where all files have 0x00000000)

Maybe, flags are used to differentiate types of files (like unix with directories, block files, regular files...)

Changing flags and the name of a ressource seems to don't have any consequence on the game...

------------------------------------------------------------------------
Index 3 record (164 bytes = 0xA4 bytes), one record per datablock but unused records are zeroyed (for the moment there was only one record used for all archives analysed in AC and PoP)
------------------------------------------------------------------------

0000	int32	maximum file index number of the archive. (equals to file number - 1)
0004	int64	0xFFFFFFFFFFFFFFFF
0012	int64	0xFFFFFFFFFFFFFFFF
0020	byte[128]	null bytes (maybe to store a name)
0148	int32	0x0000000D or 13 (unknown)
0152	int32	0x00000000 (unknown)
0156	int32	0x00000000 (unknown)
0160	int32	0x00000004 (unknown)

Maybe this records store folders. There seems to be unused by the games (you can zeroyed this records and the game will work fine...). The only used record could be the root directory of the archive.

------------------------------------------------------------------------
Datablocks (440 bytes = 0x1b8 bytes)
------------------------------------------------------------------------

0000	byte[8]	"FILEDATA" string (without null end byte)
0009	byte[128]	ressource name (unused bytes are set to zero)
0009	byte[255]	null padding
0391	int32	identifier 1
0395	int32	ressource length
0399	int64	identifier 2
0407	int64	0x0000000000000000
0415	int32	flag 3
0419	int32	flag 2
0423	int64	flag 1
0431	int32	timestamp
0435	int32	0x00000000 (unknown)
0439	byte	0x00 (unknown, probably to realign the data)
0440	byte[]	ressource data

========================================================================
Ressource
========================================================================

Each ressource begin with a 64bit identifier which is the type of the ressource.

List of ressource types (most significant byte first) found in PoP and AC :

0x0000002800011B01 Sound file (AC) (OGG file or ADPCM)
0x000000281000210F Sound file (PoP) (can be OGG file, OGG with truncated header)
0x1004FA9957FBAA33 compressed archive (PoP et AC). Contains textures, scripts...
0x0000000400000001 for all "GlobalMetaFile" (AC et PoP)
0xC043215626E7DB94 some files unamed in second position in forge archives
0x0000002810001F02 some sound files

The ressources are plateform dependant regardless the endianess :
- PC versions have little endianess ressources (including their identifier)
- Xbox version (and probably PS3 version too) have big endianess ressources

========================================================================
Ressource : PoP Sound (40 bytes = 0x28 bytes)
========================================================================

0000	int64	0x0000002810001F02 (identifier)
0008	byte[16]	(unknown, probably an hash value but which algorithm)
0024	int64	0x0000000000000000 (unknown)
0032	int32	0x50000000 (unknown)
0036	int32	0x00000002 (unknown, maybe channel number)
0040	byte[]	data

========================================================================
Ressource : AC Sound (40 bytes = 0x28 bytes)
========================================================================

0000	int64	0x0000002800011B01 (identifier)
0008	int32	(unknown, but never greater than 0xFF)
0012	int32	(unknown, but never greater than 0xFF)
0016	int32	0xFFFFFFFF (unknown)
0020	int32	0x00000000 (unknown)
0024	int64	probably a timestamp but unknown algorithm
0032	int32	0x50000000 (like PoP sound ressource)
0036	int32	encoding used : 0x15F3F950 for OGG stream (with or without header or two ogg files concatenated but unreadables) or 0x355C6300 for IMA-ADPCM (this sound ressources can be read in Audacity with RAW import and selecting VOX-ADPCM and 32000Hz)
0040	byte[]	data

OGG files in AC are probably a kind of archive.

========================================================================
AC OGG Archive (32 bytes = 0x24 bytes)
========================================================================

0000	int32	0x00040008 (unknown)
0004	int32	(unknown)
0008	int32	0x00000002 (unknown, maybe number of files in the archive)
0012	int32	(unknown, always 16 bits values)
0016	int32	0x00000010 (unknown)
0020	int32	0x00002808 (unknown)
0024	int32	(unknown, always 16 bits values)
0028	int32	(probably the offset or the length of the 1st file, always 0x00001400)
0032	int32	(probably the offset or the length of the 1st file, always 0x00001400)
0036	byte[]	data

========================================================================
Compressed ressources
========================================================================

A compressed archive is always composed by 2 concatenated metablocks :
- first metablock contains a compressed index
- second metablock contains compressed data

Each metablock can be uncompressed independently.
------------------------------------------------------------------------
Metablock
------------------------------------------------------------------------

0000	int64	0x1004FA9957FBAA33 (identifier)
0008	int16	0x0001 (unknown)
0010	byte	0x01 or 0x02 : compression algorithm
0011	int16	0x8000 (unknown, probably the maximal size of compressed blocks)
0013	int16	0x8000 (unknown, probably the size of decompressed blocks)
0015	int16	number of LZO blocks
Block table (one record for each block)
XXXX	int16	uncompressed block size
XXXX	int16	compressed block size
Blocks table (one record for each block)
YYYY	int32	(unknown, probably the block checksum)
YYYY	byte[]	data

Algorithms :
0x01	LZO1X_1
0x02	LZO2A

Other algorithm could be used. I have found these string in the executable file of the games :
- LZO1X_999 (can be uncompressed with LZO1X algorithm)
- LZX (based on LZ77 algotirhm)

If a block is uncompressible (means compressed data is bigger than uncompressed data), the block remaind uncompressed. You can localise these blocs which have same value for compressed and uncompressed size. (don't try to uncompress a such bloc or your program will probably crash !).

------------------------------------------------------------------------
Compressed ressources : index
------------------------------------------------------------------------

0000	int16	record number
Records (one record per file)
XXXX	int32	identifier 1 (seems to be an identifier used by the game to retrieve the ressource)
XXXX	int32	length of data (including header)

------------------------------------------------------------------------
Compressed ressources : data
------------------------------------------------------------------------

Datablock are concatenated without padding between them

0000	int32	identifier 2 (seems to be the type of ressource)
0004	int32	length of ressource + 8 bytes (probably to include identifiers 1 and 2)
0008	int32	length of ressource name (without null terminating character !)
0012	byte[]	ressource name (variable length)
XXXX	byte	0x00 or 0x01. If this byte is 0x01, it's followed by a additional table (unkwnown utility) :

YYYY	byte[3]	0x 02 00 00 table header
YYYY	int32	number of records in the table
YYYY	byte[] records in the table

ZZZZ	int32	identifier 1
ZZZZ	int32	identifier 2
ZZZZ	byte[]	data

Table record structure (12 bytes = 0x0C each):
0000	int32	0x00000000 (unknown)
0004	int32	(unknown,maybe flags, there is values like 0x00070000,0x00050000,0x00030000)
0008	int32	(unknown, first record contain big value like 0x18EE, others weaker values like 0x04,0x03...)

Exemple of identifiers 2 :

0x 17 E9 B7 A2	DDS Texture with modified header
0x 60 35 A8 E5	File list or directories ?
0x E7 33 81 AF	Table of identifiers
0x EC 19 78 0E	Parameters (binary)
0x 5E 41 84 09  Probably compiled scripts
0x 29 8C C4 3B	String table
0x 16 1C 43 DA	Script ?
0x D2 F1 E9 23	Function name ?
0x BA 23 4A 82	Animation ?

========================================================================
DDS Texture
========================================================================

0000	int32	dimension 1 (width or height)
0004	int32	dimension 2 (width or height)
0008	int32	0x00000001 (unknown)
0012	int32	0x00000000 or 0x00000005 (unknown)
0016	int64	0x0000000000000001 (unknown)
0024	int64   type of texture (7 = DXT1, 8 = DXT5, maybe other values...)
0032	int64	0x0000000000000000 (unknown)
0040	int32	0x00000001 (unknown)
0044	int32	0x00000001 (unknown)
0048	int32	0x00000001 (unknown)
0052	int32	0x00000007 (unknown)
0056	int64	0x0000000000000002 (unknown)
0064	byte[3]	padding ?
0067	int32	0x13237FE9 (unknown)
0071	int32	linear length of uncompressed texture (from DDS format documentation)
0075	byte[]	data
```
## Post #43
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-21T08:46:57+00:00
- Post Title: Re: Assassins Creed PC .forge files

welcome The Mauler
i hope the nightmare of forge files end here ...
## Post #44
- Username: The Mauler
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 21, 2009 1:25 am
- Post datetime: 2009-10-21T17:12:28+00:00
- Post Title: Re: Assassins Creed PC .forge files

Ty for your message 

I don't know if there is other file format like that but you're right : this is a nightmare !
- All the files seems to reference themself by using identifiers (some files/ressources don't have a name)
- There is many ressources with a well-known format like DDS textures or OGG sounds but their headers are truncated or modified
- The forge archive itself looks more like a file-system (optimised to add files but no to remove them) that an archive...
- All the ressources types are mixed in the archives/datablocs (except for the sounds) : textures, models, texts, animations, compiled code and even piece of C++ source code !

I will try to add some explications here (sorry for my bad english  )

The format is exactly the same in Prince of persia 2008 and Assassin's creed. Only the strategy of adding files is different, in princce of persia, all the archives have a fixed fragment size (5000 files) and have 1 or 2 fragments (eg : for the sound archives where you have aproximately 8000 files). In Assassin's creed, the fragment size is equal to the number of files in the archive and you always have 2 fragments, one with the files and one empty. With my tool, you can change the fragments size/number without any problem to be recognised by the games  The comparaisons between the 2 games help me a lot !

You can change many values without crashing the games even the (probably) checksums but the Identifiers 1 and 2 seems to be important for the game to find the ressources.

I've also analysed the code of the main executable files : when the game start, it search for all the forge archives in it's directory and probably load their indexes. There is a lot of hidden parameters. Some of them refer to test levels and crash the game at startup. Some others doesn't anything ("log" log nothing even in stdout if the game is started in cmd). But I'm not experienced with debugging tools...

```
Exe Command Line (Prince of Persia)
========================================================================

Syntax is
/<name of option>:<parameter1>,<parameter2>,...

Options available are (non exhaustive) :

/startupmenu:off|on
Enable or disable debug menu. Anyway, you cant see the debug menu if bink video are enabled (see /bink)
/log:on|off
Probably to log game activity, but in reality, seems to do nothing
/fullScreen:off|on
No comment :)
/world:<string>
It's the entry point of the game. Default value is "POP0WORLD". Maybe the name of the forge archive DataPC_POP0WORLD.forge (but if you change the filename AND this parameter, the game will don't work too...)
So, it can be too name of the ressource named "POP0WORLD" located in DataPC_POP0WORLD.forge/POP0WORD Compressed Archive/
/fast
If this parameter is not present, the game try to load remote ressources throught an middleware called "perforce". This software seems to be a version manager probably used in the developpement.
/shadows:on|off
Enable/Disable dynamic shadows
/lightmode:normal|?
Probably to modify light renderer
/fardist:1500
Maybe to change dynamic LOD limits, in reality, this parameter seems to have no effect
/mission:<string>
No effect, by default, his value is "pop0_root". Maybe an entry point for debug ?
/localbigfile
Any idea. Maybe to tell to the game to search forge file in the local machine (see /fast)
/noconsole
No effect. If you erase this parameter of the default command line (by modifying the executable) this has no effect. Maybe you must enter a secret key combination to enable a developper console (as in Half-Life)
/langage:<string>
Change langage used (texts and sounds). Possible values : eng,fre,ger,ita,spa depend of your game version).
/resolution:<width>,<height>
Screen resolution

By default, the game is launched with following command line (options are writed in exe file) :
/log:off /fullScreen:on /world:POP0WORLD /fast /shadows:on /lightmode:normal /fardist:1500 /noconsole /bink:on /mission:pop0_root /startupmenu:on /localbigfile

In addition, the executable contains some interesting strings. These are probably other options and values avalaible. Some may crash you game (especially test* options because the associated ressource has probably been removed)

Options found in exe file :

gcmreplay
vsync
help
startupmenu
usesharedobjects
flushdiskcache
nodiskcaching
DynamicMip0MemoryBudget
testvideo
turbodebug
ps3floodmeminfo
smallFakeEntitiesActivationRange
gpuprofiler
customphysmemalloc
defaultallocator
memvalidate
memgearstats
memgeartracker
meminfodump
memall
memdebugfreequeuemaxalloc
memdebugfreequeuesize
memdebug
memtag
memworldstats
memtypestats
memlog
heartbeat
profilerout
sanitycheck
logtime
noconsole
invertcameraverticalaxis
invertcamerahorizontalaxis
testmissiontemproot
testmission
missiontemproot
mission
missions
nochangeworld
loadingrange
startpos
walkthroughsmoketest
walkthroughloading
walkthrough
loadondemand
startanvil
quit
noscimitaroutput
consoleout
darespy
nosoundchangelistprotection
soundsystemdebug
language
fast
gfxassert
useptcoptim
skipmips
msaa
lightmode
transparency
noindirectlight
shadows
postfx
fixedfov
fardist
neardist
worldarea
world
importforge
revert
syncsound
sync
localbigfile
dataservice
maxthread
autoprofileworst
autoprofile
soundengine
nosound

Parameters founds

default
normal
full
4x
2x
none
edge
```


Finally i analysed the DLC of Prince of Persia (XBox version) : all the forge files have the same format but if you put them in the directory of the PC version of the game, the game crashes... Actually, the forge archives are coded in little endian in both XBox and PC plateforms (probably on the PS3 too) but the datablocks are in big endian format on XBox (probably for the PowerPC based architecture).

That's all
## Post #45
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-22T06:23:11+00:00
- Post Title: Re: Assassins Creed PC .forge files

thanks , golden information
## Post #46
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-10-22T07:25:23+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from shekofte
>
> thanks , golden information

Golden?    Plz tell me what that infos explores fo you?   

There's nothing discovered more than is Turfster's Tool doing, so if someone will tell how to extract/import for exmp. just font file texture and text for the subtitles, then I will say that is the really gold info.
## Post #47
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-10-22T07:38:12+00:00
- Post Title: Re: Assassins Creed PC .forge files

take it easy , you must be patient
## Post #48
- Username: Vixez
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 08, 2008 9:29 pm
- Post datetime: 2009-12-16T10:27:38+00:00
- Post Title: Re: Assassins Creed PC .forge files

Turfster's site mentions it can also extract 3D meshes, however, I can't seem to find one.
Can anyone point me to which file contains one (like the one he shows on his site of Damascus)
## Post #49
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-01-03T10:30:52+00:00
- Post Title: Re: Assassins Creed PC .forge files

How can I extract resource files that are sound, voice, text from Assassin's Creed ?

If you have any solution to rip the forge format, Tell me!
## Post #50
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-03-04T15:14:58+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from wuixntx
>
> How can I extract resource files that are sound, voice, text from Assassin's Creed ?

If you have any solution to rip the forge format, Tell me!

+ font files from.

Are anyone gonna rip this hell out? Dudes there is AC2 released!

I know which one more asking about mentioned files of game...
## Post #51
- Username: VenomOC
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Mar 21, 2010 9:01 am
- Post datetime: 2010-04-08T00:05:09+00:00
- Post Title: Re: Assassins Creed PC .forge files

hello, I'm having trouble extracting the files from the DataPC.forge AC2, I'm using maki, but it's a mistake.

Any suggestions?

Thanks.
## Post #52
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-04-14T07:54:38+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from VenomOC
>
> hello, I'm having trouble extracting the files from the DataPC.forge AC2, I'm using maki, but it's a mistake.

Any suggestions?

Thanks.

Peaple, if maki doens't work with Assassin's Creed 2, that means it's not supported yet. And no one knows if it would be even ever, be couse the author has gone so even didn't said I'll be back...

So if you ain't sure do not ask anything about it, until the author replays with news. I want more than anyone to translate this game, nothing more, but I can't do even that with those damned forge.
## Post #53
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2010-04-20T21:17:55+00:00
- Post Title: Re: Assassins Creed PC .forge files

For all the people wanting to look in AC2 forge files and at its textures, try the new [Lucy](http://maki.turfster.be) plugin.
Only had the one forge file someone sent me to work with since I own the PS3 version myself and am not planning on double-dipping on the game, but extraction from forge files should work, as should texture conversion. 
(Since I don't own the PC version, I can't work on file replacement, and I probably won't have much time to take a closer look at the files anyway.)
## Post #54
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-22T10:21:00+00:00
- Post Title: Re: Assassins Creed PC .forge files

What's the status of this?  Unpacking archive?  Unpacking data files?

Anyone know what file contains music?


If it needs a lot work, I might start chipping away at the PC version.  I only like doing the damn near impossible...with good music as a reward.
## Post #55
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2010-04-22T12:24:02+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from FordGT90Concept
>
> What's the status of this?  Unpacking archive?  Unpacking data files?
Unpacking archives and conversion of some datafiles (only textures for ac2, more types of files for ac1)

> Reply from FordGT90Concept
>
> 
Anyone know what file contains music?
I have no idea, since I only got the one file =p
It's probably DataPC_StreamedSounds.forge
## Post #56
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-22T12:36:09+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Turfster
>
> Unpacking archives and conversion of some datafiles (only textures for ac2, more types of files for ac1)
How confident are you that you got it 100% unpacked?  Do you think there's other data unextracted there?


> Reply from Turfster
>
> It's probably DataPC_StreamedSounds.forge
Assassin's Creed II unfortunately doesn't have that file.  Here's the list (including sizes) or .forge files:

```
 83,492,864 DataPC_Abstergo.forge
118,849,536 DataPC_Altair_Memory.forge
 91,619,328 DataPC_extra.forge
 91,619,328 DataPC_extra_dlc.forge
790,888,448 DataPC_Firenze.forge
 95,846,400 DataPC_Hideout.forge
 58,195,968 DataPC_LGS01_Duomo.forge
 69,074,944 DataPC_LGS02_Palazzo_Medic.forge
 53,805,056 DataPC_LGS03_Gimignano.forge
 88,702,976 DataPC_LGS04_Novella.forge
 63,143,936 DataPC_LGS05_Forli_Citadel.forge
 41,353,216 DataPC_LGS06_Frari.forge
 42,991,616 DataPC_LGS07_San_Marco.forge
 64,978,944 DataPC_LGS08_ArsenalShipya.forge
 33,619,968 DataPC_LGS09_Monteregionni.forge
 65,765,376 DataPC_LGS10_Visitazione.forge
120,061,952 DataPC_Mountains.forge
158,695,424 DataPC_Roma.forge
  2,031,616 DataPC_TitleScreen.forge
303,136,768 DataPC_Toscana.forge
698,089,472 DataPC_Venezia.forge
262,045,696 DataPC_Villa.forge
390,987,776 DataPC_Wetlands.forge
 95,813,632 DataPC_WhiteRoom.forge
```

I'm thinking there's a pretty good chance it isn't in .forge files.  I doubt the music is embeded in with the levels because, for example, combat music is usually shared.  At the same time, shared music could be in the generically named files and, as someone in this thread suggested, they might be usiner URIs (Uniform Resource Identifiers) to load resources transparent of what file it is actually in.


The other best guess is the SoundData dir which contains the following files:

```
251,339,055 sounds_ita.pck
554,694,991 sounds_sfx.pck
```

Music generally doesn't have a language associated with it though unless the music is in the ITA pck.  The entire game takes place in Italy so the music is very Italian in nature.  ENG would have the voice overs and SFX containing the typical sound effects.

.PCK has AKPK for identifying characters (first 4 bytes).  It clearly has a 24 byte array following the header.  ita.pck has some 12168 entries in that table.  There are some uncompressed RIFF WAVEs and more than one table structure in here.



Are you saying no one ever extracted the music out of Assassin's Creed (the original)?
## Post #57
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2010-04-22T18:10:28+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from FordGT90Concept
>
> Turfster wrote:Unpacking archives and conversion of some datafiles (only textures for ac2, more types of files for ac1)
How confident are you that you got it 100% unpacked?  Do you think there's other data unextracted there?
Oh there's shitloads of data I haven't decoded yet, but all files should get unpacked fine.

> Reply from FordGT90Concept
>
> 
The other best guess is the SoundData dir which contains the following files:
Code: Select all245,208,708 sounds_eng.pck
251,339,055 sounds_ita.pck
554,694,991 sounds_sfx.pck
Music generally doesn't have a language associated with it though unless the music is in the ITA pck.  The entire game takes place in Italy so the music is very Italian in nature.  ENG would have the voice overs and SFX containing the typical sound effects.

.PCK has AKPK for identifying characters (first 4 bytes).  It clearly has a 24 byte array following the header.  ita.pck has some 12168 entries in that table.  There are some uncompressed RIFF WAVEs and more than one table structure in here.
sounds_sfx.pck looks like a winner here, datapc_streamedsounds also contained both sfx and music.

> Reply from FordGT90Concept
>
> 
Are you saying no one ever extracted the music out of Assassin's Creed (the original)?
I only wrote an extractor for the ogg streams and have a half-working decoder for the others, but decubisnd should be able to extract quite a few sound files from Assassin's creed.
## Post #58
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-22T21:23:36+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Turfster
>
> sounds_sfx.pck looks like a winner here, datapc_streamedsounds also contained both sfx and music.
Do you know if anything exists to handle .pck format?
## Post #59
- Username: VenomOC
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Mar 21, 2010 9:01 am
- Post datetime: 2010-04-22T23:16:00+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hello friend Turfster, this new plugin (Lucy) is working perfectly here, but he is not converting the file I want.

I know you said that in AC-II it only converts the textures, but is not there a way to convert the file I want? It is a simple text file (txt) that I need are those, both are within the DataPC.forge:

LocalizationPackage_English
LocalizationPackage_English_Subtitles

Are these two files I want, both are text files, I say this because in 2008 Prince Of Persia is like that.

Please, if you can solve this, be grateful.

Hugs.
## Post #60
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2010-04-23T00:18:38+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from VenomOC
>
> Hello friend Turfster, this new plugin (Lucy) is working perfectly here, but he is not converting the file I want.

I know you said that in AC-II it only converts the textures, but is not there a way to convert the file I want? It is a simple text file (txt) that I need are those, both are within the DataPC.forge:

LocalizationPackage_English
LocalizationPackage_English_Subtitles

Are these two files I want, both are text files, I say this because in 2008 Prince Of Persia is like that.

Please, if you can solve this, be grateful.

Hugs.
Actually, Ubi changed the localization packages in AC2. 
In POP2008, they were pretty easy to convert. In AC2, they're encrypted in some way I haven't figured out yet (haven't really looked at it long and hard yet), but they're definitely not "simple" text files 

> Reply from FordGT90Concept
>
> Turfster wrote:sounds_sfx.pck looks like a winner here, datapc_streamedsounds also contained both sfx and music.
Do you know if anything exists to handle .pck format?
No, but if you upload say the first 5 or 10 megs of it, I could take a quick look at it.
## Post #61
- Username: VenomOC
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Mar 21, 2010 9:01 am
- Post datetime: 2010-04-23T00:35:18+00:00
- Post Title: Re: Assassins Creed PC .forge files

Ok friend, I'll be waiting for your progress to convert these files.

Hugs.
## Post #62
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-23T04:57:23+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Turfster
>
> No, but if you upload say the first 5 or 10 megs of it, I could take a quick look at it.
I'll document it myself then. 


Edit: It uses URIs (Uniform Resource Identifiers) and practically all offsets are relative.  This is going to be a pain. 

Oh, and Assassin's Creed II was coded by Ubisoft Montreal and it shows: Most of the acroynms (AKPK, BKHD, DIDX, HIRC, STMG) make no sense in English.  They probably stand for something in French.  


Edit: Every acronym is followed by a 32-bit length of that section (this is true without exception).  Found more too: DATA (uncompressed data, used exclusively for short .wav files), STID, and I doubt that's all.


The URIs generally aren't in order either.  I don't think you'd get far with only 10 MiB of it.
## Post #63
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-23T12:07:56+00:00
- Post Title: Re: Assassins Creed PC .forge files

Assasins creed 2 uses the WWise audio platform, no french.
## Post #64
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-23T12:56:13+00:00
- Post Title: Re: Assassins Creed PC .forge files

All those four-letter combos I posted are known WWise identifiers?  If so, is there already a program to handle them?
## Post #65
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-24T03:03:33+00:00
- Post Title: Re: Assassins Creed PC .forge files

Someone posted this script for PCK before somewhere on these forums, I don't recall where. aluigi probably wrote it -- though it was made for the XBox 360 version of the game, so I had to fix the script for PC.

And yes, sounds are wwise format and you can use ww2ogg to convert.

```

Endian little

# Main header
IDString "AKPK"
Get HEADER_TOTAL_SIZE long

Get HEADER_UNK1 long
If HEADER_UNK1 != 1
   Print "Strange HEADER_UNK1 = %HEADER_UNK1%, may crash..."
EndIf

Get HEADER_EXTRA_DATA_SIZE long
Get SIZE_OF_BLOCK1 long
Get SIZE_OF_BLOCK2 long

SavePos TEMP_POS
Math TEMP_POS += HEADER_EXTRA_DATA_SIZE
GoTo TEMP_POS

# Block 1
Set EXTRACT_BLOCK_BASE_PATH string "1"
CallFunction EXTRACT_BLOCK

# Block 2
Set EXTRACT_BLOCK_BASE_PATH string "2"
CallFunction EXTRACT_BLOCK

# Function to extract a block
# Set EXTRACT_BLOCK_BASE_PATH to the path where the files should be extracted before calling
StartFunction EXTRACT_BLOCK
   Get BLOCK_NUM_ENTRIES long

   For I = 0 < BLOCK_NUM_ENTRIES
      # Read the file entry
      Get ENTRY_ID long
      Get ENTRY_BLOCK_SIZE long
      Get ENTRY_SIZE long
      Get ENTRY_UNK1 long
      If ENTRY_UNK1 != 0
         Print "Strange ENTRY_UNK1 = %ENTRY_UNK1%, may crash..."
      EndIf
      Get ENTRY_OFFSET_IN_BLOCKS long
      Get ENTRY_UNK2 long
      If ENTRY_UNK2 != 0
         If ENTRY_UNK2 != 1
            Print "Strange ENTRY_UNK2 = %ENTRY_UNK2%, may crash..."
         EndIf
      EndIf

      # Extract
      Set PATH EXTRACT_BLOCK_BASE_PATH
      String PATH += "/"
      String PATH += ENTRY_ID

      Set OFFSET ENTRY_OFFSET_IN_BLOCKS
      Math OFFSET *= ENTRY_BLOCK_SIZE

      Log PATH OFFSET ENTRY_SIZE
   Next I
EndFunction
```
## Post #66
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-24T03:41:30+00:00
- Post Title: Re: Assassins Creed PC .forge files

That would unpack the file but it wouldn't do anything about all the subtypes I listed.  I'll look at the app you mentioned to see if it does...

ww2ogg looks like it will only handle the RIFF WAVE files which is useful but, from the looks of it, that is only like 2% of the PAK files.  There's a whole lot more there.
## Post #67
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-24T04:58:27+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from FordGT90Concept
>
> That would unpack the file but it wouldn't do anything about all the subtypes I listed.  I'll look at the app you mentioned to see if it does...

ww2ogg looks like it will only handle the RIFF WAVE files which is useful but, from the looks of it, that is only like 2% of the PAK files.  There's a whole lot more there.Uh, huh? subtypes? the "subtypes" you're talking about are part of the WWise format stuff, and are not really interesting (except where the RIFF data is embedded), those are mostly in the "1" directory. I converted all of the "2" directory with ww2ogg with no issues (or most of, don't recall, I think the only exception were already wav format?).
## Post #68
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-24T05:46:50+00:00
- Post Title: Re: Assassins Creed PC .forge files

It is block 1 that has all the BKHD, DIDX, HIRC, STMG, DATA, etc. subtypes.  So block 1 apparently contains a sort of compiled script and block 2 contains the audio?

I wouldn't say block 1 isn't interesting because it is.  I never seen a file format that uses names like that to define what is following.  Is it worth investigating further? Probably not because there is little to gain by doing so.
## Post #69
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-24T19:35:36+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from FordGT90Concept
>
> I never seen a file format that uses names like that to define what is following.It's actually quite a common method.

[http://en.wikipedia.org/wiki/Interchange_File_Format](http://en.wikipedia.org/wiki/Interchange_File_Format)

> Reply from FordGT90Concept
>
> Is it worth investigating further? Probably not because there is little to gain by doing so.It's WWise related data (soundbank information, etc). Some of the files in the 1 directory have some sound data but otherwise it's nothing interesting if you just want to get sound files.
## Post #70
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-24T22:34:44+00:00
- Post Title: Re: Assassins Creed PC .forge files

Learn something new everyday.


Oh, right, there are some RIFFs in block 1.  I think that's what I'll try to do: extract all RIFFs from both blocks.
## Post #71
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-26T04:45:07+00:00
- Post Title: Re: Assassins Creed PC .forge files

I extracted 29,478 RIFF files out of block 2 and all successfully converted to OGG with ww2ogg.exe.  Most of the music is in the sfx file.


Edit: Extracted 3,178 RIFF files out of block 2 (BKHD) of sounds_eng.pck and had a listen to 6 of them: two were a fire crackling, two were a horses galloping (different speeds), one was something creeking loudly, and the last one was the voice overs for one of the major plot speeches by the main character.  Not too likely to find any music in those so I think my pck research ends there.
## Post #72
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-04-26T12:32:29+00:00
- Post Title: Re: Assassins Creed PC .forge files

All music is in the Sounds_sfx pck.
## Post #73
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-04-26T14:17:12+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from OrangeC
>
> All music is in the Sounds_sfx pck.Sort by filesize after converting and the large files should mostly be music. That's how I found the music track I was after.
## Post #74
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-04-27T02:48:14+00:00
- Post Title: Re: Assassins Creed PC .forge files

Dear Turfster can you make support skinning data?
## Post #75
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-04-27T02:55:40+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Rick
>
> OrangeC wrote:All music is in the Sounds_sfx pck.Sort by filesize after converting and the large files should mostly be music. That's how I found the music track I was after.
Same.  There are 4 music tracks in the language files (eng and ita).  Either works as they are the same.  Other than that, most are in SFX.
## Post #76
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2010-04-27T23:25:33+00:00
- Post Title: 

> Reply from Tosyk
>
> Dear Turfster can you make support skinning data?
You mean loading files back into the forge files to make changes to the models in the game? 
Not going to happen. Since I don't have the PC version of the game, the plugin will only do exporting.


Anyway, there's a new version [up](http://maki.turfster.be) with some minor changes. 
There were a few datafiles in the forge files that didn't extract correctly before + I've added really rudimentary support for the pck files.
It's just plain simpler to run the pck files through something like my generic file ripper tho.

Anyway, I'll be working on and off on adapting my 3D mesh code to also convert simple AC2 meshes in the near future.
## Post #77
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2010-04-30T01:14:11+00:00
- Post Title: 

New version [up](http://maki.turfster.be), now supports conversion of at least some  3D mesh types
## Post #78
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-04-30T08:56:53+00:00
- Post Title: 

How can I translate the subtitles into other languages ?
## Post #79
- Username: Dankichi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 01, 2010 2:48 am
- Post datetime: 2010-04-30T21:18:04+00:00
- Post Title: 

Hi there 

Sorry to bother, but I was looking forward to get the assassin's creed (one) textures, and I've been searching, and I can't get it... I tried to use Maki, and it did a lot of things wich... i dont understand xD

Since the original creator of this tool is on this forum, can someone explain me in simple non-professional words who to get them in usable file ? Or just how to use maki correctly, i havent been able to find a tutorial anywhere... 

Thx by advance
## Post #80
- Username: DMCdesigns
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Sep 16, 2009 4:56 am
- Post datetime: 2010-05-01T01:24:14+00:00
- Post Title: 

Try with TexMod. It's really easy to work with it. The file formats are dds, bmp, jpg, png, etc.
## Post #81
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2010-05-01T09:37:29+00:00
- Post Title: 

> Reply from Dankichi
>
> Hi there 

Sorry to bother, but I was looking forward to get the assassin's creed (one) textures, and I've been searching, and I can't get it... I tried to use Maki, and it did a lot of things wich... i dont understand xD

Since the original creator of this tool is on this forum, can someone explain me in simple non-professional words who to get them in usable file ? Or just how to use maki correctly, i havent been able to find a tutorial anywhere... 

Thx by advance
It's pretty straightforward.
Two things in advance: 
1) Never ever turn dump mode on if you're just a normal user
2) Turn on autoconvert single datafiles in the options tab

On to the tutorial.

 Install Maki and the relevant plugin Animus in this case, then run it. Note that if you have both Animus and Lucy plugins installed, you'll have to force the relevant plugin in the options tab by checking 'force plugin' in the 'plugin selector' area and then selecting Animus from the drop down box.
 Open a forge file in the Archives tab.   I'll use datapc_loadingroom2.forge in my example
 Check the file(s) you want to extract, rightclick and select extract.   Cell00010_DataBlock
 Open the extracted file in in the datafiles tab.   You'll get a list of 95 things
 Now you can extract whatever you want to. If it's a known block type, it'll convert (or at least give more info).
You can speed up searching by using Find..., which jumps to the next instance of whatever you typed or Select... which will select all blocks matching whatever you type, so entering for example 'Texture data' (without quotes) will select all textures in the file.
For our example, select the 4 "texture data" at the end and extract them. You should now have 4 dds files in your assassin's creed directory
## Post #82
- Username: Dankichi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 01, 2010 2:48 am
- Post datetime: 2010-05-01T11:28:28+00:00
- Post Title: 

DMC design --> Working good, Thx for the trick  It's not easy to catch the texture you're watching, and it takes time, but it work 

Turfster --> I've been doing all this, and indeed it works fine, I have only one thing, i cannot find directly the textures... I've been using "find" like you said, but it didnt ticked the texture datas... I just have the aminus plug-in, since im just I can extract everything and choose afterward but I guess it will cost time and space :p

In fact im just searching for the textures of the city, do you know where they are, it will reduce my search 

By the way, did someone allready made some "texture package", for the main cities ? It would save me some time 

Anyway, with both texmod and Maki I think I can start working on it, thx for you advices
## Post #83
- Username: xjohnx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Mar 04, 2010 8:06 pm
- Post datetime: 2010-05-13T23:10:13+00:00
- Post Title: 

[quote="FordGT90Concept"]I extracted 29,478 RIFF files out of block 2 and all successfully converted to OGG with ww2ogg.exe.  Most of the music is in the sfx file.
quote]

Extracted the pck 'sfx' file using Maki's Lucy plugin which gave me a load of wav files but when i tried to convert using wav2ogg, the resulting ogg files are still unplayabe?
14kb wav file converts to 1kb ogg file.
## Post #84
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-05-20T15:00:24+00:00
- Post Title: 

> Reply from Turfster
>
> Tosyk wrote:Dear Turfster can you make support skinning data?
You mean loading files back into the forge files to make changes to the models in the game? 
Not going to happen. Since I don't have the PC version of the game, the plugin will only do exporting.
Oh no no no, do not pack extracted files back into the game! I meant another.
You create a very wonderful tools, but all the 3D objects are converted to obj format. My question is: can you make the conversion of 3D models of characters, along with the bones? Link 3D model and bones I call skinning data.

Thank you for all you do!
## Post #85
- Username: Stevan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 26, 2010 7:21 am
- Post datetime: 2010-05-26T07:07:58+00:00
- Post Title: 

Did someone figured out how is possible to create a new translation. Did anyone encrypted translation file?

I extracted both English files from Data, but I can't read it.

Little help?
## Post #86
- Username: VenomOC
- Rank: beginner
- Number of posts: 23
- Joined date: Sun Mar 21, 2010 9:01 am
- Post datetime: 2010-05-26T13:57:32+00:00
- Post Title: 

Hello friend Stevan, I am also trying to translate it, but so far nothing yet. I'm waiting to get Turfster break the encryption of texts.
## Post #87
- Username: Stevan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 26, 2010 7:21 am
- Post datetime: 2010-05-26T15:26:56+00:00
- Post Title: 

Is there any prediction when is possible to be that?
## Post #88
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-05-31T09:11:33+00:00
- Post Title: 

I've been fooling around with Maki and the Animus Plugin, trying to Extract some Files from Assassin's Creed (1) to use in other Games.

Right now, I'm just trying to find a good way to look at the Files and see what's there.  I followed the Instructions earlier on about the Loading Room 2 and Texture Data, but I don't see any Files in my Game Folder.  I don't know where these Extracted Files are going, or if they're really even Extracting.

Anyways, if anyone could help me out with that it would be Wonderful!
## Post #89
- Username: Jeremonster
- Rank: n00b
- Number of posts: 12
- Joined date: Mon May 31, 2010 4:12 pm
- Post datetime: 2010-06-12T07:54:14+00:00
- Post Title: 

Has there been any progress on this at all?  I'd be very Interested in some News.

I've got a lot of great Ideas for Mods that use the Meshes and Skins from this Game.
## Post #90
- Username: nightsqual05
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 26, 2010 11:38 am
- Post datetime: 2010-08-13T21:03:06+00:00
- Post Title: 

> Reply from Turfster
>
> New version up, now supports conversion of at least some  3D mesh types

thanks for the tool turfster.
anyway where can i find the 3d model of ezio auditore de firenze?
on what .forge?
## Post #91
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2010-08-14T06:01:26+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from VenomOC
>
> Hello friend Stevan, I am also trying to translate it, but so far nothing yet. I'm waiting to get Turfster break the encryption of texts.
Hey guys, extracted text is zlib compressed, so need someone to decompress it, it isn't encrypted at all.
## Post #92
- Username: grotesque
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Mar 18, 2010 4:12 am
- Post datetime: 2010-08-14T13:27:00+00:00
- Post Title: Re: Assassins Creed PC .forge files

I extract all "wav" from .pck of Assassin's Creed 2, and now I have to convert these file in ogg with ww2ogg.
Can help me for make a .bat file?
## Post #93
- Username: 360
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 06, 2010 7:40 am
- Post datetime: 2010-09-13T11:12:16+00:00
- Post Title: Re: Assassins Creed PC .forge files

i'm really freaking out...i tried to extract the sounds_sfx.pck with several methods.

1st - filestripper
2nd - quickbms with rick's script
3rd - makilucy

all did extract me (RIFF?)WAV files.

after that i used ww2ogg. it seems to convert all files to OGG but i cannot listen to them.
neither adobe audition nor windows media player can playback them.
other ogg files can be played back without a problem...so i guess there must be something wrong with the converted (RIFF?)WAV files.

i used a batch file: for %%a in (*.*) do ww2ogg "%%a" --full-setup
while converting it says "parse error invalid codebook identifier"
anyway it does output me the unplayable ogg files...

can someone tell me what i'm doing wrong?

i'm really desperate...been trying it for hours without a pleasant result.

thanks a lot,
360
## Post #94
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-11-28T09:08:29+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from grotesque
>
> I extract all "wav" from .pck of Assassin's Creed 2, and now I have to convert these file in ogg with ww2ogg.
Can help me for make a .bat file?

Can y really listen something files.wav which extracted by the FileStripper.exe or Maki.exe?
If u so, how do you do?
## Post #95
- Username: hammerhorn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 23, 2011 10:31 pm
- Post datetime: 2011-01-23T14:42:29+00:00
- Post Title: Re: Assassins Creed PC .forge files

Guys,

I have tried using MAKI with Assassin's Creed 2 files but all I get when I try to extract anything is !Aborting... Possible Sound File.  Could anyone tell me how to remedy this... I really want to dive into this content and try playing around with replicating some of the locations in Maya and then in the cryEngine.

Please help!
## Post #96
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-01-23T19:02:41+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from hammerhorn
>
> Guys,

I have tried using MAKI with Assassin's Creed 2 files but all I get when I try to extract anything is !Aborting... Possible Sound File.  Could anyone tell me how to remedy this... I really want to dive into this content and try playing around with replicating some of the locations in Maya and then in the cryEngine.

Please help!

Do you have the Lucy plugin installed?  If you have more than one plugin, check under Options; Plugin Selector.  Select the Lucy plugin from the dropdown and check Force plugin.  Close and restart Maki.  Should work after that.
## Post #97
- Username: hammerhorn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 23, 2011 10:31 pm
- Post datetime: 2011-01-24T14:21:16+00:00
- Post Title: Re: Assassins Creed PC .forge files

That was the problem... thanks so much!
## Post #98
- Username: hammerhorn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 23, 2011 10:31 pm
- Post datetime: 2011-01-25T03:28:13+00:00
- Post Title: Re: Assassins Creed PC .forge files

Out of curiosity... once you've extracted an archive and you have a TON of the texture files that are simply .tga inside their wrapper... is there a way to batch extract all the data-files instead of selecting them one-by-one with Maki to extract each one?  It gets to be a painful process when you have 400-1000 data files?  Perhaps I have not caught on to some of the process, if there is any, to automate this.
## Post #99
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-01-25T07:55:14+00:00
- Post Title: Re: Assassins Creed PC .forge files

The texture files are actually header-less DDS files.  I haven't been able to find anything other than that.

Unfortunately, I don't think there is a way to accomplish what you want.  Its pretty much a trial and error process.  The forge file has never been fully discovered, I've been working on it off and on since AC1 came out for the PC and I'm only slightly ahead of where Turfster managed to get in a much shorter period of time.

My explorer took a slightly different approach, but doesn't really do much more than Maki.
## Post #100
- Username: hammerhorn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 23, 2011 10:31 pm
- Post datetime: 2011-03-19T23:07:58+00:00
- Post Title: Re: Assassins Creed PC .forge files

I'm trying to extract all of the Jerusalem and Damascus forge files and their datafiles.  I'm using MAKI.  When extracting some of the data files i'm getting the following error with MAKI:

Exception EFOpenError in Module Animus.dll at 00016762

The extraction process freezes on this archive and fails... You can pick through the gazillion files there but I was wondering fi there is any solve to this.  I'm working with PC forge file and was curious if the forge files packed on the PS3 or 360 are any more reliable unpacking?

Any information would be helpful... thanks!

I'm trying to replicate some of the city in the cryengine...
## Post #101
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-03-20T03:36:30+00:00
- Post Title: Re: Assassins Creed PC .forge files

Can you be more specific as to which datafile(s) are causing the error?
## Post #102
- Username: fedeita
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri May 22, 2009 12:49 am
- Post datetime: 2011-03-27T09:40:33+00:00
- Post Title: Re: Assassins Creed PC .forge files

what about brotherhood?
## Post #103
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-03-27T16:20:55+00:00
- Post Title: Re: Assassins Creed PC .forge files

So far, images/textures.  Model files are slightly different from previous versions, but I am working on it.
## Post #104
- Username: salut333
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2011 11:07 pm
- Post datetime: 2011-03-27T20:42:23+00:00
- Post Title: Re: Assassins Creed PC .forge files

Any updates on Assassin's Creed Brotherhood?
## Post #105
- Username: kosmoski
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Feb 20, 2010 6:53 pm
- Post datetime: 2011-03-27T21:07:33+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Turfster
>
> New version up, now supports conversion of at least some  3D mesh types

Hi guys i have a problem with textures. "Maki"  crashes when texture is exported. Any ideas? I need them raiden for the raiden 

[](http://img809.imageshack.us/i/raidenu.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)
## Post #106
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-03-27T23:18:37+00:00
- Post Title: Re: Assassins Creed PC .forge files

Not sure why Maki is crashing on a texture, but it definitely does, and does not export the DDS properly.

I can export the texture properly...



But unfortunately at this time I am not yet ready to release ForgeX for public use.

But if you tell me what textures you need for the Raiden suit and what you used to get the model file, I'll provide the textures.
## Post #107
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-03-28T02:30:45+00:00
- Post Title: Re: Assassins Creed PC .forge files

Well I was slightly wrong.  Model files aren't that much different.  A slight difference with X, Y, Z, but it still looks halfway decent in 3DSMax...



Still plugging away...
## Post #108
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-28T04:05:27+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from MichaelDarkAngel
>
> Well I was slightly wrong.  Model files aren't that much different.  A slight difference with X, Y, Z, but it still looks halfway decent in 3DSMax...Hi, where i can download xforge tool?
## Post #109
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-03-28T04:21:17+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Tosyk
>
> Hi, where i can download xforge tool?

> Reply from MichaelDarkAngel
>
> But unfortunately at this time I am not yet ready to release ForgeX for public use.

Sorry.  Nowhere... yet...
## Post #110
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-28T04:23:43+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from MichaelDarkAngel
>
> Sorry.  Nowhere... yet...  only bad news today, we'll waiting your progress anyway
## Post #111
- Username: salut333
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2011 11:07 pm
- Post datetime: 2011-03-28T11:23:40+00:00
- Post Title: Re: Assassins Creed PC .forge files

Can someone make a program whick properly exports AC: Brotherhood files and textures?
## Post #112
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2011-03-28T22:04:38+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from salut333
>
> Can someone make a program whick properly exports AC: Brotherhood files and textures?

Currently textures are no problem.  Models are still a little iffy.  Any other files in particular?

As soon as I clean up some code and make sure some of the files that I can read with AC1 and POP are the same with AC2 and Brotherhood I may do a beta release.
## Post #113
- Username: salut333
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2011 11:07 pm
- Post datetime: 2011-03-28T22:22:58+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from MichaelDarkAngel
>
> salut333 wrote:Can someone make a program whick properly exports AC: Brotherhood files and textures?

Currently textures are no problem.  Models are still a little iffy.  Any other files in particular?

As soon as I clean up some code and make sure some of the files that I can read with AC1 and POP are the same with AC2 and Brotherhood I may do a beta release.
Thats great news.
BTW, Altair armor i mean most of the models  wont export properly...
## Post #114
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-03-30T02:48:24+00:00
- Post Title: Re: Assassins Creed PC .forge files

Only have the first game, and still a lot of catch-up work to do at the moment.  i'll compare against the other games once i get the chance.



Once i work out a more reliable way to dump the data, i can hopefully move a bit quicker.....Have only mapped out a few types so far, so i still have a good number of structures to investigate and cross reference.
## Post #115
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-30T04:00:42+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from revelation
>
> Only have the first game, and still a lot of catch-up work to do at the moment.  i'll compare against the other games once i get the chance.



Once i work out a more reliable way to dump the data, i can hopefully move a bit quicker.....Have only mapped out a few types so far, so i still have a good number of structures to investigate and cross reference.
Omg, that is great news, will you support bones and weighting too?
## Post #116
- Username: salut333
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2011 11:07 pm
- Post datetime: 2011-04-16T08:33:15+00:00
- Post Title: Re: Assassins Creed PC .forge files

Updates?
## Post #117
- Username: quadcoremax
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Jan 30, 2011 8:33 pm
- Post datetime: 2011-04-20T13:32:28+00:00
- Post Title: Re: Assassins Creed PC .forge files

Really good work guys ! Thx for your efforts...

If that's succeed, I'll might use your tools to port the skinned meshes to Racer, we now can do a lot with animations & scripting...

Actually, been a pionner in this domain....only for Racer (racer.nl)
I'm brainstorming about bringing something completely new like AC2 BH + GTA....in a huge map !
## Post #118
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-05-10T09:32:10+00:00
- Post Title: Re: Assassins Creed PC .forge files

sooooo......................any support for the brotherhood models yet?(michaeldarkangel)
Bring on the xforge who cares if it is beta, it looks awesome
## Post #119
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-05-13T17:28:42+00:00
- Post Title: Re: Assassins Creed PC .forge files

I wanna translate AC2. Anyway to do this?
## Post #120
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-05-15T12:36:01+00:00
- Post Title: Re: Assassins Creed PC .forge files

any support for lucy(maki) with brotherhood textures yet?
## Post #121
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2011-05-25T18:34:59+00:00
- Post Title: Re: Assassins Creed PC .forge files

[viewtopic.php?f=10&t=6617](http://forum.xentax.com/viewtopic.php?f=10&t=6617)
ForgeX - MichaelDarkAngel
## Post #122
- Username: Beagle Boy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 29, 2011 11:01 pm
- Post datetime: 2011-06-29T16:16:53+00:00
- Post Title: Re: Assassins Creed PC .forge files

Nothing for correct extraction of .forge files? Please, Anyone?
Maki 1.2 and dll Lucy, is almost perfect. 
But I Need of LocalizationPackage_English LocalizationPackage_English_Subtitles, anyone decrypt it, please.
## Post #123
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-06-30T04:20:43+00:00
- Post Title: Re: Assassins Creed PC .forge files

Up!
## Post #124
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2011-08-21T15:39:40+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hi all,

I did some research on ACB's forge files, here's the result.

It's an unfinished tool (and will probably stay unfinished).

What it can do:
- view/export textures as DDS/PNG
- view/export LocalizationPackage files as *.txt
- view most Models - very simple viewer using WPF, no proper texture support (uses first texture which has 'Diffuse' in its name...)
- view/export data of unknown types as hex/binary

What it can't do:
- no Model export, no import...

some facts:
- most id type fields (EntryId, ...) are CRC32 hashes
- lots of data is stored as duplicate in the same forge (probably console specific optimization)
- I started to decode some other types: Skeleton, Material, MaterialTemplate, ... see source code.

The tool needs .net 4 (client profile) and should be compilable with VC# Express 2010

If you want to use some of the code in your own tool/program go ahead...

I won't give any support or can be held responsible for damage - USE AT OWN RISK

[](http://imageshack.us/photo/my-images/38/meshviwer.jpg/)

Uploaded with [ImageShack.us](http://imageshack.us)
[forgelib_release.7z](https://xentaxbackup.github.io/file/4651_forgelib_release.7z)
## Post #125
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2011-08-21T21:27:45+00:00
- Post Title: Re: Assassins Creed PC .forge files

Thanks for tool but we are waiting txt import features
## Post #126
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2011-08-22T06:57:21+00:00
- Post Title: Re: Assassins Creed PC .forge files

I don't think thats possible... as I mentioned in my previous reply: each forge file works independently (has all the resources needed to render the level and sometimes the same resource is stored multiple times in the forge file). You would need to replace all instances of said resource to change things completely.

It's a bit like cooked upk packages in Unreal Engine games where a single texture/mesh/... file can be contained in 10 different upk files...
## Post #127
- Username: TimurKo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 27, 2011 1:43 am
- Post datetime: 2011-08-27T14:58:28+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hi, i'm new! 
DerPlaya, Thank you for your tool! You are the Best!
However, I have a trouble. Recently, Assassin's Creed Brotherhood English version was release for Mac(I have a Mac), and for PC(Russian version) it was release has long ago.
I has copied the sound files from a PC and transferred them on a MAC, but subtitles(menu text, mission text) were in English. However I found Russian subtitles inside Brotherhood forge file, although the release was reported about several languages​​, but certainly not about the Russian.
Whether there has any possibility of editing Forge files, in order to replace the contents from LocalizationPackageRussian to LocalizationPackageEnglish?
Or maybe there's another way?
Sorry for my English
## Post #128
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2011-08-27T16:49:03+00:00
- Post Title: Re: Assassins Creed PC .forge files

The forge files contain localization stuff for languages which are not officially supported, but some of them are obviously incomplete (hungarian, turkish, ...). I don't know if 
the russian version is complete and if it would be enough to switch localization packages... the russian version also uses a different font. 

If there is an official Russian version, I would try to force the game to switch using a different language. On PC this is done through registry changes (HKEY_LOCAL_MACHINE\SOFTWARE\Ubisoft\Assassin's Creed Brotherhood\language). 

If the mac forge files are identical to the PC ones (and the russian version is identical to the international version) it could work. 

I don't have a Mac so I can't tell you how to do this on Mac...

Either way, Implementing write support for forge files is not on my todo list... I'm usually just interested in extracting stuff to see how developers did stuff.
## Post #129
- Username: TimurKo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 27, 2011 1:43 am
- Post datetime: 2011-08-27T18:45:14+00:00
- Post Title: Re: Assassins Creed PC .forge files

Thank you for reply, DerPlaya!

> Reply from DerPlaya
>
> The forge files contain localization stuff for languages which are not officially supported, but some of them are obviously incomplete (hungarian, turkish, ...). I don't know if the russian version is complete and if it would be enough to switch localization packages... the russian version also uses a different font.

Officially Russian version is full complete, at least on PC. However on MAC It did not was released with other languages. And on PC version also contains the font files. My guess is that they are contains in the original version.

Maybe some file is responsible for language, and I want to find him. As far as I can see, spoken language is defined by the presence of files in a folder SoundData, such as sounds_rus.pck and so on. And the subtitle language is defined in the file localization.lang. Originally it defined the following languages​​: English, French, Italian, German, Spanish, Dutch, Danish, Norwegian, Swedish, but after I removed it there was only English. But as it is edited, I did not understand.
## Post #130
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2011-08-27T20:59:28+00:00
- Post Title: Re: Assassins Creed PC .forge files

What happens when you replace the forge files with the PC ones... Multiple forge files contain the same localization packages (console optimization for better dvd seek speeds...) so you should probably replace all files (and localization.lang). I don't know if this works but if it doesn't then editing the forge files wouldn't either because there's some kind of file integrity check in place...

edit: about the font: even if it's there, the information which font to use isn't stored in the LocalizationPackage file, so if you managed to replace LocalizationPackage_English with one with russian text. the game would still use the en/us font and you would only get garbage text...
## Post #131
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-08-27T23:42:58+00:00
- Post Title: Re: Assassins Creed PC .forge files

BTW, I'm interesting in translating the series.
Is there anyway to do it?
## Post #132
- Username: TimurKo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 27, 2011 1:43 am
- Post datetime: 2011-08-28T15:42:47+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from qabRieL
>
> BTW, I'm interesting in translating the series.
Is there anyway to do it?
I'm also trying to find it. But for this we must understand how to edit FORGE files and localization.lang.

> Reply from DerPlaya
>
> What happens when you replace the forge files with the PC ones...
Happens crash the game when start. I've already tried it. The thing is that FORGE files on MAC and PC differ not only content but also in size. 

> Reply from DerPlaya
>
> You should probably replace all files (and localization.lang).
It doesn't work. I've already tried it too. When replace the localization.lang from PC version, Russian language in the menu is still not provided. I do not know why it doesn't work, maybe it has links to the location, which are lost.

> Reply from DerPlaya
>
> edit: about the font: even if it's there, the information which font to use isn't stored in the LocalizationPackage file, so if you managed to replace LocalizationPackage_English with one with russian text. the game would still use the en/us font and you would only get garbage text...
This means, must find the files that store this information.

And if there are tools that are just FORGE edit files? And is it possible find descriptions localization.lang file?
## Post #133
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2011-08-28T16:30:49+00:00
- Post Title: Re: Assassins Creed PC .forge files

- the localization.lang file is a bit to small to get any useful information out of it.

- I did research some other file types but haven't found any hints about localization other than files of FireData type: those are Adobe Flash files with a different header and used for all the ui stuff (maps, animus desktop, minigames, ...). 
You can't edit those files as far as I know - my tool extracts those files as *.swf and you can use a tool like Sothink SWF Decomiler (to see ActionScript code)...

- the reason why mac and pc files are different is probably the structure of meshes and shaders, they probably  use OpenGL and GLSL compiled shaders on mac / Direct3D and HLSL shaders on PC...

One other possibility is that available languages are hardcoded into the game executable.
## Post #134
- Username: TimurKo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 27, 2011 1:43 am
- Post datetime: 2011-08-28T19:56:41+00:00
- Post Title: Re: Assassins Creed PC .forge files

Also about fonts. I noticed that FontDescriptor Russian font is present in every Package File of FireData. Look:


> Reply from DerPlaya
>
> I did research some other file types but haven't found any hints about localization other than files of FireData type: those are Adobe Flash files with a different header and used for all the ui stuff (maps, animus desktop, minigames, ...). 
You can't edit those files as far as I know - my tool extracts those files as *.swf and you can use a tool like Sothink SWF Decomiler (to see ActionScript code)...
Thanks for hint!
I opened the FireData file and found that there:


Now it remains to find file, from the which this function is called.
## Post #135
- Username: TimurKo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Aug 27, 2011 1:43 am
- Post datetime: 2011-08-28T23:53:41+00:00
- Post Title: Re: Assassins Creed PC .forge files

This is what I found in ActionScript:

And while I do not understand what this command, I not know how to program in Flash Lite: (
## Post #136
- Username: DerPlaya
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Mar 22, 2010 5:41 am
- Post datetime: 2011-08-29T13:50:14+00:00
- Post Title: Re: Assassins Creed PC .forge files

fscommand in normal Flash is an external command provided for example by javascript... in this case it's probably a call to a native function in the game executable...

Is the font file only present in PC forge files or also in mac files? If it's not in the mac files then there's probably no reliable way of telling the game to use a different font... If it is, there must be a way to switch languages by editing some kind of configuration file...

You could try to replace the LocalizationPackage_* and font types but implementing write support in my tool wouldn't be trivial, you could try Maki (linked somewhere in this thread) or try to implement write support yourself (which means implementing lzo compression, I didn't use an external lzo.dll but implemented decompression by modifying the c source from minilzo...)

You would also have to edit the russian LocalizationPackage file (If you look in CompressedLocalizationPackage.cs, there's an enum defining which language the package is for)

I don't have any time or desire to change my tool, but you can use the source if you want to do it yourself...
## Post #137
- Username: qabRieL
- Rank: veteran
- Number of posts: 124
- Joined date: Wed Aug 04, 2010 10:58 pm
- Post datetime: 2011-09-10T21:16:05+00:00
- Post Title: Re: Assassins Creed PC .forge files

Anyone else thinking to contuine to tool?
I really need to inject translated text into game.
## Post #138
- Username: GamerSuper
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Sep 09, 2010 7:36 pm
- Post datetime: 2011-09-12T19:44:51+00:00
- Post Title: Re: Assassins Creed PC .forge files

does this tool work with xbox360 version of the game?
## Post #139
- Username: novemba
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 10, 2011 5:17 am
- Post datetime: 2011-09-15T14:15:25+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from qabRieL
>
> Anyone else thinking to contuine to tool?
I really need to inject translated text into game.

Me too... Any news?
## Post #140
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2011-09-16T15:24:03+00:00
- Post Title: Re: Assassins Creed PC .forge files

When i used maki i get text file but only compressed. And another way for me was to find the font file (probably dds format).

Guys do you know which file is the font file? You don't need to dict the game to use different language file, you've to modify original ones, - chars on font texture to your lang chars and that's it, but this is only works with any chars in ASCII codepage not for Unicode ones.
## Post #141
- Username: lionking7
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 16, 2011 11:08 pm
- Post datetime: 2011-10-19T02:25:09+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hi i cant find the program Maki and the pluguins to downlaod,the turf site is out..someone have to share?And you guys could convert the animations to other format?Because ineed the animations.thanks  ,and great work Turf,are people like you who make the world better.
## Post #142
- Username: novemba
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 10, 2011 5:17 am
- Post datetime: 2011-10-19T15:58:21+00:00
- Post Title: Re: Assassins Creed PC .forge files

Maki only can open and replace Assassin's creed pc .forge files. Are you sure?
## Post #143
- Username: lionking7
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Oct 16, 2011 11:08 pm
- Post datetime: 2011-10-21T19:55:46+00:00
- Post Title: Re: Assassins Creed PC .forge files

no this program extract the files,but i want the animation files do you guys got the animations files and can convert to the other file?Ineed the horse animation.thanks
## Post #144
- Username: blasphemie
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 24, 2011 12:15 am
- Post datetime: 2011-10-24T14:12:46+00:00
- Post Title: Re: Assassins Creed PC .forge files

Will the tool be updated? Cause i want to be able to edit the mesh files
## Post #145
- Username: novemba
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 10, 2011 5:17 am
- Post datetime: 2011-10-25T13:26:20+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from blasphemie
>
> Will the tool be updated? Cause i want to be able to edit the mesh files
No, i want to say it. The tool didn't update.(Maki)
## Post #146
- Username: salut333
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2011 11:07 pm
- Post datetime: 2011-11-02T09:54:59+00:00
- Post Title: Re: Assassins Creed PC .forge files

Will anyone continue to upgrade this tool, we really need it for AC:Brotherhood:D , and the AC:Revelations is almost out.
## Post #147
- Username: revelation
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Tue May 13, 2008 12:15 am
- Post datetime: 2011-11-02T21:55:44+00:00
- Post Title: Re: Assassins Creed PC .forge files

i am planning to, but i am backlogged a bit, and trying to rework my available time, heh.
## Post #148
- Username: novemba
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 10, 2011 5:17 am
- Post datetime: 2011-11-04T16:57:10+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hi all,
My friend created a replace .dll for AC:Brotherhood and AC2 to Maki.

Here is the dll and program:

http://www.multiupload.com/A3MKWDVOLO

What can it do?

Extraction and Replace.(%90)
## Post #149
- Username: Ryu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 25, 2011 4:47 am
- Post datetime: 2011-11-25T14:29:51+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hey guys, any chance to get music from the forge-files in AC2 / ACB / or the just released ACR? I want t extract the music from "Dens Defense"-forge file in Revelations and am unable to hear the music... the player plays the extracted files i extracted with maki when named ".wav" but its just some odd noise and not music... any ideas?
## Post #150
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-25T14:39:50+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from novemba
>
> Hi all,
My friend created a replace .dll for AC:Brotherhood and AC2 to Maki.

Here is the dll and program:

http://www.multiupload.com/A3MKWDVOLO

What can it do?

Extraction and Replace.(%90)

Who made this dll ? It freez on some percents on x360 version. Could we contact person who made it please ?
## Post #151
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-11-25T21:02:00+00:00
- Post Title: Re: Assassins Creed PC .forge files

Please anyone who was working on this tool or DLL ??? I'm also willing to pay something who gonna make this tool works with x360 files....
## Post #152
- Username: novemba
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Sep 10, 2011 5:17 am
- Post datetime: 2011-11-26T10:37:09+00:00
- Post Title: Re: Assassins Creed PC .forge files

I didn't create that .dll and I don't know who did it. Also it doesn't work on xbox360 files. So wait for news michalss.
## Post #153
- Username: ufo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 02, 2011 12:18 am
- Post datetime: 2011-12-01T17:07:02+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from michalss
>
> Please anyone who was working on this tool or DLL ??? I'm also willing to pay something who gonna make this tool works with x360 files....

mailto:[turfster@gmail.com](mailto:turfster@gmail.com)
## Post #154
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-02T05:47:04+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from ufo
>
> michalss wrote:Please anyone who was working on this tool or DLL ??? I'm also willing to pay something who gonna make this tool works with x360 files....

mailto:turfster@gmail.com

I did try to send the email to him a few times. No respons  It is very sad becasue this is one of the game where it should be in all languages
## Post #155
- Username: ufo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 02, 2011 12:18 am
- Post datetime: 2011-12-02T06:40:02+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from michalss
>
> 
I did try to send the email to him a few times. No respons  It is very sad becasue this is one of the game where it should be in all languages

He is here too:[Turfster 's Profile](http://forum.xentax.com/memberlist.php?mode=viewprofile&u=905)
## Post #156
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-12-02T06:54:35+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from ufo
>
> michalss wrote:
I did try to send the email to him a few times. No respons  It is very sad becasue this is one of the game where it should be in all languages 

He is here too:Turfster 's Profile

Thx allready contact him on email and PM, so ill just wait and see....
## Post #157
- Username: DarkFeather
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 17, 2011 4:06 pm
- Post datetime: 2011-12-17T08:19:54+00:00
- Post Title: Re: Assassins Creed PC .forge files

Any progress on the ACB or ACR versions?
## Post #158
- Username: qwzzz
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 13, 2011 1:29 am
- Post datetime: 2011-12-17T18:13:08+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hi, is there no way to extract ACR 3d models, i needed to create a clay sculpture
## Post #159
- Username: carbint
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 12, 2010 1:25 am
- Post datetime: 2012-01-18T22:09:05+00:00
- Post Title: Re: Assassins Creed PC .forge files

Maki can be used with the AC2 plugin to extract complete meshes from ACB and ACR, I have done this myself, but no textures get extracted  If only it would be updated to include textures for these games, that's all that needs doing!!! Please, someone?
## Post #160
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2012-02-08T17:02:45+00:00
- Post Title: Re: Assassins Creed PC .forge files

For those of you who don't already know, Revelations is out. 
So does maki still work or what? I haven't used it since asscreed2, but it should work for in time though right? Or does it?
If my memory serves correctly, there were some texture issues with brotherhood, and apparently there is some texture issues with revelations as well.

Please also check out this thread as well, its a different tool with (imo) a better ui, it fixed the texture error(for brotherhood).
NOT MY THREAD BTW. No self promoting here.
[viewtopic.php?f=10&t=6617](http://forum.xentax.com/viewtopic.php?f=10&t=6617)
## Post #161
- Username: djguro
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 20, 2012 4:13 am
- Post datetime: 2012-03-20T18:44:35+00:00
- Post Title: Re: Assassins Creed PC .forge files

any news? 

I want to translate this game Assasin's Creed 2 subtitles into Georgian. 

Where Subtitles are? in what file? 

and how to open it?

my group, AcidLabz is translating games into Georgian. so far we translated Max Payne 2, Stalker - Shadow of chernobyl and more than 5 games.. It's my idea to translate AC2 too. 

Can anyone help?
## Post #162
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-04-21T07:26:16+00:00
- Post Title: Re: Assassins Creed PC .forge files

novemba : Please can you upload here tools? I want translate this game into russian on xbox 360.
michalss: Do you have answer from Turfster ?
Sorry for my bad english   
Please help
## Post #163
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-04-21T09:38:17+00:00
- Post Title: Re: Assassins Creed PC .forge files

Anybody ?
## Post #164
- Username: Beagle Boy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 29, 2011 11:01 pm
- Post datetime: 2012-06-15T13:21:00+00:00
- Post Title: Re: Assassins Creed PC .forge files

The Translating of AC2 is possible, say this because the brazilians succeeded.

The proof: [http://www.tribogamer.com/jogos/traducoes/?id=148](http://www.tribogamer.com/jogos/traducoes/?id=148)

Bye.
## Post #165
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2012-06-16T17:36:18+00:00
- Post Title: Re: Assassins Creed PC .forge files

Yeah, we did it here in Brazil.
If anyone interested, pls tell me you country and a link to your translation group.

Tools can be shared...

See you!
## Post #166
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2012-06-17T13:13:29+00:00
- Post Title: Re: Assassins Creed PC .forge files

I just only had extracted the text for translation.
I am working on this format and I will try to make complete tools right after I will done my translation of the text.
As soon as it would be ready, I promise to release them!

If there will be any updates, I'll come in periodically and update the post.
## Post #167
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-17T17:59:08+00:00
- Post Title: Re: Assassins Creed PC .forge files

Is it possible unpack/repack forge file ?
Can somebody upload tools ?
THX
## Post #168
- Username: RMac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 18, 2012 2:43 am
- Post datetime: 2012-06-17T18:56:37+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hi. Can someone teach me how to extract fonts from AC2?
Really want the font from Russian localization ^_^
## Post #169
- Username: RMac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 18, 2012 2:43 am
- Post datetime: 2012-06-18T10:52:09+00:00
- Post Title: Re: Assassins Creed PC .forge files

Extracted LocalizationPackage_Russian and LocalizationPackage_Russian_Subtitles. What program i can open these files with?
## Post #170
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-19T15:18:04+00:00
- Post Title: Re: Assassins Creed PC .forge files

I want it too .
## Post #171
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-23T12:50:25+00:00
- Post Title: Re: Assassins Creed PC .forge files

Gocha : when you will relase tools to unpack/repack .forge file.
## Post #172
- Username: xboxmaniac
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Apr 21, 2012 3:19 pm
- Post datetime: 2012-06-25T13:25:40+00:00
- Post Title: Re: Assassins Creed PC .forge files

PLEASE
## Post #173
- Username: Delacroix
- Rank: advanced
- Number of posts: 70
- Joined date: Thu Sep 15, 2011 9:12 pm
- Post datetime: 2012-08-30T05:24:13+00:00
- Post Title: Re: Assassins Creed PC .forge files

I'm also very interested. Mainly due to Prince of Persia (2008), both X360 and PC versions of the forge format. I do hope you'll eventually release your tools, Gocha.
## Post #174
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2012-08-30T10:07:48+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Delacroix
>
> I'm also very interested. Mainly due to Prince of Persia (2008), both X360 and PC versions of the forge format. I do hope you'll eventually release your tools, Gocha.
also me
## Post #175
- Username: Azurfan
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Jun 24, 2010 5:12 am
- Post datetime: 2012-10-13T16:20:39+00:00
- Post Title: Re: Assassins Creed PC .forge files

I'm also very interested in this tools, especially to get my hands on the console exclusive Epilogue DLC files or Prince of Persia.
## Post #176
- Username: montcer9012
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Jul 14, 2012 2:14 pm
- Post datetime: 2012-11-04T23:50:38+00:00
- Post Title: Re: Assassins Creed PC .forge files

Anything yet?
## Post #177
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2012-11-28T22:44:02+00:00
- Post Title: Re: Assassins Creed PC .forge files

Is it possible to update FogeX to be compatible with AC3?
## Post #178
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2012-11-30T23:38:40+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from milance941
>
> Is it possible to update FogeX to be compatible with AC3?
 As soon as I get AC3 I will be doing so.

Thanks for your interest.
## Post #179
- Username: milance941
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Sep 06, 2011 1:00 am
- Post datetime: 2012-12-01T18:07:50+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from MichaelDarkAngel
>
> milance941 wrote:Is it possible to update FogeX to be compatible with AC3?
 As soon as I get AC3 I will be doing so.

Thanks for your interest.
Thank you very much for making it 
ForgeX is the best
## Post #180
- Username: TopSecretOfficial
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 17, 2011 3:45 pm
- Post datetime: 2013-01-06T01:07:53+00:00
- Post Title: Re: Assassins Creed PC .forge files

I have been curious...  Since Ubisoft refuses to release the AC:B "Copernicus Conspiracy" DLC on PC or XBox, does anyone thing that it would be possible to convert the PS3 .Forge files from the DLC package to a format which the PC edition of the game would be able to pick up and use?
## Post #181
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2013-11-18T14:57:30+00:00
- Post Title: Re: Assassins Creed PC .forge files

[viewtopic.php?f=35&t=10968](http://forum.xentax.com/viewtopic.php?f=35&t=10968)

Okay, just directing your attention to this thread. Of course, we could just go on in this one, but it seems despite all these years no-one managed to create a tool that would allow localization? I can't believe it, didn't the Brazilians do it? Or was that just AC2?
## Post #182
- Username: pigtail
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 01, 2014 12:28 am
- Post datetime: 2014-10-31T16:36:57+00:00
- Post Title: Re: Assassins Creed PC .forge files

> I have been curious... Since Ubisoft refuses to release the AC:B "Copernicus Conspiracy" DLC on PC or XBox, does anyone thing that it would be possible to convert the PS3 .Forge files from the DLC package to a format which the PC edition of the game would be able to pick up and use?

Some crazy person has converted the files to PC. People are already playing it. I won't post the link but google: "Copernicus campaign done"

Source tools (some from here) were released by hacker. Documents forge scripting engine in some detail. ^^
## Post #183
- Username: nanujoshi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 10, 2014 7:34 am
- Post datetime: 2014-11-10T12:04:19+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from Turfster
>
> Dankichi wrote:Hi there 

Sorry to bother, but I was looking forward to get the assassin's creed (one) textures, and I've been searching, and I can't get it... I tried to use Maki, and it did a lot of things wich... i dont understand xD

Since the original creator of this tool is on this forum, can someone explain me in simple non-professional words who to get them in usable file ? Or just how to use maki correctly, i havent been able to find a tutorial anywhere... 

Thx by advance 
It's pretty straightforward.
Two things in advance: 
1) Never ever turn dump mode on if you're just a normal user
2) Turn on autoconvert single datafiles in the options tab

On to the tutorial.

 Install Maki and the relevant plugin Animus in this case, then run it. Note that if you have both Animus and Lucy plugins installed, you'll have to force the relevant plugin in the options tab by checking 'force plugin' in the 'plugin selector' area and then selecting Animus from the drop down box.
 Open a forge file in the Archives tab.   I'll use datapc_loadingroom2.forge in my example
 Check the file(s) you want to extract, rightclick and select extract.   Cell00010_DataBlock
 Open the extracted file in in the datafiles tab.   You'll get a list of 95 things
 Now you can extract whatever you want to. If it's a known block type, it'll convert (or at least give more info).
You can speed up searching by using Find..., which jumps to the next instance of whatever you typed or Select... which will select all blocks matching whatever you type, so entering for example 'Texture data' (without quotes) will select all textures in the file.
For our example, select the 4 "texture data" at the end and extract them. You should now have 4 dds files in your assassin's creed directory

hi 

first of all thanks for the instruction above it was a big help there was one more thing i wanted to add a question is it possible to extract altair model as a whole in blender? if so how and what plugins do i need. and what about animation is that possible as well?

i know it's a really old post but any help would be great.
thank you
## Post #184
- Username: nanujoshi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 10, 2014 7:34 am
- Post datetime: 2014-11-10T23:46:16+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from The Mauler
>
> Ty for your message 

I don't know if there is other file format like that but you're right : this is a nightmare !
- All the files seems to reference themself by using identifiers (some files/ressources don't have a name)
- There is many ressources with a well-known format like DDS textures or OGG sounds but their headers are truncated or modified
- The forge archive itself looks more like a file-system (optimised to add files but no to remove them) that an archive...
- All the ressources types are mixed in the archives/datablocs (except for the sounds) : textures, models, texts, animations, compiled code and even piece of C++ source code !

I will try to add some explications here (sorry for my bad english  )

The format is exactly the same in Prince of persia 2008 and Assassin's creed. Only the strategy of adding files is different, in princce of persia, all the archives have a fixed fragment size (5000 files) and have 1 or 2 fragments (eg : for the sound archives where you have aproximately 8000 files). In Assassin's creed, the fragment size is equal to the number of files in the archive and you always have 2 fragments, one with the files and one empty. With my tool, you can change the fragments size/number without any problem to be recognised by the games  The comparaisons between the 2 games help me a lot !

You can change many values without crashing the games even the (probably) checksums but the Identifiers 1 and 2 seems to be important for the game to find the ressources.

I've also analysed the code of the main executable files : when the game start, it search for all the forge archives in it's directory and probably load their indexes. There is a lot of hidden parameters. Some of them refer to test levels and crash the game at startup. Some others doesn't anything ("log" log nothing even in stdout if the game is started in cmd). But I'm not experienced with debugging tools...
Code: Select all========================================================================
Exe Command Line (Prince of Persia)
========================================================================

Syntax is
/<name of option>:<parameter1>,<parameter2>,...

Options available are (non exhaustive) :

/startupmenu:off|on
Enable or disable debug menu. Anyway, you cant see the debug menu if bink video are enabled (see /bink)
/log:on|off
Probably to log game activity, but in reality, seems to do nothing
/fullScreen:off|on
No comment :)
/world:<string>
It's the entry point of the game. Default value is "POP0WORLD". Maybe the name of the forge archive DataPC_POP0WORLD.forge (but if you change the filename AND this parameter, the game will don't work too...)
So, it can be too name of the ressource named "POP0WORLD" located in DataPC_POP0WORLD.forge/POP0WORD Compressed Archive/
/fast
If this parameter is not present, the game try to load remote ressources throught an middleware called "perforce". This software seems to be a version manager probably used in the developpement.
/shadows:on|off
Enable/Disable dynamic shadows
/lightmode:normal|?
Probably to modify light renderer
/fardist:1500
Maybe to change dynamic LOD limits, in reality, this parameter seems to have no effect
/mission:<string>
No effect, by default, his value is "pop0_root". Maybe an entry point for debug ?
/localbigfile
Any idea. Maybe to tell to the game to search forge file in the local machine (see /fast)
/noconsole
No effect. If you erase this parameter of the default command line (by modifying the executable) this has no effect. Maybe you must enter a secret key combination to enable a developper console (as in Half-Life)
/langage:<string>
Change langage used (texts and sounds). Possible values : eng,fre,ger,ita,spa depend of your game version).
/resolution:<width>,<height>
Screen resolution

By default, the game is launched with following command line (options are writed in exe file) :
/log:off /fullScreen:on /world:POP0WORLD /fast /shadows:on /lightmode:normal /fardist:1500 /noconsole /bink:on /mission:pop0_root /startupmenu:on /localbigfile

In addition, the executable contains some interesting strings. These are probably other options and values avalaible. Some may crash you game (especially test* options because the associated ressource has probably been removed)

Options found in exe file :

gcmreplay
vsync
help
startupmenu
usesharedobjects
flushdiskcache
nodiskcaching
DynamicMip0MemoryBudget
testvideo
turbodebug
ps3floodmeminfo
smallFakeEntitiesActivationRange
gpuprofiler
customphysmemalloc
defaultallocator
memvalidate
memgearstats
memgeartracker
meminfodump
memall
memdebugfreequeuemaxalloc
memdebugfreequeuesize
memdebug
memtag
memworldstats
memtypestats
memlog
heartbeat
profilerout
sanitycheck
logtime
noconsole
invertcameraverticalaxis
invertcamerahorizontalaxis
testmissiontemproot
testmission
missiontemproot
mission
missions
nochangeworld
loadingrange
startpos
walkthroughsmoketest
walkthroughloading
walkthrough
loadondemand
startanvil
quit
noscimitaroutput
consoleout
darespy
nosoundchangelistprotection
soundsystemdebug
language
fast
gfxassert
useptcoptim
skipmips
msaa
lightmode
transparency
noindirectlight
shadows
postfx
fixedfov
fardist
neardist
worldarea
world
importforge
revert
syncsound
sync
localbigfile
dataservice
maxthread
autoprofileworst
autoprofile
soundengine
nosound

Parameters founds

default
normal
full
4x
2x
none
edge

Finally i analysed the DLC of Prince of Persia (XBox version) : all the forge files have the same format but if you put them in the directory of the PC version of the game, the game crashes... Actually, the forge archives are coded in little endian in both XBox and PC plateforms (probably on the PS3 too) but the datablocks are in big endian format on XBox (probably for the PowerPC based architecture).

That's all

is there any way one could extract animation ?? from forge files ??
## Post #185
- Username: portgas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 13, 2014 3:42 am
- Post datetime: 2014-11-12T19:43:23+00:00
- Post Title: Re: Assassins Creed PC .forge files

Any chance of extracting Unity's forge files?
## Post #186
- Username: Darkkk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 03, 2015 9:48 am
- Post datetime: 2016-08-31T19:52:58+00:00
- Post Title: Re: Assassins Creed PC .forge files

Hello,
I am interested in commercial service by someone who can write a aplication that will allow me to export voice dialogues from Assasin's Cred 1 files (I mean DataPC_StreamedSounds.forge)
Or maybe someone could already do that? Maybe he could then tell how ?

Specifically, I am interested in the files with version from my country. Just in case, here I throw a full file (124mb). Maybe someone will look at it with kindly eye 

[https://www.dropbox.com/s/xkf1lw28cs7zq ... forge?dl=0](https://www.dropbox.com/s/xkf1lw28cs7zq8k/DataPC_StreamedSoundspol.forge?dl=0)

Greetings
## Post #187
- Username: Darkkk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 03, 2015 9:48 am
- Post datetime: 2016-09-29T11:33:05+00:00
- Post Title: Re: Assassins Creed PC .forge files

Refresh. Cost isn't important. I can pay for that in US dollar, euro, or any currency from countries of the European Union Square (or Russian rubles). Does anyone would be able to take this? Please let me know.
## Post #188
- Username: iambosh
- Rank: advanced
- Number of posts: 61
- Joined date: Sat Oct 04, 2014 12:22 pm
- Post datetime: 2016-12-02T17:00:44+00:00
- Post Title: Re: Assassins Creed PC .forge files

anyone have a link? I wanna mess around with the forge files for STEEP and Rainbow Six Siege
## Post #189
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2016-12-06T19:12:03+00:00
- Post Title: Re: Assassins Creed PC .forge files

> Reply from iambosh
>
> anyone have a link? I wanna mess around with the forge files for STEEP and Rainbow Six Siege
same
## Post #190
- Username: volfin
- Rank: ultra-veteran
- Number of posts: 452
- Joined date: Sun Jul 06, 2014 1:30 pm
- Post datetime: 2016-12-07T17:21:56+00:00
- Post Title: Re: Assassins Creed PC .forge files

The tool discussed here went on to become ARchive_neXt:

[viewtopic.php?f=10&t=6617](http://forum.xentax.com/viewtopic.php?f=10&t=6617)

It works with just about ever A.C. game. however, Rainbow 6: Siege support has never been finished.   If you hack the INI file you can enable his beta support, but it only dumps raw files.
## Post #191
- Username: Mayadesk
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 15, 2019 6:32 am
- Post datetime: 2019-11-14T20:02:35+00:00
- Post Title: Re: Assassins Creed PC .forge files

this is assassins creed odyssey localization file im  unpack to text but dont know how repack again i need help 

txt english
[https://mega.nz/#!5XY1gQCZ!OH42mmq8pvCI ... b8tXiCLrQQ](https://mega.nz/#!5XY1gQCZ!OH42mmq8pvCIKabaaLny63X5y4gTcC-QQb8tXiCLrQQ)
## Post #192
- Username: clarkx211205
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Sep 14, 2019 2:37 pm
- Post datetime: 2019-11-15T16:22:01+00:00
- Post Title: Re: Assassins Creed PC .forge files

As unpack and pack files language in all parts Assassin Creed
## Post #193
- Username: Mayadesk
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 15, 2019 6:32 am
- Post datetime: 2019-11-15T23:36:15+00:00
- Post Title: Re: Assassins Creed PC .forge files

how dear clark
## Post #194
- Username: andheartman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed May 06, 2020 9:28 am
- Post datetime: 2020-06-13T03:56:49+00:00
- Post Title: Re: Assassins Creed PC .forge files

What is the latest situation? I need a tool to translate the game into Turkish.
## Post #195
- Username: Zaonx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 05, 2021 8:21 am
- Post datetime: 2021-02-05T00:27:41+00:00
- Post Title: Re: Assassins Creed PC .forge files

I'm not sure if I'm posting this in the right place or if anyone still uses this topic, this website is really confusing to me, but I really need help with something I've been trying to do nonstop for the past week. I'm trying to make a recreation of assassins creed 2 in a different engine and I need all of the files from the original game. I've got pretty much all the textures and some character models, but no matter what I do I cannot find the 3d model files for the map or any of the buildings anywhere in the forge files. If anyone could tell me where they're located or where I can get them I would really appreciate it
