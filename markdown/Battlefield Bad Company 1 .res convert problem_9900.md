## Post #1
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2012-11-22T02:12:50+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Hey guys, This is a long shot for me but here goes. 

First, I'm fairly new to this but I've been able to do some extracting. I was able to extract the 360 version Bad Company's 2 sound effects using tools posted on hcs64.com and a well explained post on a battlefield mod forum. So I'm familiar with the tools and the code on how to extract and convert. However for kicks and giggles I wanted to extract the sound effects from the first bad company. 

I did my research and found the method was not that different. Except I can't get any .res files to convert and I don't know what I'm doing wrong. At first I thought it was simply the wrong offset, so I went into HxD to search for the offset. In Bad Company 2 you could figure it out by finding the hex value 48 00 00 0C, but none of the .res files for bad company 1 have that hex value.

These are the codes I used:  

```
ren *.res_stream1 *.str
for %%i in (*.str) do "%CD%\xma_test.exe" %%i  -1 -r %%~ni.xm
del *.str
for %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addXMARIFFHeader.bms" %%i "%CD%"
del *.xm
@towav.exe *.xma
del *.xma
```


```

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x44\xac\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
```


I tired these offsets: 0x00, 0x04, 0x08, 0x10, 0x0C, 0x14, 0x18, 0x20. I tried those all with both mono and stereo headers, as well as the different sample rates and channels in the xmaRIFF header. 

No dice, (pun not intended) the process doesn't produce a .wav file. If I use quickbms and load up the xmaRIFF header I get a .xma from the .res but towav just spits out a garbled mess no matter what I do.  

What am I doing wrong, does the .res files for BC1 have the hex 48 00 00 0C, or is there another value that I need to look for, or is the code or the method wrong? Or is it just my copy of BC1 doesn't support the method posted. 

If a sample is needed I can upload one if anyone is grateful enough to help me out. Thanks.
## Post #2
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2012-11-23T22:31:01+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

I figured it out. For single stream files, the offset is 0x2C. For multi stream files the offset you'll look for in HxD is BB 80 00 00 skip two lines and the following 00 is the offset you're looking for.
## Post #3
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-03-26T20:08:30+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Hi mates,

I re-open this topic because, for me, I get several errors like " block too small at 0x10038 ", " unknown flags at 0x2c " and " Parse error: skip bits ( * : misc number like 411, 306,etc... ) did not match previous packet overflow (0) " with all Battlefield Bad Company 1 sounds.
It's very strange because I managed to extract sounds from Battlefield 1943 and Battlefield Bad Company 2 two months ago and I never get those errors in the CMD.

