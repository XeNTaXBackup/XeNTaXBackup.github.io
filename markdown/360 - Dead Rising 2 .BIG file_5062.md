## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-19T04:45:53+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

[http://www.megaupload.com/?d=96UJJOQ0](http://www.megaupload.com/?d=96UJJOQ0)


Can someone look at this and maybe make a bms script that will extract these files with the names out of the archive, there is a table at the beginning of this chunk.
## Post #2
- Username: joqqy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-19T11:02:01+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

I already did this and have the models converted.
this is for the pc version

```
get unk01 long
get unk02 long
get unk03 long
get files long
get unk04 long
get namestart long
savepos tableoff
for i = 0 < files
goto tableoff
get NameOff long
get unk05 long
#print %unk05%
get zsize long # -4
get size long
get offset long # + 4
get type7 long
print %type7%
get zip long
savepos tableoff
goto NameOff
get name string
if zip == 1
math zsize - 4
math offset + 4
clog name offset zsize size
endif
if zip == 0
log name offset zsize
endif
next i


```


here is a pic of a model
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-09-19T16:11:08+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Thanks chrrox, it works !
## Post #4
- Username: joqqy
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-19T19:14:39+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

here is an update to auto convert textures to dds.

```
get type EXTENSION
print %type%
get unk01 long
get unk02 long
get unk03 long
get files long
get unk04 long
get namestart long
savepos tableoff
for i = 0 < files
goto tableoff
get NameOff long
get unk05 long
#print %unk05%
get zsize long # -4
get size long
get offset long # + 4
get type7 long
get zip long
savepos tableoff
goto NameOff
get name string
if zip == 1
math zsize - 4
math offset + 4
clog name offset zsize size
endif
if zip == 0
if type == "tex"
goto offset
get type1 long
print %type1%
get width2 byte
get width1 byte
get height2 byte
get height1 byte
getdstring null 0x10
get baseoff long
math offset + baseoff
math zsize - baseoff
   callfunction addDDSheader
   math zSIZE + 0x80
string name + ".dds"
   log NAME 0 zSIZE MEMORY_FILE
else
log name offset zsize
endif
endif
next i


startfunction addDDSheader
set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x0A\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x05\x00\x00\x00\x44\x58\x54\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x08\x10\x40\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0x11 width1 byte
putVarChr MEMORY_FILE 0x10 width2 byte
putVarChr MEMORY_FILE 0xD height1 byte
putVarChr MEMORY_FILE 0xC height2 byte

if type1 == -536805120
putVarChr MEMORY_FILE 0x57 0x31
endif
if type1 == 135
putVarChr MEMORY_FILE 0x57 0x33
endif
if type1 == -469696256
putVarChr MEMORY_FILE 0x57 0x35
endif

   append
   log MEMORY_FILE OFFSET zSIZE
   append
endfunction



```
## Post #5
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-09-25T07:34:50+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Nothing extracts for me... I tried out a lot of them already. Am I doing something wrong? All of the big files are very small. Except some packs like music.big or cine_props.big. None work. Only the sample file extracted for me.
## Post #6
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-09-25T08:23:25+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Working for anyone else? Dtmech? I see you reading this.
## Post #7
- Username: Malakesh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 30, 2010 8:46 pm
- Post datetime: 2010-09-25T12:49:55+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

It worked for me. Even worked with the files from the PS3 version. Just need a way to repack, and then the fun can truly begin.
## Post #8
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-09-25T16:49:58+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

How big are the files for you guys? Also what folders are you extracting the big files from? Sample: [http://filesmelt.com/dl/zombies.big](http://filesmelt.com/dl/zombies.big) This damn file is 50 mb but nothing is extracted out of it. I'm using the steam version and it hasn't released yet. Do you have to start the game once or something? Could anyone upload their bms script? I maybe doing something wrong.
## Post #9
- Username: Rich246
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 26, 2010 5:48 am
- Post datetime: 2010-09-25T21:50:10+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Looking forward to this getting better... 

I want to mod this game
## Post #10
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-09-25T22:14:09+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Never mind I got it working. Now, how did you get the models into max?
## Post #11
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2010-09-27T12:51:46+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Extraction works perfect, any chance of making a repacking tool?
I have extracted datafile.big and there is camera.txt, I want to increase the FOV and repack it.
## Post #12
- Username: Agret
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Jan 26, 2006 12:48 pm
- Post datetime: 2010-09-27T13:01:34+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Looking further at this it looks like it is possible to make own weapons 

items.txt contains every weapon/item in the game so you can add your own definitions to that
each map contains its own txt file with locations to spawn items so you can add your new weapon to it 

missions.txt contains a lot of references to:
ShowInDebugMenu = "true"

Perhaps we can enable the debug menu somehow?
## Post #13
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-09-30T08:49:19+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

How to make a quickbms for building back the datafile.big based on chrrox bms script?
## Post #14
- Username: sprayer
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Sep 10, 2010 2:09 pm
- Post datetime: 2010-10-01T09:57:37+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

how i can convert extracted .big files for 3d program?
## Post #15
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2010-10-02T02:08:12+00:00
- Post Title: 360 - Dead Rising 2 .BIG file

Okay, the farthest I've gotten so far is extracting "Combined Vertices 56" and "Combined Indices 2" files, but they don't have a specific file type.
## Post #16
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-10-03T08:27:12+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

How'd you do that anyways Dean? Did you do some bms scripting?
## Post #17
- Username: prefim
- Rank: n00b
- Number of posts: 19
- Joined date: Fri May 21, 2010 6:10 pm
- Post datetime: 2010-10-03T09:39:45+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

Hi Chrrox, 

Excellent script for quickBMS. Worked like a charm including the tex to dds. I'm asking the same question as someone else though. how did you get the model into max (or any other program for that matter). I looked inside the combined vertices 56 file but couldnt see a pattern to any regular file formats i knew.

I'm continuing to investigate but it would save heaps of time if you can shed any light on your workflow.

Cheers,

Mat
## Post #18
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2010-10-03T16:06:25+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from Ryan7259
>
> How'd you do that anyways Dean? Did you do some bms scripting?
No, just keep extracting the .big files it churns out. I did that 2 or 3 more times and got what looks like bone file names, and the combined vertices files. Don't know what format they're in, though.
## Post #19
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-10-03T18:00:44+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

No, I meant on FP, you had stars uniform texture for the swat gear. Did you somehow open the tex and converted it back?
## Post #20
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2010-10-03T21:21:56+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

That was with Texmod, nothing of the sort. [http://filesmelt.com/dl/texmod.zip](http://filesmelt.com/dl/texmod.zip) Launch deadrising2.exe with logging mode, use numpad + and - to sort through textures, rip the ones you want, exit the game and edit what you want, then create a package of the .log file it creates and re-launch the game with package mode or whatever it's called.
## Post #21
- Username: valvoga
- Rank: advanced
- Number of posts: 67
- Joined date: Sat May 01, 2010 10:03 am
- Post datetime: 2010-10-04T09:17:17+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

Oh,chroxx you're awesome
## Post #22
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-10-04T10:12:46+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

The contents of this post was deleted because of possible forum rules violation.
## Post #23
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2010-10-04T22:16:19+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

Thanks. Much easier to extract .big files, but it still doesn't help me with what format the model files are supposed to be in.
## Post #24
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-10-04T23:47:17+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

I looked in valuesets and saw some words. In the srv_matthew it said 'srv_matthew_mtl_pants.pdv'
## Post #25
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-10-05T00:39:43+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

Any way to unpack the .BIG files of the 360 version yet?
## Post #26
- Username: Malakesh
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun May 30, 2010 8:46 pm
- Post datetime: 2010-10-05T03:44:38+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

The means to unpack every version of the game's .big files are right here in this thread.
## Post #27
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-10-05T14:34:37+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from Dean
>
> Thanks. Much easier to extract .big files, but it still doesn't help me with what format the model files are supposed to be in.
Im not a programmer but the vertex/uvmap was stored inside:
geo_torsoShape Vertices 0

Im converted the file into float from srv_lulu:
[01.jpg](https://xentaxbackup.github.io/file/3496_01.jpg)
## Post #28
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-10-06T05:17:11+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from Malakesh
>
> The means to unpack every version of the game's .big files are right here in this thread.

I've tried both the BMS script and Gibbed's tools and it doesn't work for me
## Post #29
- Username: Mshi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 08, 2010 4:25 pm
- Post datetime: 2010-10-08T08:39:56+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

I cant read Indices correct.
Any advices?
## Post #30
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-10-08T10:42:15+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

they are tri-stip.
## Post #31
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2010-10-08T18:37:28+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from DerMeister
>
> Malakesh wrote:The means to unpack every version of the game's .big files are right here in this thread.

I've tried both the BMS script and Gibbed's tools and it doesn't work for meWhat file/platform? My tools work fine with PC and PS3 data with no problems, I'm sure they work for 360 data too.
## Post #32
- Username: Ryan7259
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jun 21, 2010 3:42 pm
- Post datetime: 2010-10-09T05:52:00+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from chrrox
>
> they are tri-stip.
On darkmatter2 modding section you said that some tools will be ready by tomorrow which was in September. Its been more than a week and it is already October.
## Post #33
- Username: Mshi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 08, 2010 4:25 pm
- Post datetime: 2010-10-09T16:05:58+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from chrrox
>
> they are tri-stip.
Thank you Chrrox
## Post #34
- Username: Dean
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 09, 2010 6:09 am
- Post datetime: 2010-10-09T17:57:54+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

Two people have figured out how to import the models and yet they cannot, for some reason, share how they did it.
## Post #35
- Username: DerMeister
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Mar 31, 2009 4:37 am
- Post datetime: 2010-10-11T17:03:41+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from Rick
>
> DerMeister wrote:Malakesh wrote:The means to unpack every version of the game's .big files are right here in this thread.

I've tried both the BMS script and Gibbed's tools and it doesn't work for me  What file/platform? My tools work fine with PC and PS3 data with no problems, I'm sure they work for 360 data too.

Yes 360, the PAL version of the game specifically. The only one I could get to extract was the music one.
## Post #36
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2010-11-18T08:24:02+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

Im getting this error when I run the script posted by chroxx
## Post #37
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-11-18T11:48:25+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

> Reply from CMihai
>
> Im getting this error when I run the script posted by chroxx
Are you trying to use a BMS script posted here in Max?
## Post #38
- Username: DIO007
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 12, 2010 6:45 pm
- Post datetime: 2010-11-18T15:09:59+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file


## Post #39
- Username: DIO007
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 12, 2010 6:45 pm
- Post datetime: 2010-11-18T15:18:01+00:00
- Post Title: Re: 360 - Dead Rising 2 .BIG file

Geo2Obj Converter
[Chuck.JPG](https://xentaxbackup.github.io/file/3617_Chuck.JPG)
