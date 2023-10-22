## Post #1
- Username: Speed Nukem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 10, 2015 5:42 pm
- Post datetime: 2015-06-10T10:06:51+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

I wanted to replace the music in metal gear solid twin snakes with the original ps1 music
on extracting the gc rom the files in the shared/audio/stream and the audio/stream folder are actually dsp files, all the level music and  ingame voices(whos there,a surveillance camera,tighten security,mantis reading the memory card,title theme,snake snake SNAAAAAAAAAAAAAKE) I edited some of them in audacity and replaced cd 1 level music but then i ran into this problem

scanning the vox.dat and movies.dat with psound and solidus which are supposed to contain the codec convos and real time rendered video music results in no files found
 as far as I understand the working of solidus and psound(I may be wrong) they look for specific file types in the dat archive so if the search is modified to find files without extensions then it can esily extract all the files present in the dat archive in this case fioles wthout extensions are music files
so can I have a versions of solidus that extracts files without extensions? pretty please  

ps. if someone wants a list of music ouside the dat files let me know
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-06-15T13:27:24+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

> Reply from Speed Nukem
>
> I wanted to replace the music in metal gear solid twin snakes with the original ps1 music
on extracting the gc rom the files in the shared/audio/stream and the audio/stream folder are actually dsp files, all the level music and  ingame voices(whos there,a surveillance camera,tighten security,mantis reading the memory card,title theme,snake snake SNAAAAAAAAAAAAAKE) I edited some of them in audacity and replaced cd 1 level music but then i ran into this problem

scanning the vox.dat and movies.dat with psound and solidus which are supposed to contain the codec convos and real time rendered video music results in no files found
 as far as I understand the working of solidus and psound(I may be wrong) they look for specific file types in the dat archive so if the search is modified to find files without extensions then it can esily extract all the files present in the dat archive in this case fioles wthout extensions are music files
so can I have a versions of solidus that extracts files without extensions? pretty please  

ps. if someone wants a list of music ouside the dat files let me know

Solidus supposedly only worked with texture formats in twin snakes if i recall, but i never even got that working. psound is designed for sony ps1/2/psp audio formats, I'm pretty sure twin snakes uses ogg vorbis (weird on gamecube, I know, but the dev behind it was starting a big project on UE3, which ended up being their downfall)   The only problem is, the audio you get is recognizable, but segments of audio are jumbled across inside all the files, and not coherent to one bit of audio. I can't really describe it better, you'll see when you get the files out.
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2015-06-16T18:23:27+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

> Reply from Pepper
>
> Speed Nukem wrote:I wanted to replace the music in metal gear solid twin snakes with the original ps1 music
on extracting the gc rom the files in the shared/audio/stream and the audio/stream folder are actually dsp files, all the level music and  ingame voices(whos there,a surveillance camera,tighten security,mantis reading the memory card,title theme,snake snake SNAAAAAAAAAAAAAKE) I edited some of them in audacity and replaced cd 1 level music but then i ran into this problem

scanning the vox.dat and movies.dat with psound and solidus which are supposed to contain the codec convos and real time rendered video music results in no files found
 as far as I understand the working of solidus and psound(I may be wrong) they look for specific file types in the dat archive so if the search is modified to find files without extensions then it can esily extract all the files present in the dat archive in this case fioles wthout extensions are music files
so can I have a versions of solidus that extracts files without extensions? pretty please  

ps. if someone wants a list of music ouside the dat files let me know

Solidus supposedly only worked with texture formats in twin snakes if i recall, but i never even got that working. psound is designed for sony ps1/2/psp audio formats, I'm pretty sure twin snakes uses ogg vorbis (weird on gamecube, I know, but the dev behind it was starting a big project on UE3, which ended up being their downfall)   The only problem is, the audio you get is recognizable, but segments of audio are jumbled across inside all the files, and not coherent to one bit of audio. I can't really describe it better, you'll see when you get the files out.

Solidus could/can extract the textures but thats it, it can't do anything else with twin snakes.

Twin Snakes does use OGG Vorbis for its music, but not sure what it uses for its cutscene audio or basically non gameplay background music audio.
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-06-18T02:43:39+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

> Reply from lionheartuk
>
> Pepper wrote:Speed Nukem wrote:I wanted to replace the music in metal gear solid twin snakes with the original ps1 music
on extracting the gc rom the files in the shared/audio/stream and the audio/stream folder are actually dsp files, all the level music and  ingame voices(whos there,a surveillance camera,tighten security,mantis reading the memory card,title theme,snake snake SNAAAAAAAAAAAAAKE) I edited some of them in audacity and replaced cd 1 level music but then i ran into this problem

