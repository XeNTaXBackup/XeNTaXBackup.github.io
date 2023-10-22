## Post #1
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-03-11T13:57:05+00:00
- Post Title: Street Supremacy - BUILD.DAT and BUILD.TOC

Hello, i require help to extract and open files inside of BUILD.DAT file from the game Street Supremacy. I will provide 3 files, which is 2 pieces of BUILD.DAT, and BUILD.TOC . [EDIT : BUILD.DAT was cut into 2 MB pieces. Original is 372 MB]
If you require the full BUILD.DAT, please reply to this topic.

BUILD.DAT 1st piece - [https://www.dropbox.com/s/99v2u053ujm67 ... DAT.0?dl=0](https://www.dropbox.com/s/99v2u053ujm67gh/BUILD.DAT.0?dl=0)
BUILD.DAT 2nd piece - [https://www.dropbox.com/s/dx125oqze9dr5 ... DAT.1?dl=0](https://www.dropbox.com/s/dx125oqze9dr5lp/BUILD.DAT.1?dl=0)
BUILD.TOC - [https://www.dropbox.com/s/qy996to8j1hvr ... D.TOC?dl=0](https://www.dropbox.com/s/qy996to8j1hvrwr/BUILD.TOC?dl=0)

So what i'm trying to do here, is to get map models of the whole Shutokou Expressway (Tokyo Highway) from this game. There's a japanese guy who managed to get the models and converted it to GTA SA, but he didn't put it for download.
[https://www.youtube.com/watch?v=yO5khGzpsbQ](https://www.youtube.com/watch?v=yO5khGzpsbQ) <--- Video of the map

It's a pain in the a to rip the map from the game via PPSSPP emulator, since using Ninja Ripper, all roads and objects positions are reset to x 0 y 0 and z 0. For 3DRipperDX, all was ripped fine, but the models are rotated according to camera position, and that made things even harder.

I really need help of someone willingly to open that BUILD.DAT file and figure out a way to import the map to 3d editors like 3DS Max, Maya, Cinema 4D, or ZModeler 2. Or else, i'll be stuck ripping pieces of the map and rearrange them all with seemingly unimaginable amount of low-res texture which is hard to apply.

P.S: I can't use hex2obj. I tried to learn it, but my brain failed. This is why i need someone to help me on this. Thanks in advance.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-11T20:37:58+00:00
- Post Title: Street Supremacy - BUILD.DAT and BUILD.TOC

you' ll need to know the method of encryption for Genki games.

(I tried the first 147 algos from quickbms using a comtype_scan at no avail.)

> Reply from REDZOEU
>
> For 3DRipperDX, all was ripped fine, but the models are rotated according to camera position, and that made things even harder.
Could you show a picture, please? (Guess, the angles are different, depending on the models' distance to the camera?)
## Post #3
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-03-13T10:01:54+00:00
- Post Title: Street Supremacy - BUILD.DAT and BUILD.TOC

> Reply from shakotay2
>
> 
Could you show a picture, please? (Guess, the angles are different, depending on the models' distance to the camera?)


Firstly, i apologize for the image size.

From the picture, you can see the 1st rip result had the car facing forward, the map is the same. But in the 2nd picture, the car is still the same direction, but the map has been rotated (due to chase camera). Not to mention when map elevation changes, it'll be a pain to rip each part and combine them all. Rip 1 and Rip 2 is just few meters away from each other though.

In short, yes. Distance of the camera and models matters.
About the encryption... Someone made a bms script for the PS2 version of this game (different map and gameplay, but same file, but probably different structure)

[http://aluigi.altervista.org/papers/bms ... rift_2.bms](http://aluigi.altervista.org/papers/bms/others/tokyo_xtreme_racer_drift_2.bms) <--- Link to the BMS script
[http://aluigi.altervista.org/papers/bms ... r_zero.bms](http://aluigi.altervista.org/papers/bms/others/tokyo_xtreme_racer_zero.bms) <--- bms script for the same looking game with same map, but ps2 version

Well, just hoping these might help the process of trying to extract the files from this psp ver though :\
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-13T13:11:23+00:00
- Post Title: Street Supremacy - BUILD.DAT and BUILD.TOC

> Reply from REDZOEU
>
> Rip 1 and Rip 2 is just few meters away from each other though.thany you for the pictures!

Sure the rips are showing the same segment of the road? For me it doesn't seem so.

Anyway, my thought was to scale and rotate a ripped map.
Scaling factor to be obtained from measuring the same object on two rips.

Did you try to scale and rotate the 2nd rip in your 3D program so that it might look like rip1?
-------
For the bms script - this is a log from a first try on the toc file:

 Files dum dum dat_size: 9031 8912397 8895504 8887996

 0 48784 24 0 176768 --- compressed?
 ZSIZE=48784?, SIZE=176768?

 24 1348 1 0 0
 25 1152 1 0 0
 26 401456 197 0 864368 --- compressed?
 223 21581 11 0 81440 --- compressed?
 234 220158 108 0 1218656
 342 235041 115 0 1218656
 457 237902 117 0 1218656
 574 240382 118 0 1218656
 692 227424 112 0 1218656
 804 228574 112 0 1218656
 916 244934 120 0 1218656
 1036 235558 116 0 1218656
 1152 254260 125 0 1218656
 1277 239268 117 0 1218656
 1394 231002 113 0 1218656
 1507 243888 120 0 1218656
 1627 241332 118 0 1218656
 1745 239060 117 0 1218656
 1862 242273 119 0 1218656
 1981 239741 118 0 1218656
 2099 232489 114 0 1218656
 2213 227029 111 0 1218656
 2324 229594 113 0 1218656
 2437 231648 114 0 1218656
 2551 262781 129 0 1218656
 2680 393397 193 0 805776 --- compressed?
 2873 20619 11 0 59424 --- compressed?
 2884 312335 153 0 1160864
 3037 329039 161 0 1160864
 3198 333470 163 0 1160864

As can be seen seems we're missing the starting offsets of the files' data.
Just checking a multiplier of 0x800...

well, check this line: 2680 393397 193 0 805776
393397 fits in 193 x2048, so 193 (x 0x800) might give the relative offset.

From this theory there should be an uncompressed file at 0xBE90, and yes, at 0xC000, there is:
OMG.00.1PSP
## Post #5
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2015-03-13T13:29:31+00:00
- Post Title: Street Supremacy - BUILD.DAT and BUILD.TOC

Well, i haven't tried rotating the 2nd rip, since i've yet to finish converting the 1st rip to gta. Even if i succeed on the 1st rip, the 2nd rip will take some time to be rotated and properly scaled so that it can connect to the 1st rip. And since Tokyo Expressway is huge (more like it's the whole tokyo), ripping pieces like this will take me approximately more than 6 months.

It's hard to do this, i know. That's why i'm searching for help to easen up the job. For the script, i expected that it needed the starting offsets. Due to my lack of hex codes knowledge, i guess i might need to look for a professional to try and help.
I guess i'll just leave it like this for now.
Or maybe when i'm good fiddling with hex codes... :\
