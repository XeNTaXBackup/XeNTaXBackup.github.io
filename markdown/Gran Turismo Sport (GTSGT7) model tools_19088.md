## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-11-20T08:57:34+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

Gran Turismo GTS/GT7 model tools

Current version extracts static models and textures. Skeletal models also supported, but will be exported static. Car wheels and some other parts will be not in correct positions. This may be corrected with future adding their skeletons and weights. You can convert maps (tracks/courses) with this tool, after you extract the track from PACK file with GTS_Pack tool.

IMPORTANT NOTE. The tool extracts the highest LOD of game data. Many car parts are using tesselation. These meshes are marked with "_T" in their name. Thats why they look like they are low detail. But actually those are highest quality meshes. This tech was also used in GT6.

You can read about what is tesselation here:
[https://www.gtplanet.net/forum/threads/ ... st.307532/](https://www.gtplanet.net/forum/threads/tessellation-car-list.307532/)

Usage: drop model file onto the tool.

OBJ & ASCII files will be created. ASCII will have all UV layers.











Maps output:

GTS_PACK is the tool to unpack PACK files, which contain tracks.
It will hopefully unpack ANY pack from GTS, not just tracks.
Thats how it works:
Any pack contains a few sections
usually 2: SYS and VRAM
naturally its data loaded into system and video memory
these sections have names
after unpacking, you will see all of them in subfolder
then you must know that the usual model files are combined data for SYS and VRAM
so to make it work, you have to MERGE 2 parts of the PACK into one
for example
you have world.sys & world.vram
merge them (sys first) and then model tool will convert it

You can merge files via any tool you have for it, or windows command.
For example: copy /b WORLD.SYS + WORLD.VRAM WORLD
[gts_gt7_tools.7z](https://xentaxbackup.github.io/file/22482_gts_gt7_tools.7z)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-01T11:59:48+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

The new version of model tool that fixes lots of problems is uploaded.

Changes:
- all UV types supported
- texture pack extraction support (drop texture file onto the tool)
- PACK unpacker added (GTS_Pack) to unpack tracks
- ASCII files split in 100MB parts
## Post #3
- Username: streetracer23
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Sep 28, 2014 8:51 pm
- Post datetime: 2018-12-01T15:26:23+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from daemon1
>
> The new version of model tool that fixes lots of problems is uploaded.
I will describe it later.
Plase write detailed instructions step by step
## Post #4
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-12-01T20:13:32+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

is it possible to extract files from a *.pkg game archive? or how exactly we can find the models to convert them with your tools?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-01T21:01:39+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

i cant post gttool here, its posted there: 
[https://zenhax.com/viewtopic.php?f=5&t=8916](https://zenhax.com/viewtopic.php?f=5&t=8916)
## Post #6
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-12-03T16:20:41+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

how can i import ascii files? with which software?
## Post #7
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-12-03T16:38:31+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from Gta5KoRn
>
> how can i import ascii files? with which software?
Both Noesis and Blender can import it.
Blender just needs the XPS XNALara plugin/script, and for Noesis you can get it here, or in most posts or tools by ID-Daemon [viewtopic.php?p=140154#p140154](http://forum.xentax.com/viewtopic.php?p=140154#p140154)
## Post #8
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-12-06T12:56:24+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

Very nice daemon1 ! 

Now we need the same for Driveclub. ; P
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-06T15:58:39+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from zaykho
>
> Very nice daemon1 ! 

Now we need the same for Driveclub. ; P
i know, but i'm working on GT6 now
## Post #10
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-12-07T13:42:04+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from daemon1
>
> 
i know, but i'm working on GT6 now

No problem, I would be happy to have a tool for GT6 too ! ; D
## Post #11
- Username: solidpoke412
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 15, 2018 9:37 am
- Post datetime: 2018-12-10T13:43:00+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from Gta5KoRn
>
> is it possible to extract files from a *.pkg game archive? or how exactly we can find the models to convert them with your tools?

I've attached the car list and track list... all the versions of the tools so far... and some info to help 1st timers...

after running GT TOOL to decrypt/extract the GT??.VOL files (the files that are inside the .PKG usually, except when running or unpacked via the FW5.05FakePKGtools on PC)

cars are found in "CAR" 
use the BRAND code / CAR code list to identify easily between the up-to 205 cars...
the files you want to use GTS MDL with are :
HQ/BODY or HQ/WHEEL for cars parts... 
RACE/BODY or RACE/WHEEL
but each car has an "INTERIOR" too, which also with give you textures and 3D...
and most of the files you get have MULTIPLE LODs which you'll appreciate are much easier to identify since sub-meshes with tessellation are now marked with "_T"
textures get extracted in .DDS (DXT10) convert to .BMP for eg... (can't link the tool yet)
(if you want to from there, i like to use ImBatch to .TGA > .PNG with a Vertical Flip)
regardless there is some work to do assigning textures for now but texture coordinates are there afaik... 


tracks are in "CRS" likewise use the list provided for reference...
info on merging / unPACKing etc in the attachment too

fonts are in "FONT/PS4/FONTS/ LATIN, LETS, MORISAWA, NUM, SST... in .OTF (OpenType) or .TTF (TrueType) (both seem to work on w10 for eg)

also all the MUSEUM images are normal .JPG
1920x1270 (400 DPI 24 bit sRGB) (they used PhotoShop CS3 apparently for some)
1919x1280 (300 DPI 24 bit) (DxO Optics Pro 6.5.1 build 8012)
1287x1280 (1200 DPI 24 bit sRGB) (PhotoShop CS6 - Win)
etc etc...

and
CARPARTS/HQ for more Wheels it seems use GTS MDL

GRANDTOP/SCAPES has .JXR files you view / convert to .TIF 1 at a time using a free photoshop plugin...
can then use techniques mentioned above to convert to .PNG or other without brightness problem... afaik...

2/3 .MP4 videos in "MOVIE" work in VLC (one of them is diff in v1.00 compared to v1.14)

also the files in "CHARACTER" mostly work with the MDL tool too...for eg... 
BG060 > BG060.obj & BG060.ascii pop out, along with the folder of textures (.DDS DXT10)
HM037 for example is a HELMET  and .TXS files too from LIVERY/DECAL/TXS etc

and there are .PNG files in LIVERY/LIVERY_SET/?? 304 diff folders... 1 in each...
[GTS easy.rar](https://xentaxbackup.github.io/file/15303_GTS easy.rar)
## Post #12
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2018-12-10T15:17:45+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from solidpoke412
>
> Gta5KoRn wrote:is it possible to extract files from a *.pkg game archive? or how exactly we can find the models to convert them with your tools?

I've attached the car list and track list... all the versions of the tools so far... and some info to help 1st timers...

after running GT TOOL to decrypt/extract the GT??.VOL files (the files that are inside the .PKG usually, except when running or unpacked via the FW5.05FakePKGtools on PC)

cars are found in "CAR" 
use the BRAND code / CAR code list to identify easily between the up-to 205 cars...
the files you want to use GTS MDL with are :
HQ/BODY or HQ/WHEEL for cars parts... 
RACE/BODY or RACE/WHEEL
but each car has an "INTERIOR" too, which also with give you textures and 3D...
and most of the files you get have MULTIPLE LODs which you'll appreciate are much easier to identify since sub-meshes with tessellation are now marked with "_T"
textures get extracted in .DDS (DXT10) convert to .BMP for eg... (can't link the tool yet)
(if you want to from there, i like to use ImBatch to .TGA > .PNG with a Vertical Flip)
regardless there is some work to do assigning textures for now but texture coordinates are there afaik... 


tracks are in "CRS" likewise use the list provided for reference...
info on merging / unPACKing etc in the attachment too

fonts are in "FONT/PS4/FONTS/ LATIN, LETS, MORISAWA, NUM, SST... in .OTF (OpenType) or .TTF (TrueType) (both seem to work on w10 for eg)

also all the MUSEUM images are normal .JPG
1920x1270 (400 DPI 24 bit sRGB) (they used PhotoShop CS3 apparently for some)
1919x1280 (300 DPI 24 bit) (DxO Optics Pro 6.5.1 build 8012)
1287x1280 (1200 DPI 24 bit sRGB) (PhotoShop CS6 - Win)
etc etc...

and
CARPARTS/HQ for more Wheels it seems use GTS MDL

GRANDTOP/SCAPES has .JXR files you view / convert to .TIF 1 at a time using a free photoshop plugin...
can then use techniques mentioned above to convert to .PNG or other without brightness problem... afaik...

2/3 .MP4 videos in "MOVIE" work in VLC (one of them is diff in v1.00 compared to v1.14)

also the files in "CHARACTER" mostly work with the MDL tool too...for eg... 
BG060 > BG060.obj & BG060.ascii pop out, along with the folder of textures (.DDS DXT10)
HM037 for example is a HELMET  and .TXS files too from LIVERY/DECAL/TXS etc

and there are .PNG files in LIVERY/LIVERY_SET/?? 304 diff folders... 1 in each...

...something's wrong with attached file, it is corrupted...
## Post #13
- Username: solidpoke412
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 15, 2018 9:37 am
- Post datetime: 2018-12-10T15:21:51+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from rex1825
>
>  ...something's wrong with attached file, it is corrupted...

seems ok with WINRAR 5.50... i had to make a smaller .rar then i expected at first... 
here are all the tool versions that i omitted earlier... because 256kb/1 attachment only is quite annoying...
GT TOOL is 1MB and hasn't changed since ID-DAEMON first compiled it afaik...
so use his link [https://zenhax.com/viewtopic.php?f=5&t=8916](https://zenhax.com/viewtopic.php?f=5&t=8916)
[___GTS MoDeL TOOL - ALL VERSIONS - get GT TOOL elsewhere.rar](https://xentaxbackup.github.io/file/15304____GTS MoDeL TOOL - ALL VERSIONS - get GT TOOL elsewhere.rar)
## Post #14
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2018-12-10T15:25:34+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

> Reply from solidpoke412
>
> rex1825 wrote: ...something's wrong with attached file, it is corrupted...

seems ok with WINRAR 5.50

...lol me, using old WinRar 4.xx
## Post #15
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2018-12-10T15:44:06+00:00
- Post Title: Gran Turismo Sport (GTS/GT7) model tools

Wondering if updated files 1.31 from PS4 PKG Viewer can be used for model extraction?
## Post #16
- Username: solidpoke412
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 15, 2018 9:37 am
- Post datetime: 2018-12-10T15:46:14+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from rex1825
>
> solidpoke412 wrote:rex1825 wrote: ...something's wrong with attached file, it is corrupted...

seems ok with WINRAR 5.50

...lol me, using old WinRar 4.xx



 GT TOOL 64 BIT WIN noGUI - FLATZ.7z
Compiled by ID-DAEMONusage eg inside... (232.43 KiB) Downloaded 216 times
## Post #17
- Username: solidpoke412
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 15, 2018 9:37 am
- Post datetime: 2018-12-10T15:52:18+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from streetracer23
>
> daemon1 wrote:The new version of model tool that fixes lots of problems is uploaded.
I will describe it later.
Please write detailed instructions step by step

let me know how you go, and what you might want more info on...
## Post #18
- Username: solidpoke412
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 15, 2018 9:37 am
- Post datetime: 2018-12-10T16:05:33+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from rex1825
>
> Wondering if updated files 1.31 from PS4 PKG Viewer can be used for model extraction?
[https://sites.google.com/site/theleeche ... ects=0&d=1](https://sites.google.com/site/theleecherman/ps4pkgviewer/PS4PKGViewer.v1.5-LMAN.rar?attredirects=0&d=1)

or have a look for "Fake_PKG_Tools_v1.5.1.rar" instead...
orbis-pub-chk.exe comes with that... i won't post that here though...
password for Fake Signed .PKG = all zeros...
00000000000000000000000000000000

good F*cking luck if you're looking for GT SPORT v1.15 - 1.31 + Content...
having v1.00 -> v1.14 is already nice enough... i mean 205 cars already ffs...
v1.15 of GT:S requires FW 5.50 ? to decrypt it, and no PS4 kernel exploit afaik above FW5.05 is public yet...
## Post #19
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2018-12-10T19:14:45+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from solidpoke412
>
> rex1825 wrote:Wondering if updated files 1.31 from PS4 PKG Viewer can be used for model extraction?
https://sites.google.com/site/theleeche ... ects=0&d=1

or have a look for "Fake_PKG_Tools_v1.5.1.rar" instead...
orbis-pub-chk.exe comes with that... i won't post that here though...
password for Fake Signed .PKG = all zeros...
00000000000000000000000000000000

good F*cking luck if you're looking for GT SPORT v1.15 - 1.31 + Content...
having v1.00 -> v1.14 is already nice enough... i mean 205 cars already ffs...
v1.15 of GT:S requires FW 5.50 ? to decrypt it, and no PS4 kernel exploit afaik above FW5.05 is public yet...

PS4 PKG Viewer cannot open it... so that's it...
## Post #20
- Username: xzelao
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Dec 11, 2018 8:49 pm
- Post datetime: 2018-12-11T12:54:02+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

daemon1, thank you for the incredible work you are doing! So many years hoping to see this happen 

Can someone please send an invitation the GT research discord?
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-12-11T15:45:49+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from rex1825
>
> PS4 PKG Viewer cannot open it... so that's it...
PS4 PKG Viewer CAN open decrypted versions of packages.
It will never open official PKG downloaded from sony servers
## Post #22
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2018-12-11T23:56:32+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from solidpoke412
>
> ...
good F*cking luck if you're looking for GT SPORT v1.15 - 1.31 + Content...
having v1.00 -> v1.14 is already nice enough... i mean 205 cars already ffs...
v1.15 of GT:S requires FW 5.50 ? to decrypt it, and no PS4 kernel exploit afaik above FW5.05 is public yet...

...just so you know, FW 6.x.x is close to be exploited, so, we'll probably have access to new patches too...
## Post #23
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2018-12-12T04:57:16+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from rex1825
>
> 
...just so you know, FW 6.x.x is close to be exploited, so, we'll probably have access to new patches too...

Oh boy ! I hope you are right !
## Post #24
- Username: Flandyn
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Oct 12, 2015 9:06 pm
- Post datetime: 2018-12-16T14:05:32+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

I don't know where else to ask this, so i'll ask it here.

I used to be a member of the GT discord, but it is not appearing in my server list anymore (I noticed this today).
Why is this? Was the server deleted? Was I banned? (if so, why?) If somebody could help me out here, I would be very thankful.
## Post #25
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2019-01-05T16:43:58+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from Flandyn
>
> I don't know where else to ask this, so i'll ask it here.

I used to be a member of the GT discord, but it is not appearing in my server list anymore (I noticed this today).
Why is this? Was the server deleted? Was I banned? (if so, why?) If somebody could help me out here, I would be very thankful.
u can find Gran Turismo Sport models here [https://www.facebook.com/media/set/?set ... tn__=-UC-R](https://www.facebook.com/media/set/?set=a.1958720130870416&type=3&__xts__%5B0%5D=68.ARC8lRKTWTeHNNtX8IG3_YpyoWQZo3q2HJIuhxfx7jl4V9weTMcRL7gGIeOYUQMSWimk8YG7H5CnC3wjBD86Cc4xuo1uulpSCmWWOlBIDgtd9MBT1VCOrbg2ww2el2bQa0ELj4URywVEVqRL85K2-DEzomVgJ7MlxZXOSAAXsn1yYT-ZL3_smncqGT5fw4r1VKmpHMJ4WZLJNBD4TnS6FmQViieTXjjyD4mVa0fY7NGIaNrbReH9inf0s6Ak1CQuO3l4wLCdXf8OhNwJdwesy8xT-tYB-iVBJ--6px8o6NbdFDZRuPbuab8y6JdG2el_5uCZI7-NpW_XDxwDn0-aTq9HJOaYMJAWRmRrTKlEtbP4aRSOwMT0cGMa9ewAJppWGnh34WrdEwM1fFGswj86b3ee1G8QShYLABiKj4Roiit7i_itSmjBmw8AMFeSv16enTxM7NntlG3zNsE&__tn__=-UC-R)
## Post #26
- Username: nicotine41
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 23, 2019 4:00 am
- Post datetime: 2019-07-03T17:54:00+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

i extracted "EP9001-CUSA02168 00-GTSPORT000000000-A0113-V0100.pkg" with Fake_PKG_Generator_3.38, now i have "gtui.vol" and "gtun.vol" files but how can i extract them.
## Post #27
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-03T21:48:43+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from nicotine41 ↑Thu Jul 04, 2019 1:54 am at Thu Jul 04, 2019 1:54 am
>
> ...but how can i extract them.
[https://forum.xentax.com/viewtopic.php?p=146331#p146331](https://forum.xentax.com/viewtopic.php?p=146331#p146331)
## Post #28
- Username: nicotine41
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 23, 2019 4:00 am
- Post datetime: 2019-07-03T23:30:36+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from mono24 ↑Thu Jul 04, 2019 5:48 am at Thu Jul 04, 2019 5:48 am
>
> 
nicotine41 wrote: ↑Thu Jul 04, 2019 1:54 am...but how can i extract them.
https://forum.xentax.com/viewtopic.php?p=146331#p146331

Thank you for answer. i did instructions on that page but i get this error "unable to load volume". do u know how to fix this.
## Post #29
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-07-04T00:40:25+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from nicotine41 ↑Thu Jul 04, 2019 7:30 am at Thu Jul 04, 2019 7:30 am
>
> ...i get this error "unable to load volume". do u know how to fix this.
Double check again, trace your steps, your using the command wrong somehow.
[https://zenhax.com/viewtopic.php?p=4088 ... c34#p40884](https://zenhax.com/viewtopic.php?p=40884&sid=deaf224e90e29dd57c2b3d22169dac34#p40884)
## Post #30
- Username: nicotine41
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jun 23, 2019 4:00 am
- Post datetime: 2019-07-04T00:58:38+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from mono24 ↑Thu Jul 04, 2019 8:40 am at Thu Jul 04, 2019 8:40 am
>
> 
nicotine41 wrote: ↑Thu Jul 04, 2019 7:30 am...i get this error "unable to load volume". do u know how to fix this.

Double check again, trace your steps, your using the command wrong somehow.
https://zenhax.com/viewtopic.php?p=4088 ... c34#p40884

sorry, i forgot to write, i realised that im working with patch files, not main game files   

thanks so much for the link.
## Post #31
- Username: morimotoyoshi86
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 11, 2019 4:28 am
- Post datetime: 2019-10-09T08:02:08+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Has anyone been able to extract the models from 1.15 onwards? Looking for the McLaren P1 GTR model.
Thanks.
## Post #32
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-10T00:27:54+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from morimotoyoshi86 ↑Wed Oct 09, 2019 4:02 pm at Wed Oct 09, 2019 4:02 pm
>
> Has anyone been able to extract the models from 1.15 onwards
Anything beyond 1.14 is impossible for now, as many times has been stated on so many forum boards and such, for now the PS4 exploit is kept private, no one has anything public yet, maybe in the future.
## Post #33
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2019-10-15T14:51:14+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from mono24 ↑Thu Oct 10, 2019 8:27 am at Thu Oct 10, 2019 8:27 am
>
> 
morimotoyoshi86 wrote: ↑Wed Oct 09, 2019 4:02 pmHas anyone been able to extract the models from 1.15 onwards
Anything beyond 1.14 is impossible for now, as many times has been stated on so many forum boards and such, for now the PS4 exploit is kept private, no one has anything public yet, maybe in the future.

What makes it impossible?
## Post #34
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-15T15:29:53+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from markerfede ↑Tue Oct 15, 2019 10:51 pm at Tue Oct 15, 2019 10:51 pm
>
> What makes it impossible?



answer.jpg (70.72 KiB) Viewed 583 times


BUT, if you are an amazing hacker you can do it yourself and not wait on anyone else, that's the ONLY way for now, so hack the PS4 find a new exploit and come back and share with us the results so WE as well can gain access to latest updates
## Post #35
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2019-10-16T02:52:08+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from mono24 ↑Tue Oct 15, 2019 11:29 pm at Tue Oct 15, 2019 11:29 pm
>
> 
markerfede wrote: ↑Tue Oct 15, 2019 10:51 pmWhat makes it impossible?
answer.jpg
BUT, if you are an amazing hacker you can do it yourself and not wait on anyone else, that's the ONLY way for now, so hack the PS4 find a new exploit and come back and share with us the results so WE as well can gain access to latest updates

I managed to get the PKG files from the latest GT Sport from the last 1.46 update. I'm still fiddling with it but I'll share my results once I come across something!
## Post #36
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-16T04:20:34+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from markerfede ↑Wed Oct 16, 2019 10:52 am at Wed Oct 16, 2019 10:52 am
>
> I managed to get the PKG files from the latest GT Sport from the last 1.46 update. I'm still fiddling with it but I'll share my results once I come across something!
Not to burst your bubble or anything like that, but, every single one of us who is interested in the game, can literally download the official updates straight from Sony servers, unfortunately you'll hit a very heavy, thick wall, they have a unique decryption key that is 100% impossible to gain access to even to this day by most talented hackers, only the faaar future will tell what will come out of that, until then you are stuck just like all of us.
The ONLY people that can gain access to it is those who have the private exploit from the hackers community, that's it.
## Post #37
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2019-10-23T23:21:28+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Gentlemen! I have already unpacked the game.In which files will I find textures of better quality and how to extract them ? BIG THANKS ! BUT FROM Gran Turismo 6 !
## Post #38
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2020-01-27T16:35:35+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

New version added. This new GTS_mdl_q.exe has additional features:
- fixes for crashes with some maps
- SMD skeleton output
- tesselation meshes output in quads (in OBJ file only!):





p.s. these quads are not proper quads, just an attemps to build them from actual tesselation info, so may not work correct for all meshes
## Post #39
- Username: Pupsik
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Oct 18, 2017 3:18 am
- Post datetime: 2020-04-26T07:29:55+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hi guys!
Has anyone been able to extract these two models from the GTS?

1953 Aston Martin DB3S CN.1
[https://www.igcd.net/vehicle.php?id=173807&l=ru](https://www.igcd.net/vehicle.php?id=173807&l=ru)


1967 Ford Mark IV
[https://www.igcd.net/vehicle.php?id=160424](https://www.igcd.net/vehicle.php?id=160424)  (He is in GT6 but he has problems with UVW mapping, lost coordinates...)
## Post #40
- Username: Khoes
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 24, 2020 3:30 am
- Post datetime: 2020-12-23T21:11:46+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Any idea from where i can get the GT Sport EU version .pkg file? I would like to export Dragon Trail Circuit to play it in AC and i would like to know if you can share the link to download that EU version. ID - CUSA02168_00 the only thing that i found that makes a reference to the EU Version. Thank you everyone for creating this forum thread!
## Post #41
- Username: Cauri
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 04, 2021 6:20 pm
- Post datetime: 2021-02-07T20:00:55+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hello there. I did everything in the right way somehow. Now i have all the cars and tracks models in my pc.
Is there any chance to have an explanation of the steps i have to do in blender?
The models are a mess, there are meshes that have to be delete i guess, and i don't know what to do. I feel like i'm so close to get what i want but i can't go further.

There are already some car mods from GT sport for AC and they are so beautifull, and an awsome version of the tsukuba circuit. 

Any help is very appreciated, so we can have more content for AC.

Thanks.
## Post #42
- Username: Aud
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 28, 2020 3:31 pm
- Post datetime: 2021-02-13T18:05:23+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Seconded, the import works but dealing with the meshes and what to delete and where and how to use textures and materials is incredibly non-obvious, any help with this is greatly appreciated
## Post #43
- Username: ruzhyo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 17, 2021 10:54 am
- Post datetime: 2021-02-17T03:55:29+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Is it possible to repack the extracted files to send to the PS4 to play a modded GTSport?
## Post #44
- Username: andrewcowboy87
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 21, 2021 9:13 pm
- Post datetime: 2021-06-23T07:35:49+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hi How can I export the 3d models of gran turismo 6?
## Post #45
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2021-06-23T10:03:16+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from andrewcowboy87 ↑Wed Jun 23, 2021 3:35 pm at Wed Jun 23, 2021 3:35 pm
>
> 
Hi How can I export the 3d models of gran turismo 6?
[viewtopic.php?f=16&t=19919](https://forum.xentax.com/viewtopic.php?f=16&t=19919)
## Post #46
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2021-06-30T21:53:29+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

...so, can someone explain to me process of extracting tracks? Would like to get my hands on Tokyo tracks layout, not sure if above 1.14 is possible... thanks
## Post #47
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-07-01T20:29:19+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from rex1825 ↑Thu Jul 01, 2021 5:53 am at Thu Jul 01, 2021 5:53 am
>
> 
...so, can someone explain to me process of extracting tracks?...
[viewtopic.php?p=146036#p146036](https://forum.xentax.com/viewtopic.php?p=146036#p146036)
Maps output, that's where its explained, you call them tracks, same thing.
## Post #48
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2021-07-01T22:02:48+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

...does this tool work on any version of the game? Or is it strictly made for 1.00 and 1.14?

Thanks

Edit: ...managed to open 1.61 version of game, just to ask another question, does anyone know what exact track/car brand is under what folder code? I know for some tracks (once that were opened up until 1.14)... Thanks...
## Post #49
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2021-07-02T15:51:41+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Here is full list of tracks, every single one can be opened in 3DS Max. 


GTS tracks.PNG (28.54 KiB) Viewed 952 times
## Post #50
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2021-07-02T18:15:40+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

And cars... Didn't open all, but they do work... 


cars.PNG (14.18 KiB) Viewed 935 times
## Post #51
- Username: rex1825
- Rank: advanced
- Number of posts: 69
- Joined date: Thu Aug 14, 2014 2:48 am
- Post datetime: 2021-07-06T16:33:01+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Here is complete car list that can be extracted, missing only new Yaris GR and new 86 GT...
After car name is 8 digit code, this is reference for all to easily find car, 4+4 digits, meaning first for is main folder of same car brand, second 4 is car specifically.

Cheers
[GT Car List.PNG](https://xentaxbackup.github.io/file/20424_GT Car List.PNG)
## Post #52
- Username: AkioZeT30
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 22, 2021 6:48 am
- Post datetime: 2021-08-21T08:33:05+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Does anyone have a list of wheel names for GTS with their code (for example, HE002)?
## Post #53
- Username: ErM1999
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 26, 2019 5:36 am
- Post datetime: 2021-10-10T10:07:01+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

has anyone here ever tried to extract the Scapes Backgrounds / HDR files? As far I know they are under Scapes and Grandtop. However, it seems that I can't unpack the .JXR files correctly as they seem to be corrupt. Photoshop and any online converter always return an error when opening these files
## Post #54
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2022-01-22T21:04:54+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Anyone been able to rip engine sounds from this game?
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-05-14T15:56:47+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

This tool will also work with GT7 models, except probably the new separate high-quality textures.
So I'm surprised, i dont even have to change the thread name.
## Post #56
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-05-15T14:59:38+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

I checked a few cars. I think this one Jaguar Vision GT is new to GT7:
## Post #57
- Username: Squiff
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 15, 2022 12:38 pm
- Post datetime: 2022-05-18T16:34:51+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

So can we make requests of GT7 models here?
## Post #58
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-05-18T18:39:09+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from Squiff ↑Thu May 19, 2022 12:34 am at Thu May 19, 2022 12:34 am
>
> 
So can we make requests of GT7 models here?
No, this forum is for reverse engineering, technical stuff, NOT for models requests or any other game content requests/posts and as such, etc.
A lot of users are under the impression that is allowed, well, it is NOT. Simply put this is not like a warez forum.
## Post #59
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2022-06-11T16:23:11+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hi,
Where we can download the GT7 .pkg files cars?
## Post #60
- Username: toab776
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 11, 2019 8:05 am
- Post datetime: 2022-06-17T17:57:49+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Where can i get the gt sport sound files?
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-13T19:08:27+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Tool updated. Full GT7 support.

GT7 cars have .sepdat files with separate geometry/texture data. It's now supported.
## Post #62
- Username: djibsone2
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Dec 21, 2016 10:15 am
- Post datetime: 2022-07-14T14:16:19+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

hi do you know how to recover the ASTON MARTIN DB3S CN1 models THANK YOU
## Post #63
- Username: ErM1999
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 26, 2019 5:36 am
- Post datetime: 2022-07-15T19:35:39+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

I'm genuinely curious. How did you figure out what files are .sepdat and what not? I was able able to figure out a pattern for the car files but I have no clue about the additional files to be honest.
The tool is working perfectly but just as assumed the .sepdat are required for cars with tuning parts or else they won't be fully converted.
## Post #64
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-15T19:43:26+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from ErM1999 ↑Sat Jul 16, 2022 3:35 am at Sat Jul 16, 2022 3:35 am
>
> 
I'm genuinely curious. How did you figure out what files are .sepdat and what not? I was able able to figure out a pattern for the car files but I have no clue about the additional files to be honest.
The tool is working perfectly but just as assumed the .sepdat are required for cars with tuning parts or else they won't be fully converted.
there's info inside each model, that indicates if there must be a .sepdat file
and in this case the tool informs that .sepdat is missing
## Post #65
- Username: ErM1999
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 26, 2019 5:36 am
- Post datetime: 2022-07-18T15:28:25+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

can you give a hint on how to find the corresponding sepdat file for a car mesh? I got everything sorted out but the last puzzle to find out which sepdat belongs to what car is missing. I can't find anything useful in the file itself or I'm just lacking knowledge for that. I fear I need to find it out via playing the game with debug tools but that's not possible for the moment.
If I can get that working I wouldn't mind posting a decoded car list here with all corresponding files for each car
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-18T16:30:44+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from ErM1999 ↑Mon Jul 18, 2022 11:28 pm at Mon Jul 18, 2022 11:28 pm
>
> 
can you give a hint on how to find the corresponding sepdat file for a car mesh? I got everything sorted out but the last puzzle to find out which sepdat belongs to what car is missing. I can't find anything useful in the file itself or I'm just lacking knowledge for that. I fear I need to find it out via playing the game with debug tools but that's not possible for the moment.
If I can get that working I wouldn't mind posting a decoded car list here with all corresponding files for each car
Each car file and each sepdat file has its name. Use names during export, or use gttoolsharp that exports files with names.
## Post #67
- Username: ErM1999
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 26, 2019 5:36 am
- Post datetime: 2022-07-18T18:05:31+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

ah god damn I used the outdated unpacker then. Thank you very much
## Post #68
- Username: an90dy905909
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 30, 2018 3:02 am
- Post datetime: 2022-07-22T13:16:52+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hy guys, have trouble exporting .vol files from gran turismo 7... I have tried extract it with GttoolsSharp but have no luck.
The version of gt7 is 1.0 from Fake pkg US.

Is there other tool except GTTOOLSSHARP?  The code i am using in CMD is GTToolsSharp.exe gt7unpack -i gt.idx -o (output folder)?

Thanks for help...!
## Post #69
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-07-22T18:50:54+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from an90dy905909 ↑Fri Jul 22, 2022 9:16 pm at Fri Jul 22, 2022 9:16 pm
>
> ...Is there other tool except GTTOOLSSHARP?  The code i am using in CMD is GTToolsSharp.exe gt7unpack -i gt.idx -o (output folder)?
That is the right tool too use for extraction, and based on your example you forgot to specify the path for the .idx and you didn't leave "(output folder)" like that, did you? You replace that with your actual output folder on your HDD.

Example:

```
GTToolsSharp gt7unpack -i X:\YOUR\VOL\FILES\gt.idx -o Y:\YOUR\OUTPUT\FOLDER
```

Now replace those paths with your actual folders and HDD letters.
## Post #70
- Username: an90dy905909
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 30, 2018 3:02 am
- Post datetime: 2022-07-22T20:21:58+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Sorry again, actually i did put the right code,i just wrote the code for example, but i did put the output folder and gt.idx location, i forgot to mention
that extraction starts it process but after a minute of extraction stops and asking for Overwrite Bruteforced GT7 file list,
and no matter what i put yes or no it stops for some reason?

Thanks again!



Image link:
[https://www.photobox.co.uk/my/photo/ful ... 4779987443](https://www.photobox.co.uk/my/photo/full?photo_id=504779987443)
## Post #71
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-07-22T22:58:33+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from an90dy905909 ↑Sat Jul 23, 2022 4:21 am at Sat Jul 23, 2022 4:21 am
>
> ...no matter what i put yes or no it stops for some reason?...
No clue what that link was supposed to be, yet no picture is shown, anyway, if you type letter "y" and hit enter on keyboard the actual extraction of the assets will happen, do not actually write "yes", first thing the process does is checking the list of names, then tries to bruteforce more paths, then it tries to save it, hence the overwriting yes/no question.
## Post #72
- Username: an90dy905909
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 30, 2018 3:02 am
- Post datetime: 2022-07-23T12:22:06+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Sorry for bothering you again, actually i did tried with letters y and n, i didn't put yes or no what you thought...
And then process stops no matter i write y or n and hit enter...

Sorry for link with image, i tried to share screenshot of CMD prompt what actually happening...

Maybe this link will work better (google drive link with image)

Thanks!

link:
[https://drive.google.com/file/d/1U-yW96 ... sp=sharing](https://drive.google.com/file/d/1U-yW96HVfqL6JgrJbOnMVQl1jBtJk3wg/view?usp=sharing)
## Post #73
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-23T12:35:52+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from an90dy905909 ↑Sat Jul 23, 2022 8:22 pm at Sat Jul 23, 2022 8:22 pm
>
> 
Sorry for link with image, i tried to share screenshot of CMD prompt what actually happening...
this is zstd error. Wrong tool version, it will not work. Use latest version.
## Post #74
- Username: an90dy905909
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 30, 2018 3:02 am
- Post datetime: 2022-07-24T00:31:41+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

ah, that's it, i didn't see actually that it has new version...
Now it works...

Thanks a lot! 

And if i may i would ask just one more question about this .sepdat file, is this file can be converted somehow or it is connected with
for  example "body" file (i mean it serves only for converting "body file" to obj format, or?)

Thanks.
## Post #75
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2022-07-24T05:51:50+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from an90dy905909 ↑Sun Jul 24, 2022 8:31 am at Sun Jul 24, 2022 8:31 am
>
> 
it is connected with
for  example "body" file
yes
## Post #76
- Username: 2222222
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 15, 2022 4:30 pm
- Post datetime: 2022-07-25T10:17:58+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

[/quote]
GTS_PACK is the tool to unpack PACK files, which contain tracks.
It will hopefully unpack ANY pack from GTS, not just tracks.
Thats how it works:
Any pack contains a few sections
usually 2: SYS and VRAM
naturally its data loaded into system and video memory
these sections have names
after unpacking, you will see all of them in subfolder
then you must know that the usual model files are combined data for SYS and VRAM
so to make it work, you have to MERGE 2 parts of the PACK into one
for example
you have world.sys & world.vram
merge them (sys first) and then model tool will convert it

You can merge files via any tool you have for it, or windows command.
For example: copy /b WORLD.SYS + WORLD.VRAM WORLD
[/quote]

could you explain this more i cant seem to get it working
## Post #77
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-07-25T19:18:00+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from 2222222 ↑Mon Jul 25, 2022 6:17 pm at Mon Jul 25, 2022 6:17 pm
>
> could you explain this more i cant seem to get it working
First, fix the quote it is confusing a bit.

What the dev means is that you drag/drop the "pack" asset on to the "GTS_pack.exe" tool to unpack it, example of a pack is "\crs\c024\pack", you will get a folder with it's extracted assets at root of "c024" called "pack_unp"
inside that "pack_unp" folder you will see multiple files, example is main course files of "c024"

```
world.vram
```

you merge those two as per instructions already mentioned by the dev, that is in a text file you write the following:

```
copy /b WORLD.SYS + WORLD.VRAM WORLD
```

rename the extension TXT to BAT and then run it like any other executable by double clicking on it, that means it will concatenate those two files, SYS will be first then VRAM will be next in line
you can even add what ever name you like so you will not get confused like "world_merged" or "world_merged.mdl"
that means

```
copy /b WORLD.SYS + WORLD.VRAM world_merged
```

or

```
copy /b WORLD.SYS + WORLD.VRAM world_merged.mdl
```

your choice 
once you have that concatenated file created at root of your unpacked assets like those SYS/VRAM files, you use it like any other model file to get the ASCIIs and its textures

have fun
## Post #78
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2022-08-01T18:10:35+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Guys, please check. I'm doing everything right? For example, this model does not have some openings on the front bumper and there is no opening for the fuel tank. Do you also?
[mclarenF1.jpg](https://xentaxbackup.github.io/file/22583_mclarenF1.jpg)
## Post #79
- Username: Sushi015
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 24, 2020 10:33 am
- Post datetime: 2022-08-02T15:56:04+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from MichaelBFS ↑Tue Aug 02, 2022 2:10 am at Tue Aug 02, 2022 2:10 am
>
> 
Guys, please check. I'm doing everything right? For example, this model does not have some openings on the front bumper and there is no opening for the fuel tank. Do you also?

Its all correct my man, u have to boolean it
## Post #80
- Username: AkioZeT30
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Feb 22, 2021 6:48 am
- Post datetime: 2022-08-04T23:07:06+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from MichaelBFS ↑Tue Aug 02, 2022 2:10 am at Tue Aug 02, 2022 2:10 am
>
> 
Guys, please check. I'm doing everything right? For example, this model does not have some openings on the front bumper and there is no opening for the fuel tank. Do you also?

just boolean it
## Post #81
- Username: markerfede
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Oct 15, 2019 9:19 pm
- Post datetime: 2022-08-25T20:28:07+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Has anyone been able to get the files from later updates of the game and able to successfully remarry updates to them?
## Post #82
- Username: avwrtn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 16, 2022 10:26 pm
- Post datetime: 2022-10-06T01:01:51+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hey everyone, can anybody explain these errors for me?

```
A fatal error occurred. The required library hostfxr.dll could not be found.
```


and if I give GTToolsSharp the dll from the dotnet folder it tells me:

```
The library hostfxr.dll was found, but loading it from (filepath) failed.
```


If I use the previous version I get the ZStdDCtx error like another user posted a few months ago.

Since getting the errors, I've even installed Windows fresh and the same errors persist...

Thanks.
## Post #83
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-10-06T19:44:59+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from avwrtn ↑Thu Oct 06, 2022 9:01 am at Thu Oct 06, 2022 9:01 am
>
> 
Hey everyone, can anybody explain these errors for me?...
Install the required NET specified in the GitHub repo and you should be good to go.
## Post #84
- Username: Eggplantegg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 13, 2022 1:07 pm
- Post datetime: 2022-10-13T05:28:42+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hi, where can I find car paint and interior colour information? I suspect this information come from livery file (however I don't have the livery files), there are also METER and INFO file inside the car folder and what are these files used for and how can I extract them? thanks.
## Post #85
- Username: avwrtn
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 16, 2022 10:26 pm
- Post datetime: 2022-10-30T02:53:41+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from mono24 ↑Fri Oct 07, 2022 3:44 am at Fri Oct 07, 2022 3:44 am
>
> 
avwrtn wrote: ↑Thu Oct 06, 2022 9:01 am
Hey everyone, can anybody explain these errors for me?...
Install the required NET specified in the GitHub repo and you should be good to go.

My bad, I should have specificed I've done that already, it doesn't seem to work at all no matter on the .NET I have installed. And that's also both before I reinstalled windows and after incase that means anything.

I also just tried the newest 5.2.0, same result.
## Post #86
- Username: beastmode123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 22, 2022 9:17 am
- Post datetime: 2022-11-22T01:20:31+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Is there any easy way to figure out what lods i dont need ?
## Post #87
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-11-22T01:51:26+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from beastmode123 ↑Tue Nov 22, 2022 9:20 am at Tue Nov 22, 2022 9:20 am
>
> 
Is there any easy way to figure out what lods i dont need ?
Read the red note: [viewtopic.php?p=146036#p146036](https://forum.xentax.com/viewtopic.php?p=146036#p146036)
## Post #88
- Username: sarize
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 18, 2023 10:46 pm
- Post datetime: 2023-02-18T14:52:07+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

I tried to unpack gt many times but failed, Has anyone been able to extract porsche vision gran tursimo successfully?

[https://gran-turismo.fandom.com/wiki/Po ... an_Turismo](https://gran-turismo.fandom.com/wiki/Porsche_Vision_Gran_Turismo)
## Post #89
- Username: babayaga
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 20, 2023 2:58 pm
- Post datetime: 2023-03-20T07:00:27+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Guys is it posible to extract the brand logos, track logos, car masks from gt7.
## Post #90
- Username: FungusBingus69
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 30, 2023 9:47 pm
- Post datetime: 2023-05-02T09:21:01+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Is it work exporting tyre models? I did some and don't see any tyres, just calipers and brakes.
## Post #91
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-05-02T20:08:28+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from FungusBingus69 ↑Tue May 02, 2023 5:21 pm at Tue May 02, 2023 5:21 pm
>
> 
Is it work exporting tyre models? I did some and don't see any tyres, just calipers and brakes.
Nope, the game has none in the format you'd expect as actual geometry, its a different format for tires from what i can remember.
## Post #92
- Username: FungusBingus69
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Apr 30, 2023 9:47 pm
- Post datetime: 2023-05-22T13:30:02+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

One quick question. I have extracted the GT7 pkg files but i cannot locate where the scapes are located. I tried finding grandtop but there are no such files and the scape file only has a txt file. Am i missing something?
## Post #93
- Username: JoshMod
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 05, 2021 4:24 pm
- Post datetime: 2023-06-28T19:57:01+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

Hey everyone, i asked before on zenhax so i thought id ask here, are we going to see support for newer gt7 updates anytime soon? Or does anyone know what it would take to extract the new updates?
## Post #94
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-28T21:10:14+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from JoshMod ↑Thu Jun 29, 2023 3:57 am at Thu Jun 29, 2023 3:57 am
>
> ...Or does anyone know what it would take to extract the new updates?
Since the game devs changed encryption, after script/tool release was made, and even flatz himself archived his own script for decryption on github, it means no one will touch the game publicly until the game will no longer be updated and game devs move on to another game, my best bet.
## Post #95
- Username: JoshMod
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 05, 2021 4:24 pm
- Post datetime: 2023-06-28T21:59:55+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from mono24 ↑Thu Jun 29, 2023 5:10 am at Thu Jun 29, 2023 5:10 am
>
> 
JoshMod wrote: ↑Thu Jun 29, 2023 3:57 am...Or does anyone know what it would take to extract the new updates?

Since the game devs changed encryption, after script/tool release was made, and even flatz himself archived his own script for decryption on github, it means no one will touch the game publicly until the game will no longer be updated and game devs move on to another game, my best bet.

I personally don't know coding or anything but, if i really wanted to extract the models i'm assuming i would have to pay someone to make it compatible to be able to extract it. I have a friend who says hes willing to even pay someone to make it, we are just kind of desperate at this point. GT7 has alot of cars we need, for example the new evo that just released. I've been working with a modeler for the past year trying to make a good evo 3 model and what would you know PD drops this update.
## Post #96
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-30T10:49:22+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from JoshMod ↑Thu Jun 29, 2023 5:59 am at Thu Jun 29, 2023 5:59 am
>
> 
I personally don't know coding or anything but, if i really wanted to extract the models i'm assuming i would have to...
No, you are wrong. This will not help here.
## Post #97
- Username: JoshMod
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Aug 05, 2021 4:24 pm
- Post datetime: 2023-06-30T14:14:51+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from daemon1 ↑Fri Jun 30, 2023 6:49 pm at Fri Jun 30, 2023 6:49 pm
>
> 
JoshMod wrote: ↑Thu Jun 29, 2023 5:59 am
I personally don't know coding or anything but, if i really wanted to extract the models i'm assuming i would have to...

No, you are wrong. This will not help here.

So there's nothing i can do, other than cry about it and wait?
## Post #98
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-06-30T18:36:17+00:00
- Post Title: Re: Gran Turismo Sport (GTS/GT7) model tools

> Reply from JoshMod ↑Fri Jun 30, 2023 10:14 pm at Fri Jun 30, 2023 10:14 pm
>
> So there's nothing i can do, other than cry about it and wait?
In time, things will change, one way or another, patience.
