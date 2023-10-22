## Post #1
- Username: gomibakomusic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 22, 2016 6:36 pm
- Post datetime: 2016-08-22T10:42:32+00:00
- Post Title: Complete Newb...No programming skills: .wem files

After playing Giga Wrecker on steam for the past day, I decided to try my hand at attempting to find the BGM's since I enjoyed the tracks so much. I viewed a couple guides explaining the general process of extracting music, tried them out, and after hours of work, I remained unsuccessful. I figured I'd post here to see if anyone could help. Please note that I have no programming abilities what so ever, just  guy who likes video game music and is/has been interested in ripping for awhile...and is terrible at it.

Here's what I've done so far:

============
1. Being a PC game on Steam, I first located the game soud files:

C:\Program Files (x86)\Steam\steamapps\common\GigaWrecker\GigaWrecker_Data\StreamingAssets\Audio\GeneratedSoundBanks

Here I found 3 files of note: BGM.bnk, Init.bnk, SE.bnk. Noticing that the BGM.bnk was 285 MB, I had my starting point.

2. I followed various pieces of information found on this forum in order to try to rip the files.

Dragging the BGM.bnk file to "bnkextr.exe" 15 .wem files were created. 

3. I created a separate folder named "WorkSpace" and moved the 15 .wem files to it. In it were: the 15 .wem files, revorb.exe, ww2ogg.exe, and packed_codebooks_aoTuV_603.bin.

4. I then created a .bat file, named "convert.bat" with the following text: 

```
pause
for %%f in (*.ogg) do revorb.exe %%f
pause   
```


The file was placed in the WorkSpace folder, and run. In the command window, I received the following text for all .wem files:

```
Audiokinetic Wwise RIFF/RIFX Vorbis to Ogg Vorbis convertor 0.22 by hcs

Input: 0001.wem
Parse error: expected 0x42 fmt if vorb missing
```


5. I then began going on a wild goose hunt, attempting to find a way to fix the "Parse error: expected 0x42 fmt if vorb missing" through attempting, yet not knowing how to use tools such as:

ima_rejigger2.exe
ima_rejigger5.exe
wwise_ima_adpcm
Wwise Sound Tool.exe

I would simply drag the .wem files (all 15 at once) into the .exe's. The command window would open for a brief second, and nothing would happen (that I am aware of). 

