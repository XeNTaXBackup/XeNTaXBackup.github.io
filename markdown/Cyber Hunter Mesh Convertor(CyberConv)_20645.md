## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-11T15:28:35+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

Another tool for skin testing purpose of my binary FBX builder, which was intended to convert Cyber Hunter mesh files to FBX format with skeleton, skin info and material groups. With the tool being updated to v1.2.0, now it supports a couple more games, technically any NeoX mesh format of NetEase, skinned or static ones.

Usage:
Double click on the executable and follow the leads, or use batch commands.

Supported Games:
Cyber Hunter (Tested on v0.100.143)
Onmyoji (Tested on v1.0.41)
RULES OF SURVIVAL (Tested on v1.281908.285092)
Crusaders of Light (Tested on v6.0.4)
BuildTopia (Tested on v2.1.10)
Creative Destruction (Tested on v2.0.1801)
Galactic Frontline (Tested on v1.0.109350)
MARVEL Super War (Unreleased) (Tested on v1.6.0)
Onmyoji Arena (Tested on v3.64.0)

Examples from above Games:
Cyber Hunter


Onmyoji


RULES OF SURVIVAL


Crusaders of Light


BuildTopia


Creative Destruction


Galactic Frontline


MARVEL Super War (Unreleased)


Onmyoji Arena





 CyberConv.zip
v1.2.0 (34.29 KiB) Downloaded 913 times



