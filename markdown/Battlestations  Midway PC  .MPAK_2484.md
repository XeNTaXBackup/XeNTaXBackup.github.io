## Post #1
- Username: Splurger
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Feb 04, 2007 11:14 am
- Post datetime: 2007-02-27T11:55:30+00:00
- Post Title: Battlestations : Midway PC  .MPAK

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-27T20:40:29+00:00
- Post Title: Battlestations : Midway PC  .MPAK

In the rapidshare files, there seems to be (Fast look)

After the general stuff: 

4D50414B440000000400000001000000544F43003800

There is the file length(maybe compressed file size)
And then another length(maybe decompressed file size)

Then a 012D, Filename, File.

Heh, I'll look better to it tomorrow, have to sleep
## Post #3
- Username: Drawde
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 26, 2007 9:00 pm
- Post datetime: 2007-03-26T13:34:13+00:00
- Post Title: Battlestations : Midway PC  .MPAK

Any further progress with this?
This game has a huge amount of potential, and it looks like it will be easily moddable once there is a way to unpack the data files (data appears to be in common formats such as .lua and .tga). However there is zero official support for modding the game and there is unlikely to be any in the future.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-26T13:57:31+00:00
- Post Title: Battlestations : Midway PC  .MPAK

> I tried a multitude of other extractors
I only tried one, zlib  

Well, i played with this and here it's a the one of examples unpacked

Your example:


After:


I recommend to get zlibc and "play" with hexworkshop using the examples

