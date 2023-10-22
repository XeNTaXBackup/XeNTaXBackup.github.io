## Post #1
- Username: pythonnoob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 14, 2007 7:22 am
- Post datetime: 2007-01-13T23:35:37+00:00
- Post Title: The Last Express HPF files

Hello,

I am a complete noob at this, but here goes:

Is anyone able to take see if they can make any sense of the *.HPF files that contain the data for the 1997 game The Last Express?

As far as I kinow, no one has ever been able to extract data from the files, although that could be because the game flopped commercially.  The file that I am attaching is a "cut" version of the 30 MB file HD.HPF (the file that contains the data stored on the hard disk).  The rest of the game's data is stored on the game's 3 CD's and run from there.  On each cd there is one HPF file about 500-600 MB in size, named CD1.HPF, CD2.HPF, etc.

As well, the game's demo (42 MB) can be downloaded from here: [http://lastexpress.markmoran.net/download/expdemo.zip](http://lastexpress.markmoran.net/download/expdemo.zip)

You may not have much luck, as I believe that because of the radically different game approach (real-time as in 24), the game uses its own custom programming language.

I hope that someone will be able to figure out this format, as I would love to see what is inside after all these years.
[HD.HPF.zip](https://xentaxbackup.github.io/file/1027_HD.HPF.zip)
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-14T01:26:58+00:00
- Post Title: The Last Express HPF files

> Reply from pythonnoob
>
> I hope that someone will be able to figure out this format, as I would love to see what is inside after all these years.
Well, the archive structure seems to be quite straightforward. Try the attached program; it worked pretty well with the demo file.

You probably will not be able to do much with the extracted files, however. They have custom formats, so we will have to figure out those as well ...

```
HPFExt.exe archive.hpf
```

[HPFExt.zip](https://xentaxbackup.github.io/file/1028_HPFExt.zip)
## Post #3
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-14T16:50:44+00:00
- Post Title: The Last Express HPF files

Okay, here is a converter for BG background files as well ... now I need to refrain from disassembling for a while. 

```
BG2BMP.exe *.bg
```

[BG2BMP.zip](https://xentaxbackup.github.io/file/1029_BG2BMP.zip)
## Post #4
- Username: pythonnoob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 14, 2007 7:22 am
- Post datetime: 2007-01-14T22:55:55+00:00
- Post Title: The Last Express HPF files

Wow.  I am speechless.

I have been searching for a way to look at the files for years, and I post here and you're able to write programs that can extract and look at some of the data in a matter of hours.  Isn't the internet a wonderful thing?   

I am extremely gratified to you Deniz.  Thank you so much!

Now, if I could just figure out how to listen to the SND files...
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-15T00:14:59+00:00
- Post Title: The Last Express HPF files

> Reply from pythonnoob
>
> Isn't the internet a wonderful thing?
It can be, yes. 

> Reply from pythonnoob
>
> I am extremely gratified to you Deniz.  Thank you so much!

Now, if I could just figure out how to listen to the SND files...
You're welcome.

I have already started looking at the SND files; I assume that they are compressed with a customized ADPCM variant -- applying the standard 4-bit [IMA ADPCM](http://wiki.multimedia.cx/index.php?title=IMA_ADPCM) decompression scheme gives somewhat audible results. I cannot promise anything, though, since I do not have enough time to work consistently at this project.
## Post #6
- Username: pythonnoob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 14, 2007 7:22 am
- Post datetime: 2007-01-16T16:06:30+00:00
- Post Title: The Last Express HPF files

> Reply from Deniz Oezmen
>
> I cannot promise anything, though, since I do not have enough time to work consistently at this project.

No problem.  Whatever you can manage is much appreciated.  Thanks again.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-16T18:21:59+00:00
- Post Title: The Last Express HPF files

W00t, Deniz strikes again! D
## Post #8
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-20T01:54:54+00:00
- Post Title: The Last Express HPF files

This might be a fine time for a third strike. 

The files were indeed compressed by an IMA ADPCM variant as I suspected; I just was too blind to see the correct parameters at first. The attached program should convert SND files to standard wave files -- at least it worked correctly for the demo. (Though two seemingly corrupt files were packed into the demo archive for some reason.)

```
SND2WAV *.snd
```


Note that there might be minor differences between the output of this program and the sound output the game generates. As the game executable uses a strangely customized decompression variant -- which I do not feel inclined to disassemble to its full extent -- I simply used the standard scheme instead. However, the differences should usually be so small as to go unnoticed by the human ear. (We're talking about something like two levels of deviance on a 65536 level scale here ...)

Anyway, let me know if this works or if there are still any problems.


Have fun,

Deniz
[SND2WAV.zip](https://xentaxbackup.github.io/file/1038_SND2WAV.zip)
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-20T16:40:35+00:00
- Post Title: The Last Express HPF files

... and let's just throw in something unspectacular for a change. This here extracts the text from SBE "subtitle" files for easier reading. I assume the values I have called "start" and "stop" to specify the point in time and duration the text is displayed on screen while playing a sound file, but this might be a wrong guess.

```
SBE2TXT *.sbe
```

[SBE2TXT.zip](https://xentaxbackup.github.io/file/1041_SBE2TXT.zip)
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-01-20T16:57:51+00:00
- Post Title: The Last Express HPF files


## Post #11
- Username: pythonnoob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 14, 2007 7:22 am
- Post datetime: 2007-01-20T21:31:18+00:00
- Post Title: The Last Express HPF files

You are da man, Deniz!  I never would have imagined that I'd be able to look into all of this stuff.  Thank you so much again!

> Reply from Deniz Oezmen
>
> I assume the values I have called "start" and "stop" to specify the point in time and duration the text is displayed on screen while playing a sound file

Listening to some of the soundfiles (hurray!), it seems that a conversation between multiple characters is stored in one audio stream, so "start" and "stop" would probably tell the subtitles at what point in the audio stream to appear and disappear.

If you have some spare time, Deniz, could you do one more small check for me please?  

I was wondering if you could look at the NIS and SEQ files to see if there's any recognizable data in them?  I believe NIS stands for non-interactive-scene, which would mean that they store the data for cutscenes.  The NIS files are quite large (compared to some of the other types), so I assume that there must be some multimedia data in there...and I guess that SEQ stands for "sequence" or something...

Anyway, you have made my day (yes!) and keep up the good work helping people!
## Post #12
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-21T19:30:21+00:00
- Post Title: The Last Express HPF files

> Reply from pythonnoob
>
> so "start" and "stop" would probably tell the subtitles at what point in the audio stream to appear and disappear.
That's what I suspected. The only remaining question would be what unit of time these values are expressed in. But on the other hand, that is probably not important anyway ...

> Reply from pythonnoob
>
> I was wondering if you could look at the NIS and SEQ files to see if there's any recognizable data in them?
Way ahead of you. 

You are most probably right about the cutscenes. By the way: Could you check whether the music or sounds of cutscenes you know can be found in SND files? If not, it might be contained within the NIS data as well.

I suspect the SEQ files to contain the character animation frames, which are probably once again compressed. This time, however, I do not exactly know what to look for -- I have some structural ideas and have located some related parts of code within the demo .exe, but I cannot see the purpose of most of the data yet.


Maybe somebody else could support me here? I have somehow seen enough disassemblies for the upcoming three months ...

What I know so far:

- SEQ files start with an int32 "counter" value (probably for the number of frames). Afterwards, there are (at least) as many 68 byte structures as the "counter" value indicates. Within these structures, at least one int32 value (from the fifth byte on) is a file offset value for the respective frame. Afterwards, there are some int32 or int16 values that look suspiciously like width and height ...
- The frame data of SEQ files is probably uint16-formatted. A "conversion routine" in the .exe, located at 0x00410420, indicates this.
- The routine which probably handles SEQ files is located at 0x00410F40.
- NIS files also start with this int32 "counter", which is followed by as many  8 byte structures, the purpose of which are unknown to me.

Well ... that's about it. Not enough for me to see anything useful yet. Anybody?

> Reply from pythonnoob
>
> Anyway, you have made my day (yes!) and keep up the good work helping people!
You're welcome. You got me hooked up on these formats ...
## Post #13
- Username: pythonnoob
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 14, 2007 7:22 am
- Post datetime: 2007-01-22T00:33:01+00:00
- Post Title: The Last Express HPF files

> Reply from Deniz Oezmen
>
> By the way: Could you check whether the music or sounds of cutscenes you know can be found in SND files? If not, it might be contained within the NIS data as well.

I looked, and none of the cutscene sounds are in any SND files where they should be.  FYI, the first three letters of a SND filename is the name of the character that the file involves, e.g. ANN is Anna, ALX is Alexei, and so forth.  Because there were both DOS and Windows versions of the game, I assume that they had to stick to 8.3 filenames.

> Reply from Deniz Oezmen
>
> I suspect the SEQ files to contain the character animation frames, which are probably once again compressed.

I suspect that you are right.  I'm not sure if you ran the demo I sent you, but the game uses a "rotoscope" effect on characters, which use a very limited colour palette (I think there are no more than 16 colours on any character).  As well, the game uses very little FMV, instead using a sort of "slideshow" method for cutscenes.  As such, most cutscenes might not use more than 10 frames for the whole thing.  While there is FMV, it is very rare, and runs at about 15 frames per second, with no synchronized audio...as well, I suspect that the animations have alpha channels/transparency, as the same animations can occur in a variety of locations.

Is it possible that the NIS files are archives that contain more SEQ, SND and BG files?

That's just me rambling.  Thanks, and keep up the good work!
## Post #14
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-01-23T13:02:07+00:00
- Post Title: The Last Express HPF files

> Reply from pythonnoob
>
> I looked, and none of the cutscene sounds are in any SND files where they should be.
I see. Then we might find sound data within NIS files as well. Except maybe if they contain the audio-less FMV sequences you mentioned.

> Reply from pythonnoob
>
> I suspect that you are right.  I'm not sure if you ran the demo I sent you, but the game uses a "rotoscope" effect on characters, which use a very limited colour palette (I think there are no more than 16 colours on any character).
Yes, I ran the demo and saw what you mean. The largely uniform colouring makes compression easy -- though I am not entirely sure how the colours are represented within the sequence files. I do not even know if the data is always stored as "full frames" or if the format makes use of delta frames as well ...

> Reply from pythonnoob
>
> as well, I suspect that the animations have alpha channels/transparency, as the same animations can occur in a variety of locations.
They will probably just have one special colour defined as transparent. Or are there any "real" transparency effects, such as half-lucent objects, in the game?

> Reply from pythonnoob
>
> Is it possible that the NIS files are archives that contain more SEQ, SND and BG files?
I would not describe them as archives, but rather as a form of proprietary video format; at least that is what I suspect them to be.

Alas, there is much guesswork involved ...
## Post #15
- Username: ltronic
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 20, 2009 6:19 pm
- Post datetime: 2009-02-20T10:37:50+00:00
- Post Title: The Last Express HPF files

Hello Guys !

Bumping this thread, since I'm trying to rewrite the whole game engine in modern, cross-platform C/SDL.
Thanks to the great tools posted here, I've been able to extract and convert most of the data :
- SND2WAV ==> Ogg files
- BG2BMP ==> Png24 optimized files

I'm now digging into the following file formats mentioned in that thread : NIS, SEQ.
I've also found some LNK files while decompressing the HPF archives.

Has anyone progressed on the NIS/SEQ files ? Any clue about the LNK files ?
I've start to disassemble the whole game (ExpressW.exe) under IDA Pro. 
Also tried to produce pseudo-C file with Hex-Rays, but does not seem to give useful results so far.

Anyone wanting to help ?

Cheers,
## Post #16
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-02-20T15:01:02+00:00
- Post Title: Re: The Last Express HPF files

Rewrite the whole game engine is a good news.
Can you add a unicode subtitle display option in your new engine?
I remember this game did not display  the subtitle .
## Post #17
- Username: ltronic
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 20, 2009 6:19 pm
- Post datetime: 2009-02-21T16:29:32+00:00
- Post Title: Re: The Last Express HPF files

Thanks to tools posted here, yes, handling subtitles is definitely possible.
However I need (help) to reverse engineer NIS, SEQ and LNK files.
Once done, the game engine should not be *that* complicated to write.

Anyone willing to help ?
## Post #18
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2009-02-22T08:27:42+00:00
- Post Title: Re: The Last Express HPF files

some information about .seq files

[http://www.geocities.com/hcc.soft/doc2/SEQ_format.html](http://www.geocities.com/hcc.soft/doc2/SEQ_format.html)
## Post #19
- Username: ltronic
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 20, 2009 6:19 pm
- Post datetime: 2009-02-22T11:06:04+00:00
- Post Title: Re: The Last Express HPF files

Hmmmm,

Thanks for the link stevenx, however I don't think it is the same SEQ file format since the link you provided is about a music file format (MIDI related).
Most Sounds (except cutscenes ones) is The Last Express are stored into SND files.
From the various discussions, we can guess the cutscenes sounds are "somewhere" stored in NIS files.
## Post #20
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2009-03-01T22:46:56+00:00
- Post Title: Re: The Last Express HPF files

Ah yes, you reminded me that I abandoned work on the missing formats when I found quite a zoo of decompression algorithms within the disassembly.

I'm not sure how far you've gotten already, so I've taken a look at the code again. The code handling some (or maybe even all?) of the decompression for SEQ frames can be found at 0x0042614b in expressw.exe. If I follow it to the minute for a sample frame, this is what I get:



A bit strange, isn't it? I wonder whether I have found a sample that describes an image switch ...
Anyway, filling up the colors by doubling them gives the following more reasonable, though a bit "guessed" picture:



Let's see if we can find out a bit more ... I'd be glad to hear of your progress.

Best wishes,
Deniz
## Post #21
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2009-03-02T22:01:42+00:00
- Post Title: Re: The Last Express HPF files

Okay, I'm now pretty sure that this method works by the aforementioned pixel-doubling. The game developers probably stored the "switch frame" and the full frame combined into this single format to save space.

However, there are at least two or three other compression methods used on SEQ files. I'll have to analyze those first before there is a chance of extracting all frames.

Until then, here's another sample. This time the colors and transparency should be roughly correct:



Best wishes,
Deniz
## Post #22
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2009-03-14T00:10:45+00:00
- Post Title: Re: The Last Express HPF files

Even if I risk talking to myself here:

NIS and SEQ files can now be decompressed and converted. The file formats are quite messy and inefficient, so I didn't bother to track down each byte, but the bulk of the data can be extracted. Since there are different proprietary decompression methods involved, I won't have time to document the formats soon. If you have technical questions, don't hesitate to ask.
LNK files are actually audio streams that "link" to NI sequences: When the NIS has finished (and the player regains control), the audio continues with the stream stored in the matching LNK file.

Updated tools can (as always) be found either on [my site](http://oezmen.eu/gameresources/) or as a [direct download](http://xentax.com/uploads/author/denizoezmen/express.zip) from XeNTaX. Be careful when converting many files at once -- all sequence frames are extracted as full-color 640x480 TGAs, which might fill up your hard drive sooner than you think.

An interesting observation just as a side note: As all major file formats are now known and none of them contains anything like script data, the game logic is probably built completely into the executable. If anybody wants to re-implement the engine, they probably will have to disassemble and analyze the whole deal -- or try to find one of the original developers and ask for the source code, which might be your better bet.
[Edit: I'll have to revise that statement a bit: The files TRAIN.DAT and CD?TRAIN.DAT in HD.HPF might contain script data. But nevertheless, there is much data hardcoded into the .exe.]

Additionally, I have one request: Could somebody who owns the full game (preferrably the english version) extract CD2.HPF and tell me the file sizes of 1917.SEQ and 1917.LNK? (The reason: These files store the concert sequence, but they seem to be truncated in my german-language copy.)
[Edit #2: Thanks to Marcus, this question has been answered: The german version indeed has a corrupt copy of 1917.LNK, cutting the concert scene shorter by about 9 minutes, while the english version is intact.]

Best wishes,
Deniz
## Post #23
- Username: ltronic
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 20, 2009 6:19 pm
- Post datetime: 2010-07-14T13:03:14+00:00
- Post Title: Re: The Last Express HPF files

Great work !!

I'm back on track on this project, will try to keep you updated...
## Post #24
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2010-07-14T17:54:26+00:00
- Post Title: Re: The Last Express HPF files

Are you aware of [this endeavour](http://code.google.com/p/lastexpressengine/)? These guys already seem to be on a pretty good track. Your help might be needed ...
