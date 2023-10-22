## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-14T17:54:34+00:00
- Post Title: Splinter cell Double agent

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T18:58:20+00:00
- Post Title: Splinter cell Double agent

Well, you surely scanned the EXE file to get the "Encrypted" message,
but from i see these UTX files (isnt this supposed to be Unreal Engine Texture format?) contains something that looks like DDS data.
(no headers though)

Maybe an UTX reader could opens these without any problems?


nothing seems encrypted here =o
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-14T21:46:52+00:00
- Post Title: Splinter cell Double agent

> Reply from Strobe
>
> Well, you surely scanned the EXE file to get the "Encrypted" message,
but from i see these UTX files (isnt this supposed to be Unreal Engine Texture format?) contains something that looks like DDS data.
(no headers though)

Maybe an UTX reader could opens these without any problems?


nothing seems encrypted here =o
MAYBE.
Jaeder sed they was lol.
But wudnt it be stupid for a company to make a file that can be hacked with NO EFFORT AT ALL and easily exported.
though, the unreal engine doesnt export textures.
So unless i pay for the source code i aint gonna get them that way lol.
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T22:14:09+00:00
- Post Title: Splinter cell Double agent

Well, i guess the developers are stupid then, as i just successfully decoded
parts of DDS textures with the assumed DDS data i found.
its just a matter of time before i have a full DDS exporter for the UTX format.
nothing is encrypted or encoded.

the ONLY problem i have is finding the correct offset for the DDS data
to create a valid header. right now i have to hex them in order to find
the correct offset. well well :X
## Post #5
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T22:19:59+00:00
- Post Title: Splinter cell Double agent

Heres a bump map extracted.
[bump01.gif](https://xentaxbackup.github.io/file/975_bump01.gif)
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T22:36:40+00:00
- Post Title: Splinter cell Double agent

Someone wanted textures?

well. okay.
[DECALS_8442.zip](https://xentaxbackup.github.io/file/977_DECALS_8442.zip)
## Post #7
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-14T22:53:29+00:00
- Post Title: Splinter cell Double agent

> Reply from Strobe
>
> Someone wanted textures?

well. okay.
NICE
OMFG U DID IT!
SO FAST
SOOO FAST MAN!
adding this to jeader?
or u using ur new ripper thingy ur makign for this?
Il post the links to the model files soon aswell then, see if we can get anything from them.
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-14T23:01:56+00:00
- Post Title: Splinter cell Double agent

Well. the easy part is done.
I now know for sure that all textures in these UTX files are DDS.

the hard part still remains. getting the correct offset for the textures
so i can create a DDS header for them.

because currently all ripped textures are done by hexxing.

but yes, it will be added to Jaeder Naub when finished =)
## Post #9
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-14T23:25:32+00:00
- Post Title: Splinter cell Double agent

> Reply from Strobe
>
> Well. the easy part is done.
I now know for sure that all textures in these UTX files are DDS.

the hard part still remains. getting the correct offset for the textures
so i can create a DDS header for them.

because currently all ripped textures are done by hexxing.

but yes, it will be added to Jaeder Naub when finished =)thanks man.
thats great news.
kon kon
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-11-15T01:09:15+00:00
- Post Title: Splinter cell Double agent

UTX is the Unreal Engine Texture Archive. Basically it is pretty much the same as a .U or .UMX except they seperate them to keep things organized.

And many know that Splinter Cell uses the Unreal Engine. 

In all likelyhood newer Unreal archive tools should work with it. 

Edit: I'll test this and see what I get. I'll keep you updated.
## Post #11
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-11-15T01:20:59+00:00
- Post Title: Splinter cell Double agent

Ive figured that  , but i guess its about time my ripper
also supports the Unreal engine files =D
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-11-15T01:23:00+00:00
- Post Title: Splinter cell Double agent

Fair enough XD
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-15T01:25:59+00:00
- Post Title: Splinter cell Double agent

> Reply from Darkfox
>
> UTX is the Unreal Engine Texture Archive. Basically it is pretty much the same as a .U or .UMX except they seperate them to keep things organized.

And many know that Splinter Cell uses the Unreal Engine. 

In all likelyhood newer Unreal archive tools should work with it.
yes
i know
i made a game with unreal tools u know...
but. its better for a normal program to support the conversion as apposed to getting everyoen who wants the textures to simply download the unreal runtime.
but the runtime doesnt EXPORT if i remember rightly.
PLUS this was made with NEW UNREAL ENGINE maybe.
so the new oen isnt downloadable off the main site.
so i cant get a hold of it to export these textures.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-11-15T01:58:01+00:00
- Post Title: Splinter cell Double agent

Yeah, it is better that way if he just adds support. But as I recall Unreal tends to allow extraction and importing of textures, the problem is apparently it cannot extract models. Not sure 100% there though. lol
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-11-19T11:37:02+00:00
- Post Title: Splinter cell Double agent

> Reply from Darkfox
>
> Yeah, it is better that way if he just adds support. But as I recall Unreal tends to allow extraction and importing of textures, the problem is apparently it cannot extract models. Not sure 100% there though. lol
nah it cant extract models ur correct.
I can only extract CERTAIN textures aswell u know lol.
Its too limited if you ask me.
I wonder how progress is going on these recently then.
## Post #16
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-12-10T12:18:39+00:00
- Post Title: 

any news on this at all?
I left it a logn time before i asked again because i ahve been busy and as i know so has strobe lol/
## Post #17
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2007-01-21T17:50:52+00:00
- Post Title: 