scanning the vox.dat and movies.dat with psound and solidus which are supposed to contain the codec convos and real time rendered video music results in no files found
 as far as I understand the working of solidus and psound(I may be wrong) they look for specific file types in the dat archive so if the search is modified to find files without extensions then it can esily extract all the files present in the dat archive in this case fioles wthout extensions are music files
so can I have a versions of solidus that extracts files without extensions? pretty please  

ps. if someone wants a list of music ouside the dat files let me know

Solidus supposedly only worked with texture formats in twin snakes if i recall, but i never even got that working. psound is designed for sony ps1/2/psp audio formats, I'm pretty sure twin snakes uses ogg vorbis (weird on gamecube, I know, but the dev behind it was starting a big project on UE3, which ended up being their downfall)   The only problem is, the audio you get is recognizable, but segments of audio are jumbled across inside all the files, and not coherent to one bit of audio. I can't really describe it better, you'll see when you get the files out.

Solidus could/can extract the textures but thats it, it can't do anything else with twin snakes.

Twin Snakes does use OGG Vorbis for its music, but not sure what it uses for its cutscene audio or basically non gameplay background music audio.

it's pretty much ogg vorbis for cutscene audio, it's just smashed into small bits of audio stored in each ogg file. I would guess the game somehow takes these 0.1-1 second chunks strewn about inside each ogg vorbis stream and reassembles them. Haven't got the faintest clue how it knows what to do what with, and the files just sound like a jumbled phonetic mess of syllables from recognizable voices.
## Post #5
- Username: Speed Nukem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 10, 2015 5:42 pm
- Post datetime: 2015-06-26T00:56:22+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

I don't think the music files are ogg I guess they are dsp files like the ones outside the DAT files
maybe the dsp and ogg have something common in their hex which results in the jumbled up audio
this obviously is a speculation
I have got a open source DAT extractor called dragon unpacker
modifying this program to find dsp files should give a answer

P.s. 
I have replaced all the level music in mgs tts rom how do i make a patch?
## Post #6
- Username: Jonathan Ingram
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 22, 2015 6:20 am
- Post datetime: 2015-07-03T01:07:30+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

The files found in the \audio\ or \shared\audio\ directories are standard Nintendo DSP streams and SPD/SPT banks.

