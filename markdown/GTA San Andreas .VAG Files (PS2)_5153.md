## Post #1
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-10-07T19:54:22+00:00
- Post Title: GTA San Andreas .VAG Files (PS2)

Hi I am trying to convert the .VAG files that are inside the .PAK files on the game Grand theft Auto San Andreas for the PS2. I have successfully extracted the VAGs from the .PAK archives with a tool I found on the net and now I need to find the correct settings to use in MFAudio. I do have the San Andreas Radio program but that only does the radio stations, I would like to extract all of the audio from the game like all the sound effects but mostly the police chatter that you hear when on a police motorcycle and the background music heard in some of the stores and clubs. I have uploaded one of the .VAG files, this one is the little tune that you hear when you pass a mission. 


[http://www.filefactory.com/file/b3d8b39/n/FILE0007.VAG](http://www.filefactory.com/file/b3d8b39/n/FILE0007.VAG) 

There is a captcha and then 30 second wait but no popups on my end. your milage may vary.
It is also attached to this message.

What I need is the correct settings in MFAudio and when I find the right settings i'm hoping that I can apply them to the rest of the files. the programs that I used to extract the VAGs from the .PAK archives they do spit out a text file with a bunch of numbers but I don't know what to do with those. Anyone know? I would really appreciate the help. I have also attached it to this message so either way you will get the file. it's 275KB so I hope that's not too big.
Thanks for the help I appreciate it.
[FILE0007.rar](https://xentaxbackup.github.io/file/3505_FILE0007.rar)
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-12T09:54:10+00:00
- Post Title: GTA San Andreas .VAG Files (PS2)

How did you get the file? Where's the original file name?
## Post #3
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-10-12T16:11:20+00:00
- Post Title: GTA San Andreas .VAG Files (PS2)

> Reply from AlphaTwentyThree
>
> How did you get the file? Where's the original file name?

I used a set of programs I found online for this game. the original files off the PS2 game disc are .pak archives. these programs are the closest that i've gotten to extracting the stuff I want from this game all I need is the right settings to use in MFAudio. The VAGs in this game will play in that program but they skip and stutter. I need to put in the right settings and I've been trying forever to get it right Please help. what info do you need for this? the original filenames are AA.pak, beats.pak, CR.pak, and so on. they can be found on the PS2 disc b/c i'm not sure if there is one I can post here. did you download the attached file?
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-12T21:53:20+00:00
- Post Title: GTA San Andreas .VAG Files (PS2)

Yes I did and the structure is very strange as the stream has a big zero block in the middle of the file so it seems as if it's in fact two files. That's why I asked which program EXACTLY did you use to extract them? Looks like some random VAG scanner like ADPCM Player. I'd need one of the *.pak files to check the structure.
## Post #5
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-10-13T03:49:51+00:00
- Post Title: GTA San Andreas .VAG Files (PS2)

> Reply from AlphaTwentyThree
>
> Yes I did and the structure is very strange as the stream has a big zero block in the middle of the file so it seems as if it's in fact two files. That's why I asked which program EXACTLY did you use to extract them? Looks like some random VAG scanner like ADPCM Player. I'd need one of the *.pak files to check the structure.
I can maybe post one of the .PAK files but it's an archive file. I used this tool called GTASA tool. heres the readme that comes with it.


GTA_SA_IMG-tool.exe
all .img file
===========================
GTA_SA_Streams_PAK-tool.exe - table file and bigfile must be same path
AUDIO\STREAMS folder-all the .pak
table file 
- AUDIO\CONFIG\TRAKLKUP.DAT
=====================================
GTA_SA_SFX_PAK-tool.exe - table file and bigfile must be same path
AUDIO\SFX\ folder-all the .pak
FEET01.PAK = FEET02.PAK ->same size
GENRL01.PAK = GENRL02.PAK ->same size
PAIN_A01.PAK = PAIN_A02.PAK ->same size
SCRIPT01.PAK =SCRIPT02.PAK ->same size
table file 
- AUDIO\CONFIG\BANKLKUP.DAT
=======================================
GTA_SA_SFX_vag-tool.exe - for all the .vag files
this tool is for all the SFX .PAK file after extracted .vag
============================================================

it has other files:
VAG2WAV.BAT
GTASA2WAV.exe
MFAudio.exe
streams_pak.exe
wav2gtasa.exe
These are the tools that I was able to use to extract the VAG files out of the .pak archives but that's as far as I got. Like I said in my other comment I can open each VAG file in MFAudio and play it but it skips and is choppy I need the right settings. There is a text file seen here this is from the beats.pak file made by the above tools.

00000000|005AEF84|FILE0000.VAG
005AEF84|009EFF84|FILE0001.VAG
00F9EF08|00653F84|FILE0002.VAG
015F2E8C|005F0F84|FILE0003.VAG
01BE3E10|0058DF84|FILE0004.VAG
02171D94|00611F84|FILE0005.VAG
02783D18|00632F84|FILE0006.VAG
02DB6C9C|00044F84|FILE0007.VAG
02DFBC20|00044F84|FILE0008.VAG
02E40BA4|00233F84|FILE0009.VAG

Note that the file0007 in this text file is not for the other attached file the mission passed tune

I don't know what these number and letter combos are for I think they are hex values or something. the above mentioned program has generated this file. Any more info needed?

I can post the feet01.pak file b/c it's the smallest. I'm hoping the settings are the same for every other sound in this game. Please help. Thanks in advance.
[FEET01.rar](https://xentaxbackup.github.io/file/3524_FEET01.rar)
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-13T11:31:46+00:00
- Post Title: GTA San Andreas .VAG Files (PS2)

As written in the txt file, I'll also need the AUDIO\CONFIG\BANKLKUP.DAT
## Post #7
- Username: gamehead
- Rank: advanced
- Number of posts: 48
- Joined date: Sat Nov 17, 2007 4:11 am
- Post datetime: 2010-10-14T04:28:23+00:00
- Post Title: GTA San Andreas .VAG Files (PS2)

> Reply from AlphaTwentyThree
>
> As written in the txt file, I'll also need the AUDIO\CONFIG\BANKLKUP.DAT

Done. Anything else?
[BANKLKUP.rar](https://xentaxbackup.github.io/file/3530_BANKLKUP.rar)
