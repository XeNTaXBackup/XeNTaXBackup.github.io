## Post #1
- Username: Dazz
- Rank: beginner
- Number of posts: 21
- Joined date: Thu Mar 17, 2011 7:10 pm
- Post datetime: 2011-12-15T13:03:17+00:00
- Post Title: Final Fantasy XIII-2 extraction

I've got myself a Japanese copy of Final Fantasy XIII-2 for 360, opened it up, and it's surprisingly similar in contents to Final Fantasy XIII.

However, using QuickBMS to try and extract the delicious contents doesn't seem to work using the old script for the first game - anybody else got a copy they care to check out?

I would upload samples, but I'm not uploading 1.8gb of data...
## Post #2
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2011-12-16T22:23:05+00:00
- Post Title: Final Fantasy XIII-2 extraction

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-12-17T02:56:18+00:00
- Post Title: Final Fantasy XIII-2 extraction

[](http://img402.imageshack.us/img402/5839/newlightning.jpg)
Some small (but very weird) changes to the model format from FF13. chrrox and I are still working on extracting the data.
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-12-17T03:30:27+00:00
- Post Title: Final Fantasy XIII-2 extraction

sexy
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-12-17T10:26:46+00:00
- Post Title: Final Fantasy XIII-2 extraction

I'm pretty sure the filelist has a 48 byte header (as indicated by the size of actual data given 16 bytes in), so I've tried running the data through a whole bunch of different ciphers using the key from img.key. I've tried the 16 bytes at offsets 0 and 32 as IV's and I've tried decrypting each with the given cipher to use as the new IV for the file, but unfortunately none of that produced anything readable. The 8 zeroed bytes at the end of the file also seem suspicious. There are too many unknowns (like whether the img.key is the correct key to be using, if the IV is in the file itself or the xex, whether the encrypted data is segmented to intentionally throw people off, whether the encryption algorithm is something known or something modified/proprietary, etc.) to keep on randomly guessing without being able to disassemble the xex, and unfortunately I don't have a copy of IDA capable of doing that.

So, no correct filenames unless someone else wants to decrypt and decompile the xex for me.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-17T22:36:19+00:00
- Post Title: Final Fantasy XIII-2 extraction

here is the best extractor that is possible at the moment.
[viewtopic.php?f=33&t=4582&p=63683#p63683](http://forum.xentax.com/viewtopic.php?f=33&t=4582&p=63683#p63683)
## Post #7
- Username: livid123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 16, 2010 3:37 am
- Post datetime: 2011-12-19T02:12:37+00:00
- Post Title: Final Fantasy XIII-2 extraction

hi, MrAdults

i have a question. where is UV in trb file? ff13-2 model format is not much change.

ff13    = 2 vertex stream
ff13-2 = 3 vertex stream, but last stream(uv) have empty data?

i got everything almost ok, like pos,bone weight/index, but not UV. can't find data anywhere.

need your help.. thank you very much.
## Post #8
- Username: livid123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 16, 2010 3:37 am
- Post datetime: 2011-12-19T07:34:30+00:00
- Post Title: Final Fantasy XIII-2 extraction

I found uv in img bundle file by trace noesis.exe fopen(). and it's ok now.

great job, MrAdults.
## Post #9
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-12-19T08:35:02+00:00
- Post Title: Final Fantasy XIII-2 extraction

how can i extract the .trb file from the bin file? pls
## Post #10
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-12-19T15:15:59+00:00
- Post Title: Final Fantasy XIII-2 extraction

> Reply from 652845095
>
> how can i extract the .trb file from the bin file? pls

Lol:

Check the posts above and you'll find this:

[viewtopic.php?f=33&t=4582&p=63683#p63683](http://forum.xentax.com/viewtopic.php?f=33&t=4582&p=63683#p63683)
## Post #11
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-12-19T21:07:53+00:00
- Post Title: Final Fantasy XIII-2 extraction

> Reply from livid123
>
> I found uv in img bundle file by trace noesis.exe fopen(). and it's ok now.

great job, MrAdults.
They also changed the vertex weights to use absolute indices and just sorted their bones so that the bones with weight influences come first. (so a maximum of 256 weighted bones per model is imposed, but plenty of models still go way beyond 256 bones...just not weighted ones)

Despite this they still have the bone index maps in the file, and this new method is probably slower because they don't sort their vertices well to optimize matrix palette accesses. Overall both the changes were a fairly bad idea (taking UV's out of your interleaved vertex array is another performance hit on both consoles, not on most PC hardware though), unless of course they're correcting the data on load, but that would be pretty silly.
## Post #12
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-12-20T01:11:29+00:00
- Post Title: Final Fantasy XIII-2 extraction

when i extract the file "white_img.x360.bin" i got this error.
[error.jpg](https://xentaxbackup.github.io/file/4920_error.jpg)
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-20T02:10:27+00:00
- Post Title: Final Fantasy XIII-2 extraction

update your quickbms
## Post #14
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-12-20T03:03:28+00:00
- Post Title: Final Fantasy XIII-2 extraction

already updated the bms to 0.5.4,but still get the same error....
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-20T03:59:12+00:00
- Post Title: Final Fantasy XIII-2 extraction

use command line
not sure what your doing.
tons of people already have it working so i cant do much to help.
## Post #16
- Username: Seyiji
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Sep 20, 2011 11:37 pm
- Post datetime: 2011-12-20T10:15:01+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from chrrox
>
> use command line
not sure what your doing.
tons of people already have it working so i cant do much to help.I had the same error as 652845095 and I "fixed" it by editing the script you posted [here](http://forum.xentax.com/viewtopic.php?f=33&t=4582&p=63683#p63683)

```
log MEMORY_FILE 0 0
put NAME string MEMORY_FILE
get size asize MEMORY_FILE
math size - 4
goto size MEMORY_FILE
getdstring EXT2 4 MEMORY_FILE
if EXT2 == "360"
set EXT "x360"
else
set EXT ps3
endif

comtype unzip_dynamic
for
findloc START string \x78\xDA
goto START
findloc END string \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end
math SIZE - START
goto END
if SIZE > 0x40
clog MEMORY_FILE START SIZE SIZE
getdstring SEDB 8 MEMORY_FILE
if SEDB == "SEDBRES "
goto 0x30 MEMORY_FILE
get COUNT long MEMORY_FILE
math COUNT * 16
math COUNT + 0x40
goto COUNT MEMORY_FILE
getdstring TRB 7 MEMORY_FILE
if TRB == "SEDBtxb"
string START + .
string START + EXT
get SIZE asize MEMORY_FILE
set NAME START
string NAME + .trb
log NAME 0 SIZE MEMORY_FILE
set NAME START
string NAME + .imgb
clog NAME OFFSET ZSIZE2 SIZE2
endif
endif
if SEDB != "SEDBRES "
set OFFSET START
set ZSIZE2 SIZE
get SIZE2 asize MEMORY_FILE
endif
endif
next
```


I have no idea if this will solve your problem 652845095 and I take no credit for this script it is all chrrox's work all I did was move the line "\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00" to be in line with "findloc END string" which then allowed me to get past the error 652845095 was experiencing although when I ran it on the sample files provided by rexil it found nothing to extract.
## Post #17
- Username: 652845095
- Rank: beginner
- Number of posts: 29
- Joined date: Tue May 31, 2011 12:22 pm
- Post datetime: 2011-12-20T14:05:13+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

yeah! it works,thanks a lot...
## Post #18
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-12-21T04:35:56+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Stupid question: is there any difference between ps3 and 360 models??
## Post #19
- Username: Darko
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-21T04:36:33+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

no
## Post #20
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2011-12-21T05:57:59+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from chrrox
>
> no

Thnks
## Post #21
- Username: unlimited32
- Rank: beginner
- Number of posts: 38
- Joined date: Sat Oct 16, 2010 8:27 pm
- Post datetime: 2011-12-22T16:23:46+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hello, how do i extract the game data from the PS3 version?
## Post #22
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-22T18:20:55+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

the same way
## Post #23
- Username: purupeo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 11, 2010 2:55 am
- Post datetime: 2011-12-22T19:16:54+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hello, models are too small, but they say "the game uses real time rendering movies", maybe on the disc have hq models?
## Post #24
- Username: purupeo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-22T20:32:51+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

those are the only models on the disk. its the shaders they use.
you need to set up the textures correctly.


if you want i looked and dint see anything but this script will extract everything from the game but it wont match anything to its textures and it will name some files trb that contain no mesh data.
I looked and dint see anything the first script missed but ill throw this out there for those that think something might be missing.

```
log MEMORY_FILE 0 0
put NAME string MEMORY_FILE
get size asize MEMORY_FILE
math size - 4
goto size MEMORY_FILE
getdstring EXT2 4 MEMORY_FILE
if EXT2 == "360"
set EXT "x360"
else
set EXT ps3
endif

comtype unzip_dynamic
for
findloc START string \x78\xDA
goto START
findloc END string \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end
math SIZE - START
goto END
if SIZE > 0x40
clog MEMORY_FILE START SIZE SIZE
getdstring SEDB 8 MEMORY_FILE
string START + .
string START + EXT
if SEDB == "SEDBRES "
set NAME START
string NAME + .trb
else
set NAME START
string NAME + .imgb
endif
get size asize MEMORY_FILE
log NAME 0 SIZE MEMORY_FILE
endif
next

```
## Post #25
- Username: livid123
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 16, 2010 3:37 am
- Post datetime: 2011-12-23T05:22:40+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

wow, is that Lighting animation come from .mot file?

may be it's skin matrix animation, but hard to disassemble shader-pcode in console format
## Post #26
- Username: amano
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 11, 2011 6:46 pm
- Post datetime: 2011-12-23T06:03:52+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I want to know how to get the model files Or can you send them to me?
## Post #27
- Username: cenjianneng
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 02, 2011 2:58 am
- Post datetime: 2011-12-26T23:11:02+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from chrrox
>
> those are the only models on the disk. its the shaders they use.
you need to set up the textures correctly.


if you want i looked and dint see anything but this script will extract everything from the game but it wont match anything to its textures and it will name some files trb that contain no mesh data.
I looked and dint see anything the first script missed but ill throw this out there for those that think something might be missing.

how did you do that?
use itself shader? 
it so cool!  

can you show the shader map?
## Post #28
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-12-28T19:46:41+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

The contents of this post was deleted because of possible forum rules violation.
## Post #29
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-28T20:38:53+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

not all models are matched up correctly. you will have to match some up manually.
The uv's are paired with the textures.
## Post #30
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-12-29T00:33:43+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I'm not sure you understand the problem I'm having. That or I misunderstand what you're asking me to do here. The IMGB file was manually matched the the 7kb TRB, which is the only TRB it will export the textures with. When matched to either of the other two Noel models, the textures don't export at all and his UV's come out as spaghetti. It's like the 7kb TRB is suppose to be apart of his model file, but for whatever reason it's not? I'm not even sure I'd say it's a problem with your script, so much as it's an oddity with the game.. But uh, yeah. I don't know what to do here to get his UV's exported intact.
## Post #31
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-12-29T00:36:07+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

7kb is way to low that is the wrong file. most character texture files should be around 5mb and the model file should be >500k < 1.2 mb or so
## Post #32
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-12-29T00:46:24+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Well yes. The two Noel TRB's are around 500k and the IMGB is around 3-4mb. The problem is that his IMGB isn't working with his TRB's, it's only working with this mysterious 7kb TRB that contains no mesh whatsoever. And I see now that you managed it, but I have no idea what you did, hmm.. Curse it all.
## Post #33
- Username: Krisan Thyme
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Jan 15, 2011 4:04 am
- Post datetime: 2011-12-29T00:56:08+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Wait a sec.. I think I see the problem. I tried the script posted on the last page in this thread, not the one you ORIGINALLY posted in the Noesis thread. Huh. I'll need to poke around to be sure, but I think that's all my problem was.

Edit:
Yep, that was definitely my problem. The original script worked much much better overall than the one posted on the last page. I now have it working properly. Sorry for the inconvenience! I had no idea the two were even different until I took a look at them a few minutes ago.
## Post #34
- Username: Jecht
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Jan 26, 2012 9:32 am
- Post datetime: 2012-02-06T18:18:02+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

lol... ya are quick for extract this thing in no time XD...
hmm.... if any ask, i don't really like the FF13, but... some time i get interesting in the clothes of the model, for take them...


to bad i don't have the iso, our ever space for get the model of this ones... well... just two, the rest can be erase it for ever LOL! [yeah, just the clothes of Snow & Sahara]

other thing, have any manage to extract that two?
## Post #35
- Username: aspen552001
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Feb 10, 2012 10:55 pm
- Post datetime: 2012-02-10T15:53:26+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hi, this is my first time trying to extract 3D models. Can someone please guide how and what should I do with the .bin files in order to extract the 3D models out.

Thanks a lot.
## Post #36
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-02-12T23:10:32+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Anyone mind uploading the latest quickbms? Aluigi's site's gone down.
## Post #37
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T23:15:39+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Aluigi's site is fine.
Just don't use the altervista one.
## Post #38
- Username: s25jin
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 15, 2011 1:11 am
- Post datetime: 2012-02-19T00:00:08+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Stupid question I will.
i was extract *.bin(ex.white_z0240c_img.x360.bin)........ .*.trb using neosis . but  i can't show imgb
could you tell me how to convert imgb to dds or pong ?
## Post #39
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-02-19T15:49:11+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from s25jin
>
> Stupid question I will.
i was extract *.bin(ex.white_z0240c_img.x360.bin)........ .*.trb using neosis . but  i can't show imgb
could you tell me how to convert imgb to dds or pong ?

Evrery trb must have a imgb file... basically renaming both of them with the same name will load the model correctly.
## Post #40
- Username: damboc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Feb 23, 2012 10:58 pm
- Post datetime: 2012-02-23T15:08:38+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

hello,
Does anyone have there a solution for extracting audio files and subtitles
thank you
## Post #41
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-04T16:15:46+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I bought DLC for this game, and want to modify it to add my own additional costumes
But unfortunately the DLC has compressed archives, and there seems to be no sign of data indicating pack/unpack size ?? 
Still I think its possible to make small edits to the model and its textures, as long as my new compressed size is equal or smaller.

Goal:
Import the geometry /Edit and send back to the game

> I had a hard time importing the geometry, chroxx sent me his old FF13 script, written in maxscript. However the script would hang on trying to search for chunk IDs.
I just went into hex and manually input the offsets for all the objects of my model. However my imported geometry looked like this



seems that the model is affected by some bounding box?????? the vertices were cut or divided into four quadrants.
I was able to easily move them back to there correct spot in 3dsmax, so atleast I have a method to input/output the vertices

..but when I tested my edits in game!! nothing happened 

I coloured the bikini blue, and that shows in game


however no vertex edits seem to be showing?????


I went as far as taking a whole vertex chunk and nulling all with zeros! but nothing appears apparent ingame!!


Can anyone clarify the FF13-2 Format?

What I did was searched for the string "STMS"
this would bring me to 3 different data types, which would repeat
the first STMS instance is face data, the second instance is vertex data, and I'm not sure what the third instace is?

the STMS chunks just repeat in that order, and thats how I've imported the geometry. I'm only editing the second STMS instance (Vertices)

does anyone have an idea to why my vertex edits are not appearing ingame?


overview of method
- Jtagged Xbox360 (Freestyle Dashboard) transferred saves&dlc via FTP
- wxPirs to extract DLC from LIVE container
- QuickBMS / BMS script to dump & repack compressed files
- Maxscript to import / export 2d & 3d data
- Xbox360 SDK to create new LIVE package
- YarisSwap to hex the LIVE package to work on jtagged unit
## Post #42
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2012-03-04T22:16:05+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Anyone know what this is?



49260544.x360.trb if you want to see for yourself.

Turns out it's an adornment for your monsters...

Anyway there's a few models that either don't have UVs, or have distorted UVs. Particualarly 11530240.x360.trb.
## Post #43
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-03-06T03:07:59+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

mariokart64n, I wrote a small utility to extract the different sections of the trb format.  It allows you to align the data more quickly from different trb files for comparison in a hex editor.  

Here is the link.
[http://www.mediafire.com/?5mu4crcb58ub5c6](http://www.mediafire.com/?5mu4crcb58ub5c6)

To use it, type the following at the command prompt:

"FFXIII trb Extractor.exe" <filename> <preferred prefix>
example: "FFXIII trb Extractor.exe" 1619968.x360.trb SerahBeachwear

If I may ask, what did you do to the trb to color the bikini blue?  

Also, I took your advice and 0'ed out the second section of certain STMS chunks, and was successful in getting it to show up "in game".  

 



I too, would like a better explanation of the trb AND imgb formats.  It would be really nice to be able to edit the texture maps and put them back as well.
## Post #44
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-03-06T19:09:57+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

First, chrrox and MrAdults, you guys rock so hard I had to drive over to my mom's house and kick her in the face! (figure of speech) ¯\ (ツ) /¯

Second, mariokart64n, you're too ambitious. You're making the rest of us look bad. (°-°)

Third, EcheloCross, I second having detailed info on the trb AND imgb files.
Digital Tutors and Lynda don't have training videos for this stuff......|◔◡◉| Huuuuur

And finally, I didn't realize they used photo textures for the buildings in Academia; kinda cool: [http://i.imgur.com/0iDqd.jpg](http://i.imgur.com/0iDqd.jpg)

El Duderino, out.
## Post #45
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-03-07T02:39:24+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Well, I'm getting closer to understanding the trb + imgb relation. I've got the proper imgb segments into some kind of dds format based on what MrAdults said a year or so ago in the FFXIII-1 thread.
MrAdults explained the trb format pretty well for all parts of it in that old thread.  The GTEX segments refer to the offsets, size and type in the corresponding imgb file.
See: [viewtopic.php?p=36433#p36433](http://forum.xentax.com/viewtopic.php?p=36433#p36433)

This is the output from noesis.


..and this is what I'm able to get so far based on reading MrAdults advice.

Its pretty easy to see once you get this far, that the data is endian swapped before you slap a dds header on it.
I'm not sure if I'm defining the dds header correctly.
The only way I get the data to load in the dxtex tool is using DXT1 for the FourCC bytes, but as you can see, this is not proving to be enough.

He mentions that he had to write an un-tiler, and I think that's where I'm at now. 

If anyone can offer any guidance, please help.
## Post #46
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-03-07T20:52:08+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Did you check the Noesis source (pluginshare.h)?
I saw the raw and dxt untilers in there, but I have C dyslexia.
## Post #47
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-03-07T21:09:19+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Source code for noesis is public?  I've been looking for it.  You have a link?

I looked at that file in the pluginsource.zip.  It talks about the prototype methods for un-tiling I think.

I've taken a dds exported from noesis and inverted the colors in photoshop.  I then saved it as DXT1, stripped the header, reversed its endianness every 2 bytes, and injected back into imgb file.  I also told the GTEX segment in the trb the new size of the dds data.  

Since the data wasn't re-tiled, I assume noesis still un-tiled it again when viewed, but this is the result.
## Post #48
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-07T21:54:33+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

man, I can't believe you got the geometry to alter in game... now I'm totally confused.. shit why do I suck >_< !!! damn damn damn

sorry for being offline *cough* MASS EFFECT 3 IS FUCKING AWESOME!

can you give more details on what you zero'd, like the offset etc.. so I can reattempt the experiment on my end.

Also I got the textures ingame by using a program voltron created before me. initially I wanted to mod xbox360 games, but I did not know how to program at all.
so I took a swizzled xbox360 texture 1024x1024 = over 1million pixels ... in paintshop and I rebuilt it pixel for pixel.. it took me over a month. but I was the very first person to put a texture mod on the xbox360.

later I asked voltron to reverse my findings, but instead he just wrote a pixel manipulator. where i was able to script up a new pixel order. O_O
retarded that I did this I know, but I manually redefined each pixel to unswizzle the texture... the draw back is I can only swizzle and unswizzle textures that I have scripted an order for... 

so long story short I have an alternative method to tiling texture.. but it is not conventional!

anyway you can find that over here if you are interested;
[viewtopic.php?f=18&t=2205](http://forum.xentax.com/viewtopic.php?f=18&t=2205)
## Post #49
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-03-07T23:05:10+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

What I did to get the geometry back in game was 0'ed out the STMS section 24 bytes after the STMS header to the end of the STMS section, and then used the method you described to get it back into DLC.  
To get true texture mods for this game, I need to learn how to unswizzle + reswizzle them, and then we need a filelist decryptor+encryptor to get past the re-zlibbed chunks being too large.  If anyone can help with the filelist decrypting+encrypting please let me know.
## Post #50
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-07T23:32:30+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I contacted another hacker involved with alot of 360 hacking. this was his reply

> Reply from Genesis
>
> we have already figured out the encrypted data (and it's compressed) we also made are own DLC days ago


.. I'm not good with compressions or encryption, but this gives us a push in the right direction.. I wonder if its xmem? they can't leak it.. I wonder what is soo hush about it
## Post #51
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-03-08T00:08:04+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Yup, Genesis and I wrote the ffxiii-2 save editor.  The decryption he's talking about is not for filelists.  I have made some progress though.  I pulled the decrypted filelist out of memory.  It was still zlibbed, but I was easily able to unzlib it.  I now have the filelists in plain text.  I'm going to try to patch the xex to skip the decryption and just go straight from decrypted (still zlibbed) filelist.  

Last thing in the way after that for true in game texture mods is the un-swizzling/re-swizzling.
## Post #52
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-08T00:27:35+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

theres a bit of C code included with the SDK docs is there not?

I'll PM you what I got, I tried transcoding it before but coudnt understand 100% the syntax of C


Edit

.. I still cant get vertex edits to show in game.. I'm doing something dumb I know it


anyway I wanted to show you something off topic...

I was doing vertex modding for smash bros brawl early on, before they had mesh import.

I imported marth, and I completely remodeled him into a different character just by pushing the vertices and modding the textures!.
I did the same with lucario > mewtwo, and ganon > gannon ... but anyway even if we can not reconstruct the DLC, I can't wait to get vertex mods working !! 


[func_swizzle2.zip](https://xentaxbackup.github.io/file/5166_func_swizzle2.zip)
## Post #53
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-03-10T06:23:26+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Oooooooooo, it's written in Python. ಠ.ಠ
I can actually understand "that".  
Thanks Mario Kart.
## Post #54
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-11T07:15:41+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

[](http://www.youtube.com/watch?v=GIQePZcDXUQ)


[http://www.facepunch.com/threads/1169563?p=35092099](http://www.facepunch.com/threads/1169563?p=35092099)
[http://www.gamefaqs.com/boards/619314-f ... 2/62200226](http://www.gamefaqs.com/boards/619314-final-fantasy-xiii-2/62200226)
[http://www.finalfantasy-fxn.net/boards/ ... -2-Modding](http://www.finalfantasy-fxn.net/boards/showthread.php?12540-FF13-2-Modding)
[http://finalfantasyforums.net/showthread.php?t=52027](http://finalfantasyforums.net/showthread.php?t=52027)
[http://finalfantasy-xiii.net/forums/sho ... p?p=368466](http://finalfantasy-xiii.net/forums/showthread.php?p=368466)
[http://www.finalfantasyforum.com/final- ... dding.html](http://www.finalfantasyforum.com/final-fantasy-13/9245-ff13-2-modding.html)
[http://www.ffnet.net/forum/](http://www.ffnet.net/forum/)
## Post #55
- Username: korupt
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jul 09, 2005 8:15 am
- Post datetime: 2012-03-12T08:09:09+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Great work! mario. I hope you do other edits.
## Post #56
- Username: Newbie31
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 12, 2012 7:00 am
- Post datetime: 2012-03-14T23:06:26+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

hi, I'm real new at this, no laughing please.

I've had a look at alot of diffirent guides for FFXIII-2 and can get to opening models with Noesis but when I do they all come up with crazy textures. 
Could anyone tell me where I went wrong.

what I did?
1.backup FFXIII-2 xbox360 version.
2.export ISO with noesis to "".bin
3.open ".bin with quickbms to get "".trb
4.open "".trb with Noesis

also my files have the suffix "Number".ps3.trb but they come from Xbox360?
[Crazy_tex.png](https://xentaxbackup.github.io/file/5189_Crazy_tex.png)
## Post #57
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-15T06:01:20+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

the xbox360 requires or preforms best with tiled texture, so it can gain some speed over the GPU during rendering.
because the two platforms are different (PS3) and (XBOX360) your textures appear swizzled.

the only detection mechanism for noesis to distinguish between the xbox360 format and the ps3 format is that file extension.. and yous are buggered up.

simple rename them, or re-extract your files

a batscript you can use to rename your folder

```
FOR %%1 in (*.ps3) DO REN %%1 %%~n1.x360.trb
FOR %%1 in (*.ps3.imgb) DO REN %%1 %%~n1
FOR %%1 in (*.ps3) DO REN %%1 %%~n1.x360.imgb
```

[rename.zip](https://xentaxbackup.github.io/file/5191_rename.zip)
## Post #58
- Username: EcheloCross
- Rank: veteran
- Number of posts: 88
- Joined date: Sun Feb 28, 2010 1:57 am
- Post datetime: 2012-03-15T20:54:34+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Well well.  I made some progress.  Looks like big time mods are possible now!
## Post #59
- Username: Newbie31
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 12, 2012 7:00 am
- Post datetime: 2012-03-15T21:53:09+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Thanks for the rename.bat, renamed the files and the textures now work fine.
I tried rextracting and the files always come out with the suffix .ps3.trb, must be the extracter.

Thanks Again.
[fixed.png](https://xentaxbackup.github.io/file/5192_fixed.png)
## Post #60
- Username: Newbie31
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 12, 2012 7:00 am
- Post datetime: 2012-03-16T21:48:46+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

heyo, its me again.

I need some more help, I am most familiar with modding Oblivion which uses "".nif, I rarely export(I use 3dsmax) to anything other than .nif or .b3d so I know nothing about collada".dae" and wavefrontobject".obj". Do they export mapping channels and UVWmaps, because when I export from noesis to either and than import into 3dsmax it comes up with "can't find texture paths" so I open the material editor and manually attach the right textures to the right part of the mesh but it doesn't unwrap and align the texture properly.

Could someone offer some advice about what I'm doing wrong?
## Post #61
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-17T00:34:08+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from Newbie31
>
> heyo, its me again.

I need some more help, I am most familiar with modding Oblivion which uses "".nif, I rarely export(I use 3dsmax) to anything other than .nif or .b3d so I know nothing about collada".dae" and wavefrontobject".obj". Do they export mapping channels and UVWmaps, because when I export from noesis to either and than import into 3dsmax it comes up with "can't find texture paths" so I open the material editor and manually attach the right textures to the right part of the mesh but it doesn't unwrap and align the texture properly.

Could someone offer some advice about what I'm doing wrong?

Porting models from noesis violates the terms stated in the noesis readme. And also your problem is not related to FF13-2 in the slightest.
## Post #62
- Username: Newbie31
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 12, 2012 7:00 am
- Post datetime: 2012-03-17T07:25:31+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

sorry, I saw the diffirent outfit mods and thought how awesome it would be to be able to have similar ones. I assumed that they were done with noesis. Thanks anyway.
## Post #63
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-03-20T11:10:44+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Why this script does not work on Ps3 version?

```
log MEMORY_FILE 0 0
put NAME string MEMORY_FILE
get size asize MEMORY_FILE
math size - 4
goto size MEMORY_FILE
getdstring EXT2 4 MEMORY_FILE
if EXT2 == "360"
set EXT "x360"
else
set EXT ps3
endif

comtype unzip_dynamic
for
findloc START string \x78\xDA
goto START
findloc END string \x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
set SIZE end
math SIZE - START
goto END
if SIZE > 0x40
clog MEMORY_FILE START SIZE SIZE
getdstring SEDB 8 MEMORY_FILE
if SEDB == "SEDBRES "
goto 0x30 MEMORY_FILE
get COUNT long MEMORY_FILE
math COUNT * 16
math COUNT + 0x40
goto COUNT MEMORY_FILE
getdstring TRB 7 MEMORY_FILE
if TRB == "SEDBtxb"
string START + .
string START + EXT
get SIZE asize MEMORY_FILE
set NAME START
string NAME + .trb
log NAME 0 SIZE MEMORY_FILE
set NAME START
string NAME + .imgb
clog NAME OFFSET ZSIZE2 SIZE2
endif
endif
if SEDB != "SEDBRES "
set OFFSET START
set ZSIZE2 SIZE
get SIZE2 asize MEMORY_FILE
endif
endif
next
```
## Post #64
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2012-03-27T03:02:31+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Try the script that chrrox posted in the middle of page 2.
## Post #65
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-03-28T10:57:56+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I've tried all but not working,hic
## Post #66
- Username: messiahlad
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 27, 2012 5:10 pm
- Post datetime: 2012-03-28T11:46:04+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Wow this thread is interesting! Im very impressed and a little confused. Im wondering how you guys are able to get your modded textures back into the imbg + trb files. Im not trying any thing close to the vertex/ geometry mods you have done, just simple texture map changes. 

ps I am only new here and I am very impressed by the wealth of information shared by the community. glad to be here.
## Post #67
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-03-28T23:35:35+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I've been slowly working on a tool to release, which will handle both texture and geometry modding. maybe even new model import (ultimate goal)
anyway the xbox360 uses image tiling to make the data more presentable to the systems processor.. but on the human side the actual image looks like a pile of crapolia after tiled

the only method I can offer is re-writting the IMGB into a XPR2

an XPR2 file is generated by the xbox360 SDK, using its bundler.exe tool. the bundler handles textures which converts them between untiled and tiled images...

so if you can get your hands on the SDK, then you'll have no problem modding the textures. I'm just working on a "IMGB to XPR2" and a "XPR2 to IMGB" script... 

more updates as I get free time  ..which seems wont be anytime soon
## Post #68
- Username: messiahlad
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 27, 2012 5:10 pm
- Post datetime: 2012-03-29T09:28:00+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I know the feeling about "free time". Thanks for such a concise explanation, looking forward to attempting it. 
Good luck with automating the process, it will make a lot of people very happy(me including if i cant figure it out before then).
nice work on the zero samus mod, very tidy work.
## Post #69
- Username: messiahlad
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 27, 2012 5:10 pm
- Post datetime: 2012-04-02T14:16:55+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hi Mario
Hows the tool creation going?
I got my hands on sdk 20871.2. and am currently learning the "bundler.exe" tool as well as trying to fast pace my 3DS max skills. 
have you thought of releasing your smoothed down Serah geometry model for people to do texture wraps for?
With a smooth model I would love to redraw a: Spider Girl costume or venom, SF Camy, Catwoman, saints row 3 bdsm girl
Or if i can learn 3ds geometry an Alice in wonderland costume.

Keen to see where people are at with modding this game?
## Post #70
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-02T21:03:03+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

sure thing, sorry there hasn't been much progress. I've been lazy, watched Game of Thrones on the weekend... got nothing done lol

anyway this was the old script 
[http://pastebin.com/K2M1Bh74](http://pastebin.com/K2M1Bh74)

this will let to import a model into 3dsmax, and allow you to inject vertex changes.... I can't recall if UVs are supported.. might be but the pointer method is still flaky, so donno if its enabled or disabled.

as for textures... my original hack was me hexing files... so there is no tool yet. another guy has a working tool, but I'm not sure when he'll announce or release anything?
in the mean while I've been trying to script up my own method of exchanging texture data... however it still requires the SDK...

my script isn't ready yet, its still buggy.. and only XPR creation was attempted to extract data.. not inject.

so in the mean while you can use noesis to get the textures. you'll have to wait for a texture tool.


other then that, theres the script you'll need to import the mesh into max, and put it back.


as for file extraction, chhrox has a BMS that extracts files... surprisingly quickBMS also has a injection feature.. so thats how I repacked files
## Post #71
- Username: messiahlad
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 27, 2012 5:10 pm
- Post datetime: 2012-04-08T23:27:51+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Cheers for that MarioKart
I've finally had some time to have a play with the model script and the SDK. The script you provided was great thank you, it worked well for importing the models in MAX and I was able to smooth down the geometry. 
But I have hit a few walls, most I believe are to do with my own lack of experience. If I switch modes to inject changes back into the imgb+trb should the vertex changes be reflected if I were to view them again in Noeisis? 
I also was successful in re-introducing(seemed to at least) these files back into the .bin files they came from and by using Xlast I was able to create another DLC package with them that reflected no changes except that I had just duplicated the original DLC.
Im still playing around with bundler/unBundler as well. what method did you use to convert imgb to xpr2. I assume an XPR2 can be "unbundled" edited with different textures, maybe UVs and "bundled" then converted back.

EcheloCross talked about injecting his hexed DDS file back into an imgb file. Im wondering what method was used to do that.
## Post #72
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-09T01:51:57+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

the injector edits the vertices in the TRB, and edits the UV buffers in the IMGB.

if you opened the files using noesis you'll see the changes, however getting it back into the game is a bit more difficult ^_^

quickBMS has support to re-inject data back into the BIN file, but the BMS scripts that have been posted are not compatible. thus if you use the inject feature in quickBMS it'll simply give you a copy of your original input file 

I head to hex stuff back into the BIN file, eventually I just wrote up a new BMS script with the offsets of the bikini and the quickbms feature worked after.

I wish there were more people involved in coding programs for FF13-2 modding, I only know a bit of maxscript so I can't write my own compressor/injector


anyway here is my BMS with hard set offsets. will only work on the North American bikini DLC for Serah "white_p0000015img_u.x360.bin" 

```
clog "c159.x360.trb" 0x0018B800 0x0003D528 0x0009C800
clog "c159_def.x360.mpk" 0x001C9000 0x0000F447 0x00027680
clog "c159_rain.x360.mpk" 0x001D8800 0x000103E9 0x000281C0
clog "c159_snow.x360.mpk" 0x001E9000 0x00010434 0x00028790

```


this will dump the files, as well should be compatible with quickBMS's injection feature
## Post #73
- Username: messiahlad
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 27, 2012 5:10 pm
- Post datetime: 2012-04-09T13:25:44+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Thanks again
It seems my changes weren't showing up because I was just deleting parts of the model. Therefore when I was making selections for injection, they never got introduced as the original object remained in the trb. I've over come this and  have gotten the modified geometry into the DLC. Thanks for the BMS script as well, that worked for injecting back into the .bin file.

The next hurdle for me is being able to get the modded textures back into the imgb files. Right now Im a bit of a noob, but I hope to in time, be able to add to the community.
## Post #74
- Username: SuperShadic2017
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 8:50 am
- Post datetime: 2012-04-10T18:19:51+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I just exported the files (except for filelist ones). However, i can't find any textures. Where would they be?
## Post #75
- Username: Newbie31
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 12, 2012 7:00 am
- Post datetime: 2012-04-10T22:21:20+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Probably a silly question, but how do you get to export to .trb with 3dsmax so you can veiw the revised model in noesis?
## Post #76
- Username: SuperShadic2017
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 8:50 am
- Post datetime: 2012-04-10T22:39:53+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from Newbie31
>
> Probably a silly question, but how do you get to export to .trb with 3dsmax so you can veiw the revised model in noesis?
You can't unless you have a plugin for it. You'd have to find one or make one. But why would you want to just look at it in Noesis?
## Post #77
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-10T23:58:35+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I got the DLC from the new costumes and the one from Noel is a little different. 
It has 4 files 
white_p0000020img_c.x360.bin
white_p0000020img_e.x360.bin
white_p0000020img_j.x360.bin
white_p0000020img_u.x360.bin
When extracted with chrrox script those files generate the exactly same .trb and .imgb.
Loading the model with Noesis it doesn't show or export the textures (the trb and imgb have the same name) It extract garbage textures.
it looks like this DLC is different from the others cause they work fine and don't have those _c, _e... files.
Anyway if someone wants to look into it here's the sample:
## Post #78
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-11T00:57:07+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

yeah there funny they have like multiple IMGB's or something right....
## Post #79
- Username: messiahlad
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 27, 2012 5:10 pm
- Post datetime: 2012-04-11T02:43:30+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from rexil
>
> I got the DLC from the new costumes and the one from Noel is a little different. 
It has 4 files 
white_p0000020img_c.x360.bin
white_p0000020img_e.x360.bin
white_p0000020img_j.x360.bin
white_p0000020img_u.x360.bin
When extracted with chrrox script those files generate the exactly same .trb and .imgb.
Loading the model with Noesis it doesn't show or export the textures (the trb and imgb have the same name) It extract garbage textures.
it looks like this DLC is different from the others cause they work fine and don't have those _c, _e... files.
Anyway if someone wants to look into it here's the sample:
http://www6.zippyshare.com/v/84458643/file.html

mmm I assume E= pal, J= Japan, U= North America.... C= ? not sure. my PAL serah DLC contained white_p0000020img_e.x360.bin where as the NA copy extracted white_p0000020img_u.x360.bin.
Again Im only guessing but maybe its just multi regional.
## Post #80
- Username: rexil
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-04-11T03:17:14+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

the textures are not in this dlc the 2nd model loads the textures correct they just are not in the file. the uv maps are fine on the 2nd model. the textures might be located in a completely different area or use existing ones from another file.
## Post #81
- Username: SuperShadic2017
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Apr 01, 2012 8:50 am
- Post datetime: 2012-04-11T03:28:23+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from chrrox
>
> the textures are not in this dlc the 2nd model loads the textures correct they just are not in the file. the uv maps are fine on the 2nd model. the textures might be located in a completely different area or use existing ones from another file.
What about for the actual game? I can't seem to find any textures for anything.
## Post #82
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-04-11T05:14:26+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from chrrox
>
> the textures are not in this dlc the 2nd model loads the textures correct they just are not in the file. the uv maps are fine on the 2nd model. the textures might be located in a completely different area or use existing ones from another file.

I think that's the case, they must have placed the texture in the disc or another DLC...
Thanks for looking.
## Post #83
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2012-04-18T18:04:04+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hey guys

Great work on everything so far, I'm having a little trouble working out how to extract the data from the 'Zone folder' Doesn't appear to work the same way as in FF13.

Has anyone managed this at all?

EDIT: nevermind, seems to work now, Though is there a way to turn of animating of textures in Noesis?
Some files in FFXIII-2 when opened seem to switch between texture after texture constantly, I can pause it but there no way of turning of the setting altogether and scrolling through manually (that I can think of).

Any Ideas?
## Post #84
- Username: messiahlad
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Mar 27, 2012 5:10 pm
- Post datetime: 2012-04-28T13:51:35+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hows your progress going Mario. I haven't seen any new tools released by any one as yet. reminds me of when street fighter 4 hit a wall for a while. 
I've had limited success with modding the game. but no real texture modding as yet. Has any one else got a complete method of introducing texture/vertex mods to the game?
## Post #85
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-28T15:03:50+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

only thing I can do is add XPR support to my script that would allow texture modding... as for rebuilding, it would take alot more time and work.
## Post #86
- Username: MiKE41
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 02, 2012 8:58 am
- Post datetime: 2012-04-29T00:06:48+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I have been trying to do a similar thing with the texture modding. I don't know what a XPR is, but I did manage to unpack a imgb, modify 2 textures and rebuild it. It does not work as intended in game though 

Normal IMGB (rendered by Noesis): [http://mich431.com/serah/serah-normal.png](http://mich431.com/serah/serah-normal.png)
Modded IMGB (rendered by Noesis): [http://mich431.com/serah/serah-mod.png](http://mich431.com/serah/serah-mod.png)
Modded IMGB (in game, far camera): [http://mich431.com/serah/mod-2.png](http://mich431.com/serah/mod-2.png)
Modded IMGB (in game, semi-close camera): [http://mich431.com/serah/mod-1.png](http://mich431.com/serah/mod-1.png)
Modded IMGB (in game, super close camera): [http://mich431.com/serah/mod-3.png](http://mich431.com/serah/mod-3.png)

If I move the camera close to Serah- then I can see the modified texture. However with the camera at normal following distance Serah returns to normal.

Tools used: Hex Workshop, a modified version of the GTA 4 Texture Editor (I used the ConvertToLinearTexture and ConvertFromLinearTexture functions), QuickBMS for extraction/injection (I made crappy python scripts for this too, but QuickBMS works so much better), Photoshop with the Nvidia Texture Tools addon.
## Post #87
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-29T01:09:32+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

yeah thats the problem me and EcheloCross have... its how to handle the MIP maps...

MIPs is some greek word, but it basically stores smaller res images of a base image, used to lighten the processor load when rendering objects from a far..

of course what your seeing is your image and the original image's old MIP maps mixing.... anything close is the base image, anything far away is the MIPs ... which from what I see, suggests you did not re-write the MIPs only the base image  

I made a concept mod when this all started
[](http://www.youtube.com/watch?v=GIQePZcDXUQ)

for the textures I used the xbox360 SDK, used there resource packaging tool to convert my image data into the xbox360 formatted data.. they use a tiling method on the textures to speedup texture reading across there GPU... 

the problem is that all of us around this forum "do not yet have a solid legit tiling and untiling method" least none posted publically.. and this is pretty much the bane of 360 modding.

anyway I went the "cheating" route and used tools from the SDK, thats how I got my mod to work, by replacing the textures properly using the sdk tools. which properly generates the base image and its mips I needed for my FF13-2 mod
## Post #88
- Username: MiKE41
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 02, 2012 8:58 am
- Post datetime: 2012-04-29T02:22:56+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Very nice, I figured it was something like this- I just didn't know what it was called. I tried looking for another texture in the imgb that the game would use from far away, but I didn't see anything.

I used the untile code from the GTA IV Texture Mod tool that I found on the main Xentax blog, it seemed to work fine- I just don't know anything about the mip maps.

I also found this untile code using google, but I didn't manage to get it working. [http://www.binrand.com/post/783672-widt ... izzle.html](http://www.binrand.com/post/783672-width-bits-xbox-swizzle.html)

What is the tool you're using called?
## Post #89
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-29T02:46:05+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

bundler

code posted is for decompression?
DXT?
## Post #90
- Username: MiKE41
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 02, 2012 8:58 am
- Post datetime: 2012-04-29T02:51:40+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from mariokart64n
>
> bundler

code posted is for decompression?
DXT?

I would guess its to un-tile an image and output it DXT, but I can't be sure (its not my code)

Edit: You were right before. I pulled my texture out of the imgb again and loaded it (before untiling) with "Load Mipmaps" turned on, and this is what I got: [http://mich431.com/serah/mod-mipmaps.png](http://mich431.com/serah/mod-mipmaps.png)
The only issue is now if I run it through my previous untiling method I get a mess of junk like this: [http://mich431.com/serah/mod-untiled-mipmaps.png](http://mich431.com/serah/mod-untiled-mipmaps.png) Edit2: Nevermind this. That's what happens when you tile an already tiled texture. I used the wrong function.

Time to see if I can untile it with mipmap data intact.

Edit3: This is where I end for the night  [http://mich431.com/serah/maps.png](http://mich431.com/serah/maps.png)
## Post #91
- Username: Newbie31
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Mar 12, 2012 7:00 am
- Post datetime: 2012-04-29T08:58:16+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Heyo, I'm still new at this. From your pictures it looks like you have altered the vertices on the mesh?
when I use the maxscript to import and inject if I delete any mesh/vertex or edge I get and error that stops it form injecting again, I assumed that it was because the maxscript doesn't actually export but opens the original file and modifies the vertex X,Y,Z positions so if a mesh is deleted than the vertice data isn't altered and the mesh looks the same(I use Noesis to view the change inbetween the models).

Is it possible to delete parts of the mesh/vertices or did you just move them or am I making a mistake somewhere? I'm not good with programming scripts and whatnot, I'm better at the meshing side of things.
## Post #92
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-04-29T12:59:29+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

you are correct, only move vertices and UVs.. don't make an changes like deleting a face, or even breaking or detaching a face.. that'll cause the vertex count to increase.

just grab a vertex, or UV coordinate and move.... "thats it" 

for my concept mod, I reshaped her body, then baked the textures from the original zero samus model into serah

the original normal maps were designed for accessories and clothes that were no longer there on my modification. so I converted the entire model back to quads, and imported it into mud box. Created a new high poly model, and was able to generate new normal maps by projecting the highpoly into serah's model..

even with all that work you'll notice my concept mod suffers from two unfortunate errors.
1. MisMatched Materials
2. Unwelded Vertex Normals

Not that these cannot be edited, but its was changed when the mod was finalized... most n00bs won't pickup the differences anyway
## Post #93
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-04-29T22:41:06+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Anyone extract fully this?
## Post #94
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-04-30T10:48:13+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

At that time i searched for it trough the ffxIII disk content, and I found only the two t-posed shivas, so probably u need to pose them by yourself. Anyway it seems that somebody in xnalara forum, ( if i remember well ) already posed them to create the motorbike.
[http://www.tombraiderforums.com/showthr ... &page=4421](http://www.tombraiderforums.com/showthread.php?t=147100&page=4421)
Mybe you can ask to him.
## Post #95
- Username: MiKE41
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 02, 2012 8:58 am
- Post datetime: 2012-05-05T01:51:14+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I've improved my texture editing method, and coded up a tool to extract and reimport textures from imgb. Please note that I've never actually coded anything in C++ before, so I'm fairly sure my code is trash, but it is working trash.

Untiling/Retiling code from GTA IV Texture Editor: [blog/?p=302](http://forum.xentax.com/blog/?p=302)

Limitations:
Only supports import and export of DXT1 textures from imgb.
Modifying the texture dimensions between export an import will corrupt your imgb.
Doesn't check to see if its going to overwrite something- it just does it.
Probably more I didn't think of.

Usage: imgbtool.exe [-e|-i] [file.trb] [file.imgb]
-e stands for export
-i stands for import

When exporting:
Writes files in .dds format to your current working directory. The file name is based on the hex location of the identifier in the .trb file.

When importing:
Reads files in .dds format from your current working directory, expects the files to be named based on the hex location of the identifier in the .trb file. Writes the new .imgb file in your current working directory as 'output.imgb'.

If you find an issue: Tell me about it (with details, such as the model and what you were trying to do). I make no guarantees I will fix it though.
[IMGBTool.zip](https://xentaxbackup.github.io/file/5396_IMGBTool.zip)
## Post #96
- Username: EstelaGremista
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 11, 2012 4:55 am
- Post datetime: 2012-06-10T21:06:33+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hi. I'm trying to extract Lightning's 3D model from this game but I can't find her in any .TRB file I extract from some .BIN files. There are still some .BIN files that QuickBMS couldn't open.
These are the files where I couldn't extract from:

XBOX 360:
white_z0220u_img.x360.bin
white_z0230u_img.x360.bin
white_z0240u_img.x360.bin

PS3:
white_z0160e_img.ps3.bin
white_z0220e_img.ps3.bin
white_z0230e_img.ps3.bin
white_z0240e_img.ps3.bin

Can anyone help me?
## Post #97
- Username: mlan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 26, 2011 10:50 pm
- Post datetime: 2012-06-10T23:04:24+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Any way to extract things beside the models? like sound effect, music, video etc? quickbms scrip for ff13 does everything, how can I make this one do that? thx
## Post #98
- Username: blablukura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Jun 25, 2012 9:32 pm
- Post datetime: 2012-07-01T07:35:44+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from chrrox
>
> those are the only models on the disk. its the shaders they use.
you need to set up the textures correctly.


if you want i looked and dint see anything but this script will extract everything from the game but it wont match anything to its textures and it will name some files trb that contain no mesh data.
I looked and dint see anything the first script missed but ill throw this out there for those that think something might be missing.

it's not easy to set up the textures correctly, for the face skin and hair, what texture to add to make them look glossy like that and in the game ? I dunno which texture is specular level or which is spec color or glossiness... I can only identify them for the armor, anyone help ?
## Post #99
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2012-07-02T20:39:57+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from blablukura
>
> chrrox wrote:those are the only models on the disk. its the shaders they use.
you need to set up the textures correctly.
[img]http://th06.deviantart.net/fs71/PRE/i/2 ... 4jerzy.png[/ig]

if you want i looked and dint see anything but this script will extract everything from the game but it wont match anything to its textures and it will name some files trb that contain no mesh data.
I looked and dint see anything the first script missed but ill throw this out there for those that think something might be missing.


it's not easy to set up the textures correctly, for the face skin and hair, what texture to add to make them look glossy like that and in the game ? I dunno which texture is specular level or which is spec color or glossiness... I can only identify them for the armor, anyone help ?

The skin, hair, etc spec maps are on either on a channel of the normal map or on one of the mask maps^^
## Post #100
- Username: Animus777
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 11, 2010 12:24 am
- Post datetime: 2012-07-23T11:41:38+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Hi Guys. I want to extract videos from PS3 version. I've found file moviee.ps3.bin and opened it in hex editor:



How can i extract pam videos from that bin?
## Post #101
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2012-07-26T01:29:01+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I was curious if anyone has been able to extract the DLC monsters (Omega, Ultros, Gilgamesh)?

All i've seen across forums so far is alternative outfits from the DLC but not these monsters.  Just curious.

Thanks for your time. Lubdar


31JUL2012: Nevermind Mariokart helped me out with it...thanks!
## Post #102
- Username: COKEORPEPSI50
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Thu May 24, 2012 11:31 am
- Post datetime: 2012-08-19T06:04:32+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from mlan
>
> Any way to extract things beside the models? like sound effect, music, video etc? quickbms scrip for ff13 does everything, how can I make this one do that? thx
## Post #103
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-04-24T15:36:20+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Sorry for the necro people, but I'm having an issue...

Ive extracted .trb's and .imgb's from the ps3 version of 13-2, but whenever i view the models in Noesis (i have the latest version) they do not show up with their textures, also ive tried the IMGBTool posted here and it does not work, Ive tried dragging imgb's onto it and running it in the folder where the imgb's are... nothing happens.

can anyone help me out, I'm really intrigued to see how square did they're models and textures please get back to me with an answer ASAP.

PS, Ive also tried renaming textures to what the trb's reference... with no change to the results....

Thx in advance

~flarespire
## Post #104
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-05-05T02:25:20+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I made some changes to the bms script so that it would work better, but I'm not sure what I did with it.   
I'll try and find it and if I can't I'll try and redo it.
## Post #105
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-05-06T22:55:32+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Thanks for the response, I've managed to pair a few models, but most, like the Time Gate model for one, don't seem to pair and render even though they are paired (I switched to the Xbox 360 versions as my ps3 ones became corrupt) anything that you have that can ease this is going to be of great use to everyone on this thread.
## Post #106
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2013-05-10T00:25:27+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Well I found that BMS script I was looking for, but it doesn't do anything helpful.
It just extracts some other file types.
## Post #107
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-05-10T08:10:54+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Manual pairing it is then :L... maybe id have better luck with the ps3 imgb's....

You know we would probably have better luck if someone here could decrypt the FFXIII-2 filelists...
## Post #108
- Username: rhadamants
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Oct 10, 2014 3:13 am
- Post datetime: 2014-12-14T11:00:54+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Is there any way how to extract the files from the PC version of FFXIII-2.
## Post #109
- Username: cloudslsw
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 04, 2010 5:37 pm
- Post datetime: 2014-12-28T09:46:17+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

the pc version,anyone could help to extract sound?
## Post #110
- Username: SkacikPL
- Rank: advanced
- Number of posts: 53
- Joined date: Tue Oct 28, 2014 2:51 pm
- Post datetime: 2014-12-28T23:20:44+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from rhadamants
>
> Is there any way how to extract the files from the PC version of FFXIII-2.
Yes, absolutely, you need this script to decrypt filelist(filelistu for US and filelistc for JP).
[viewtopic.php?p=90451#p90451](http://forum.xentax.com/viewtopic.php?p=90451#p90451)

And then you use this tool to extract scr/img archives:
[https://steamcommunity.com/linkfilter/? ... 13tool.rar](https://steamcommunity.com/linkfilter/?url=http://www.tzarsectus.com/tools/ff13tool.rar)

Bear in mind you need to edit .bat files to properly (de)compile FFXIII-2 archives. You need to change FF13 to FF132 inside the bat.


Though beyond that it's useless, none of the people who originally took the effort to reverse file formats seem interested in reversing the PC variants. Even though everyone claims the differences are marginal.

'Tis a shame.
## Post #111
- Username: mrjack900
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 31, 2016 7:34 am
- Post datetime: 2016-07-31T21:19:34+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Sorry to necro an old thread but I've been following all the instructions in trying to get character meshes out of FFXIII-2 and I managed to decrypt the file lists and extract the raw .trb files but I can't view them in Noesis or anything else I've found.

I think I may need to run a script in Noesis or something? Or some people are using Max Script to import the files? I'm not really sure what the next step is and i would appreciate any advice 

I thought I saw a tutorial about decrypting any mesh through hex editing but I can't seem to find it now. It would be a slow and painful process for me but I would probably give it a go.
## Post #112
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-10T18:01:27+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from mrjack900
>
> I managed to decrypt the file lists and extract the raw .trb files but I can't view them in Noesis or anything else I've found.which version of Noesis did you use? .trb is a "known file format" in Noesis since many months.

Which error message arouse?
which trb did you try? PC or console version?

There's so many one time posters who feel ignored - for good reasons.

Possible helpers - me at least - expect more from you than this "it doesn't work...  ".
## Post #113
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2016-08-10T21:10:24+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Could anyone help me too, please? :C
I've created a topic here: [viewtopic.php?f=16&t=14832](http://forum.xentax.com/viewtopic.php?f=16&t=14832)
Tried exporting some other blocks, there are a few which have UVs(like the Mystic chamber in Serendipity or the buildings with vertex colors in Academia), but the ones without any textures or VC give me thi warning(the majority is like this sadly)
## Post #114
- Username: mrjack900
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 31, 2016 7:34 am
- Post datetime: 2016-08-11T02:41:22+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from shakotay2
>
> mrjack900 wrote:I managed to decrypt the file lists and extract the raw .trb files but I can't view them in Noesis or anything else I've found.which version of Noesis did you use? .trb is a "known file format" in Noesis since many months.

Which error message arouse?
which trb did you try? PC or console version?

There's so many one time posters who feel ignored - for good reasons.

Possible helpers - me at least - expect more from you than this "it doesn't work...  ".

It's the PC version. Noesis 4.177.

I can see the trb files but the models don't appear in the viewport and I am unable to export them.



I've modded plenty of other games and the learning curve has been steep. This is obviously my first time modding this particular game and so I am a little lost. I'm not crying about it. I'm simply asking for help.

Help me or don't but you don't have to be so damned rude about it.
## Post #115
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-11T18:29:05+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from mrjack900
>
> Help me or don't but you don't have to be so damned rude about it.apologies!  
I was just a little bit tired of such posts. And  I didn't expect you to return ever.  

If you uploaded the trb in question I could have a look at.

(I suppose Noesis doesn't support PC version and there's no simple solution then because there's no script or source, afaics.)
## Post #116
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2016-08-16T21:49:45+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from shakotay2
>
> If you uploaded the trb in question I could have a look at.

(I suppose Noesis doesn't support PC version and there's no simple solution then because there's no script or source, afaics.)
Hey guys.

Well, if you or those who didn't have PC samples, still like to take a look at all three games, you can grab them here.

UPDATED
[https://mega.nz/#!a8VxFbJC!J7ryLoywE8pa ... bvOJwlv5Hw](https://mega.nz/#!a8VxFbJC!J7ryLoywE8pajGJgTE4B2mCHjBXSDjZCgbvOJwlv5Hw)

cheers
## Post #117
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-17T10:47:24+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

thanks for your efforts but I won't download about 100 MBs just to get some samples.
## Post #118
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2016-08-17T23:18:40+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from shakotay2
>
> thanks for your efforts but I won't download about 100 MBs just to get some samples.
Reduced in size an updated.

cheers
## Post #119
- Username: mrjack900
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jul 31, 2016 7:34 am
- Post datetime: 2016-08-18T11:57:10+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from shakotay2
>
> mrjack900 wrote:Help me or don't but you don't have to be so damned rude about it.apologies!  
I was just a little bit tired of such posts. And  I didn't expect you to return ever.  

If you uploaded the trb in question I could have a look at.

(I suppose Noesis doesn't support PC version and there's no simple solution then because there's no script or source, afaics.)

You're forgiven 

It's every trb but I guess that somewhere in all this information I must have missed that the PC version wasn't compatible. I could send you one trb but I'd have no clue who or what it was I'd be sending.

Edit: I see mono already uploaded a smaller file sample.
## Post #120
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-18T18:48:20+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

this is one submesh (of about 16) from c102_win32_trb:



c102_win32_trb.jpg (74.99 KiB) Viewed 161 times

(uvpos=8 is wrong here)

(FIs count at 0x71B2C, vertices count at 0x7463C)

This is a H2O file for another SM:

0xDFD98 1215
Vb1
24 99
0xE0788 539
120400
0x0 255

btw: Noesis' debug log says: "This is not a supported TRB platform, and you're probably some kind of terrible furry for owning it." (  )
## Post #121
- Username: aagems
- Rank: advanced
- Number of posts: 75
- Joined date: Thu May 31, 2012 1:07 am
- Post datetime: 2016-11-12T21:47:29+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

I think the easiest solution is get ps3/x360 version and using noesis to get the model file.I myself of course want a support for pc version but since there's lack of interest,i guess its time to move on
## Post #122
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2017-07-22T16:30:53+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

Is there any way to read the UV's on some zone trb files which don't have vertex colors? I'm trying to convert Academia buildings but almost all .trb's don't have UV's in the corresponding .imgb's and i don't know where to find them
## Post #123
- Username: korea0799
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2016 3:44 pm
- Post datetime: 2017-08-15T07:17:22+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

UVs Should be existing

[http://imgur.com/a/QP5JT](http://imgur.com/a/QP5JT)

for texture:
In other package path such like m010\bin\block010.ps3.trb
## Post #124
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2017-10-08T12:58:42+00:00
- Post Title: Re: Final Fantasy XIII-2 extraction

> Reply from korea0799
>
> UVs Should be existing

http://imgur.com/a/QP5JT

for texture:
In other package path such like m010\bin\block010.ps3.trb

the area on your screenshot is oerba from xiii and i can get uv's for it, however almost none xiii-2 maps have uvs for me :/
