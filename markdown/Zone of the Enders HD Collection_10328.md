## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-04-11T20:26:56+00:00
- Post Title: Zone of the Enders HD Collection

here is a bms script to extract the pak files of this game.

```
#Zone of the Enders HD Collection
#pak extractor by chrrox
goto 0xC
get files long
for i = 0 < files
getdstring name 0x2C
get size long
Padding 0x800
savepos offset
log name offset size
math offset + size
goto offset
next i

```
## Post #2
- Username: mihakase
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 23, 2010 4:01 pm
- Post datetime: 2013-07-30T07:10:33+00:00
- Post Title: Zone of the Enders HD Collection

I've started investigating Zone of the Enders 2 to attempt to fix an issue with undub versions on the PS3. Subtitles apparently go out of sync with the Japanese audio since the timing is different between EN and JP voices. I'm just trying to track the subtitles themselves down for now since I believe the timing information is probably stored with it. Supposedly this isn't a problem for the 360 undub.

I've been able to rule out the following -

fmv/ - videos in bink format
fonts/ - not sure. definitely not the subtitle text; my completely unsupported guess is that theyre glyph mappings to HVSTEX8f/font_code_8000.tga
HVSTEX8f/ - contains the texture for glyphs used in the game including the alphabet and key mappings for console controllers
init/ - seem to be game assets like models and textures
stage/ - data.cnf files seem to be metadata representing the structure of each stage in the game

That leaves the following -

bin/ - these are stage files. I don't know what format these are in.
HVSTEX/ - very large "tdb" file in this folder
ZOE2/ - I assume these are the PAK files that OP is referencing. I haven't looked into these just yet.
sound/ - .wem and .bnk files. The .wem files are the actual audio (in AudioKinetic Wwise RIFX format). The filenames between the english and japanese dialogue are different. I havent ruled them out yet because the filenames themselves might have some functionality associated with them.
## Post #3
- Username: ratanegra
- Rank: n00b
- Number of posts: 17
- Joined date: Wed May 23, 2012 5:12 pm
- Post datetime: 2013-07-30T17:26:10+00:00
- Post Title: Zone of the Enders HD Collection

Thanks chrrox, works fine in pak files of ZOE1 and would be great for someone to get a plugin for models and textures ...
It appears that ZOE2 has another compression system, and I suspect that is the same as used in MGS3.
[dat.jpg](https://xentaxbackup.github.io/file/6537_dat.jpg)
## Post #4
- Username: arc1vest
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 19, 2011 9:09 am
- Post datetime: 2013-09-14T11:09:57+00:00
- Post Title: Zone of the Enders HD Collection

Does anyone have a method for converting the .wem / .bnk files into something listenable?  I'd really appreciate it.
