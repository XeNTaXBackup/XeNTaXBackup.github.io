## Post #1
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2023-03-18T02:15:18+00:00
- Post Title: Diablo 4 beta Extraction

Has anyone managed to extract the Diablo 4 beta files? CASC Explorer is not liking it, even if you try to use the fenrisdev setting or change the setting to fenrisb.

Any ideas?
## Post #2
- Username: PlanK69
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 02, 2015 5:32 am
- Post datetime: 2023-03-18T14:10:46+00:00
- Post Title: Diablo 4 beta Extraction

here's all of the archive files so that some1 smart can have a look:

[https://easyupload.io/m/3z93zb](https://easyupload.io/m/3z93zb)
[https://easyupload.io/m/gq71dz](https://easyupload.io/m/gq71dz)
## Post #3
- Username: nic77
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Aug 13, 2021 8:22 am
- Post datetime: 2023-03-21T13:18:18+00:00
- Post Title: Diablo 4 beta Extraction

Hey, I was able to extract the files, but I can't seem to be able to conver the .tex into .dds. Can anyone help me with that? Here is an example

[https://easyupload.io/rnzg9a](https://easyupload.io/rnzg9a)
## Post #4
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2023-03-21T18:10:44+00:00
- Post Title: Diablo 4 beta Extraction

> Reply from Rushster ↑Sat Mar 18, 2023 10:15 am at Sat Mar 18, 2023 10:15 am
>
> 
Has anyone managed to extract the Diablo 4 beta files? CASC Explorer is not liking it, even if you try to use the fenrisdev setting or change the setting to fenrisb.

Any ideas?

CASC Explorer has been updated to support Diablo 4 beta:

[https://github.com/WoW-Tools/CASCExplorer/releases](https://github.com/WoW-Tools/CASCExplorer/releases)
## Post #5
- Username: StrefaPD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 15, 2023 3:24 am
- Post datetime: 2023-05-14T19:26:14+00:00
- Post Title: Diablo 4 beta Extraction

I downloaded new cascview and RIP files, but how can i extract or convert  .wsb files?
## Post #6
- Username: lowtotheride
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 02, 2023 1:30 am
- Post datetime: 2023-06-01T18:00:18+00:00
- Post Title: Diablo 4 beta Extraction

I have the same issue, no idea how to extract audio from WSB files. They look like WAV format, but bytes 21-22 are FFFF ("Development").

Here are some sample files:
- enUS_Speech/child/wWiseSoundBank/CAMP_Hawe_Crusaders_Intro-0.wsb [https://pixeldrain.com/u/ngU8WhcT](https://pixeldrain.com/u/ngU8WhcT)
- enUS_Speech/child/wWiseSoundBank/Camp_Frac_Tundra_FindBoss-9.wsb [https://pixeldrain.com/u/BsFbsAFs](https://pixeldrain.com/u/BsFbsAFs)
- enUS_Speech/meta/wWiseSoundBank/CAMP_KeironsPyre_Intro.wsb [https://pixeldrain.com/u/Zg5YZ7r6](https://pixeldrain.com/u/Zg5YZ7r6)

I ran the first one through ww2ogg and got this corrupted file:

- CAMP_Hawe_Crusaders_Intro-0.ogg [https://pixeldrain.com/u/BUjWT1YC](https://pixeldrain.com/u/BUjWT1YC)

Then I converted it to mp3 with ffmpeg and it made my ears bleed:

- CAMP_Hawe_Crusaders_Intro-0.mp3 [https://pixeldrain.com/u/2NJHBU1U](https://pixeldrain.com/u/2NJHBU1U)

Any ideas?
## Post #7
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2023-06-06T11:33:37+00:00
- Post Title: Diablo 4 beta Extraction

```
- enUS_Speech/child/wWiseSoundBank/Camp_Frac_Tundra_FindBoss-9.wsb
```


vgmstream can playback / convert these files. I just changed the file extension from .wsb to .wem and it identified it as custom vorbis audiokinetic Wwise.

As for CAMP_KeironsPyre_Intro, that one is different to the other two sample files as it doesn't have the RIFF file header.
## Post #8
- Username: GloriouslyPurposeful
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 10, 2023 12:32 am
- Post datetime: 2023-06-09T16:34:13+00:00
- Post Title: Diablo 4 beta Extraction

> Reply from brendan19 ↑Tue Jun 06, 2023 7:33 pm at Tue Jun 06, 2023 7:33 pm
>
> 
Code: Select all- enUS_Speech/child/wWiseSoundBank/CAMP_Hawe_Crusaders_Intro-0.wsb
- enUS_Speech/child/wWiseSoundBank/Camp_Frac_Tundra_FindBoss-9.wsb

vgmstream can playback / convert these files. I just changed the file extension from .wsb to .wem and it identified it as custom vorbis audiokinetic Wwise.

As for CAMP_KeironsPyre_Intro, that one is different to the other two sample files as it doesn't have the RIFF file header.

Doesn't work "failed to convert files". Ripped the wsb's from the online beta build via CASC, changed extension to wem. Nothing.
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2023-06-10T15:10:45+00:00
- Post Title: Diablo 4 beta Extraction

Checking a few files myself, you might need to remove the first 0x800 bytes in a hex editor or use some kind of file trimmer / cutter tool e.g. simple file cutter located inside [vgmtoolbox](https://sourceforge.net/projects/vgmtoolbox/) to do multiple files in succession quickly. The file should start with the magic "BKHD"

Save it, change the extension from .wsb to .bnk and vgmstream can playback / export all of the files inside the soundbank.

If there is still no sound, than it probably doesn't contain any audio data which means that it might be located elsewhere.
## Post #10
- Username: lexkoro
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 20, 2023 4:32 am
- Post datetime: 2023-06-13T16:57:40+00:00
- Post Title: Diablo 4 beta Extraction

Does anyone have any idea where the text transcriptions for the dialogue files are stored?
## Post #11
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2023-06-14T12:48:46+00:00
- Post Title: Diablo 4 beta Extraction

> Reply from lexkoro ↑Wed Jun 14, 2023 12:57 am at Wed Jun 14, 2023 12:57 am
>
> 
Does anyone have any idea where the text transcriptions for the dialogue files are stored?

Not sure about texts, could be streamed online ? I was not interested abut this game much, since someone told me that texts are not present in the archives..
## Post #12
- Username: GloriouslyPurposeful
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 10, 2023 12:32 am
- Post datetime: 2023-06-18T00:55:52+00:00
- Post Title: Diablo 4 beta Extraction

> Reply from brendan19 ↑Sat Jun 10, 2023 11:10 pm at Sat Jun 10, 2023 11:10 pm
>
> 
Checking a few files myself, you might need to remove the first 0x800 bytes in a hex editor or use some kind of file trimmer / cutter tool e.g. simple file cutter located inside vgmtoolbox to do multiple files in succession quickly. The file should start with the magic "BKHD"

Save it, change the extension from .wsb to .bnk and vgmstream can playback / export all of the files inside the soundbank.

If there is still no sound, than it probably doesn't contain any audio data which means that it might be located elsewhere.

Nevermind, nowhere near worth the fuss.
## Post #13
- Username: Rushster
- Rank: n00b
- Number of posts: 10
- Joined date: Sat May 08, 2021 9:55 pm
- Post datetime: 2023-06-21T01:36:42+00:00
- Post Title: Diablo 4 beta Extraction

> Reply from lexkoro ↑Wed Jun 14, 2023 12:57 am at Wed Jun 14, 2023 12:57 am
>
> 
Does anyone have any idea where the text transcriptions for the dialogue files are stored?

Probably in the Stringlist file.
## Post #14
- Username: lexkoro
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 20, 2023 4:32 am
- Post datetime: 2023-06-22T16:34:27+00:00
- Post Title: Diablo 4 beta Extraction

> Reply from Rushster ↑Wed Jun 21, 2023 9:36 am at Wed Jun 21, 2023 9:36 am
>
> 
Probably in the Stringlist file.

Thanks, using [https://github.com/alkhdaniel/diablo-4-string-parser](https://github.com/alkhdaniel/diablo-4-string-parser) I was able to extract the transcriptions.

For the audio files I just used ww2ogg.exe with ww2ogg.exe "filepath" --pcb packed_codebooks_aoTuV_603.bin as command to convert the .wsb files to .ogg .
Haven't checked all files but those I did are working without problems.
## Post #15
- Username: StrefaPD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 15, 2023 3:24 am
- Post datetime: 2023-06-23T20:59:55+00:00
- Post Title: Diablo 4 beta Extraction

> Reply from lexkoro ↑Fri Jun 23, 2023 12:34 am at Fri Jun 23, 2023 12:34 am
>
> 
Rushster wrote: ↑Wed Jun 21, 2023 9:36 am
Probably in the Stringlist file.


Thanks, using https://github.com/alkhdaniel/diablo-4-string-parser I was able to extract the transcriptions.

For the audio files I just used ww2ogg.exe with ww2ogg.exe "filepath" --pcb packed_codebooks_aoTuV_603.bin as command to convert the .wsb files to .ogg .
Haven't checked all files but those I did are working without problems.

Can u uload video with instruction how to do this? How extract sound files or if u can read the tutorial please...
## Post #16
- Username: lexkoro
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 20, 2023 4:32 am
- Post datetime: 2023-06-27T15:19:59+00:00
- Post Title: Re: Diablo 4 beta Extraction

> Reply from StrefaPD ↑Sat Jun 24, 2023 4:59 am at Sat Jun 24, 2023 4:59 am
>
> 
How extract sound files or if u can read the tutorial please...

I used CASCExplorer Build from [https://github.com/WoW-Tools/CASCExplor ... 1569715689](https://github.com/WoW-Tools/CASCExplorer/issues/83#issuecomment-1569715689)
to access the Diablo 4 files.

Extracted the folder enUS_Speech which contains the .wsb files.

To convert .wsb to .ogg I used [https://github.com/hcs64/ww2ogg](https://github.com/hcs64/ww2ogg).

You can then convert a .wsb file with this command: 
```
.\ww2ogg.exe CAMP_Hawe_Crusaders_Intro-0.wsb --pcb packed_codebooks_aoTuV_603.bin
```


I wrote a small batch script which converts all .wsb files in a folder and moves the .ogg files to another.

```
setlocal enabledelayedexpansion

REM set src and dst dir
set "srcDir=C:\path\to\enUS_Speech\child\wWiseSoundBank"
set "dstDir=C:\output\path\en\ogg"

REM ensure the destination directory exists else create it
if not exist "%dstDir%" mkdir "%dstDir%"

for %%F in ("%srcDir%\*.wsb") do (
    set "baseName=%%~nF"
    ww2ogg.exe "%%F" --pcb packed_codebooks_aoTuV_603.bin
    move "%srcDir%\!baseName!.ogg" "%dstDir%"
)

endlocal
```