You can use [demux_dat_be.exe](http://www.hcs64.com/files/demux_dat_02.zip) to extract the Vorbis streams from demo.dat and \shared\movie.dat and have them play back correctly. It will name them as .mtaf files, so change the extensions to .ogg after extraction.

Solidus can extract the files from stage.dat and \shared\face.dat. It can also convert the .texturefiles, but it won't work with the .kmy models.

I still haven't found anything that successfully extracts the Vorbis streams from vox.dat. demux_dat_be will only recognize the subtitle data. I've heard that [Obscure Extractor GTK](http://sourceforge.net/projects/extractor-gtk/) works on vox.dat as well as extracts the VP3 format movies from movie.dat, but I can never get the thing to work.

If anyone here knows how to get vox.dat's contents and in a way so that they play back correctly, please let me know.
## Post #7
- Username: solidcrash
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 14, 2019 12:34 am
- Post datetime: 2019-07-15T09:46:17+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

Has there been progress in this project. I'm having some trouble with it. I found how identify wich audio modify from the audio/stream folder. Every audio are split left and right channel. How can i replace that? First i need to convert the psx audio in dsp format. Do i need to split them left and right? Or can i simple put the same audio in both channel? 
It will be nice to have some tutorial for doing everything if someome as already did. Thanks a lot
## Post #8
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2022-08-03T08:02:07+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

Hello!
I made some progress on the file extraction from .dat files. So far my tool works on both vox.dat, movie.dat and demo.dat. Other dat files use a different data structure as far as I know. My aim is to replace the audio files with the ones in another language provided by the PSX version. I don't really know if it will be feasible or not, but I think it's worth trying.

Before releasing the tool I want to add some basic features, like being able to only analyze the dat file without extracting every file, or extracting audio files only. 


Anyway, I want to document here how the data structure works. I have understood like 90% of the entire structure. Hopefully, someone can help me understanding what the few "unknown" values actually represent.

Let's start. These are the first bytes of vox.dat from Disc 1:
[](https://imgbb.com/)

Data is stored as a "dictionary", and is split into multiple "pages". Each page has the following structure:
Blue rows represent dictionary "definitions", which tells how many and what kind of data is stored in every dictionary.
Green rows represent data in the dictionary.
Red rows represent zeros used for padding.

Let's see the first dictionary definition in detail. Every definition is composed of 16 bytes organized as follows:
00 00 00 10 = 0x10 (in big endian) is an identifier for "dictionary definition"
00 00 00 10 = 0x10 = 16 bytes is the length of the definition
00 00 00 00 are all zeros in the definition
00 01 00 04 is the defined data type

Data types, in particular, are split into two word (2-bytes numbers). The second word (in big endian) is the type of datum stored. So far I encountered the following four types:
0x01 = audio
0x04 = subtitle
0x02 = unknown
0x06 = unknown
0x07 = unknown 

The first word (again, in big endian) represents the language:
0x00 = default
0x01 = english
0x02 = french
0x03 = german
0x04 = italian
0x05 = spanish
0x07 = japanese

So the first definition actually defines a subtitle (0x04) in english (0x01). The second definition, instead, a subtitle (0x04) in japanese (0x07). 

Let's now focus on the green part that represent the data, here called dictionary entry. Each entry is identified with a 16-bytes header. The first entry has
00 01 00 04 = 0x04 (subtitle) and 0x01 (english) identifies the data
00 00 00 40 = 0x40 = 64 bytes is the length of data (with header)
00 00 00 00 (unknown1) are all zeros here
00 00 00 00 (unknown2) are all zeros here

The second entry is very similar. The only difference is in the subtitle language (jap instead of eng).

Finally, a padding section is found in the red area:
00 00 00 F0 = 0xF0 identifies the padding
00 00 00 10 = 0x10 = 16 bytes is the length of this header
00 00 01 2C (unknown1) I don't know what this represents. It is not the number of 00 used for padding.
00 00 00 00 (unknown2) are all zeros here

The zeros used for padding end at the file offset 0x800 and mark the end of a dictionary page. Every page in the file is always aligned to 0x800 (so for example, it can end at 0x800, 0x1000, 0x1800 and so on).


Since I'm interested in audio files, I want to show how they are stored. In vox.dat, the first audio file appears at the offset 0x26b090:
[](https://imgbb.com/)

Audio files are organized as chunks of 8192 bytes. However, before the first chunk one can find the following header:
00 00 00 01 = 0x01 (audio) and 0x00 (default language)
00 00 00 20 = 0x20 = 32 bytes is the length of data (with header)
00 00 00 00 (unknown1) are all zeros here
00 00 00 08 (unknown2) = 0x08
which contains the following data, that I'm not able to interpret:
00 00 00 07 = 0x07 (data type unknown)?
00 00 20 00 = 0x2000 = 8192 bytes?
66 66 66 66 (unknown1) 
66 66 66 66 (unknown2) 

But then, after this first chunk, one can find:
00 00 00 01 = 0x01 (audio) and 0x00 (default language)
00 00 20 10 = 0x2010 = 8208 bytes is the length of data (with header) -> 8192 + 16
00 00 00 00 (unknown1) are all zeros here
00 00 20 00 = 0x2000 = 8192 bytes. For audio files, this represents the encapsulated data length.
Finally, the first 8192-byte chunk of audio data occurs.

The analysis on this page reveals the following data:

```
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 0     Data (no pad) 8192  at file offset 0xb0
I: Chunk Type unk    (0x0006) Lang eng (0x0001) Length 256   Data size 240   Unk 0     Data (no pad) 0     at file offset 0x20c0
I: Chunk Type unk    (0x0006) Lang ger (0x0003) Length 256   Data size 240   Unk 0     Data (no pad) 0     at file offset 0x21c0
I: Chunk Type unk    (0x0006) Lang fra (0x0002) Length 256   Data size 240   Unk 0     Data (no pad) 0     at file offset 0x22c0
I: Chunk Type unk    (0x0006) Lang ita (0x0004) Length 256   Data size 240   Unk 0     Data (no pad) 0     at file offset 0x23c0
I: Chunk Type unk    (0x0006) Lang esp (0x0005) Length 256   Data size 240   Unk 0     Data (no pad) 0     at file offset 0x24c0
I: Chunk Type unk    (0x0006) Lang jap (0x0007) Length 256   Data size 240   Unk 0     Data (no pad) 0     at file offset 0x25c0
I: Chunk Type unk    (0x0007) Lang def (0x0000) Length 624   Data size 608   Unk 1     Data (no pad) 0     at file offset 0x26c0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 1     Data (no pad) 8192  at file offset 0x2930
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 2     Data (no pad) 8192  at file offset 0x4940
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 3     Data (no pad) 8192  at file offset 0x6950
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 4     Data (no pad) 8192  at file offset 0x8960
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 5     Data (no pad) 8192  at file offset 0xa970
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 6     Data (no pad) 8192  at file offset 0xc980
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 576   Data (no pad) 8192  at file offset 0xe990
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 1209  Data (no pad) 8192  at file offset 0x109a0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 1588  Data (no pad) 8192  at file offset 0x129b0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 2081  Data (no pad) 8192  at file offset 0x149c0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 2518  Data (no pad) 8192  at file offset 0x169d0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 3022  Data (no pad) 8192  at file offset 0x189e0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 3650  Data (no pad) 8192  at file offset 0x1a9f0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 4028  Data (no pad) 8192  at file offset 0x1ca00
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 4611  Data (no pad) 8192  at file offset 0x1ea10
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 5328  Data (no pad) 8192  at file offset 0x20a20
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 5749  Data (no pad) 8192  at file offset 0x22a30
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 6229  Data (no pad) 8192  at file offset 0x24a40
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 6699  Data (no pad) 8192  at file offset 0x26a50
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 7270  Data (no pad) 8192  at file offset 0x28a60
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 7765  Data (no pad) 8192  at file offset 0x2aa70
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 7995  Data (no pad) 8192  at file offset 0x2ca80
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 8369  Data (no pad) 8192  at file offset 0x2ea90
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 8925  Data (no pad) 8192  at file offset 0x30aa0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 9441  Data (no pad) 8192  at file offset 0x32ab0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 10032 Data (no pad) 8192  at file offset 0x34ac0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 10554 Data (no pad) 8192  at file offset 0x36ad0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 8208  Data size 8192  Unk 10977 Data (no pad) 8192  at file offset 0x38ae0
I: Chunk Type audio  (0x0001) Lang def (0x0000) Length 2448  Data size 2432  Unk 11392 Data (no pad) 2419  at file offset 0x3aaf0
```


where "Unk" is actually "unknown1". As you can see, "unknown1" increases by 1 up to 6, then it increases by (random?) amounts, which in principle do not have any relationship with the data size. The same behaviour can be observed with audio files in the other pages. So hopefully someone can help me understanding, in particular, the meaning of this value, which may be important to replace the audio files inside the .dat. 

Thank you for the attention (if you read up to this point  )

Big thanks to the the authors of "demux_dat", which was very helpful at the beginning of my research.
## Post #9
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2022-08-03T18:40:57+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

Just to add a little bit more from what I found out when I looked into the MGS games a while ago when trying to do my own extractor.

As you've already got, a block type of 1 is audio.  If the block size is 0x20, then it's an audio header, otherwise it's audio data.

Your unknown2 value in the audio header is the audio type, in this case 8, which identifies the audio data as Ogg format - IIRC, I think this is the only format used in the Twin Snakes dat files.  If the audio type is 0 (as in PSX MGS1 and PS2 MGS2), this indicates the audio data is headerless and then the rest of that header block contains the sample rate, channels and the actual audio codec.  The 0x66 values in the header are values that are not required for Ogg as it's a self-contained format, not sure what the 7 represents.
## Post #10
- Username: giofrida
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Nov 08, 2020 5:14 pm
- Post datetime: 2022-08-06T06:44:05+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

Thank you DKDave for explaining the meaning of that audio header. 

[I linked here](https://mega.nz/file/kNQgRZQC#Z6RXmrV06jngcp4_9U3Fv5pfw0zzEvMSyAX63dLO8ow) the source of my tool with a precompiled executable with cygwin. I tried to be as clear as possible in my code, but it's been a while since I programmed so much, so it may look a bit messy at times. 

It can extract the contents of movie.dat, demo.dat and vox.dat successfully. Also, it can "decode" (nothing fancy here ) the following files:

audio files: audio header is removed and padding zeros are stripped
subtitle files: subtitle lines are interpreted with the correct timestamp and the speaker name (note: I didn't search for all the speaker codes, many are still missing; also, japanese subtitles are not decoded properly as there is additional data used to most probably store/encode japanese fonts) and exported as .srt files
so-called "sync" files are also correctly interpreted as subtitles. These are files of type 0x06 that store timestamps and speaker names, but without text data. Indeed, text data are stored in codec.dat, but I'm unable to understand the link between the two files, that is, how is that sync file pointing to the correct location in codec.dat?
movie files: as far as I know these are VP3 (version 1) movies. Padding zeros are stripped, but I still cannot decode them via ffmpeg. Most probably there is some kind of unexpected header that prevents ffmpeg to correctly decode the file.


I would like to test repacking the data file, but first I need to understand the meaning behind that "unknown" value. As shown in the [linked debug logs](https://mega.nz/file/lERlWThD#A-7qo4N3ezDnoPM31iJ4MLHrxhNBFX1kch-HSANHBSw) of movie, demo and vox, "Unk" increases with every new chunk of data in a page, then it gets reset to 0 or another value. I think the increment depends on the number of chunks in every page, maybe the order of data types and the (total?) size of chunks. Anyway, two relationships are always valid:

Unk in padding chunk (type 0xF0) is always equal to Unk of the previous chunk + 300 (dec)
Unk of the last chunk is always equal to Unk of the previous chunk + 1
## Post #11
- Username: USER1000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Mar 17, 2023 3:37 am
- Post datetime: 2023-03-16T22:16:41+00:00
- Post Title: Metal gear solid Twin snakes .dat files and audio

Hi giofrida.

Could you explain a little how to run your tool when extracting dat files?

Thanks.