Anyone considering trying to extract the music from SC:DA? I'd LOVE to get my hands on that, but although I'm a programmer myself, I have next to no experience with this.

If anyone would be able to get the music out of those .ss0 files, that'd ROCK!   The files are too large to be attached here, but if you can download the single player demo, I guess (although I haven't tried it myself) there should be such files.

I think I will try to install the demo just to make sure.
## Post #18
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2007-01-25T06:05:17+00:00
- Post Title: 

(Bumpity doo)

Nobody interested or able?  I think the single player demo should suffice as a test subject, although it amounts to quite massive ~850 MB.
## Post #19
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2007-01-25T10:07:36+00:00
- Post Title: 

> Reply from clayman
>
> (Bumpity doo)

Nobody interested or able?  I think the single player demo should suffice as a test subject, although it amounts to quite massive ~850 MB.

took a quick look very limited time, heck it is 4 am here :\

here is what I saw

03_Okhotsk_01_Texture.hlnc     ->   03_Okhotsk_01_Texture.tlnc
so .hlnc   contains file lookup for .tlnc

k so now for the format (bit tricky :p ) for each listing the "marker byte" is a generic term for what they are doing.

[4] - crc?
[1] - Markerbyte
[4] - Unicode Text String (null terminated)
*null padded for 512 bytes before string (so string length (unicode) - 512)
[1] - Markerbyte
[4] - unknown (always blank?)

if marker byte is 75 then:
[1] - Markerbyte
[4] - unknown (crc?)
[1] - Markerbyte
[4] - number of files ( if 0 there is no offset!)
[numberoffiles loop]
[1] - Markerbyte
[4] - ? CRC ? 
[1] - Markerbyte
[4] - offset
[1] - Markerbyte
[4] - ?
[/numberoffiles loop]
/75
if markerbyte = 88 then:
1] - Markerbyte
[4] - size?
[1] - Markerbyte
[4] - number of files ( if 0 there is still an offset!)
[numberoffiles loop]
[1] - Markerbyte
[4] - size of something?
[1] - Markerbyte
[4] - size again?
[1] - Markerbyte
[4] - some type of offset?
[/numberoffiles loop]
/88
*each file adds 15 bytes to the next location, each listing begins 512 bytes before textstring begins

like I said very brief and it is not pretty
## Post #20
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2007-01-25T10:52:16+00:00
- Post Title: 

Umm, is that for the textures or the sounds/music?  I'm far more interested in the sounds... 

But thanks anyway.

(Also, sorry for the -- sort of -- hijack of this thread. I didn't want to create a new one since I saw that one dedicated to SC: Double Agent still occupies the first page.)
## Post #21
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2007-01-26T18:36:25+00:00
- Post Title: 

I'm trying to determine the relation between the large sound files in SCDA-Offline\Sounds (.ss0, .sm0) and the small ones (.et0, .sp0). I *guess* the small ones are probably indices to the large files, but I find kinda strange that the large files do not contain any traces of headers of OGG files (which is the format Splinter Cell usually uses), so it is possible that the files are compressed in some way.

But as I said, I'm a total n00b when it comes to hacking file formats, so if anyone more skilled felt like trying to look into the sound files, I'd really appreciate it...
## Post #22
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2007-01-31T13:00:43+00:00
- Post Title: 

I really hate bugging you guys, but is there really no one able to find out if something (usable) can be gotten out of the .ss0/.sm0 files in SC:DA?

I guess it IS difficult considering that I have yet to see a music/sound extractor for the first two releases of Splinter Cell, but maybe, just maybe, somebody will be able to extract the contents of the game's sound files.

If anyone could download the SP demo of SCDA and check the files out, that would be great.
## Post #23
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-08-03T02:58:27+00:00
- Post Title: 

Unreal Engine Runtime is simply a demonstration of the engine.  Unreal games like UT, U2, UT2004 come with their own editors which allow you to import and export data, and save your own .u .utx etc.. packages.  The only way you can export textures would be to go into the Texture browser and save them one at a time.  Also, you can export 3d geometry, However you lose the animation data associated with that object.  IF someone wanted to export a 3d character all they would have to do is open a new level, open the  character animations tab and place a character pawn, and then convert it to a brush.  Once converted to a brush it can be exported (like exporting a map) as a .t3d file, an .stl file, or a .obj file (obj files will be most likely the one you want).  This is very tedious however,  I do know that all the 3d geometry files made in external packages by the developers were in .ASE format so if someone can find the offset to the package archives that can get them to view the files in the .u or .usx etc... then we'd be able to extract all the geometry files.

UT2004 is running on the Unreal engine 2.0
UT2007 is going to be running the Unreal Engine 3.0

Splinter Cell Chaos Theory and Double agent are using modified versions of the Unreal Engine 3.0...

In response to the Splinter Cell audio packages, the packages may work in a similar function to the way microsoft XACT audio packages work.  They stream in audio files packed away in a wavebank or a soundbank, and then specify locations in the master list file usually for reference of size of file, it's package, and offset from point of origin.
## Post #24
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-08-03T04:51:23+00:00
- Post Title: 

So if we figure out how to hack the SS0 files then possibly we can hack the other ubisoft SS0 games.

COME ONE GUYS WE CAN DO THIS!!
## Post #25
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2007-08-03T20:01:54+00:00
- Post Title: 

That would be correct, keep in mind that modified versions of the engine licensed  by developer studio that makes Splinter Cell series is able to modify the file structure as well, so cracking the unreal engine format itself wouldn't accomplish much for the Tom Clancy series games such as Splinter Cell, Rainbow Six Vegas... or Ghost Recon Advanced Warfighter...