A BMS script for unpacking npk archives from Cyber Hunter, and one for unpacking unencrypted npk files containing nameless assets with extension filtering (of mesh, ktx, and png only) are also attached. For npk files contain encrypted assets (like Onmyoji Arena and MARVEL Super War), use [this script](https://forum.xentax.com/viewtopic.php?p=154556#p154556).
## Post #2
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-06-12T03:17:06+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

This tool is great. Can you support other Netease games, such as Onmyoji Arena
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-16T07:35:41+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from lkw019 ↑Wed Jun 12, 2019 11:17 am at Wed Jun 12, 2019 11:17 am
>
> 
This tool is great. Can you support other Netease games, such as Onmyoji Arena

Now the tool supports many other games. As for Onmyoji Arena, whose npk files are encrypted, unless someday the xor key is found, there's not much I can do.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-16T07:41:19+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

Tool updated to v1.2.0. 

Changes:
Maximum compatibility of NetEase's mesh format, supporting both static and skinned meshes.

Probably this will be the last version of this tool.
## Post #5
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-06-20T02:32:08+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

The tools is worked... But I can't open KTX file using PVRTexTool.
How you get the texture like the picture above (black suit on character)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-20T02:38:41+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from alictzelt ↑Thu Jun 20, 2019 10:32 am at Thu Jun 20, 2019 10:32 am
>
> 
But I can't open KTX file using PVRTexTool.
Upgrade your PVRTexTool.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-07-07T14:22:47+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

Tested on another two games.

MARVEL Super War (Unreleased)


Onmyoji Arena



Edit: 
Get the npk decryptor for these two games [here](https://forum.xentax.com/viewtopic.php?f=16&t=20783#p154557).

Here's a BMS script to handle the decrypted npk files.
[npkUnpackerExtFilter.zip](https://xentaxbackup.github.io/file/17365_npkUnpackerExtFilter.zip)
## Post #8
- Username: duyhaicx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 09, 2017 7:02 am
- Post datetime: 2019-08-09T06:25:41+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

Thank you. This article is very useful.
I am trying to import the Onmyoji Arena 3d model files into Blender.
I am having a problem using CyberConv.exe.
After I drag and drop the * .mesh file into the window, it immediately turns off and nothing happens.
How can I import a * .mesh file into Blender.
Sorry for English not my native language.
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-09T07:19:01+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from duyhaicx ↑Fri Aug 09, 2019 2:25 pm at Fri Aug 09, 2019 2:25 pm
>
> 
I am having a problem using CyberConv.exe.
After I drag and drop the * .mesh file into the window, it immediately turns off and nothing happens.
Drag and drop the files onto the tool itself, not the command line window popped up by double-clicking the exe.

> Reply from duyhaicx ↑Fri Aug 09, 2019 2:25 pm at Fri Aug 09, 2019 2:25 pm
>
> 
How can I import a * .mesh file into Blender.
You can't. CyberConv will generate an FBX file along the input if execution succeed. But as far as I know, Blender doesn't support FBX skeleton properly.
## Post #10
- Username: duyhaicx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 09, 2017 7:02 am
- Post datetime: 2019-08-09T12:11:29+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

Sorry, can you give me detailed instructions?
When I drag and drop 00000005.mesh to CyberConv nothing happens. ( Like this picture)

Sorry this is my first time using 3D applications
## Post #11
- Username: duyhaicx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 09, 2017 7:02 am
- Post datetime: 2019-08-09T12:36:29+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

Oh I figured out the cause. The problem is in the name of the folder where my files contain special characters.
Thank you for everything
## Post #12
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-08-10T00:42:32+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

Hey mate, great toolset. I'm loving the addition of Marvel: Super War. I've run into a snag using your "npkUnpackerExtFilter.bms" script. After using "EXPKDec.exe" with the downloaded "xorKey.bin", I've used "npkUnpackerExtFilter.bms" on both "hero.npk" and "scene.npk". At about 100 - 120 files extracted, your script throws an error, which I have a screenshot of...



I've updated my Quickbms, moved files to different directories and I'm still getting this error. Hope you can help me out as I'd love to add these models to my collection.

Cheers again, for the awesome tools.
Ecelon
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-10T01:24:29+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Ecelon ↑Sat Aug 10, 2019 8:42 am at Sat Aug 10, 2019 8:42 am
>
> I've used "npkUnpackerExtFilter.bms" on both "hero.npk" and "scene.npk". At about 100 - 120 files extracted, your script throws an error
You were using the wrong script. Use the one posted [there](https://forum.xentax.com/viewtopic.php?p=154556#p154556).
## Post #14
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-08-10T01:33:20+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Sat Aug 10, 2019 9:24 am at Sat Aug 10, 2019 9:24 am
>
> 
You were using the wrong script. Use the one posted there.

Thanks for the quick response. Sorry to say mate, but I'm still receiving the same error. I even tried the other 2 that came with CyberConv for good measure.

I've uploaded both hero.npk and scene.npk to my Google Drive, so you can check em out if it helps.
[https://drive.google.com/open?id=1HI-WA ... L3m892OoIq](https://drive.google.com/open?id=1HI-WA2NTi_Wav6U_InDSUdL3m892OoIq)
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-08-10T03:44:19+00:00
- Post Title: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Ecelon ↑Sat Aug 10, 2019 9:33 am at Sat Aug 10, 2019 9:33 am
>
> so you can check em out if it helps.
I see. It's caused by the decryptor which didn't update the entries when they're unencrypted. Redownloading the decryptor should work.
## Post #16
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-08-11T00:01:59+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Sat Aug 10, 2019 11:44 am at Sat Aug 10, 2019 11:44 am
>
> 
I see. It's caused by the decryptor which didn't update the entries when they're unencrypted. Redownloading the decryptor should work.

Thanks so much mate, that got it working perfectly. Really impressed by the unreleased characters in this game lol.
## Post #17
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-08-11T21:36:49+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Thank you! It works fine for Marvel Super War
## Post #18
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2019-09-02T22:58:17+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hi,

This tool is awesome. However I ran into an issue, when tried to unpack
Creative Destruction npk.
It doesn't matter which bms script I tried, none of them worked.
Aluigi's nxpk script is working, but gave me 18k nameless file, and it is really hard to get what i need.
Ccould you please take a look?

Thank you!
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-03T04:06:23+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Vindis ↑Tue Sep 03, 2019 6:58 am at Tue Sep 03, 2019 6:58 am
>
> However I ran into an issue, when tried to unpack
Creative Destruction npk.
It doesn't matter which bms script I tried, none of them worked.
Coz the data is encrypted.
Here's aluigi's srcipt with extra code for extension filtering. Should handle all cases other than Cyber Hunter.
[nxpk_modified.zip](https://xentaxbackup.github.io/file/16686_nxpk_modified.zip)
## Post #20
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-12T10:55:57+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Is there a way to solve the naming problem in Netease games? Often no corresponding map can be found.
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-09-12T11:30:45+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from lkw019 ↑Thu Sep 12, 2019 6:55 pm at Thu Sep 12, 2019 6:55 pm
>
> 
Is there a way to solve the naming problem in Netease games? Often no corresponding map can be found.
Use the script posted above for any games other than Cyber Hunter, MARVEL Super War and Onmyoji Arena. If they output without proper names, then they don't have any.
## Post #22
- Username: vtrbh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Sep 28, 2019 8:35 pm
- Post datetime: 2019-09-30T03:10:31+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Thank you so much for the tool, can you somehow convert those animations to make them able to use in fbx?
## Post #23
- Username: vimdarbump
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 10, 2019 11:02 pm
- Post datetime: 2019-10-10T15:04:22+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

how i can import .gis animations ?
i need open tpose.gis
## Post #24
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-12-19T10:02:04+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hello Bigchillghost, thank you for allthe awesome tools you made, I tried to extract models from Marvel Super War of today update, but I have the following error when using tool on a high model npk file:
I used NetEase NPK (EXPK) Archive Decryptor, then quickBMS on the decrypted npk with npkUnpackerExtFilter:

Did I do something wrong or npk are now different ?

Samples as of Sea release :
High models :
[https://www.mediafire.com/file/7y6yg98c ... gh.7z/file](https://www.mediafire.com/file/7y6yg98c84v0n51/sample_Release_SEA_hero_high.7z/file)
Low models :
[https://www.mediafire.com/file/iur6j0wk ... ro.7z/file](https://www.mediafire.com/file/iur6j0wk1l3vp7p/hero.7z/file)

Have a nice Christmas and New Year btw everyone
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-19T13:48:07+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from huitbgoiouythy ↑Thu Dec 19, 2019 6:02 pm at Thu Dec 19, 2019 6:02 pm
>
> 
I used NetEase NPK (EXPK) Archive Decryptor, then quickBMS on the decrypted npk with npkUnpackerExtFilter:
...
Did I do something wrong or npk are now different ?
According to the error message you were using the correct script so you did everything correct.  

> Reply from huitbgoiouythy ↑Thu Dec 19, 2019 6:02 pm at Thu Dec 19, 2019 6:02 pm
>
> 
High models :
Did these files come from the obb package or you downloaded them in game? According to the info table in these files they seem to be using another compression algorithm. I'll test it later.

> Reply from huitbgoiouythy ↑Thu Dec 19, 2019 6:02 pm at Thu Dec 19, 2019 6:02 pm
>
> 
Low models :
For this npk file it's a field in the header that makes it bypass the decryption on the data. Just change the byte at offset 8 as below:



modification.jpg (221.65 KiB) Viewed 724 times



That should do the trick for now.
## Post #26
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2019-12-19T14:22:47+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

EDIT with updated hero low.npk : Very sorry, I've just noticed that I have several obb file in Marvel Super War and I think I uploaded an hero low/npk from a previous update(the high asset I uploaded are for sure from latest update) I opened this time the latest obb I have with the following 08 value :03 this time :
[https://www.mediafire.com/file/ksxhok7j ... ad.7z/file](https://www.mediafire.com/file/ksxhok7jusylxmr/hero_latest_my_bad.7z/file)

Thank you Bigchillghost!, the byte 08 trick worked perfectly for the hero.npk (after decryption and using same bms script) for low model   

The High model npk comes from downloaded asset via the game, they have an option to download high quality asset that gives 3 new file for higher hero, scene and sounds file.
## Post #27
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-19T15:46:00+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from huitbgoiouythy ↑Thu Dec 19, 2019 10:22 pm at Thu Dec 19, 2019 10:22 pm
>
> 
I've just noticed that I have several obb file in Marvel Super War and I think I uploaded an hero low/npk from a previous update(the high asset I uploaded are for sure from latest update) I opened this time the latest obb I have with the following 08 value :03 this time :
That explains everything. They changed the encryption key, though it's still using zlib compression. Guess this method is blocked for now untill the new key is found.
## Post #28
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-20T06:02:57+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Thu Dec 19, 2019 11:46 pm at Thu Dec 19, 2019 11:46 pm
>
> They changed the encryption key, though it's still using zlib compression.
Well the compression is one of the oodle algorithms actually. And the first 255 bytes of the key are:

```
8E 91 72 39 E2 86 8A CF 72 4B EF 58 9A 86 C0 
AD 0B CA A2 EC 4C 6C 1A A2 4F 97 84 F2 1D EB 
FA 54 8D 62 2A 4D 69 B5 E4 F0 FC 84 36 B2 31 
A5 80 3B D2 03 B6 90 71 CF B2 4C 63 C0 E9 7B 
53 B3 F3 54 FE 31 E5 9E 21 A3 78 41 C7 9C D0 
EA D2 D5 F0 F5 D6 4D AC 5A 9B BC 06 BB 10 F2 
1B 93 2C 88 60 82 D2 E8 31 EA D2 17 6D EB 9F 
23 F9 7F A9 76 A2 5D B3 DD C6 29 52 8F 47 19 
22 B8 20 61 BB E5 9D 83 E1 79 4E E5 31 2E 6F 
F1 93 99 08 9A 42 0D FA 10 8B 4B 57 7E 20 CC 
24 A3 4D 18 60 E2 68 2D 20 16 E5 FC B2 1D 6F 
DB AE 3A DE C2 C9 F6 1F DA 82 05 9B A9 F7 A1 
41 88 EB EE BF B6 8C 45 04 D1 AD CD A8 C6 D3 
1A BB 0A 95 62 BE 10 A7 32 C7 15 BD BB 31 A2 
D7 1C EB 3E B6 88 2C 21 EF EF C1 39 D8 C3 BE 
61 37 FD C8 18 AE 11 93 36 F6 22 BA 81 83 48 
```


Here's the binary version of it:


 newKey.zip
Binary Key (incomplete) (414 Bytes) Downloaded 79 times
## Post #29
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2019-12-25T22:39:05+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

The zip is empty?
## Post #30
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-26T03:49:40+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from riccochet ↑Thu Dec 26, 2019 6:39 am at Thu Dec 26, 2019 6:39 am
>
> 
The zip is empty?
Oops... Seems that I zipped the file when it's been opened by an hex editor.
## Post #31
- Username: lamjed001
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 29, 2019 3:52 am
- Post datetime: 2019-12-26T23:16:27+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

How can I find the correct texture of this mesh object?
## Post #32
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2020-01-15T06:44:30+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Greetings Bigchillghost.
First of all I would like to thank you for your tools.

Currently, your CyberConv converts models as a single mesh, even if it uses more than 1 material.
Is it possible to convert models to FBX with separated meshes by materials?

Also could you update your npkUnpackerExtFilter.bms script?
For example, when I use it to unpack decripted hero.npk (Marvel Super War\main.8.com.netease.g104na.gb.obb), 
I get 20 unpacked model files and an error like this:

> Error: incomplete input file -1:
>
>        Can't read 1776922 bytes from offset 00000000000f8e0e.
>
>        Anyway don't worry, it's possible that the BMS script has been written
>
>        to exit in this way if it's reached the end of the archive so check it
>
>        or contact its author or verify that all the files have been extracted.
>
>        Please check the following coverage information to know if it's ok.
>
> 
>
>   coverage file -1  100%   1019410    1019406    . offset 00000000000f8e0e
>
> 
>
> Last script line before the error or that produced the error:
>
>   106 log OutName 0 Size MEMORY_FILE
However, when I use zhouhang95's neox_tools ([https://github.com/zhouhang95/neox_tools](https://github.com/zhouhang95/neox_tools)),
I get 68 unpacked model files and no errors.

Thanks.
## Post #33
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-15T08:41:01+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from RedBear ↑Wed Jan 15, 2020 2:44 pm at Wed Jan 15, 2020 2:44 pm
>
> 
Currently, your CyberConv converts models as a single mesh, even if it uses more than 1 material.
Is it possible to convert models to FBX with separated meshes by materials?
The models are single-meshes as they were in the first place. CyberConv merely assigns different material IDs to faces of each material groups, which can be easily accessed in 3ds Max. Of course it's possible to separate the mesh as different objects but it'll require extra work and I have no intention for that.

> Reply from RedBear ↑Wed Jan 15, 2020 2:44 pm at Wed Jan 15, 2020 2:44 pm
>
> 
Also could you update your npkUnpackerExtFilter.bms script?
For example, when I use it to unpack decripted hero.npk (Marvel Super War\main.8.com.netease.g104na.gb.obb), 
I get 20 unpacked model files and an error like this:

> Last script line before the error or that produced the error:
>
>   106 log OutName 0 Size MEMORY_FILE
Which script were you using?
The npkUnpackerExtFilter.bms within the attachment CyberConv.zip in the main post, which is out of date, has 48 lines in total.
The one from [this post](/viewtopic.php?p=154556#p154556), which is the correct one to use, has 53 lines in total.
While your error message reported that the line that produced the error was 106?
## Post #34
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2020-01-15T13:32:25+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Wed Jan 15, 2020 4:41 pm at Wed Jan 15, 2020 4:41 pm
>
> Of course it's possible to separate the mesh as different objects but it'll require extra work and I have no intention for that.I see. In this case, could you share the structure of the model file? I want to try to write a maxscript to import models. 
At the moment, it's based on code from zhouhang95's neox_tools, but there are some not pretty clear moments for me.

> Reply from Bigchillghost ↑Wed Jan 15, 2020 4:41 pm at Wed Jan 15, 2020 4:41 pm
>
> Which script were you using?
Yes, I used the npkUnpackerExtFilter.bms within the attachment CyberConv.zip in the main post.
I didn't know that it was outdated, because I thought that there are latest versions of your tools.

> Reply from Bigchillghost ↑Wed Jan 15, 2020 4:41 pm at Wed Jan 15, 2020 4:41 pm
>
> The one from this post, which is the correct one to use, has 53 lines in total.I used it to unpack decripted hero.npk (Marvel Super War\main.8.com.netease.g104na.gb.obb) and I get 72 unpacked model files and no error!
Thanks. 

> Reply from Bigchillghost ↑Wed Jan 15, 2020 4:41 pm at Wed Jan 15, 2020 4:41 pm
>
> While your error message reported that the line that produced the error was 106?Oh, I just added a few 'Magic' lines for my own needs.
## Post #35
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-17T04:28:44+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

The xor key for Marvel Super War above v2.5.0 has been released. You can find it in this [post](/viewtopic.php?p=154557#p154557).

Tests of some high res characters:
## Post #36
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-17T07:03:17+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Oh, almost forgot to update the unpacking script.

Same post [here](viewtopic.php?p=154556#p154556).
## Post #37
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-01-17T07:09:21+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from huitbgoiouythy ↑Thu Dec 19, 2019 10:22 pm at Thu Dec 19, 2019 10:22 pm
>
> the high asset I uploaded are for sure from latest update
By any chance do you still have the high res assets of a previous update below v2.5.0? Might be helpful for revealing a larger encryption key.
## Post #38
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2020-01-17T10:35:01+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

EDIT 2 : here high asset from beta2, no high asset for scene sadly.
[https://www.mediafire.com/file/3nzigzrn ... _2.7z/file](https://www.mediafire.com/file/3nzigzrniko9v2r/com.netease.g104na.gb_Downloaded_asset_Beta_2.7z/file)





EDIT : I found out I still have downloaded high asset from Beta 2, if I recall no big change for high asset from Beta 1to Beta 2, the file I uploaded on this thread was from the next update the first final release for Asian countries.
I can upload by end of next week when my connection is back at home.

Hello huge thank you for the update, I dont have anymore old High asset sadly, they overwrote downloaded file 

I still have old obb from the very first beta, I can upload if needed next week, they contain low asset npk.
## Post #39
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2020-06-09T18:04:52+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hi!

I m try to get model and textu from this game "Rangers of Oblivion" (猎魂觉醒网易官方版 ---com.netease.AVALON original). not rely life matter but i like to dig more in the file type.

so here the image what i gone to this point. use u tool and EXPKDec to play around. i get the model but no texture found.i use and extract all the file i see in folder but no texture. or im looking in wrong direction.



Screenshot (38).png (79.01 KiB) Viewed 478 times
## Post #40
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-06-23T20:39:29+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Fri Jan 17, 2020 12:28 pm at Fri Jan 17, 2020 12:28 pm
>
> 
The xor key for Marvel Super War above v2.5.0 has been released. You can find it in this post.

Tests of some high res characters:

Hi man  

first of all thanks for the script. Second I got a question, since using your .bms script to unpack npk archive I got ( .mesh and .dds ) models and texture i assume. Then there are .junk ( what are those files) ?

p.s: any possibility you would work on animation too?

thanks in advance, 
Drawing
## Post #41
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-07-07T15:36:02+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hi
May I ask about the sequence of operations to extract Onmioji Arena?
I try use EXPDec, files are decrypted, then quickBMS with that scrypts give me and error and say "0 files founded"
Which wrong?

This is what I get from quick BMS

- signature of 4 bytes at offset 0x00000000 doesn't match the one
  expected by the script:

  this one: "EXPK"
  45 58 50 4b                                       EXPK

  expected: "NXPK"
  4e 58 50 4b                                       NXPK

- 0 files found in 1 seconds
  coverage file 0     0%   4          72609948

Press ENTER or close the window to quit
## Post #42
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-07T15:53:08+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from TokiChan ↑Tue Jul 07, 2020 11:36 pm at Tue Jul 07, 2020 11:36 pm
>
> 
I try use EXPDec, files are decrypted, then quickBMS with that scrypts give me and error and say "0 files founded"
Which wrong?
That message indicates that you didn't decrypt the npk at all.
## Post #43
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-07-09T13:10:49+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Tue Jul 07, 2020 11:53 pm at Tue Jul 07, 2020 11:53 pm
>
> 
TokiChan wrote: ↑Tue Jul 07, 2020 11:36 pm
I try use EXPDec, files are decrypted, then quickBMS with that scrypts give me and error and say "0 files founded"
Which wrong?

That message indicates that you didn't decrypt the npk at all.

Ok so
Do someone can give me the right sequence of programms? I mean, what I must use first, what next, then etc.
## Post #44
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2020-07-09T13:52:33+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from TokiChan ↑Thu Jul 09, 2020 9:10 pm at Thu Jul 09, 2020 9:10 pm
>
> 
Bigchillghost wrote: ↑Tue Jul 07, 2020 11:53 pm
TokiChan wrote: ↑Tue Jul 07, 2020 11:36 pm
I try use EXPDec, files are decrypted, then quickBMS with that scrypts give me and error and say "0 files founded"
Which wrong?

That message indicates that you didn't decrypt the npk at all.


Ok so
Do someone can give me the right sequence of programms? I mean, what I must use first, what next, then etc.

What I do with Marvel Super War, have not tested on Onmyoji Arena
- Copy npk file where you have EXPKDec.exe and EXPKDec.cmd with xor.keys, then click on EXPKDec.cmd, command prompt will appear and decrypt npk files.
- use quickbms with npkUnpackerExtFilter.bms, then select desired npk to extract from, save whenever you want
- You will have extracted files from selected npk, drag & drop .mesh file to CyberConv.exe, this will give you fbx file that you can open with Noesis 3DS Max, Blender for example
- ktx file are the texture that you can open with PVRTexTool

Many thx again Bigchillghost for everything you shared
## Post #45
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2020-07-12T15:39:35+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from huitbgoiouythy ↑Thu Jul 09, 2020 9:52 pm at Thu Jul 09, 2020 9:52 pm
>
> 

What I do with Marvel Super War, have not tested on Onmyoji Arena
- Copy npk file where you have EXPKDec.exe and EXPKDec.cmd with xor.keys, then click on EXPKDec.cmd, command prompt will appear and decrypt npk files.
- use quickbms with npkUnpackerExtFilter.bms, then select desired npk to extract from, save whenever you want
- You will have extracted files from selected npk, drag & drop .mesh file to CyberConv.exe, this will give you fbx file that you can open with Noesis 3DS Max, Blender for example
- ktx file are the texture that you can open with PVRTexTool

Many thx again Bigchillghost for everything you shared

Yay! Thank you! You save my life!
## Post #46
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2020-07-16T12:28:07+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hey guys and girls, especially BC. Just wanted to let you all know that Lord Of The Rings: Rise To War meshes works with CyberConv.



Aragorn.png (78.73 KiB) Viewed 684 times

.

Textures can be converted using PVRTexTool
## Post #47
- Username: kotaxzz1
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 21, 2015 1:44 am
- Post datetime: 2020-09-15T23:06:28+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

this game [https://zgz.163.com/fab/](https://zgz.163.com/fab/) has file that contain file name list for .npk archive, is possible to extract with provided file name ?
[res.zip](https://xentaxbackup.github.io/file/18751_res.zip)
## Post #48
- Username: CybaShinobi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 09, 2020 3:03 pm
- Post datetime: 2020-11-09T07:41:51+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Wait, so how does this work? I want to get the Cyber Hunter Playermodel but all the files are .npk, adn the converter is asking for .mesh files, so how do I get a .npk to become a .mesh?
## Post #49
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-11-09T22:23:08+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Sun Jul 07, 2019 10:22 pm at Sun Jul 07, 2019 10:22 pm
>
> 

Edit: 
Get the npk decryptor for these two games here.

Here's a BMS script to handle the decrypted npk files. download/file.php?id=17365

First you need to unpack npk archive. After you got mesh files you can convert
## Post #50
- Username: CybaShinobi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 09, 2020 3:03 pm
- Post datetime: 2020-11-11T04:51:44+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

When I drag the file onto the EXPKDec.exe it does nothing, I had a look at this thing :[https://github.com/zhouhang95/neox_tools](https://github.com/zhouhang95/neox_tools) but idk how to run it, is that required and if so how do I set it up? forgive my ignorance but I'm just a modeller not a code guy
## Post #51
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-11-11T12:19:01+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from CybaShinobi ↑Wed Nov 11, 2020 12:51 pm at Wed Nov 11, 2020 12:51 pm
>
> 
When I drag the file onto the EXPKDec.exe it does nothing, I had a look at this thing :https://github.com/zhouhang95/neox_tools but idk how to run it, is that required and if so how do I set it up? forgive my ignorance but I'm just a modeller not a code guy

the EXPK works only for Onmyoji Arena (OA) and Marvel Super War  , generally with game with EXPK signature.
For other NPK just use the bms script in the second link. 
Which game are u trying to unpack?
## Post #52
- Username: themimegogo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 06, 2018 8:07 pm
- Post datetime: 2020-11-14T16:57:41+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Tue Jun 11, 2019 11:28 pm at Tue Jun 11, 2019 11:28 pm
>
> 
Another tool for skin testing purpose of my binary FBX builder, which was intended to convert Cyber Hunter mesh files to FBX format with skeleton, skin info and material groups. With the tool being updated to v1.2.0, now it supports a couple more games, technically any NeoX mesh format of NetEase, skinned or static ones.

Usage:
Double click on the executable and follow the leads, or use batch commands.

Supported Games:
Cyber Hunter (Tested on v0.100.143)
Onmyoji (Tested on v1.0.41)
RULES OF SURVIVAL (Tested on v1.281908.285092)
Crusaders of Light (Tested on v6.0.4)
BuildTopia (Tested on v2.1.10)
Creative Destruction (Tested on v2.0.1801)
Galactic Frontline (Tested on v1.0.109350)
MARVEL Super War (Unreleased) (Tested on v1.6.0)
Onmyoji Arena (Tested on v3.64.0)

Examples from above Games:
Cyber Hunter


Onmyoji


RULES OF SURVIVAL


Crusaders of Light


BuildTopia


Creative Destruction


Galactic Frontline


MARVEL Super War (Unreleased)


Onmyoji Arena




CyberConv.zip


A BMS script for unpacking npk archives from Cyber Hunter, and one for unpacking unencrypted npk files containing nameless assets with extension filtering (of mesh, ktx, and png only) are also attached. For npk files contain encrypted assets (like Onmyoji Arena and MARVEL Super War), use this script.

Hi Hi total noob here. 
I would like to learn how to do use this tool, for one of the games mentioned in this very post.

Where can I find beginner tutorials? 

Thanks!
## Post #53
- Username: CybaShinobi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 09, 2020 3:03 pm
- Post datetime: 2020-11-15T06:29:10+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Drawing ↑Wed Nov 11, 2020 8:19 pm at Wed Nov 11, 2020 8:19 pm
>
> 
CybaShinobi wrote: ↑Wed Nov 11, 2020 12:51 pm
When I drag the file onto the EXPKDec.exe it does nothing, I had a look at this thing :https://github.com/zhouhang95/neox_tools but idk how to run it, is that required and if so how do I set it up? forgive my ignorance but I'm just a modeller not a code guy


the EXPK works only for Onmyoji Arena (OA) and Marvel Super War  , generally with game with EXPK signature.
For other NPK just use the bms script in the second link. 
Which game are u trying to unpack?

I'm trying to get my playermodel from Cyber Hunter
## Post #54
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-11-16T13:27:11+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from themimegogo ↑Sun Nov 15, 2020 12:57 am at Sun Nov 15, 2020 12:57 am
>
> 
Hi Hi total noob here. 
I would like to learn how to do use this tool, for one of the games mentioned in this very post.

Where can I find beginner tutorials?
Please edit your post and remove the unnecessary part in the quote. As for how to use the tool, it's clearly stated in the first post:

> Reply from Bigchillghost ↑Tue Jun 11, 2019 11:28 pm at Tue Jun 11, 2019 11:28 pm
>
> Double click on the executable and follow the leads, or use batch commands.
If you've done that, you'd notice the tool requires mesh files for inputs, like this fellow here:

> Reply from CybaShinobi ↑Mon Nov 09, 2020 3:41 pm at Mon Nov 09, 2020 3:41 pm
>
> 
all the files are .npk, adn the converter is asking for .mesh files, so how do I get a .npk to become a .mesh?
Then again you can find the info about extracting mesh files from the npk archives in the main post:

> Reply from Bigchillghost ↑Tue Jun 11, 2019 11:28 pm at Tue Jun 11, 2019 11:28 pm
>
> A BMS script for unpacking npk archives from Cyber Hunter, and one for unpacking unencrypted npk files containing nameless assets with extension filtering (of mesh, ktx, and png only) are also attached. For npk files contain encrypted assets (like Onmyoji Arena and MARVEL Super War), use this script.
Depends on the game you're to extract, you'll find the proper script that's required. All you have to do is to read carefully the entire first post  and the one specified by the extend link, and make use of every piece of info in the process. If you have no idea of what a BMS script is or how to use it, well, you have the key word already, just use the internet wisely.

Never expect any "beginner tutorials" to be served. You're more intelligent than that.
## Post #55
- Username: themimegogo
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Nov 06, 2018 8:07 pm
- Post datetime: 2020-11-17T22:13:02+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Mon Nov 16, 2020 9:27 pm at Mon Nov 16, 2020 9:27 pm
>
> 
themimegogo wrote: ↑Sun Nov 15, 2020 12:57 am
Hi Hi total noob here. 
I would like to learn how to do use this tool, for one of the games mentioned in this very post.

Where can I find beginner tutorials? 

Please edit your post and remove the unnecessary part in the quote. As for how to use the tool, it's clearly stated in the first post:
Bigchillghost wrote: ↑Tue Jun 11, 2019 11:28 pmDouble click on the executable and follow the leads, or use batch commands.
If you've done that, you'd notice the tool requires mesh files for inputs, like this fellow here:
CybaShinobi wrote: ↑Mon Nov 09, 2020 3:41 pm
all the files are .npk, adn the converter is asking for .mesh files, so how do I get a .npk to become a .mesh?

Then again you can find the info about extracting mesh files from the npk archives in the main post:
Bigchillghost wrote: ↑Tue Jun 11, 2019 11:28 pmA BMS script for unpacking npk archives from Cyber Hunter, and one for unpacking unencrypted npk files containing nameless assets with extension filtering (of mesh, ktx, and png only) are also attached. For npk files contain encrypted assets (like Onmyoji Arena and MARVEL Super War), use this script.
Depends on the game you're to extract, you'll find the proper script that's required. All you have to do is to read carefully the entire first post  and the one specified by the extend link, and make use of every piece of info in the process. If you have no idea of what a BMS script is or how to use it, well, you have the key word already, just use the internet wisely.

Never expect any "beginner tutorials" to be served. You're more intelligent than that.

"Never expect any "beginner tutorials" to be served. You're more intelligent than that." -- 
That makes me not want to be thankful.
And frankly - this is the kind of attitude that quickly stomps enthusiasm out of people who beginners who aren't stone hearted enough, or have the experience to start off on the same foot as you.

I've been around around other forums involved with modding and dealing with 3D assets and such - and while I respect the fact that every forum is different - I was raised with the idea that "there's no harm in asking" - For example - the Resident Evil Modding forum, have entire boards dedicated to tutorials, something that's either pinned, or in someone's signature, or! if someone does the transgression of asking - is pointed by a mod or a good Samaritan who doesn't find it heavy on their heart to copy and paste a link. In your case - a simple "there are no tutorials" will do.

But for whatever reason - something in life must have jaded you to the point that asking not for a tutorial  but to be directed to one if there is any - is something you consider an insulting act of laziness because you had to work hard to get to where you are. 

I have subordinates where I work - imagine a new employee on day 1 - me telling them - go figure it out on your own. In my experience, it's been more fruitful help others - even if that help is - "the manual is in your drawer", or the on-boarding page is located here.

If you think your first post is user friendly Lets dissect it.

-  you describe what the tool does. Alright - a couple of technical jargon that i dont immediately recognize
- Double click on the executable and follow the leads, or use batch commands. (ok I click on Say Marvel Super War)
It leads me to, what seems to be a place where I can download a game? What the hell are batch commands? Is it the same thing as batch rendering something?
- you have a script for unpacking - what I assume is the game's data once you have it.

I guess those are the 3 main segments of the post - whatever I'm missing - Is obviously because I lack a lot of important knowledge thatd provide proper context. Before I'd choose to invest time in doing research to build up a vocabulary to understand all these terms first - let me check by asking if there is a more unified source of information - like a manual (or in this case) a tutorial. Because in my experience with dealing with people (1) some people learn better by practice, when shown steps (2) there's usually no harm in asking. If you didn't feel the need to insult people - and simply said -  "No there is no tutorial" - then yes, I'd go and do the searches.

Don't misunderstand - I didn't demand for one, nor am I obliging any of you vets to make one. 
Also I understand - that you guys invested and put in hard work to create such magnificent tools. I am in no position to imagine how hard or how easy it must have been for you. But I do respect the fact that you are likely not paid to make those tools, that you made them out passion perhaps. As such you guys have no obligations to any of the people who come knocking - or asking. But if somehow you're sick and tired interacting with "people who cant figure things out", why bother replying at all?  Not replying would have been better - because that would have really pushed newcomers into searching on their own. 

But in replying with your nose held high like that, whether you care to admit it to yourself or not - you're doing more harm to people who weren't as hardened by life like you were. Shove it up your a$$ man, if you're jaded, or your passion has been snuffed out - try not to impart that negative mantra onto others. I'm outa here.
## Post #56
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-11-19T14:38:40+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
That makes me not want to be thankful...why bother replying at all?
Being "thankful", in fact, is the only reason that you're getting any reply.

> Reply from Bigchillghost ↑Mon Nov 16, 2020 9:27 pm at Mon Nov 16, 2020 9:27 pm
>
> 
Never expect any "beginner tutorials" to be served. You're more intelligent than that.
It's nothing more but simply an advice for people who tend to preconceive the thing they're dealing with is complicated. 
Insulting? Why should I waste most of the space rephrasing the instructions only to insult someone? Sorry if you're such a snowflake that you felt this way.

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
I was raised with the idea that "there's no harm in asking"
That, is a philosophy still open to questions. I never object people for asking questions, just don't come up with the first question as "where is the tutorial". Some people always tend to ask about something that they can easily solve by doing a couple of searching, or something already been instructed by the first post of a topic as if they don't see it, instead of at least trying to follow the instructions and then ask about the part they really don't understand. The first question they put up with is usually like "I'm a noob, point me right to the direction". That's the kind of manner I disapprove. 

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
But for whatever reason - something in life must have jaded you to the point that asking not for a tutorial but to be directed to one if there is any - is something you consider an insulting act of laziness because you had to work hard to get to where you are.
I don't see any difference between "asking for a tutorial" and "to be directed to one". I wouldn't consider it as "an insulting act of laziness", but doing so even if there's enough infomation in the 1st post do seem inappropriate to me.

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
For example - the *** forum, have entire boards dedicated to tutorials, something that's either pinned, or in someone's signature, or! if someone does the transgression of asking - is pointed by a mod or a good Samaritan who doesn't find it heavy on their heart to copy and paste a link. In your case - a simple "there are no tutorials" will do.
Take a glance on the tutorial section on Xentax and the one through the 1st link in my signature, then we can have this conversation again. The "tutorials" are always there, and have been there for years. It's easily accessible, most of you just ignored it. In this particular situation, all you have to do is to unpack the archives with the provided scripts, and convert the mesh file with the tool. You don't need any tutorial for something that can be explained in a sentence!

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
I have subordinates where I work - imagine a new employee on day 1 - me telling them - go figure it out on your own. In my experience, it's been more fruitful help others - even if that help is - "the manual is in your drawer", or the on-boarding page is located here.
I respect your meticulous care to your subordinates, but explaining something that's already understandable in a "manual"/"on-boarding page", the way I see it, is a total waste of your time and that of others.

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
If you think your first post is user friendly Lets dissect it.

-  you describe what the tool does. Alright - a couple of technical jargon that i dont immediately recognize
- Double click on the executable and follow the leads, or use batch commands. (ok I click on Say Marvel Super War)
It leads me to, what seems to be a place where I can download a game? What the hell are batch commands? Is it the same thing as batch rendering something?
I never said it was user friendly. It's never meant to be. I prefer to provide simple yet sufficient info and leave the rest to the users themselves. In this way, those with patience to finish reading the entire post get what they came for, even if they left no trace of their user identities and never thanked the author for the tools. It's a strategy to maintain a balance between "sharing with the community" and "blocking out the leeches".

The "executable" means the .exe of the program. In a world where Windows OS has been widely used, it's really hard to imagine that you'll consider an "executable" as the same meaning of a "link" to the page containing the info of the game.
"Batch commands" is a term you can look up through the wiki or any searching engine. If you're too busy for that, just ignore it. It's not the only way to use the tool.

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
let me check by asking if there is a more unified source of information - like a manual (or in this case) a tutorial.
If you'd asked that straightforward, i.e., "is there a more unified source of information?", you'd probably get the "No there is no tutorial" kind of reply as you wished.

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
Don't misunderstand - I didn't demand for one
Asking with the word "where" means you're demanding for one.

> Reply from themimegogo ↑Wed Nov 18, 2020 6:13 am at Wed Nov 18, 2020 6:13 am
>
> 
But in replying with your nose held high like that, whether you care to admit it to yourself or not - you're doing more harm to people who weren't as hardened by life like you were. Shove it up your a$$ man, if you're jaded, or your passion has been snuffed out - try not to impart that negative mantra onto others. I'm outa here.
Since you felt yourself being so much insulted, I'll try to be tolerant with these outraged accusations you made here and ignore those "unpleasant" words.
## Post #57
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-11-19T23:31:16+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

@themimegogo
Bigchillghost release this tools and update it for FREE and he already write everything you need to do at the first post , i really dun see what upset you this much at all , since most of hand-made extractor dun even came with any lines like "simple, d&d mesh files onto the tool" and many people wont release them to public for free , i think you should be more thankful and using this tools w/o any problem , you could simply said "oh sry i didnt read" instead of 1000+ of meaningless words toward Bigchillghost
## Post #58
- Username: Vlalchinanya
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 13, 2020 9:14 pm
- Post datetime: 2020-11-22T17:32:35+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hi guys. Can anyone update the CyberConv program and add the Super Mecha Champions game? This game has archives in .npk format

For example: [http://www.mediafire.com/file/1aclymke3 ... s.npk/file](http://www.mediafire.com/file/1aclymke3thtvxq/res.npk/file)

Thanks.
## Post #59
- Username: speaker60
- Rank: beginner
- Number of posts: 32
- Joined date: Sun Jun 18, 2017 12:41 am
- Post datetime: 2021-01-19T01:47:31+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

This new Netease game here has NPK files [http://hsqsl.163.com/](http://hsqsl.163.com/)
Could we get support for this?

One of the NPK files
[https://drive.google.com/file/d/1zmZScx ... q6NUp/view](https://drive.google.com/file/d/1zmZScxFiY5J9tVeTKySz0Nf2YEkq6NUp/view)
## Post #60
- Username: DMGAME
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Mar 24, 2021 4:45 pm
- Post datetime: 2021-04-08T10:46:35+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hi RULES OF SURVIVAL Unpack Seems to have no name，but I found this  
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/15GbDKMjdNbg9UzR2D7TvMkcBblRSgBYg?usp=sharing)
## Post #61
- Username: thewitchboy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 29, 2019 7:04 am
- Post datetime: 2021-07-04T14:24:55+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hey so I managed to do it, but I am getting a load of .junk files, I am trying to extract the decals/ effects textures and sounds
## Post #62
- Username: sleepeatrepeat
- Rank: n00b
- Number of posts: 11
- Joined date: Wed May 16, 2018 1:57 pm
- Post datetime: 2021-07-06T04:08:22+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from thewitchboy ↑Sun Jul 04, 2021 10:24 pm at Sun Jul 04, 2021 10:24 pm
>
> 
Hey so I managed to do it, but I am getting a load of .junk files, I am trying to extract the decals/ effects textures and sounds

the textures usually has .ktx extension, you can open those using PVRTexTool
## Post #63
- Username: thewitchboy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 29, 2019 7:04 am
- Post datetime: 2021-07-06T12:55:52+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from sleepeatrepeat ↑Tue Jul 06, 2021 12:08 pm at Tue Jul 06, 2021 12:08 pm
>
> 
thewitchboy wrote: ↑Sun Jul 04, 2021 10:24 pm
Hey so I managed to do it, but I am getting a load of .junk files, I am trying to extract the decals/ effects textures and sounds


the textures usually has .ktx extension, you can open those using PVRTexTool

Is there anyway I can extract the sounds or fx textures?
## Post #64
- Username: lil cristal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 18, 2021 1:24 am
- Post datetime: 2021-07-17T18:11:52+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

How do I unpack the .NPK file, someone pls teach me.
## Post #65
- Username: lil cristal
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 18, 2021 1:24 am
- Post datetime: 2021-07-17T18:15:03+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

How to unpack NPK?
## Post #66
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-07-18T05:22:56+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Please do NOT make multiple posts asking the same question. 

Just read the first post and pick the right BMS script for the game you're dealing with. If you have no idea how to use a BMS script, use google, or check this page:
[http://aluigi.altervista.org/quickbms/howto.htm](http://aluigi.altervista.org/quickbms/howto.htm)
## Post #67
- Username: Maechen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 22, 2019 11:37 pm
- Post datetime: 2021-09-17T22:48:04+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hello everyone ! 
I try to unpack the NXPK of the chinese game Harry Potter Magic Awakened.
I tried all the scripts mentionned (the BMS scripts, the python soft neox_tools, even the EXPKDec script although the npk file are not EXPK signed)
Sadly none of them seems to work for this game...
Anyone have an idea to unpack these files ?

Exemple of files : [https://ucarecdn.com/2e81695d-93d5-4f2b ... b12423b56/](https://ucarecdn.com/2e81695d-93d5-4f2b-b59d-bc6b12423b56/)
## Post #68
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-09-18T07:48:57+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Maechen ↑Sat Sep 18, 2021 6:48 am at Sat Sep 18, 2021 6:48 am
>
> 
I try to unpack the NXPK of the chinese game Harry Potter Magic Awakened.
...
Anyone have an idea to unpack these files ?
The first 128 bytes of the raw data of each file within is encrypted. It'll require an individual script for this game.
## Post #69
- Username: Maechen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 22, 2019 11:37 pm
- Post datetime: 2021-09-18T12:19:22+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Sat Sep 18, 2021 3:48 pm at Sat Sep 18, 2021 3:48 pm
>
> 
Maechen wrote: ↑Sat Sep 18, 2021 6:48 am
I try to unpack the NXPK of the chinese game Harry Potter Magic Awakened.
...
Anyone have an idea to unpack these files ?

The first 128 bytes of the raw data of each file within is encrypted. It'll require an individual script for this game.

Hello and thank you for your answer.
I am able to uncript the npk file with this script (link below)
For now I can see the Mesh (.dat to transform in .mesh that I import in the soft 3d object converter) and the texture (.dds).

I'll see what can I do with the rest of the files

Thank you for your time
[nxpk_hpma_bms.zip](https://xentaxbackup.github.io/file/20826_nxpk_hpma_bms.zip)
## Post #70
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-01T03:28:18+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from Bigchillghost ↑Tue Jun 11, 2019 11:28 pm at Tue Jun 11, 2019 11:28 pm
>
> 

A BMS script for unpacking npk archives from Cyber Hunter, and one for unpacking unencrypted npk files containing nameless assets with extension filtering (of mesh, ktx, and png only) are also attached.

Hello Bigchillghost! it's me again xD!, I were checking the files from Crusaders of Light game, I got two models with their respective textures, but is really hard to match them at eye sight. Is there any way to get the filenames of this game please? Thanks for everything Bigchillghost!
## Post #71
- Username: DPress
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 12, 2019 12:43 am
- Post datetime: 2021-12-11T04:33:13+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Can we get this working for super mecha champions please? or if theres any other way to rip from the game would someone mind helping me out
## Post #72
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-12-31T03:52:32+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from nigelmerle ↑Fri Dec 31, 2021 8:43 am at Fri Dec 31, 2021 8:43 am
>
> 
just because they know everything and they dont want to help others
Honestly, seems like you are new here, Bigchillghost and many others help alot to other peoples with their scripts without asking for anything in return
## Post #73
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-31T03:53:17+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from nigelmerle ↑Fri Dec 31, 2021 8:43 am at Fri Dec 31, 2021 8:43 am
>
> 
I have been reading all this, wow, wow...can people be so evil on earth i cant believe it... make our lives easier and stop writing big paragraphs to explain yourself, you just have a bad conscience thats all...
I've already explained my point clearly. And note that I'm under no obligation to provide assistance to everyone, especially not some impatient, grumpy ignoramus who take everything for granted. If that upsets you and you can't accept it, then leave this page. I don't need to listen to any of your conceited, aggressive preaching here.

> Reply from nigelmerle ↑Fri Dec 31, 2021 8:43 am at Fri Dec 31, 2021 8:43 am
>
> 
Everything is unclear on this page I can confirm that, I didnt understand a thing about how all these scripts work together....
That's your problem, and yours only. And don't be too self righteous to think you can represent the opinions of the majority.
## Post #74
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-31T08:46:27+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

> Reply from nigelmerle ↑Fri Dec 31, 2021 8:43 am at Fri Dec 31, 2021 8:43 am
>
> I have been reading all this, wow, wow...can people be so evil on earth i cant believe it, just because they know everything and they dont want to help others who doesnt have the knowledge in programming they call this spoon feeding seriously,Well, oneTimePoster, this year has been hard for all people, admitted. But please don't put your "negative mantra onto others". It's not that you didn't understand the purpose of this forum it just looks like you're wanting to ... here. Wrong place man, sorry. 

btw: I've reported your post as being "insulting and useless", just my two cents.
(Usually I don't act so but I didn't want this year to end like this.  )
## Post #75
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-12-31T11:01:17+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

please do not insult our saviors
## Post #76
- Username: Myxtar6
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 20, 2021 12:00 am
- Post datetime: 2022-05-14T15:36:31+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hello, could you update script for Marvel Super War 3.17.2 ?
P.S: Thanks you, very much for your titanic work
## Post #77
- Username: Myxtar6
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu May 20, 2021 12:00 am
- Post datetime: 2022-06-02T12:17:49+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

Hello? There anyone alive?
## Post #78
- Username: mok10898
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 15, 2022 9:02 am
- Post datetime: 2022-08-15T01:16:06+00:00
- Post Title: Re: Cyber Hunter Mesh Convertor(CyberConv)

i really need help
