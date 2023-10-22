## Post #1
- Username: Nix56
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 03, 2017 7:39 am
- Post datetime: 2019-01-13T00:03:16+00:00
- Post Title: Ridge Racer 6 .DAT file

Hey im trying to extract the Soldat Crinale model files, ive been trying to open RRM.DAT. RRM2.DAT, and RRM3.DAT but yet still no luck can anyone please help me out?
## Post #2
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-01-08T03:35:57+00:00
- Post Title: Ridge Racer 6 .DAT file

Is there anyone here to extract model out of MDL sample from RR6 pls?

Sample link: 
https://mega.nz/file/YToxQLoD#EI2rYvKcu ... iOMS221mZg
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-09T19:25:23+00:00
- Post Title: Ridge Racer 6 .DAT file

Well, there's a list of addresses/counts before the tri strips block which hex2obj doesn't support.
So I had to create H2O files manually using the list values. Used 13 entries only (out of 69).

Strangely the created partial model looks worse than the auto created one.

(Though the later used the full amount of vertices that shouldn't be...)
Maybe I miscalculated addresses of submeshes? (since I added offsets 12 times, vertex count*FVFsize, the first fault would inherit  )
.



RR6-Mdl.png (197.3 KiB) Viewed 273 times
## Post #4
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-09T20:45:34+00:00
- Post Title: Ridge Racer 6 .DAT file

> Reply from shakotay2 ↑Tue Jan 10, 2023 3:25 am at Tue Jan 10, 2023 3:25 am
>
> ...Maybe I miscalculated addresses of submeshes?...
Hey shakotay2, i hope you didn't spent too much of your time on this as its already reversed entirely i believe by the following dev.
[https://github.com/Nenkai/RRUnpacker](https://github.com/Nenkai/RRUnpacker)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-09T20:58:13+00:00
- Post Title: Ridge Racer 6 .DAT file

> Reply from mono24 ↑Tue Jan 10, 2023 4:45 am at Tue Jan 10, 2023 4:45 am
>
> Hey shakotay2, i hope you didn't spent too much of your time on thisHey mono24, no, not really.  (Plus I had to do it anyway to get an idea of the list.)

> as its already reversed entirely i believe by the following dev.
>
> https://github.com/Nenkai/RRUnpackerWell, I thought it was an unpacker for .dat files only. (Since I don't have any .dat files, only MDL files, I could never check it, though.)
## Post #6
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-01-09T21:21:37+00:00
- Post Title: Ridge Racer 6 .DAT file

> Reply from shakotay2 ↑Tue Jan 10, 2023 4:58 am at Tue Jan 10, 2023 4:58 am
>
> ...Well, I thought it was an unpacker for .dat files only. (Since I don't have any .dat files, only MDL files, I could never check it, though.)
Ah, ok, it is only an unpacker, and I wasn't sure what type of assets you had 
I guess only thing missing is the MDL conversion support.
## Post #7
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-01-12T05:17:45+00:00
- Post Title: Ridge Racer 6 .DAT file

> Reply from mono24 ↑Tue Jan 10, 2023 5:21 am at Tue Jan 10, 2023 5:21 am
>
> 
shakotay2 wrote: ↑Tue Jan 10, 2023 4:58 am...Well, I thought it was an unpacker for .dat files only. (Since I don't have any .dat files, only MDL files, I could never check it, though.)
Ah, ok, it is only an unpacker, and I wasn't sure what type of assets you had 
I guess only thing missing is the MDL conversion support.

Interesting thing is, there's an unfinished Blender addon plugin for both RR6 and RR7 mdl. but for RR6 MDL, it gave me an error after I import it into blender which is in the screenshot

Link for blender plugin:[https://github.com/GreenTrafficLight/Ri ... nder-Addon](https://github.com/GreenTrafficLight/Ridge-Racer-Blender-Addon)
[Screenshot 2023-01-12 111603.png](https://xentaxbackup.github.io/file/23287_Screenshot 2023-01-12 111603.png)
## Post #8
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-23T14:49:03+00:00
- Post Title: Ridge Racer 6 .DAT file

sample file for Ridge Racer 6 tex file for texture extract. I believe that this file could contain xbox360 swizzled dds.

EDIT: @Durik256, any luck on that?

[https://mega.nz/file/leZxWTzA#Kwujb7Yc5 ... e8xDenHlzI](https://mega.nz/file/leZxWTzA#Kwujb7Yc5QhY1rR619QC-drkH1u_Y4oqZe8xDenHlzI)
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2023-07-25T00:36:11+00:00
- Post Title: Ridge Racer 6 .DAT file

been awhile since I did a noesis script, and I never finished my 360 unswizzler so someone would need to do up a noesis script.

header is 16 bytes for the container (RPT) followed by int32 for count, following int32 addresses per count for each R6T file.
the r6t contains the format count and two ints for width and length, I don't have noesis around to write anything.

below is a format break down in a binary template for the Hex editor, 010 Editor

```
{% raw %}
//--- 010 Editor v13.0.2 Binary Template
//
//      File: Ridge Racer 6, RPT Parser (Xbox360)
//   Authors: mariokart64n
//   Version: 1.0
//   Purpose: Research / Education
//  Category: Texture File
// File Mask: *.rpt
//  ID Bytes: 
//   History: 
//   1.0   2023-07-24 initial version
//------------------------------------------------


struct fmtR6T {
    LittleEndian();
    uint32 type;
    uint32 unk4;
    uint16 unk5;
    uint16 unk6;
    uint32 unk7;
    BigEndian();
    uint32 unk8;
    uchar unk9;
    uchar unk10;
    uchar unk11;
    uchar img_fmt <format=hex>;
    uint32 width;
    uint32 height;
    uint32 unk12;
    uint32 unk13;
    uint32 unk14;
    uint32 unk15;
    local float bbp = 4;
    switch (img_fmt) {
		case 0x52: {bbp = 4; break;} // "DXT1"
		case 0x53: {bbp = 8; break;} // "DXT3"
		case 0x54: {bbp = 8; break;} // "DXT5"
		case 0x71: {bbp = 8; break;} // "DXN"
		case 0x7C: {bbp = 8; break;} // "CTX1"
		case 0x86: {bbp = 32; break;} // "A8R8G8B8"
        default: {Printf("Unknown Image Format {%d}\n", img_fmt);}
        }
    char data[(uint)(width * height * (8.0 / bbp))];
    };

struct fmtRPT {
    uint32 type;
    uint32 unk1;
    uint32 unk2;
    uint32 unk3;
    local int pos = FTell();
    uint32 r6t_count;
    uint32 r6t_addrs[r6t_count];
    local int i = 0;
    for (i = 0; i < r6t_count; i++) {
        FSeek(pos + r6t_addrs[i]);
        fmtR6T tex;
        }
    };

// Initialize File Structure
BigEndian();
fmtRPT rpt;
{% endraw %}
```
## Post #10
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-28T12:20:33+00:00
- Post Title: Ridge Racer 6 .DAT file

sample file if anyone is interested in model import noesis plugin

[https://mega.nz/file/sK4zSa4K#zxSLFsGSK ... 8Ot0M6nb3g](https://mega.nz/file/sK4zSa4K#zxSLFsGSKmokWIn612oH6ERRUqqYtnlUR8Ot0M6nb3g)
## Post #11
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-10-13T10:43:00+00:00
- Post Title: Ridge Racer 6 .DAT file

wanna bump this topic with more sample: [https://mega.nz/file/RCpGCJCa#QrD6sTIgp ... o6sXpgY1Ik](https://mega.nz/file/RCpGCJCa#QrD6sTIgpbUMFdU10GBzx_gl5wRbvPNJSo6sXpgY1Ik)

EDIT: with model and texture samples
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-13T11:40:46+00:00
- Post Title: Ridge Racer 6 .DAT file

> Reply from UB833 ↑Fri Jul 28, 2023 8:20 pm at Fri Jul 28, 2023 8:20 pm
>
> 
sample file if anyone is interested in model import noesis pluginWhy should anyone waste his time when the blender plugin works?
.



RidgeRacer.jpg (85.29 KiB) Viewed 108 times
## Post #13
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-10-13T11:51:28+00:00
- Post Title: Ridge Racer 6 .DAT file

> Reply from shakotay2 ↑Fri Oct 13, 2023 7:40 pm at Fri Oct 13, 2023 7:40 pm
>
> 
UB833 wrote: ↑Fri Jul 28, 2023 8:20 pm
sample file if anyone is interested in model import noesis pluginWhy should anyone waste his time when the blender plugin works?
.
RidgeRacer.jpg

because for me it didn't work because I have the error in blender that I have already posted above.

EDIT: I'm so sorry if I made you annoying but I only have this error in blender 3.6.1
## Post #14
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-10-13T12:00:17+00:00
- Post Title: Ridge Racer 6 .DAT file

anyways sorry now that it worked btw. and I think the texture part was already solved long ago in zenhax.com but the script were in this site, were not archived and I didn't backed it up
## Post #15
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-10-13T15:51:34+00:00
- Post Title: Ridge Racer 6 .DAT file

alright, I finally got the archived post for Ridge Racer 6 texture file which has quickbms code and noesis code by h3x3r so nvm about the textures.

you can check it out if you want: [https://web.archive.org/web/20230429100 ... =9&t=17847](https://web.archive.org/web/20230429100351/https://zenhax.com/viewtopic.php?f=9&t=17847)