6. During my hunt for these tools, I found this thread: [viewtopic.php?p=108929#p108929](http://forum.xentax.com/viewtopic.php?p=108929#p108929)

Through trial and error, I attempted to do as Kein (thread OP) did...use Audacity to import the raw data of the .wem's.

I am able to load the .wem's to audacity, and even export them...however I noticed that the files are not what I was expecting. It appears as though the files play slightly distorted PARTS of certain BGM's, and that I was viewing a collection of sequenced audio rather than streamed audio.

In this thread, a user named spider91 stated that "You just need to change header a bit to get playable wav pcm file." and after doing research of what that meant, I realized that I was in over my head and that ripping audio, was far more challenging than I had originally thought.

That's where I stopped. 
============

Any help or insight would be much appreciated. If you need any files from me, please let me know, I'm very determined to tackle this beast. 

Lastly, I viewed this post by spider91, however do not know if it is relevant in my scenario, let alone how to go about using such code. Any information people can give would be incredibly appreciated.

[viewtopic.php?p=108929#p108929](http://forum.xentax.com/viewtopic.php?p=108929#p108929)
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-23T17:25:19+00:00
- Post Title: Complete Newb...No programming skills: .wem files

Everything up to #4 is good, sounds like it doesn't use Vorbis (given the error from ww2ogg). You should delete the .wems at this point, though, in case the steps you took in #5 messed up the files somehow; in particular ima_rejigger2 modifies the original input file.

So try recreating the .wem files with step #2. Then you can try decoding them as ADPCM:

ima_rejigger5 needs two arguments, the input and the output. 
I think you should be able to use a .bat file with

```
pause

```

in your WorkSpace folder. Try running that and see what happens.
## Post #3
- Username: lunarsythe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 23, 2016 11:59 am
- Post datetime: 2016-08-23T17:54:51+00:00
- Post Title: Complete Newb...No programming skills: .wem files

> Reply from hcs
>
> Everything up to #4 is good, sounds like it doesn't use Vorbis (given the error from ww2ogg). You should delete the .wems at this point, though, in case the steps you took in #5 messed up the files somehow; in particular ima_rejigger2 modifies the original input file.

So try recreating the .wem files with step #2. Then you can try decoding them as ADPCM:

ima_rejigger5 needs two arguments, the input and the output. 
I think you should be able to use a .bat file with
Code: Select allfor %%a in (*.wem) do ima_rejigger5 "%%a" "%%a.wav"
pause

in your WorkSpace folder. Try running that and see what happens.

```

C:\Users\User\Desktop\Wrecker_soundtrack\dis>ima_rejigger5 "0001.wem" "0001.wem.wav"
ima_rejigger5.c:203:main: not codec id 0x2

```
 
Also tried the other tools too. I'm a script kittie as well, but i'm trying to improve, i tried messing up with the header but got nothing... for reference : 
File 01 - Header
 

File 02 - Header


If any further information is needed i'd be glad to provide it and would love to learn more 
--Thanks in advance!
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-23T20:05:15+00:00
- Post Title: Complete Newb...No programming skills: .wem files

Ah, ok, it looks like that is the PCM format spider91 is describing in his post.

The code he gave is a QuickBMS script, you can get QuickBMS here: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Save spider91's code to wem.bms, put that in a directory with quickbms.exe and the .wems, and try running this from a .bat:

```
pause

```


You could also just try editing the header to change 0x14 from FE FF to 01 00, saving the result as a .wav

I really think all that is going on here is it is supposed to be [WAVE_FORMAT_EXTENSIBLE](https://msdn.microsoft.com/en-us/library/windows/hardware/dn653308%28v=vs.85%29.aspx), for channel mapping.
## Post #5
- Username: lunarsythe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 23, 2016 11:59 am
- Post datetime: 2016-08-23T22:16:43+00:00
- Post Title: Complete Newb...No programming skills: .wem files

> Reply from hcs
>
> Ah, ok, it looks like that is the PCM format spider91 is describing in his post.

The code he gave is a QuickBMS script, you can get QuickBMS here: http://aluigi.altervista.org/quickbms.htm

Save spider91's code to wem.bms, put that in a directory with quickbms.exe and the .wems, and try running this from a .bat:
Code: Select allfor %%a in (*.wem) do quickbms wem.bms "%%a"
pause


You could also just try editing the header to change 0x14 from FE FF to 01 00, saving the result as a .wav

I really think all that is going on here is it is supposed to be WAVE_FORMAT_EXTENSIBLE, for channel mapping.
    Thank you SO much, it worked like a charm (editing the FE FF to 01 00), if you could, i'd love to have any tips you have at all for general programming, hexes, reverse engeneering, everything really, thanks again!!! 
With love -Lunar

Edit : also, just if you have the time to spare, mind explaining why this worked?
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-24T02:17:56+00:00
- Post Title: Complete Newb...No programming skills: .wem files

Bytes 0x14 and 0x15 (technically 4 bytes after the "fmt " chunk identifier) in a [RIFF WAVE file](http://soundfile.sapp.org/doc/WaveFormat/) are the "format tag", which says what encoding or format the audio data uses.

This is a 16 bit little-endian value; 16 bits means it takes two bytes (8 bits in a byte), little endian means the least significant byte is written first, so 1 is stored in 16 bit little endian as 01 00 (if it was 00 01 the value would be 0x0100, or 256).

[PCM](https://en.wikipedia.org/wiki/Pulse-code_modulation), the kind of encoding used in CDs, would have the format tag WAVE_FORMAT_PCM, which is just 1.
These .wem files have a format tag of 0xFFFE (stored as FE FF, because of [Two's complement](https://en.wikipedia.org/wiki/Signed_number_representations#Two.27s_complement) this is actually -2). This is a special format, [WAVE_FORMAT_EXTENSIBLE](https://msdn.microsoft.com/en-us/library/windows/hardware/dn653308%28v=vs.85%29.aspx), which is an extension that provides for more complex ways of specifying things like higher bit depths (24 bits, etc) or channel mappings for multichannel files.

WAVE_FORMAT_EXTENSIBLE is completely unnecessary for these two channel (stereo) 16 bit files, and in any case I think Audiokinetic Wwise doesn't follow the standard correctly, which makes it not play properly in many players. By replacing those bytes you change the format to WAVE_FORMAT_PCM, which works just fine in most players.
## Post #7
- Username: lunarsythe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 23, 2016 11:59 am
- Post datetime: 2016-08-24T02:26:35+00:00
- Post Title: Complete Newb...No programming skills: .wem files

> Reply from hcs
>
> Bytes 0x14 and 0x15 (technically 4 bytes after the "fmt " chunk identifier) in a RIFF WAVE file are the "format tag", which says what encoding or format the audio data uses.

This is a 16 bit little-endian value; 16 bits means it takes two bytes (8 bits in a byte), little endian means the least significant byte is written first, so 1 is stored in 16 bit little endian as 01 00 (if it was 00 01 the value would be 0x0100, or 256).

PCM, the kind of encoding used in CDs, would have the format tag WAVE_FORMAT_PCM, which is just 1.
These .wem files have a format tag of 0xFFFE (stored as FE FF, because of Two's complement this is actually -2). This is a special format, WAVE_FORMAT_EXTENSIBLE, which is an extension that provides for more complex ways of specifying things like higher bit depths (24 bits, etc) or channel mappings for multichannel files.

WAVE_FORMAT_EXTENSIBLE is completely unnecessary for these two channel (stereo) 16 bit files, and in any case I think Audiokinetic Wwise doesn't follow the standard correctly, which makes it not play properly in many players. By replacing those bytes you change the format to WAVE_FORMAT_PCM, which works just fine in most players.
Thank you for your extensive and detailed explanation, i really appreciate it and i hope that it didnt take too much from your time, i'll try my best to grow myself on rpogramming (wich i love) and this kind of stuff is what i judge important, so, again, thank you so much .
