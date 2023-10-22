## Post #1
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2023-08-22T20:20:22+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

I want to get action voices and models from DQH2,with the quickbms(arslan.bms)I extract the LINKDATA.BIN.There are lots of .nfc ,.sdb,.vap...... and I think the sound is stored in .vap.While the vgmstream doesn't work .Does anyone can help me to extract them (or the sound can be another file).Here are some examples:[https://drive.google.com/drive/folders/ ... drive_link](https://drive.google.com/drive/folders/1IHN2w6_w94fSeit0Wq1LB-enTMngQJyT?usp=drive_link)
## Post #2
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-22T22:44:38+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

[](https://ibb.co/hD2xVMD)

Can't download the file
## Post #3
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2023-08-23T08:33:51+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

Sorry and I have updated permissions
## Post #4
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-23T08:36:03+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

None of your files contains audio data but it does contains text
Can you screenshots the contents of the extracted LINKDATAs here?
## Post #5
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2023-08-23T11:10:35+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

OK，Here are the all list movie，It contains .sp .nfc .vap .alg .cl5 .dat .mdl .gt1 .sdb .me1 .alg...,some of them are models and Textures.[https://drive.google.com/file/d/1vrEZr_ ... sp=sharing](https://drive.google.com/file/d/1vrEZr_AiTqrkLGsgQAucZrqsVk4Pn9jQ/view?usp=sharing)
## Post #6
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-23T11:38:55+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

> Reply from 15221281395 ↑Wed Aug 23, 2023 7:10 pm at Wed Aug 23, 2023 7:10 pm
>
> 
OK，Here are the all list movie，It contains .sp .nfc .vap .alg .cl5 .dat .mdl .gt1 .sdb .me1 .alg...,some of them are models and Textures.https://drive.google.com/file/d/1vrEZr_ ... sp=sharing

Can you upload a few dats, nfcs, sdbs, and cdws and then post it here?
Basically anything with size of 4-5MB or bigger.
## Post #7
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2023-08-23T13:26:07+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

[https://drive.google.com/drive/folders/ ... drive_link](https://drive.google.com/drive/folders/1ScSswuQYztJLI6bGAw2QeI8NLvBPXR1j?usp=drive_link).
## Post #8
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2023-08-23T21:25:17+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

> Reply from 15221281395 ↑Wed Aug 23, 2023 9:26 pm at Wed Aug 23, 2023 9:26 pm
>
> 
https://drive.google.com/drive/folders/ ... drive_link.

That's weird, I still couldn't find the audio data.
Is there another archive or file other than LINKDATA.BIN?
## Post #9
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2023-08-24T13:55:14+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

Ok，these are all files.The files in High and Low are vedios which can  play just rename avi but without sound.I think they are vedio versions with different resolutions so I didn't unload.Ohers are all bgmxx.g1l.The files extract from Linkdate have removed some obviously model texture contents.I really wonder where the action audio files（including SE）are.[https://drive.google.com/drive/folders/ ... drive_link](https://drive.google.com/drive/folders/1wWBvFME_Rm2LnymO9vKj84iTqM8vLFMh?usp=drive_link)
## Post #10
- Username: halo1573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 31, 2022 2:41 pm
- Post datetime: 2023-08-27T00:45:09+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

When extracting Koei-Tecmo games, recommend using Cethleann tool.
Because this tool supports most of KT games.

[viewtopic.php?t=21679](https://forum.xentax.com/viewtopic.php?t=21679)

Get the tool and learn how to use it.
*** Please use v1.2, use v1.21 only for Persona 5 scramble,

use the command.
Cethleann.DataExporter.exe --linkdata "Output folder" "Input folder(LINKDATA.BIN path)"

Most KT games use two or more sound file types.

In DQH1, 2,
BGM-g1l
Battle SE, voice - pair of wbd and wbh files
Cutscene voice - ???
(I guess it's kvs, but it's a long time ago, so I'm not sure)

You can play .wbd file with foobar2000 + Vgmtream plugin.
.wbh file is also needed to play and must be together with .wbd.

These files are usually located in "LINKDATA\misc\formats\WBH" folder path, but often are not.

For most, these exist in "LINKDATA\misc\unknown" folder path and have .bin extension.

You need to look at the headers of the .bin files and find .wbd and .wbh files separately.
.wbd -> _DBW or WBD_ 
.wbh -> _HBW or WBH_ 

You can find more detailed information about these files on vgmstream github.
[https://github.com/vgmstream/vgmstream/ ... meta/kwb.c](https://github.com/vgmstream/vgmstream/blob/master/src/meta/kwb.c)

In few games, if you change the extension of the .bin file to .wbd and .wbh, you can play it immediately on foobar2000.
However, in most cases wbd and wbh files are merged(?) into a .bin file.

I mean, you can find both _HBW0000 and _DBW0000 in one .bin file.




First of all, find all the files that header is _HBW0000 
In my experience, there are SE files in the middle of "unknown folder", and voice files at the end part.


Now just remove the first 16 digits from the .bin file and split _HBW0000 part and _DBW0000 part.

Here's how to do it manually.

1. download vgmtoolbox
[https://sourceforge.net/projects/vgmtoolbox/](https://sourceforge.net/projects/vgmtoolbox/)

Run vgmtoolbox and drag and drop the files you want to cut.


2. remove the first 16 digits 

(There is no problem in skipping this step.)

There are two ways, and the result is the same.

Byte Remover - automatically given extension of .cut.




Simple Cutter - You must enter the extension of file.



Result




3. split the _HBW0000 part and the _DBW0000 part.

.wbh files.




.wbd file.




result




In some games, sound files are located in LINKDATA\misc\formats\WBH path.
For Toukiden 2, .wbh file contains 421 pairs of wbh and wbd files.



Even in this case, wbh and wbd files can be obtained in the same way as above.

If made good use of this method, there is no need for an each quickbms script for each different kt's game using .wbh and .wbd files.
The games : DQH, WO3, DW8, Deception IV and Warriors All Stars, etc.

Even relatively new games using the ktsl2asbin and ktss formats can be extracted without programming knowledge thanks to vgmtream's update.

This is why I explain how to extract manually, instead of providing a quickbms script.

Thanks to the efforts of many people, we can get the sound of most KT games with only Cethleann tools, vgmtoolbox and foobar2000 with vgmstream plugin.
## Post #11
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2023-08-27T17:45:31+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

Thank you for detailed guidance,when I put LINKDATA.BIN in D:\sy,and try cmd:Cethleann.DataExporter.exe --linkdata  D:\sy "D:\sy",It shows:
[Cethleann] Cethleann.DataExporter v1.0.0.0
[Cethleann] Arguments: ["--linkdata","D:\\sy","D:\\sy"]
[FileList] Loading filelist for LINKDATAPatterns-link
[FileList] Loading filelist for unknown-link

without any files out.
Do you know how to deal with this?
## Post #12
- Username: halo1573
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue May 31, 2022 2:41 pm
- Post datetime: 2023-08-27T21:09:48+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

LINKDATA.BIN and LINKDATA.IDX must be in the same folder.
## Post #13
- Username: 15221281395
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Mar 20, 2022 4:30 pm
- Post datetime: 2023-08-28T11:12:03+00:00
- Post Title: Dragon Quest Heroes II - Sound format *.vap

> Reply from halo1573 ↑Sun Aug 27, 2023 8:45 am at Sun Aug 27, 2023 8:45 am
>
> 

Okay, I have found what I want. They are in continuous .wbd files, and this vgm tool is indeed easy to use and efficient. Perhaps in future footbar with vgmstream will be faster.I used to need to remove some WEMs from bnK to play, but later he was able to directly recognize bnK.Thank you for your help. I would write down your tutorial set for linkdata.
