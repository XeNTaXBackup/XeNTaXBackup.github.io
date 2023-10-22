## Post #1
- Username: FuryVI
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 06, 2008 3:06 am
- Post datetime: 2008-07-05T21:30:57+00:00
- Post Title: Sega Saturn - Dragon Force Files

I have been searching around the Dragon Force ISO trying to find the graphics data.

I believe the graphics are located in BIN files, but there are some other files that just as well could contain graphics based on the file names.

I will attach some files to this post. I have left the dir structure intact. The EVENT and BODY dir are full of EV*.bmp and BODY*.grp files repectively with all the EVENT files being 256kb. CPK are video files from what I have read. GAME is full of files, and this being an RPG some of those files are text for the game. SOUND would seem like it contains sound files for obvious reasons. 

If anyone can help start me in the right direction I would be ever grateful.

The file is linked here [http://senduit.com/380634](http://senduit.com/380634)
## Post #2
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-07-06T00:24:22+00:00
- Post Title: Sega Saturn - Dragon Force Files

I'm no expert but the .ai files in the sound folder seem to both have a file called ssnd.snd, the sound is 99.99% AIFF, it says so in the header
the .cpk is a SEGA FILM video file (confirmed)
I have no idea what the .grp files are but I am about 1% sure they are graphic files, anyway, they seem encrypted/compressed to me...
the .bmp files are obviously not bitmaps...perhaps they were renamed to bmp and their real extension is something close to it...also I believe they are split since both have the same size but I could be wrong
df2000.sbn contains game script
the .cpk decoding is handled by the cpk.bin probably, perhaps it could hold a .dll file inside or is the decoding tool itself
about the .dg2 files though...when I dissasemble them through intermediate language (MSIL) their header (50 50 or PP followed by a null byte) I get two referrences to ldind.ref, whatever that is...
field0.bin contain more game script
df.bin may contain misc game data like options and/or save building
gmover.bin contains game script and some code that is initiated when its, yes you guessed it, game over...
ready.bin could be a linking/listing file or the file containg the sprites and game code but it either points to, links/lists or carries inside it lots of other files like images
savebg.pal could be the code that takes a snapshot of your view for your save file...

Open the files with tools such as these found here:
[http://wiki.xentax.com/index.php?title=Extraction_tools](http://wiki.xentax.com/index.php?title=Extraction_tools)

good luck now excuse me but I have to go sleep
## Post #3
- Username: FuryVI
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 06, 2008 3:06 am
- Post datetime: 2008-07-07T00:17:04+00:00
- Post Title: Sega Saturn - Dragon Force Files

Thanks for the pointers and the link.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-07-08T18:06:25+00:00
- Post Title: Sega Saturn - Dragon Force Files

.BMP files are bitmaps without headers. the CLUTs are probably stored elsewhere.
(the smaller BMPs are 512x256 8 bit, the larger ones are 512x256 16 bit) there is no palette information whatsoever
stored here though.

the GRP files are sprite containers. AI files as mentioned are AIFF audio.
SBN files contains first misc data followed by Sprites. (in 8 bit).
BIN files are almost like GRP files. bitmaps and sprites.

the soundfiles without extensions contains multiple audio PCM and instruments at 16 bit.

the CPK file contains 16bit PCM data interleaved with something i havent figured out yet.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2008-07-09T08:33:25+00:00
- Post Title: Sega Saturn - Dragon Force Files

Always good to see Strobe get into "the game"
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2008-07-09T10:06:34+00:00
- Post Title: Sega Saturn - Dragon Force Files

Well, now just lets see if im unlazy enough to actually make a converter for these formats ;D
## Post #7
- Username: FuryVI
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 06, 2008 3:06 am
- Post datetime: 2008-07-11T21:23:24+00:00
- Post Title: Sega Saturn - Dragon Force Files

Thanks strobe for all the extra info you have provided.

I'll watch this spot to see if you get that motivation to write a converter for any of these formats.

I have downloaded [http://yabause.org/](http://yabause.org/) an emulator for Saturn that includes debug interface showing the graphics. The emulator is open source so I imagine looking at the source could help in learning more info.
## Post #8
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2008-11-25T03:47:39+00:00
- Post Title: Sega Saturn - Dragon Force Files

Awesome to see others doing this! You may find the info here useful:
[http://www.gamefaqs.com/boards/genmessa ... c=46469423](http://www.gamefaqs.com/boards/genmessage.php?board=197149&topic=46469423)