I know you looking for a global unpacker, but actually i dont know how to do it, actually i'm learning how to fake headers and recognize compressed files
[0_mm_MMission03.rar](https://xentaxbackup.github.io/file/1106_0_mm_MMission03.rar)
## Post #5
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-04-03T16:50:44+00:00
- Post Title: Battlestations : Midway PC  .MPAK

Savage, I was wondering. What Zlib header did you use?
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-04-03T19:45:27+00:00
- Post Title: Battlestations : Midway PC  .MPAK

> Reply from Matsy
>
> Savage, I was wondering. What Zlib header did you use?
None, just cutted where i think starts the zlib
## Post #7
- Username: DrJones
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 15, 2008 2:13 am
- Post datetime: 2009-01-04T17:02:48+00:00
- Post Title: Battlestations : Midway PC  .MPAK

> Reply from Savage
>
> 
I tried a multitude of other extractors

I only tried one, zlib  

Well, i played with this and here it's a the one of examples unpacked

Your example:


After:


I recommend to get zlibc and "play" with hexworkshop using the examples

I know you looking for a global unpacker, but actually i dont know how to do it, actually i'm learning how to fake headers and recognize compressed files

Hi,

sorry to bump this thread. I have tried using the same steps in decypering the mpak files, i have to same conclusion that after the RAWD there should be start of the compressed data

After:


I have tried to put same hex data from Hex workshop and copy it to new file, i tried using decompress INFLATE calls with different decompressing utils, like zlibc -d calls, using zlib.net dll calls in code, all inflate calls fail. Savage how did you arrive to text version of the scn file using zlibc (i have used the zlibc and INFLATE utils from this forum and to no avail)? Zlib INFLATE calls fail because they dont find at the beggining of the stream the 0x78 TYPE_COMPRESSION, ... and in this stream there is no 78 at the begining.

br.
Dr.Jones
## Post #8
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-04-29T13:48:01+00:00
- Post Title: Battlestations : Midway PC  .MPAK

Just in case anyone is still following this thread-

Been gone for 6 months and finally finished up the MPAK dissection for Battlestations Midway. We will see come May 12 if the MPAK format remains the same for Battlestations Pacific. I suspect it will be.

Currently am finishing up a GUI unpacker/repacker for the MPAK files. Working well. May release it after that date, depending on the outcome of Pacific.

Lots of fun mods can be done to this game - mission tweaks, armor tweaks, scoring tweaks, camera tweaks, including reskinning of all units - though skinning for ships (especially) is tough due to the fact that a graphic is often used for more than one ship.

timetraveller

.MPAK Format
------------
TOC = Table of contents
STOC = Sub table of contents
RAWD = Raw data
Compression is zlib

00-03 "MPAK" file header
04-07 STOC offset from TOC start (TOC starts at x10)
08-0B RAWD offset from STOC start (x04 if no STOC present)
0C-0D # of TOC entries
0E-0F # of STOC entries

TOC Table of contents :
10-13 "TOC", x00

Recurring TOC entries within TOC table:
(first entry):
14-15 Offset from here (x14) to last letter of file name
16-19 Length of raw data for this file (if data is compressed, then is = to the compressed length)
1A-1D Length when uncompressed (if not compressed, then is = to length of file and also = to above value)
1E    1 byte, x00=uncompressed, x01=compressed
1F    1 byte, file name length
20-xx File name
xx    1 byte, always x00 marking end of file name
xx-yy 2 bytes, # of 4 byte offset RAWD items to follow
yy-zz 4 bytes, offset RAWD items from RAWD start to start of data

STOC Sub table of contents (always follows all TOC entries):
(by offset)
00-03 "STOC"

Recurring STOC entries within STOC table (if present):
04-05 Offset from here (x04) to last byte of file name
06-07 Ordinal number of this entry in TOC (base 0)
08    File name length
09-xx File name
xx    1 byte, always x00 to end entry

00    "RAWD"
04-xx Raw data (zlib compressed)

--------------------------------------------------------

If a file is entered in the STOC, it seems to indicate that it is a cached file. The game will not run if certain important files are not cached, and most are.
## Post #9
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-09T16:54:35+00:00
- Post Title: Battlestations : Midway PC  .MPAK

I would love to see what you have even if BS:P doesn't use the MPAK format.

Keep us updated!
## Post #10
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-05-10T13:48:29+00:00
- Post Title: Battlestations : Midway PC  .MPAK

I have getted Battlestations Pacific, and the format is not change, also .MPAK, but the compression may be changed. I just tried zlib, but it can't not well, and the Windows Game Live also give me a big trouble on debuging game, anyone can help? thank you very much.
## Post #11
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-10T14:53:53+00:00
- Post Title: Battlestations : Midway PC  .MPAK

Hi Guys,

Got the BS Pacific demo loaded up finally and had a look. I'm on satellite internet here so have bandwidth cap problems as well as speed difficulties.

The .MPAKs for Pacific are slightly changed in the sub-table of contents area, and are not compatible with Midway, but no problem. I had them figured out in a couple of days. I have the unpacker up and running for the Pacific demo and am already making game mods.

I found a converter for the .FSB sound files too, and can convert .FSBs to .WAVs. I included it in the BSP Ripper. You need the XBOX ADPCM audio codec to play these files through Windows Media player, as they are in special format to accommodate streaming audio for XBOX and are also part of the PC version too. But they do play. Converting .WAVs back to .FSB is another story. You need the FMOD APIs and FMOD utility to do that. Have not gone that far though.

More testing to do, particularly in repacking .MPAKs, but it is up and running....

More news in a few days.

timetraveller

[[img=http://img100.imageshack.us/img100/3134 ... per.th.gif]](http://img100.imageshack.us/my.php?image=bspripper.gif)
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-10T15:18:16+00:00
- Post Title: Battlestations : Midway PC  .MPAK

about the FSB files, my [fsbext](http://aluigi.org/papers.htm#fsbext) tool can extract the files and can even rebuild the original archive with the modified files
## Post #13
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-10T16:14:52+00:00
- Post Title: Battlestations : Midway PC  .MPAK

Hi Bugtest,

Yes, thanks for checking into the thread. I have used your tool, in fact I am using it with the GUI interface in my BSP Ripper program to convert the .FSB files to .WAVs. I did some experimenting in converting back, though found it hard to create the .WAV in proper format before conversion. I thought I would leave the "back" conversion process to the user..

Was wondering if I could include your tool (fsbext.exe) in any release of my BSP Ripper program? I'd give you total credit of course. Otherwise I can pull the converter out....

timetraveller
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-10T16:45:50+00:00
- Post Title: Battlestations : Midway PC  .MPAK

yeah the fact that the files must be reinserted in headerless mode is a bit boring (damn fmod) anyway exist some ways to make the job more easy but obviously depends by the type of file and the experience of the user.

for example if you need to replace one wav it's enough to extract all the files in headerless mode (default, so without the -a option), getting the new wave file you want to put back into the archive, copying it on the extracted file to replace and remove its header (for this job I use another basic tool of mine called wavehead), so now it's possible to rebuild the FSB archive without errors.
so the keyword is: headerless :)
luckily the mp3 files (called "delta") don't have header in any case so they are the most easy to replace because don't require additional modifications before the rebuilding.

and yes, as far as I know the GPL license allows to included the executable of a GPL program in other projects (GPL and non) so no problem.
## Post #15
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-10T18:47:46+00:00
- Post Title: Battlestations : Midway PC  .MPAK

Thanks for the info, Bugtest. And thanks for your great converter program. I'll include the .exe in the ripper with a note about the author.

Thanks again.

timetraveller
## Post #16
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-05-16T05:31:54+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

I have the same question as DrJones. How can Savage arrive to text version by using zlibc, I don't find any zlib head in the RAWD data.
## Post #17
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-16T15:51:41+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

The RAWD data is the zip data without the header (and trailer). You have to extract the data from RAWD, then build a dummy header at its beginning, and a dummy trailer at the end. Then zlibc will extract it.

TT
## Post #18
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-05-17T01:49:55+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

thank you very much, timetraveller.
## Post #19
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-17T12:08:56+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Just an example.

Extract the RAWD data chunk. Then add two bytes at the beginning:

0x789C

and four bytes at the end:

0x00000000

Then zlibc will handle it.

TT
## Post #20
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-05-17T12:53:49+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from timetraveller
>
> Just an example.

Extract the RAWD data chunk. Then add two bytes at the beginning:

0x789C

and four bytes at the end:

0x00000000

Then zlibc will handle it.

TT

thank you very much. I just modify the zlib source code to skip the head and trailer check and it also works well, I have already finished a unpakcer for Battlestations Pacific. But there is another problem appears, this game doesn't read the unpacked file. For example, I just put my unpacked file from "Skel_Init.mpak" in the root directory of game, and the game doesn't read these file and it still get these file from "Skel_Init.mpak". I think this may be a big problem for modding this game, how can I fix this problem. Thanks again,timetraveller.

BTW: I just change the inflateReset function in inflate.c.
        Just change "state->mode = HEAD;" to "state->mode = TYPE;" and zlib will not check the zlib head and trailer,and you can simply use uncompress function to uncompress the RAWD data.
## Post #21
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-17T13:36:21+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hi Alex Bu,

I have had the same trouble with other games, after unpacking and modifying files, placing them in what seems like the proper folder structure in the main game folder - and the game won't accept the new files. I assume they have a switch somewhere which disallows this in the production game.

I have an unpacker too for BS Pacific, which also packs new MPAKs. You just replace the game's old MPAK with the new MPAK. I'll get it bundled up either today or tomorrow and post a link to it here in this forum. I just need to do some final checking.

The biggest problem I found in creating MPAKs for this game is in recreating the Sub-Table of Contents area of the MPAK. It has changed a little from Midway, but no problem there. It's makeup is also a little cryptic. the .MPAK STOC seems to be a table which documents to the game how common files are related to a single file path. It may also dictate which files are kept permanently in memory. I am using a method now of filing both the TOC and STOC for each MPAK in a Library folder (in the unpacker app folder) and rebuilding the new STOC using that information. So far, so good, and my new MPAKs using modified game files are working great.

There is a ton of stuff which can be modified in this game, including the mission scripting. Thankfully EIDOS has not pre-compiled the scripting in this game, which would otherwise have made scripting modifications impossible. Reskinning of units and everything else is also possible, though in the case of ships there are many common graphics shared, so changes made effect a lot of units at once. Aircraft seem to have individual graphics though, a good thing.

I also have  Battlestations Midway unpacker/repacker too, finished just a couple of weeks ago. I will get that together too and post a link.

TT
## Post #22
- Username: Alex Bu
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Nov 07, 2008 4:34 pm
- Post datetime: 2009-05-17T14:50:50+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Thank you very much for you replaying,timetraveller. At this situation,I also think that packing the file back to mpak is the best way, or maybe I can debug the game and find some way to force the game to read the unpacked file. If I succeed, I will post here. Just try my luck   

At last,wait for your great work,timetraveller
## Post #23
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-17T15:11:05+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Great to hear you have a BS:M unpacker/packer as well. I won't be able to run BS:P without a faster computer.

Can new units (models, textures, etc.) be made without having to replace old ones?

Eagerly awaiting the release,

Marc
## Post #24
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-17T15:39:43+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

"Can new units (models, textures, etc.) be made without having to replace old ones?"

Hi Marc,

I hope so, though I haven't tried to introduce new files of any kind yet. The MPAK sub-table of contents (where file references go) in BSM is different than BSP and so far seems a little more forgiving. The BSM packer simply lists all file references into it (the STOC), and so far, the game seems to be okay with it. In BSP you can't do that the same way, so I have devised a new method for it which I think will work. Haven't tried adding new files to either game, but I suspect they can be added.

As far as new models go, you would have to have an extension to your 3D modeling program to create .mmod files for BSP and BSM. I understand they used Lightwave and Modo for BSP modeling. I suspect they used the same for BSM.

TT
## Post #25
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-17T23:24:46+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Battlestations Rippers

BS Pacific:
BSPRipper build171 (full install):
[http://www.box.net/shared/9z1u9om84v](http://www.box.net/shared/9z1u9om84v)

BS Midway:
BSMRipper build113 (full install):
[http://www.box.net/shared/jr15tqxmzo](http://www.box.net/shared/jr15tqxmzo)

Unpacks game files. Repacks .MPAKs. Converts most .FSB sound files to .WAV. See instructions.

Experimental only! No guarantees!!!

timetraveller
## Post #26
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-17T23:35:06+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Great work!

Edit: Just a note, the files have been removed. I downloaded the BSM one before this happened but for some reason now they are both not there.
## Post #27
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-18T00:19:46+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Marc,

Try that link again in the post above (for BSMRipper build113). I fixed another little prob....I deleted the others so they wouldn't get out with the bug...

TT
## Post #28
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-18T00:39:42+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Nice. I noticed that for BSM there are two .mpaks for each mission, with one of the mpaks actually containing some of the same contents. Did you have to edit both to get results?
## Post #29
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-18T09:51:09+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Thanks.

Can't quite remember right now, as I have spent a lot of time lately on the Pacific ripper.

The one I worked on was the 0_might and 1_might one. That is the Yamato ship challenge one. The scene files in each (.scn extension) basically define the layout of the mission scene - units, unit positioning, etc. Can't remember where the actual script was. Will have a closer look later today or tomorrow. Got lots of stuff to do outside today and might not be back til late.

Check in with you later.... Have fun.

TT
## Post #30
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-18T14:53:17+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

I've got a lot of it figured out now. However, I keep getting errors when I try to change a type of ship to a ship that isn't in the same mission. I have a feeling it has to do with the Unit types numbers at the top or something of that sort. Maybe the model has to be imported. I'll keep messing around with it.
## Post #31
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-18T23:22:27+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

You would probably also need to change the mission script itself, and maybe several other things. For instance, the Yamato mission script in the ship challenge is at: 1_mc_might.mpak\Scripts\missions\challenge\might.lua. Remember, the scene scripts (.scn) just define the layout of the beginning mission scene, and must include all models included in the mission. They are then instantiated by the mission script itself. There are probably other hooks too.

Something for you guys to work on. Let's see some reskinning too. hehe

TT
## Post #32
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-18T23:38:33+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Ya I have made changes in the Script file as well as adding all the files related to the other unit i can find: model, textures, even sounds... but still no luck.

Also, do you remember what you had to go through to make the multiplayer missions single player?
## Post #33
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-19T00:03:58+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Marcenicus
>
> Ya I have made changes in the Script file as well as adding all the files related to the other unit i can find: model, textures, even sounds... but still no luck.

Keep at it, I know it should be able to be done.

> Reply from Marcenicus
>
> Also, do you remember what you had to go through to make the multiplayer missions single player?

I've never fooled around with this yet. Single missions have objectives for one side, where multi's seem to have objectives for both sides. Might require some substantial changes to the multi script, modifying objectives, etc..

Removing:
Mission.Multiplayer = true

from the script would be a start.

Also setting a player up:
this.Party = SetParty(this, PARTY_JAPANESE)

that just for starters.

timetraveller
## Post #34
- Username: Drawde
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 26, 2007 9:00 pm
- Post datetime: 2009-05-19T08:47:58+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Thanks to Timetraveller for all your hard work creating this! BSP (and BSM) appears to have a lot of modding potential, now all we need is a modding forum/site   (the official forum isn't much good, compared to the old BSM one)

One question, most of the core game data (such as vehicleclasses.lua with the ship/plane data) is in game_global.mpak. However, a lot of the .lua files in this MPAK are duplicated in "ggame_oninit.mpak". Do the .lua files in both MPAKs need to be changed in order for the modifications to work in-game, or just one (which)?

I think I've already worked out how to change the units available from the shipyards/airfields in Island Capture mode, though I'll probably have to wait for the game to arrive in the mail before trying it out, as (from looking through the Classes MPAK files) many unit types are missing from the demo (not surprisingly).
## Post #35
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-19T09:30:04+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hey Drawde, nice to hear from you! Hope things are going well.

> Reply from Drawde
>
> ....now all we need is a modding forum/site   (the official forum isn't much good, compared to the old BSM one)

Yep, this game desperately needs a modding forum and a modding community.

> Reply from Drawde
>
> One question, most of the core game data (such as vehicleclasses.lua with the ship/plane data) is in game_global.mpak. However, a lot of the .lua files in this MPAK are duplicated in "ggame_oninit.mpak". Do the .lua files in both MPAKs need to be changed in order for the modifications to work in-game, or just one (which)?

Yes, a lot of the files are duplicated, which I found odd. The file in GGame__OnInit seems to be the last one pulled in to memory, and I found that if I modified the one in there it seemed to work. However, since these files are duplicated down to the very last byte, I would go ahead and make any changes and replace all of them. There's a lot of good stuff in vehicleclasses.lua and more good stuff in deviceclasses.lua.

> Reply from Drawde
>
> I think I've already worked out how to change the units available from the shipyards/airfields in Island Capture mode, though I'll probably have to wait for the game to arrive in the mail before trying it out, as (from looking through the Classes MPAK files) many unit types are missing from the demo (not surprisingly).

Yep, the retail version has all the goodies!

Good luck and have fun.

TT
## Post #36
- Username: Drawde
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 26, 2007 9:00 pm
- Post datetime: 2009-05-20T11:21:44+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Whilst waiting for the full game, I've been doing some simple modding experiments with the demo which have had quite encouraging results (haven't tried changing sounds or graphics yet)!

First I managed to add the Atlanta CL to the US shipyard on the Island Capture map, it seems to be quite easy to modify the available units in IC mode and also add completely new types (light cruisers in this case). I haven't yet tried adding carriers, and will have to wait for the full game to see if it's possible to have more than one unit of the same type (e.g destroyer, fighter aircraft) available from the same shipyard/airfield.

More interestingly, I've also tried changing the ship weapon data (bulletclasses.lua in game_globals.mpak) to give more realistic engagement ranges. I assumed that it would be easy to do this, but I wasn't sure how it would turn out in-game - whether the AI would cope with it, and whether shot accuracy would realistically decrease at longer ranges (if it didn't, ship combat would be unrealistic and very difficult).
I set the ranges of the US and Japanese destroyer and cruiser guns (for the ships available in the demo, these are 9, 15, 28 and 31) to about one-third of their real-life range (this works out at around 2-3 times the standard game range), and set the shot velocity and weight to match real-life data. 
I then started up an Island Capture game as the USA and sent a whole fleet straight towards the enemy's HQ. 
The resulting battle played out quite well - the AI (both enemy and friendly) deals with the increased range without any problem, and most importantly, the increase in shot dispersion/inaccuracy with increased range seems to be already modelled into the game. At the maximum range of a cruiser's guns (about 8000m, which works out at around a centimetre below the horizon on the screen) most shots will miss. I had an AI cruiser shooting at one of my destroyers from out of visual range, and it took quite a while to sink it (which wouldn't have been the case with the default gun ranges!)
I also gave torpedoes historically accurate speed values (about 3-4x the default!) which will help balance them out against the increased gun ranges. The AI is definitely still capable of dodging the speeded-up torps!

I'll probably play through the game without mods first before attempting any serious modding of this kind. But it looks like there's a lot of potential for making the game's naval combat (and possibly air combat) a lot more realistic without also making it unbalanced. 

I'm sure all of this is also doable in Midway, though it's much easier to test in BS:P due to the skirmish modes.

One thing I haven't yet worked out is how to make pre-scripted units playable in SP and MP/skirmish siege missions. I was trying to alter the demo siege mission to make all the ships + aircraft controllable by the player (which would open up a lot more strategy - for example, playing as the Japanese, attacking the US carriers with the torpedo boats). However, it isn't obvious what scripts in the .lua or .scn files determine what the player can use and what's purely AI-controlled.
## Post #37
- Username: hexamyth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 20, 2009 1:32 am
- Post datetime: 2009-05-20T11:47:59+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hey Timetraveller, I wonder whether you can help me out here.
I'm trying to unlock all the unlockable by editing the vehicleclasses.lua. So far I changed the unlockid or remove it but still no luck. Did I miss something or did something wrong?

Your help will be highly appreciated   

~Hexamyth
## Post #38
- Username: Drawde
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 26, 2007 9:00 pm
- Post datetime: 2009-05-20T19:46:07+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

You could try removing both the UnlockID line and changing "["Unlock"] = true" to "["Unlock"] = false" for all the unlockable units. I haven't tried this yet myself, though (only got the full game today, and haven't yet got round to modding it)
## Post #39
- Username: Areon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 21, 2009 4:49 am
- Post datetime: 2009-05-21T07:06:19+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

The contents of this post was deleted because of possible forum rules violation.
## Post #40
- Username: hexamyth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 20, 2009 1:32 am
- Post datetime: 2009-05-21T11:50:52+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

The contents of this post was deleted because of possible forum rules violation.
## Post #41
- Username: Areon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 21, 2009 4:49 am
- Post datetime: 2009-05-21T14:09:48+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from hexamyth
>
> Thank you so much! I really appreciated it. One question though, does the ai has the 999999 command points as well?   

I was going to find your thread since you said you were going start a new thread and post the mod link in another forum but I can't seem to find it.
Yes, the AI will also have 999999 points. It can be easily changed to 3000 or 5000 for example, if you don't like battles with 30 ships on each side.

As for official Eidos BSP forum, the moderator hasn't answered to my question about opening a new thread about modding. If you want, you can start such thread there and we will see their reaction
## Post #42
- Username: Drawde
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 26, 2007 9:00 pm
- Post datetime: 2009-05-21T16:53:08+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Thanks to Areon for posting your unlocker mod!
It looks like Hexamyth had the right idea, but you need to edit the vehicleclasses.lua in GVMainMenu.mpak, rather than in game_globals.mpak. My idea of changing the "unlock" value to false wouldn't work, as this then means the unit isn't available at all from the unlock menu.
## Post #43
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-21T18:14:14+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Scripting Tweaks.

Hi Guys,

Most of you have found the vehicleclasses.lua and deviceclasses.lua files and have made some changes there. All well and good, those files have to do with static values for vehicles (units) and guns and ammunition.

Let me document some things you can do in the mission scripting which can make cool changes as to how a mission operates.

First of all, familiarize yourself with the luamw_init.lua file, found in the GGame__OnInit.mpak\scripts\global and Game_Global.mpak\scripts\global folders. This file contains some important enumerations for ROLES and PLAYERS. Remember them. The mission script uses these to define whether a player can take command of a unit, to define what roles you can use while commanding a unit, and what commands you can use while commanding a unit.

Let's take the US Leyte Gulf mission as an example, USN Mission #09. The actual mission script for this mission is found in 3_usn_09SOLO.mpak\scripts\missions\usn\usn_09_leyte.lua.

Open the script in a text editor.

First, it's fun to get the island fortresses firing at our ships out in Leyte. Turn the fortress guns on by enabling the artillery:

Change this:
--fortress tiltas
for idx,unit in pairs(Mission.Fortresses) do
	ArtilleryEnable(unit, false)
end

To this:
--fortress tiltas
for idx,unit in pairs(Mission.Fortresses) do
	ArtilleryEnable(unit, true)
end

Make sure you have full control of the cruiser Atlanta:

Change this:
SetRoleAvailable(Mission.Atlanta, EROLF_AA_FLAK+EROLF_AA_MACHINEGUN+EROLE_CAPTAIN, PLAYER_ANY)
UnitSetPlayerCommandsEnabled(Mission.Atlanta, PCF_NONE+PCF_TARGET)

To this:
SetRoleAvailable(Mission.Atlanta, EROLF_ALL, PLAYER_ANY)
UnitSetPlayerCommandsEnabled(Mission.Atlanta, PCF_ALL)

It would be nice to fire the big guns of the Atlanta too, so let's add use of the artillery to the Atlanta too:

SetRoleAvailable(Mission.Atlanta, EROLF_ALL, PLAYER_ANY)
UnitSetPlayerCommandsEnabled(Mission.Atlanta, PCF_ALL)
ArtilleryEnable(Mission.Atlanta, true)

If you want to make the Atlanta invincible add this right below the previous three statements:
SetInvincible(Mission.Atlanta, true)

Now if we want to take command of the CVs as a player, we can do this:

Change this:
--CV tiltas
for idx,unit in pairs (Mission.CVs) do
	if DEMO_2009_JAN then
		--CVk elitre allitva, hogy lelojek a kamikat
		SetSkillLevel(unit,SKILL_ELITE)
	end
	NavigatorSetAvoidShipCollision(unit,false)
	SetRoleAvailable(unit, EROLF_ALL, PLAYER_AI)
	SetShipMaxSpeed(unit, 
	AAEnable(unit, true)
end

To this:
--CV tiltas
for idx,unit in pairs (Mission.CVs) do
	if DEMO_2009_JAN then
		--CVk elitre allitva, hogy lelojek a kamikat
		SetSkillLevel(unit,SKILL_ELITE)
	end
	NavigatorSetAvoidShipCollision(unit,false)
	SetRoleAvailable(unit, EROLF_ALL, PLAYER_ANY)
	UnitSetPlayerCommandsEnabled(unit, PCF_ALL)
	SetShipMaxSpeed(unit, 
	AAEnable(unit, true)
	ArtilleryEnable(unit, true)
end

Some of the enumerations found in the luamw_init.lua file:

--
-- Players
--
PLAYER_1	= 0
PLAYER_2	= 1
PLAYER_3	= 2
PLAYER_4	= 3
PLAYER_5	= 4
PLAYER_6	= 5
PLAYER_7	= 6
PLAYER_8	= 7
PLAYER_AI	= 8  ***only AI gets to use this unit
PLAYER_ANY	= 9  ***any player (or THE player) can use this unit

--
-- Roles
--
EROLE_CAPTAIN			= 1
EROLE_PILOT			= 2
EROLE_AA_MACHINEGUN		= 3
EROLE_AA_FLAK			= 4
EROLE_ARTILLERY			= 5
EROLE_TORPEDO			= 6
EROLE_BOMB			= 7
EROLE_DEPTHCHARGE		= 8
EROLE_SPECIAL			= 9
EROLE_NUM			= 9

EROLF_CAPTAIN			= 1
EROLF_PILOT			= 2
EROLF_AA_MACHINEGUN		= 4
EROLF_AA_FLAK			= 8
EROLF_ARTILLERY			= 16
EROLF_TORPEDO			= 32
EROLF_BOMB			= 64
EROLF_DEPTHCHARGE		= 128
EROLF_SPECIAL			= 256
EROLF_ALL			= EROLF_CAPTAIN + EROLF_PILOT + EROLF_AA_MACHINEGUN + EROLF_AA_FLAK + EROLF_ARTILLERY + EROLF_TORPEDO + EROLF_BOMB + EROLF_DEPTHCHARGE + EROLF_SPECIAL
EROLF_ALLBUTCAPTAIN		= EROLF_PILOT + EROLF_AA_MACHINEGUN + EROLF_AA_FLAK + EROLF_ARTILLERY + EROLF_TORPEDO + EROLF_BOMB + EROLF_DEPTHCHARGE + EROLF_SPECIAL

--
--Commands
--
PCF_MOVE =               1 -- move command
PCF_TARGET =             2 -- targetolas
PCF_JOIN_LEAVE =         4 -- formacioba ki/belepes (join/leave/disband)
PCF_CHANGE_FORMATION =   8 -- formacio atrendezes
PCF_ORDERS =            16 -- orders menu allitgatas
PCF_REPAIR =            32 -- repair screen behozas (hajok)
PCF_RETREAT =           64 -- visszavonulas parancs (repulok)
PCF_ATTACK =           128 -- visszavonulas parancs (repulok)
PCF_REGROUP =          256 -- visszavonulas parancs (repulok)

PCF_NONE =               0
PCF_ALL =              511
## Post #44
- Username: Areon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 21, 2009 4:49 am
- Post datetime: 2009-05-21T20:08:58+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

timetraveller, thank you very much for your contribution! 

Can we left some mod requests here, or maybe you could give some advice? 

Here are some interesting things to implement:

1. Unlocking the ingame console and developer’s cheat menu! There is a whole variety of interesting commands and functions in Skel_Init.mpak\scripts\datatables\keyboardsetup.lua :

{
		["Name"] = "DevInputs",
		["Inputs"] =
		{
			"Debug",
			{ "Console", { IC_CONSOLE_ONOFF, }, },
			{ "Unlock All", { IC_CHEAT_UNLOCKALL, }, },
			{ "Cheat Menu", { IC_CHEAT_MENU, }, },
			{ "Quit", { IC_CHEAT_QUIT, }, },
			{ "End Scene", { IC_CHEAT_ENDSCENE, }, },
			{ "Game Speed x0.5", { IC_CHEAT_SLOW, }, },
			{ "Game Speed x2", { IC_CHEAT_FAST, }, },
			{ "Game Speed x4", { IC_CHEAT_VERYFAST, }, },
			{ "Pause Step", { IC_CHEAT_PAUSESTEP, }, },
			{ "Change Party", { IC_CHEAT_NEXTPARTY, }, },
			{ "AllocLog", { IC_CHEAT_ALLOCLOG, }, },
			{ "Kill Unit", { IC_CHEAT_KILL, }, },
			{ "Look", { IC_CHEAT_LOOK, }, },
			{ "Wire Ocean", { IC_CHEAT_WIREOCEAN, }, },
			{ "AI Debug", { IC_CHEAT_AIDEBUG, }, },
			{ "Attis1", { IC_CHEAT_ATTIS1, }, },
			{ "Attis2", { IC_CHEAT_ATTIS2, }, },
			{ "Render GeomMesh", { IC_CHEAT_RENDERGEOMMESH, }, },
			{ "No Fire", { IC_CHEAT_NOFIRE, }, },
			{ "Capture", { IC_CHEAT_CAPTURE, }, },
			{ "Save Test", { IC_CHEAT_SAVETEST, }, },
			{ "Page Up", { IC_CHEAT_PGUP, }, },
			{ "Page Down", { IC_CHEAT_PGDOWN, }, },
			{ "Skip Dialog", { IC_WARNING_DIALOGSTEP, }, },
			{ "Skip Narrative", { IC_WARNING_MISSIONINFOSTEP, }, },
			{ "FOV Up", { IC_CHEAT_FOV_DOWN, }, },
			{ "FOV Down", { IC_CHEAT_FOV_UP, }, },
			{ "Camp.Map Zoom In", { IC_CAMPAIGN_MAP_ZOOM_IN, }, },
			{ "Camp.Map Zoom Out", { IC_CAMPAIGN_MAP_ZOOM_OUT, }, },
			{ "Frontend Scroll", { IC_FE_SCROLL, }, },
			{ "Form.Close", { IC_FORM_CLOSE, }, },
			"",
			"Free Camera",
			{ "Free Camera Toggle", { IC_FREECAM_TOGGLE, }, },
			{ "Free Camera Up", { IC_FREECAM_STRAFEUPDOWN, }, },
			{ "Free Camera Down", { IC_FREECAM_STRAFEUPDOWN, }, },
			{ "Free Camera Left", { IC_FREECAM_STRAFELEFTRIGHT, }, },
			{ "Free Camera Right", { IC_FREECAM_STRAFELEFTRIGHT, }, },
			{ "Free Camera Forward", { IC_FREECAM_FORWARD, }, },
			{ "Free Camera Back", { IC_FREECAM_FORWARD, }, },
			{ "Free Camera Turn Up", { IC_FREECAM_TURNUPDOWN, }, },
			{ "Free Camera Turn Down", { IC_FREECAM_TURNUPDOWN, }, },
			{ "Free Camera Turn Left", { IC_FREECAM_TURNLEFTRIGHT, }, },
			{ "Free Camera Turn Right", { IC_FREECAM_TURNLEFTRIGHT, }, },
			{ "Free Camera Act Unit", { IC_FREECAM_ACTUNIT, }, },
			{ "Free Camera Vert to 0", { IC_FREECAM_VERT_TO_ZERO, }, },
			{ "Free Camera to 0", { IC_FREECAM_HORZVERT_TO_ZERO, }, },
			{ "Free Camera Shoot", { IC_FREECAM_SHOOT, }, },
			{ "Free Camera Weapon Change", { IC_FREECAM_GUNSWITCH, }, },
			{ "Free Camera Roll+", { IC_FREECAM_ROLL, }, },
			{ "Free Camera Roll-", { IC_FREECAM_ROLL, }, }, ........................

Especially it would be interesting to play with time by slowing or fastening it  and to play with free camera.. I have “uncommented” the above piece of code by removing some “-[[” and “]]-” at begging and at the end of it, so now in the game options menu I have an additional keyboard setup section called “DEVINPUTS” where I can map keyboard keys to that functions. But they still not work in game!

I think, we need to enable that dev mode ingame to use those keys or something.. For example, in Skel_Init.mpak\dbgprof.txt we have some possible solutions for enabling console:

...
Flag RenderConsole             1
...

There are also some interesting things in GGame__OnInit.mpak\scripts\datatables\validconsolecommands.lua

But how open the console or cheat menu in game? Please help us with this little mod, timetraveller!


2. Another great idea for a mod is adding a NUCLEAR BOMB to the skirmish Island Capture. A nuclear bomb similar to those that were thrown on Hiroshima and Nagasaki. That bomb could be launched from B-29 Superfortress bomber. And it will be a historically accurate weapon for US. Please, can you create such mod by modifying some other standard bomb parameters, just let its explosion be really huge, and with a dramatically increased damage as well as affected zone.  

3. It would be also great to add an experimental “Muteki Nippon” class battleship to Japan. It could look like this: 


Here is a comparison with Yamato: 


Can you “construct” a ship like this and add it to game? 

So, these would be 3 perfect mods that everyone will appreciate, please help us with creating them!
## Post #45
- Username: hexamyth
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 20, 2009 1:32 am
- Post datetime: 2009-05-22T12:21:30+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Areon
>
> If you want, you can start such thread there and we will see their reaction

I'll pass   

Anyway, the command points mod works well. I just don't like 40-50 cruisers and 40+ bombers rushing towards my headquarter in a wave =.=

Talk about the island capture mode, is there actually a way add more than 1 Ai to that mode by editing the scripts? 1 on 1 is kinda boring
## Post #46
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-22T13:58:41+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Areon
>
> timetraveller, thank you very much for your contribution! 

Can we left some mod requests here, or maybe you could give some advice? 

Here are some interesting things to implement:

1. Unlocking the ingame console and developer’s cheat menu!

Thanks. I have uncommented the same "devinput" code but have not had any luck with most of it. Can't get the console or freecamera to work. Some of the movie camera commands do work without any changes. Assign keys to them and check them out. One of the files missing is inputs.lua, which may be the key to the whole problem. It doesn't seem to be among any of the extracted files, but there are many references to it. It might possibly be in the .MPKG file. I have been trying to unlock this file but have not had any luck yet.

> Reply from Areon
>
> 2. Another great idea for a mod is adding a NUCLEAR BOMB to the skirmish Island Capture.

Yes, nuclear bomb would be fun. You could probably mod an existing bomb by changing its characteristics in deviceclasses.lua.

> Reply from Areon
>
> 3. It would be also great to add an experimental “Muteki Nippon” class battleship to Japan.

Can you “construct” a ship like this and add it to game?

Unfortunately I don't have any 3D modeling experience. Or a lot of time even if I did. Too many real life things going on these days. And it's summertime!

TT
## Post #47
- Username: Areon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 21, 2009 4:49 am
- Post datetime: 2009-05-23T05:42:38+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

ok, timetraveller, thanks for your answer!

as for enabling dev mode, maybe some king of command should be added to the game *.exe file shortcut, like "-dev" or "-console 1" or "-debug" ? i have tried some, but with no success..
## Post #48
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-23T09:34:39+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Areon
>
> ok, timetraveller, thanks for your answer!

as for enabling dev mode, maybe some king of command should be added to the game *.exe file shortcut, like "-dev" or "-console 1" or "-debug" ? i have tried some, but with no success..

The game seems to have several command line parameters. I looked in the .exe (bsp.exe) a week or so ago and found them.

They are:

frames
noperforce
devrr
skipBriefings
skipTitle
skipLogos
nohints
freecamera
debug
faststart

Tried -debug, etc. but won't work. They may have it turned off in software. Maybe you can find a different way to add the command.

TT
## Post #49
- Username: ksk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 22, 2009 9:51 pm
- Post datetime: 2009-05-23T09:39:31+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

hi ..
i have some qustion. how can i open the mood file in the folder shipe/us/owa.mood 

i have know idea what programm i need to open the mood file ..
hope someone can help me ..
## Post #50
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-23T13:39:51+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from ksk
>
> hi ..
i have some qustion. how can i open the mood file in the folder shipe/us/owa.mood 

i have know idea what programm i need to open the mood file ..
hope someone can help me ..

Probably you mean .mmod file? If so, it is a 3D modeling file, probably exported out of Lightwave or Modo. No idea how to open it. Sorry.

TT
## Post #51
- Username: Polarshark
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 24, 2009 10:54 pm
- Post datetime: 2009-05-24T23:45:04+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

thank you so much for your unlocked unit mod timetraveller

and your commandpoints mod is nice 

but i need some help

as you can see, it's stuck on 999999 and i don't know what to do to change it

and do you think you can make a mod, where in skirmish mode, we can unlock more than 1 unit?

thank you so much for reading and making mods =)
and thank you areon for directing me to this site
## Post #52
- Username: USSEnterprise
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 24, 2009 2:35 am
- Post datetime: 2009-05-25T03:32:40+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Drawde
>
> Whilst waiting for the full game, I've been doing some simple modding experiments with the demo which have had quite encouraging results (haven't tried changing sounds or graphics yet)!

First I managed to add the Atlanta CL to the US shipyard on the Island Capture map, it seems to be quite easy to modify the available units in IC mode and also add completely new types (light cruisers in this case). I haven't yet tried adding carriers, and will have to wait for the full game to see if it's possible to have more than one unit of the same type (e.g destroyer, fighter aircraft) available from the same shipyard/airfield.

More interestingly, I've also tried changing the ship weapon data (bulletclasses.lua in game_globals.mpak) to give more realistic engagement ranges. I assumed that it would be easy to do this, but I wasn't sure how it would turn out in-game - whether the AI would cope with it, and whether shot accuracy would realistically decrease at longer ranges (if it didn't, ship combat would be unrealistic and very difficult).
I set the ranges of the US and Japanese destroyer and cruiser guns (for the ships available in the demo, these are 9, 15, 28 and 31) to about one-third of their real-life range (this works out at around 2-3 times the standard game range), and set the shot velocity and weight to match real-life data. 
I then started up an Island Capture game as the USA and sent a whole fleet straight towards the enemy's HQ. 
The resulting battle played out quite well - the AI (both enemy and friendly) deals with the increased range without any problem, and most importantly, the increase in shot dispersion/inaccuracy with increased range seems to be already modelled into the game. At the maximum range of a cruiser's guns (about 8000m, which works out at around a centimetre below the horizon on the screen) most shots will miss. I had an AI cruiser shooting at one of my destroyers from out of visual range, and it took quite a while to sink it (which wouldn't have been the case with the default gun ranges!)
I also gave torpedoes historically accurate speed values (about 3-4x the default!) which will help balance them out against the increased gun ranges. The AI is definitely still capable of dodging the speeded-up torps!

I'll probably play through the game without mods first before attempting any serious modding of this kind. But it looks like there's a lot of potential for making the game's naval combat (and possibly air combat) a lot more realistic without also making it unbalanced. 

I'm sure all of this is also doable in Midway, though it's much easier to test in BS:P due to the skirmish modes.

One thing I haven't yet worked out is how to make pre-scripted units playable in SP and MP/skirmish siege missions. I was trying to alter the demo siege mission to make all the ships + aircraft controllable by the player (which would open up a lot more strategy - for example, playing as the Japanese, attacking the US carriers with the torpedo boats). However, it isn't obvious what scripts in the .lua or .scn files determine what the player can use and what's purely AI-controlled.

How did you manage to add on the ships? What files are involved?

Thanks.
## Post #53
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-26T12:58:22+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Polarshark-
Thanks, glad you like the unpacker. The mods you refer to were done by Areon. Possibly he could supply some info on your question.

USSEnterprise-
Adding ships to missions is not hard once you know how. I have experimented with the solo missions only (single missions).

For example, mission 09, the Divine Winds Leyte mission. The following two files are modified.

The first file:
2_usn_09SOLO.mpak\universe\scenes\missions\usn\usn_09_leyte.scn

Add your new ship to this scene file. Either duplicate one of the other ships, or find the ship of your choice in another mission. Copy its info. This is also where you position the ship on the map for the start of the mission. You will have to experiment. The 4th, 3rd, and 2nd last fields in the localframe line are the positioning coordinates. Other fields in this line are the orientation, but haven't experimented with those yet.

entity "USS Johnston" (DestroyerGen) {
localframe 0.00000 0.00000 1.0000 0.0000 0.0120 0.9999 -0.0099 0.0000 0.9990 0.0115 -0.0435 0.0000 -2000.0000 -1.0000 -5000.0000 1.0000 ;

The ship can be named whatever you want (in fact you can rename ships in existing missions to whatever you want):
GuiName = "Johnston DD-557" ;

Change its number:
Numbering = I 533 ;

And its starting speed:
StartSpeed = F 8.0000 ;

Resave the file and repack the .MPAK.

The second file:
3_usn_09SOLO.mpak\scripts\missions\usn\usn_09_leyte.lua

This is the actual mission script. You must bring the ship into existance here, and assign it its attributes.

Instantiate the new unit:
this.Johnston = FindEntity("USS Johnston")

Enable what commands it is allowed, and set its player or AI role:
UnitSetPlayerCommandsEnabled(Mission.Johnston, PCF_ALL)
SetRoleAvailable(Mission.Johnston, EROLF_ALL, PLAYER_ANY)

Set its max speed:
SetShipMaxSpeed(Mission.Johnston, 

Enable the AA and artillery:
AAEnable(Mission.Johnston,true)
ArtilleryEnable(Mission.Johnston, true)

Resave the file and repack the .MPAK.

Run the mission and play with your new ship. Aircraft are similar.

Good luck.

timetraveller
## Post #54
- Username: AlphaStrike
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 26, 2009 9:06 am
- Post datetime: 2009-05-26T15:01:34+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hey guys

First I'd like to thank timetraveller for the unpacker,very handy!

I'm a huge fan of the iowa class BB so I have been tweaking the attributes to bring her more in line with what I think she should be,shell damage,speed,armor,etc.
I alos adjusted the range of her main guns to a realistic value but alas while it is fun at first only the AI can really use a range of 20+ miles,so I've narrowed it down to about 6000 yards as acceptable for ingame purposes.

Onto my question...What I would like to do,If you've ever seen footage of one of these goliaths firing their main guns you'll notice that after each barrel fires,you get the recoil (which we see in game) but you'll also see each barrel will come to a rest position for the reload.
That is what I want to "try" to add .

I've noticed that there are values for a turret rest,but how to go about setting it to what I would like to see is where I'm stuck and hoping you guys can give me some incite.

Heres to hoping we can make this game more than what eidos thinks it should be   

Thanks for your time fellas
## Post #55
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-27T09:32:54+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hi AlphaStrike,

Thanks.

Did a search through the game files, looking for "rest...". The only place it's used seems to be in the vehicleclasses.lua file, which just defines the rest angle for the guns.

deviceclasses.lua defines the turret itself. I don't see anthing in there which would make your modification work, though you can change such things as reload time, turret speed, etc.

Might be hardcoded in the game. drawde is good at this stuff. Maybe he will return.

timetraveller
## Post #56
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-27T22:55:47+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from timetraveller
>
> Polarshark-
Adding ships to missions is not hard once you know how. I have experimented with the solo missions only (single missions).

Too bad it doesn't seem to be as easy with BS:M. I follow those same steps basically but the game still crashes. I can't figure out what I am missing.
## Post #57
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-28T18:36:43+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Marcenicus
>
> Too bad it doesn't seem to be as easy with BS:M. I follow those same steps basically but the game still crashes. I can't figure out what I am missing.

BS:M "should" be the same changes as Pacific. Be especially careful of syntax - every comma, quote, bracket, and period in place. Also be careful of where you make changes in the mission script file (the "3_...file). Bad statements there, or out of place statements will cause a game crash.

timetraveller
## Post #58
- Username: Marcenicus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 09, 2009 3:29 am
- Post datetime: 2009-05-29T16:08:09+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

```
		table.insert (this.YorkGroup, luaFindHidden("Texas"))
		table.insert (this.YorkGroup, luaFindHidden("Perkins"))

```


I don't think this is a bad statement. I changed the name of the first entry to Texas, as was done in the other mission files. Texas is a battleship so maybe it can't be grouped with a destroyer?

I also tried this:

```

this.YorkGroup = {}
		table.insert (this.YorkGroup, luaFindHidden("Perkins"))

```


I made Texas its own entity and changed everything else I needed to, but still no success.
## Post #59
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-05-31T08:54:18+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Marcenicus,

Not sure if your adding a new ship or replacing one. If you change the reference to a previous ship it may be needed elsewhere in the mission script and that might be the reason the game crashes.

Adding one is easier due to the scripting.

Any luck yet?

TT
## Post #60
- Username: USSEnterprise
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 24, 2009 2:35 am
- Post datetime: 2009-06-02T05:32:37+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from timetraveller
>
> Polarshark-
Thanks, glad you like the unpacker. The mods you refer to were done by Areon. Possibly he could supply some info on your question.

USSEnterprise-
Adding ships to missions is not hard once you know how. I have experimented with the solo missions only (single missions).

For example, mission 09, the Divine Winds Leyte mission. The following two files are modified.

The first file:
2_usn_09SOLO.mpak\universe\scenes\missions\usn\usn_09_leyte.scn

Add your new ship to this scene file. Either duplicate one of the other ships, or find the ship of your choice in another mission. Copy its info. This is also where you position the ship on the map for the start of the mission. You will have to experiment. The 4th, 3rd, and 2nd last fields in the localframe line are the positioning coordinates. Other fields in this line are the orientation, but haven't experimented with those yet.

entity "USS Johnston" (DestroyerGen) {
localframe 0.00000 0.00000 1.0000 0.0000 0.0120 0.9999 -0.0099 0.0000 0.9990 0.0115 -0.0435 0.0000 -2000.0000 -1.0000 -5000.0000 1.0000 ;

The ship can be named whatever you want (in fact you can rename ships in existing missions to whatever you want):
GuiName = "Johnston DD-557" ;

Change its number:
Numbering = I 533 ;

And its starting speed:
StartSpeed = F 8.0000 ;

Resave the file and repack the .MPAK.

The second file:
3_usn_09SOLO.mpak\scripts\missions\usn\usn_09_leyte.lua

This is the actual mission script. You must bring the ship into existance here, and assign it its attributes.

Instantiate the new unit:
this.Johnston = FindEntity("USS Johnston")

Enable what commands it is allowed, and set its player or AI role:
UnitSetPlayerCommandsEnabled(Mission.Johnston, PCF_ALL)
SetRoleAvailable(Mission.Johnston, EROLF_ALL, PLAYER_ANY)

Set its max speed:
SetShipMaxSpeed(Mission.Johnston, 

Enable the AA and artillery:
AAEnable(Mission.Johnston,true)
ArtilleryEnable(Mission.Johnston, true)

Resave the file and repack the .MPAK.

Run the mission and play with your new ship. Aircraft are similar.

Good luck.

timetraveller

Thanks, but is there a way add ships on to the island capture mode?

Thanks again.
## Post #61
- Username: timetraveller
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Apr 29, 2009 8:36 am
- Post datetime: 2009-06-02T21:42:41+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from USSEnterprise
>
> 

Thanks, but is there a way add ships on to the island capture mode?

Thanks again.

Yes, definitely. The file changes look to be roughly the same, so it should work similarly as single missions. Add the ship to the scene file "2_scene1ICx", then instantiate it (bring it into existance) in the corresponding island capture script "3_scene1ICx" file. Also in "3_scene1ICx" file" set its party affiliation and role. Use an existing ship as an example.

For instance, the existing ship Soryu in 3_scene1IC1.mpak:

Mission.Soryu  = FindEntity("IC - Soryu 01")
SetParty(Mission.Soryu, PARTY_JAPANESE)
SetRoleAvailable(Mission.Soryu,EROLF_ALL,PLAYER_5)

My unpacker for Battlestations Pacific is getting close to 200 downloads already. Judging from that, there seems to be a substantial number of people interested in modding this game. You guys should band together in a group and see what's possible, put your heads together, maybe establish a modding forum and web site separate from the EIDOS forum so you can come up with some mods to share. Just a suggestion. There are a lot of smart people out there, and a modding group will keep this great game going for a long time. Unfortunately I don't have a huge amount of time for modding. The tools part is what interests me the most, then I usually move on.

Good luck.

timetraveller
## Post #62
- Username: DragonFCPorto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 21, 2009 2:45 am
- Post datetime: 2009-06-03T13:10:12+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Areon
>
> hexamyth wrote:Thank you so much! I really appreciated it. One question though, does the ai has the 999999 command points as well?   

I was going to find your thread since you said you were going start a new thread and post the mod link in another forum but I can't seem to find it.
Yes, the AI will also have 999999 points. It can be easily changed to 3000 or 5000 for example, if you don't like battles with 30 ships on each side...
..
I'd like very much, how to modify/change this mod(999999 points) to less points(5000 points) please help us, tell how do that?
Tanks
## Post #63
- Username: neneko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 03, 2009 11:44 pm
- Post datetime: 2009-06-04T01:47:02+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hi, timetraveller 
thanks for the ripper, though there's this one issue i encountered: all the extracted files are of 0KB. 
how can i fix this? i've tried the ripper on both on vista and xp, but still no luck.
thanks in advance.

P.S.
i've downloaded all the Microsoft visual basic 6 runtime updates (though none of them were labled vista-compatible)
## Post #64
- Username: DragonFCPorto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 21, 2009 2:45 am
- Post datetime: 2009-06-04T11:13:52+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from timetraveller
>
> USSEnterprise wrote:

...My unpacker for Battlestations Pacific is getting close to 200 downloads already. Judging from that, there seems to be a substantial number of people interested in modding this game. You guys should band together in a group and see what's possible, put your heads together, maybe establish a modding forum and web site separate from the EIDOS forum so you can come up with some mods to share. Just a suggestion. There are a lot of smart people out there, and a modding group will keep this great game going for a long time. Unfortunately I don't have a huge amount of time for modding. The tools part is what interests me the most, then I usually move on.

Good luck.

timetraveller

You are right, we must create a modding forum or a web site, this games deserve..
## Post #65
- Username: Eisenhower
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 05, 2009 6:14 pm
- Post datetime: 2009-06-06T18:29:11+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

has anyone found out how to edit the units that you can buy in island capture?
for example that you can buy a carrier!

and second question is it possible to limit units in island capture?
so every player just can have 1 battleship or something like that
## Post #66
- Username: DragonFCPorto
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 21, 2009 2:45 am
- Post datetime: 2009-06-09T19:48:41+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

AREON!!..AREON!!...    where are you??   
please RESPOND.. 
tanks.
## Post #67
- Username: Drawde
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 26, 2007 9:00 pm
- Post datetime: 2009-06-10T10:32:19+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

> Reply from Eisenhower
>
> has anyone found out how to edit the units that you can buy in island capture?
for example that you can buy a carrier!

and second question is it possible to limit units in island capture?
so every player just can have 1 battleship or something like that

This is very easy to do in theory but can require a lot of "trial and error" to get working.

You need to edit a file called universe\scenes\missions\multi\sceneX.scn (where X is the number of the map) in one of the MPAK files for the IC map. Open this file in a text editor, and search for "SpawnPoint Shipyard" or "SpawnPoint Airfield". You'll then see a list of spawnable ships + planes - example: 

> "Stock 35" {
>
>           Count = I -1 ;
>
>           SquadSize = I 1 ;
>
>           Type = E ShipClasses : Narwhal  ;
>
>         }
>
>         "Stock 36" {
>
>           Count = I -1 ;
>
>           SquadSize = I 1 ;
>
>           Type = E ShipClasses : DeRuyter  ;
>
>         }
>
>         "Stock 37" {
>
>           Count = I 0 ;
>
>           SquadSize = I 1 ;
>
>           Type = E ShipClasses : Northampton  ;
>
>         }
>
>         "Stock 38" {
>
>           Count = I 0 ;
>
>           SquadSize = I 1 ;
>
>           Type = E ShipClasses : SouthDakota  ;
>
>         }

The "Count" value specifies how many of each ship/plane are available (-1 means an infinite number are available). This should answer your second question - though I haven't tried it yet, you should be able to limit the number of each unit spawnable, so that, for example, each side could only get one battleship (and once it's sunk, you can't get another!)
It's also easy to either change the names or add new "Stock" entries to the list. All the spawn points have lists for both US and Japanese forces.

The difficulty is, firstly, finding which MPAK file is the right one to edit. There appear to be many different files for each IC map. I think these correspond to different player number and map size settings; so 1_scene1IC2.mpak contains the files for IC map 1 (Dreadnought) medium size with 2 players. The name format appears to be X_sceneYicZ.mpak, where X is the number of players, Y the map number, and Z the size (1=small,2=medium,3=large)

Secondly, you'll then have to work out which "SpawnPoint Shipyard/Airfield" list corresponds to which shipyard/airfield in the map. Being familiar with the map layout will help, but you may have to try a few times before you get it right!
## Post #68
- Username: Drawde
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 26, 2007 9:00 pm
- Post datetime: 2009-06-10T11:40:29+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Also, I have a question of my own: Does anyone know where the in-game text is stored? I.E. the messages displayed in the game, unit names and descriptions, menu text etc.? All the .lua and .scn files simply contain references to text stored elsewhere - but where is this? I've looked in almost all the .mpak files.
## Post #69
- Username: Eisenhower
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 05, 2009 6:14 pm
- Post datetime: 2009-06-11T22:17:12+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

ok first thanks for the help Drawde! i looked a bit around and managed to add ships and planes

"Stock 35" {
Count = I 5 ;
SquadSize = I 1 ;
Type = E ShipClasses : Narwhal ;

i tried to limit ships to 5 in this case but every other number than 0 just means there are unlimited ships or planes!

and i also tried to add a carrier
like this:

"Stock 41" {
Count = I 1 ;
SquadSize = I 1 ;
Type = E ShipClasses : Lexington ;

i can see the ship in the ingame menu of the shipyard but when i try to spawn it the game crashes
if you have an idea to make this work it would be great.



edit: just found out that it works fine with other ships

"Stock 42" {
Count = I 1 ;
SquadSize = I 1 ;
Type = E ShipClasses : Iowa ;

works fine just the carriers crashes the game!
## Post #70
- Username: rosciak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 14, 2009 2:25 am
- Post datetime: 2009-06-14T00:52:26+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hi all I just want to say hello. I'm big Midway fan and IMO new or edited multiplayer maps can bring new life for this game. People got boring playing all these 9 maps and Eidos forgot us. Many people talking about how-to but noone did that. If I can help in any way - i'm ready. We have small community site [http://battlestations.eu](http://battlestations.eu). We can inform our community and other players, we can host new maps. I will be watching your progress... especially Midway progress...
## Post #71
- Username: knowledgeseeker
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 19, 2009 8:47 pm
- Post datetime: 2009-06-19T17:32:15+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

can someone help me? (i use a program called BSM Ripper to unzip/zip the files b.t.w.)

im trying to mod BSM but 

i dont know how to add a new map to multiplayer

also ive run into constant game-crash problems when i try to add a unit that is not native to the map in other words a unit form another map

ive added the necessary file for the unit(in this case the clemson-class)
ive modified the scn file of the map

first this

"precache" {
    "tree" {
      Vehicles = IA 18 1 2 17 19 23 31 52 53 69 70 73 81 101 108 113 150 159 162 ;
    }
to this

"precache" {
    "tree" {
      Vehicles = IA 18 1 2 17 19 23 25 31 52 53 69 70 73 81 101 108 113 150 159 162 ;

and this

        "Unit1" {
          ClassId = I 25 ;
          ClassName = S "globals.unitclass_Clemson" ;
          Icon = I 4 ;
          Name = S "Fletcher" ;
        }

and this

}
entity "Fletcher" (DestroyerGen) {
  localframe -0.8789 0.0000 -0.4772 0.0000 0.0000 1.0000 0.0000 0.0000 0.4772 0.0000 -0.8789 0.0000 -3600.3481 0.0266 6849.7598 1.0000 ;
  template "USA\SEA\Clemson-Class" ;

  properties (Common, Command, GameUnit, Ship)  {
    "Command" {
      CommandTarget = R "" ;
    }
    Crew = E  CrewXPLevels : Veteran  ;
    FireStance = E  FireStances : FreeFire  ;
    OwnerPlayer = E  Players :"Player 1" ;
    Race = E  Races : USA  ;
    RepairZoneArea = R "" ;
    StartSpeed = F 10.0000 ;
    Type = E  ShipClasses : Clemson  ;
  }

but the game keeps crashing on me i dont know what to do now

i got one thing right with the Minekaze



minekaze.JPG (41.43 KiB) Viewed 1159 times


but it wason the palawan pass so it was already native to the map

tryed to move it and the game crashed again

help please
## Post #72
- Username: setUP
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 04, 2009 3:50 am
- Post datetime: 2009-07-04T13:02:14+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Please,can some one release mod which would make the one shot kill enemy ships. I try to do it myself, but when I change the damage from the shot(compile file and replace old in gamedirectory), loading a mission, it throw me into the desktop   
I need help! Please! I need the Japanese ships will kill enemy with one shot, and US forces to. But it is necessary that these were two separate mods.First is for the Japanese, the other for the US.
## Post #73
- Username: rosciak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 14, 2009 2:25 am
- Post datetime: 2009-07-19T00:03:04+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

If anyone is interesting with that, Battlestations Midway is already modded. We succesfully testing new multiplayer map for this game. If anyone wants help or more info, screenshots or videos taken from new map, pls visit our Midway fansite [http://battlestations.eu](http://battlestations.eu)

There is a video that showing new modded unofficial map for Midway.

[http://www.youtube.com/watch?v=UQckhZnXxYA](http://www.youtube.com/watch?v=UQckhZnXxYA)
## Post #74
- Username: helpppk
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 29, 2009 8:35 am
- Post datetime: 2009-07-29T11:06:34+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Hello,

Great topic and thanks for the files that are already on here...

I have been trying to add ships to the island capture skirmish BS-P but with out any type of success so far, I have been following the two types of ways to add ships but nether have worked...

Is it possible for someone to write up a step by step guide for how to add the ships with some examples..

I have been trying to add ships to this map 1_scene1IC1.mpak which I believe to be 01-dreadnorgt Small, I update scene1 file however there appears to be many Shipyard lists and Small, Medium, and Large I have been trying to add the ships to the small ship yard as I believe this is the shipyard that the play begins with..

Also if you have added ships to these maps would you be able to post them here with details of what’s been added that way I will be able to test the files and see how they have been edited.

Thanks in advance for any help that you can provide.
## Post #75
- Username: RTY
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 25, 2009 5:18 pm
- Post datetime: 2009-11-26T09:27:26+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Well I use the BSP Ripper extract the mpak file "2_usn_09SOLO.mpak" and I open the file , saw a scn file called usn_09_leyte.scn , I open it , I can,t see any thing inside , Why ? 
The other question is how to change ship name in SP ? Which file ? (eg: USS A change to USS B)
## Post #76
- Username: rosciak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jun 14, 2009 2:25 am
- Post datetime: 2010-02-18T09:33:57+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

Since last half of year we released two new mappacks for Midway (total 11 new multiplayer maps). First mappack was simple release of 5 new maps, online community downloaded it many times, second mappack (6 new maps) was a big step forward, with changes like retexturing many units, detailed maps, sound mod (many new sounds for whole game), awesome environments...

It's sad all these guys interested with modding battlestations are gone now. Where are you timetraveller and others?

Watch our promo movies for new maps on Youtube

[http://www.youtube.com/watch?v=-Qa4UovcNGU](http://www.youtube.com/watch?v=-Qa4UovcNGU)

[http://www.youtube.com/watch?v=YgZfYTeE_kA](http://www.youtube.com/watch?v=YgZfYTeE_kA)

[http://www.youtube.com/watch?v=0n5uEoscCck](http://www.youtube.com/watch?v=0n5uEoscCck)

[http://www.youtube.com/watch?v=-CnF3Bz7r_8](http://www.youtube.com/watch?v=-CnF3Bz7r_8)

Now we have the whole PC and Mac Midway community concentrated in one place - [http://battlestations.eu](http://battlestations.eu) forum, news, downloads and Midway is alive. Where are you ? Come back and help us.
## Post #77
- Username: rupertburns
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 22, 2010 5:52 am
- Post datetime: 2010-02-21T22:07:48+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

I have been using the MPAKs for a while, and I love them (thanks btw).  However, I added the addons Mustang and Carrier Packs and now I they do not work.  Is there a way to work them into the the game with the addons.

Thanks
## Post #78
- Username: celloplayer5
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 05, 2010 4:54 am
- Post datetime: 2010-07-31T02:01:01+00:00
- Post Title: Re: Battlestations : Midway PC  .MPAK

hello, 
on the subject of the 999999 CP point mod, every time i start the game it crashes. can some1 help me get this mod to work?
cello