I use the code from this website for the .bat files : [Link](http://www.bfeditor.org/forums/index.php?s=3bfc4dfa0e7fdc23c58c718f1af7a6d8&showtopic=14539&st=30)

```

for /r %%i in (*.res) do "%CD%\ea_multi_xma.exe" "%%i" -o 0x2c
for /r %%i in (*.res_stream1) do ren "%%i" *.str
for /r %%i in (*.str) do "%CD%\xma_test.exe" "%%i" -2 -r "%%i.xm"
del /s *.str
for /r %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addheader_mono.bms" "%%i" "%%~dpi\"
del /s *.xm
for /r %%i in (*.xma) do (
"%CD%\towav.exe" "%%i" 
move *.wav "%%~dpi/"
)
del /s *.xma
pause
```


```

for /r %%i in (*.res) do "%CD%\ea_multi_xma.exe" "%%i" -o 0x00
for /r %%i in (*.res_stream1) do ren "%%i" *.str
for /r %%i in (*.str) do "%CD%\xma_test.exe" "%%i" -2 -r "%%i.xm"
del /s *.str
for /r %%i in (*.xm) DO "%CD%\quickbms.exe" -o "%CD%\addheader_stereo.bms" "%%i" "%%~dpi\"
del /s *.xm
for /r %%i in (*.xma) do (
"%CD%\towav.exe" "%%i" 
move *.wav "%%~dpi/"
)
del /s *.xma
pause
```


and this same one for mono and stereo sounds:

```
//or
//addheader_stereo.bms

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x00\x64\x61\x74\x61\xff\xff\xff\x70"

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE
```


I post an image from the RES file in the HxD editor if that can help you:



PS: There another thing that I could read in the console:

```
Offset: 0
block size: 8000
 data size: 10008 "
```


I don't know if it's normal or not.

Many thanks in advance.

Vosvoy
## Post #4
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-03-27T21:04:46+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Hello, First of all it seems strange it is giving you that problem. 

Let me just state the obvious just to be sure we are clear. First you must have a NTSC copy of Bad Company 1 for Xbox 360 only, it will not work with any other version.

Second you may not be looking for the right offset. If by default you are getting those types of errors it means there are no audio files, or the wrong offset was entered. remember to search for BB 80 00 for single wav files or BB 80 00 00 skip two bytes and the following 00 will be your offset for multi-stream files. 

here is an example:


Go by that general rule and you should be able to figure it out eventually.
## Post #5
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-03-28T16:16:48+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

> Reply from durandal217
>
> Second you may not be looking for the right offset. If by default you are getting those types of errors it means there are no audio files, or the wrong offset was entered. remember to search for BB 80 00 for single wav files or BB 80 00 00 skip two bytes and the following 00 will be your offset for multi-stream files.

Yup, with your explanations on your text above, I managed to extract Battlefield 1943 sounds because the default hex is BB 80 00 too in this game, so many thanks to you by the way. But I have to admit that I broke a rule... " Never use a PAL version "... Because PAL and NTSC don't have the same sound carrier ( 5.5 Mhz for PAL and 4.5 Mhz for NTSC ). I think this is due to this difference that I couldn't get the sounds. Thank's for me, I've got a NTSC version too.

I try it again with NTSC version but the sounds were emptyb after conversion. Later, I copy/paste your code above and use it: Tada, it worked.

Sorry for my useless hurry.

EDIT: Allright, I don't got any problem with all mono sounds but all extracted stereo sounds are messed. Moreover, an errors keeps poping in the console for both case ( block too small at ... ). I really don't understand what's going on with those sounds.

EDIT2: Okay. So, I don't have any average hex\coding understanding but I managed to extract stereo sound. I simply changed the:

```
set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x44\xac\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"
```


to

```
set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x80\xbb\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x02\x00\x64\x61\x74\x61\xff\xff\xff\x70"
```


and it seems good now for the stereo but not for the mono sounds anymore.

For a noob like me, I don't think this is an important difference but whatever it's working. Got an explanation for a novice?

Thank's in advance.

Vosvoy
## Post #6
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-03-28T20:31:54+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Hmm... The only thing I can think of is this:

# add a XMA stereo RIFF header to any headerless file

set MEMORY_FILE binary "\x52\x49\x46\x46\xb8\x59\xa7\x00\x57\x41\x56\x45\x66\x6d\x74\x20\x20\x00\x00\x00\x65\x01\x10\x00\xd6\x10\x00\x00\x01\x00\x00\x03\xe3\x9a\x00\x00\x44\xac\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x01\x02\x00\x64\x61\x74\x61\x00\x58\xa7\x00"

get NAME basename
get SIZE asize
string NAME += ".xma"

append
log MEMORY_FILE 0 SIZE
append
math SIZE += 60
log NAME 0 SIZE MEMORY_FILE

Do you see what I've highlighted? That is the header for stereo sound files, if you change x01\x02 to x01\x01 you have a mono header I would suggest using the code above (without the highlighted part of course) as your main header code and change that one line of code depending on the the type of file. 

Or create separate files, with one having a stereo header and one mono header.
## Post #7
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-03-28T21:01:24+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

All right, thank's mate for the advice.

Another little question please: in certains .res files, the hex BB 80 00 don't exist. Does it mean that there is not sound in it?

( A little info: In other files ( where BB 80 hex is not available ), I found the AC 44 hex that apparently worked ).

Many regards.

PS: I really wonder why BB 80 00 is the hex to search. Generaly, this is the frequency of the sound like 44000, 48000, etc...

Vosvoy
## Post #8
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-03-28T22:58:50+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Multi-stream files that don't have the BB 80 00 00 have another value which I forgot, but basically for most instances if you enter 0x2c and you get a .wav file, but it doesn't have a BB 80 00 tag look in HxD and look at what value is there at 0x2c and search for it again and you should find it.
## Post #9
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-03-29T18:27:23+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

I tried what you said but the 0x2C hex don't work with a bunch of sounds in Streaming_sounds00.fbrb ( for example ) that don't have the BB 80 hex nor AC 44 ( can't get any .WAV file at all because this is not the right offset apparently ).

Here a screenshot of one of those .RES file: " Explosion_XXL_Gas_Close_01_WaveDataSns_1 ".



and a little comparaison done with WinHex ( that didn't very helped me but maybe someone here):



I'm pretty sure that's not a multi-streamed sound because multi-streaming is essentialy used in weapons fire and vehicles audio ( Start, Loop, EndTail/Stop ) in Battlefield series.

Got an idea?
## Post #10
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-03-30T00:20:36+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Its been awhile since I extracted everything, but this is what I remember, in some instances some sounds aren't where they are suppose to be. For example certain explosion sounds are not in the, lets say one of the level00.fbrb but are actually located in the ondemand_sounds-00.fbrb archive.

Explosion_XXL_Gas_Close_01_WaveDataSns_1 is a stereo file, I can see the XMA1 flag which is FC 01 C0 01 located at 0x11, the offset either has to be before that, because all EA files have the XMA flag after hex's BB 80, AC 44, 48 00 ect. If not, then the real audio file is located somewhere else. 

I hope that helps I wish I could pin it down exactly, but I don't have the .res files anymore, and I'm also trying to extract the score for ODST at the moment so I cannot go digging around my backups for them.
## Post #11
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-03-30T01:27:24+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

All right, thank's. I'll go deeper in my research.

EDIT: You give me very a good clue here. The offset was 0x00 so before the stereo flag. Many thank's and good luck for your projects.

Hope I didn't waste your time.

Vosvoy
## Post #12
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-03-30T05:03:55+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Oh no no no not a problem at all, I'm glad I was able to help you. I had to figure this out all by myself when I did it, so it brings me nothing but pride to know I'm giving somebody a leg up.

One last thing in case you, or anybody else needs this XMA flag 2, which is a mono file, is identified by hex  FC 03 80 00.
## Post #13
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-03-30T12:59:42+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Yeah I know, this time I found that by myself  but thank's anyway.

But one last question run in my head. How did you find hex from those .RES by yourself? I mean just with HxD? Because there is truly a logic that I don't know about find offset.
## Post #14
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2013-03-30T15:52:02+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

I knew it had been done so there was a way. The topics about it don't give you that impression, but I put together what I knew about extracting sounds from BC2 and tried that but I couldn't get nothing to convert. I looked at the directions and almost gave up until I said "screw it I'm just gonna try every offset until I get tired or find it." When I did 0x2c and it extracted I opened up HxD and looked at that offset, it took me about a day to finally figure out what the hex was. And after that it was smooth sailing. 

I don't know a damn thing about coding, or really that much about hex editing, I but I just put two and two together to figure it out.
## Post #15
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-03-30T16:01:59+00:00
- Post Title: Battlefield Bad Company 1 .res convert problem

Ah, so " Patience " is the big word .

It's a pity that we can't detect the good offset via a code line in the .BAT converter ( like if -o 0x00 don't work, try next offset, again and again until find what we need ). Anyway, thank's a lot again for your good help.

Good luck in the future.

Vosvoy
