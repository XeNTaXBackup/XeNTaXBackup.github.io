## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2009-03-17T08:58:16+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2009-03-21T09:24:36+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

The Bin-files are the same from Prince of Persia SoT/WW and Beyond Good and Evil.

The point is that all those games are used by the same ''Jade''engine.
Here are all known games with the ''Jade''source and thus has teh same bin-files:

Games developed with Jade:
# 2003 – Beyond Good & Evil (funfact: The engine is called after it's Protagonist Jade)
# 2003 – Prince of Persia: The Sands of Time
# 2004 – Prince of Persia: Warrior Within
# 2005 – Prince of Persia: The Two Thrones
# 2005 – Peter Jackson's King Kong: The Official Game of the Movie
# 2006 – Rayman Raving Rabbids
* 2007 – TMNT
* 2007 – Rayman Raving Rabbids 2
* 2007 – Naruto: Rise of a Ninja[2]
* 2008 – Naruto: The Broken Bond

(Source:wiki)

Would be great if someone finds a way to decompress those annoying bin-files >_<
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2009-03-21T19:46:34+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

Yep, that's true, they're probably the same.
Still, nobody seems to even try to find a way to decompress them.
## Post #4
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2009-03-25T18:10:36+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

Yeah, and there is really someone who wants to make a SDK about Beyond Good and Evil:
[http://forums.ubi.com/eve/forums/a/tpc/ ... 1561021347](http://forums.ubi.com/eve/forums/a/tpc/f/908103432/m/1561021347)

I also would like to have a SDK for Prince of Persia SoT/WW so people can mod their own PoP like Princed Project.

Com'on guy, if you can read bins, can't you please help us out?
## Post #5
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2009-04-04T20:57:02+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

Guys, I'm just posting this message to tell you that I'm still waiting...

It seems you can decompress ( not extract ) the files with [Persian Rug](http://prince.turfster.be/), a tool for PoP by Turfster ( I forgot how to do it though, but I know you can, because I have one of the bin files decompressed ). Still, it can't extract the files...
## Post #6
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2009-05-12T20:52:59+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

Well, you can extract the textures out of the PoP-games, but mostly incomplete... ach, I give up, if nobody helps out, I just use 3DxRipper


EDIT:
Just make clear, since I seem to have mistyped my choose of words.

I want to decompress out of the games the Object files(.obj + .mtl) and the texture files (tga). If you use PR then you can rip on all mentioned games the bin-files. But the Persianrug promises only to decompress the SoT-trilogy, it doesn't work on BG&E or any other Jade based game.

Other problem is that while the tool manages to rip all texture files out, it has issues by ripping the object files out. Most are incomplete or won't be extracted(for example Farrah, who has no HEAD!)

Here you can see one of my extractions and how it looks like:

Without mtl:


Now with skin:




What an abomination 8/.

I just could request that turfster should update the tool,but he told on his homepage that he lost the sourcecodes of his extractor and so denies further updates. 

That'S the whole situation.

If you know C++ or any coding program  please make a tool which can rip all JAde based games(or just RR,BG&E and PoP-SoT-trilogy) and decompress their binfiles.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-12T21:22:36+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

Have you compared some working files with some nonworking to find out what has changed?
Any information about the file format available anywhere?
## Post #8
- Username: Pengulord
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Aug 21, 2007 5:21 pm
- Post datetime: 2009-05-13T12:51:56+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

Turfster said about BGAE this:

> BG&E uses the first(?) version of the JADE Engine (also used in the Prince of Persia games, for example), and its bin files are in a slightly different format than what I'm used to.

Different enough that the Persianrug can't decompress them. Also the problem with the Jade Engine is that the games uses different ways of coding and thus have their own source codes.
I talked with the artistic director of the new PoP game about it because I asked him why Ubisoft can't release a source SDK of Jade Based games for steam:

> I know the Source engine quite a bit myself having worked with it, and no it wouldn't be as easy as what Valve does. Valve built their engine with modding capacities in mind, then upgraded the core engine and moved all its games to run on that version of the engine.
>
> 
>
> Jade does the contrary. There used to be a core system, then a first game is made in conjunction with a second, each game makes its own changes, which branch again in different versions used for other games etc.
>
> 
>
> So it's clearly not as feasible as the Source SDK.

Also I know that the files are compressed (maybe 8.8.8.8 ) DDS without header.

I hope that helps. If you want, I can send you some examples and you can look through them.
## Post #9
- Username: GameReader
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-13T11:24:25+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

Quickbms script to extract these files.

```
#quickbms script
#By chrrox
get name FILENAME
string name + ".dec"
comtype LZO1X
Do
get size long
get zsize long
savepos offset
append
clog MEMORY_FILE offset zsize size
append
math offset + zsize
goto offset
While size != 0
get tsize asize MEMORY_FILE
log NAME 0 tsize MEMORY_FILE

```
## Post #10
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2011-07-14T11:40:47+00:00
- Post Title: Rayman Raving Rabbids ( PC ) - *.BIN Files

It's working perfectly! Thanks chrrox! 
I gave up two years ago, but now I think I can go on looking for traces of the Rayman 4 prototype.
After I finish the things I'm currently busy with, of course: [viewtopic.php?f=10&t=6963](http://forum.xentax.com/viewtopic.php?f=10&t=6963) and [viewtopic.php?f=10&t=3944](http://forum.xentax.com/viewtopic.php?f=10&t=3944)
Thanks again!
