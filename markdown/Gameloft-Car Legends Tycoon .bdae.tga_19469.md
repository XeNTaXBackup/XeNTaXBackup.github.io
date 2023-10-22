## Post #1
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-02-09T11:26:13+00:00
- Post Title: Gameloft-Car Legends Tycoon .bdae/.tga

Hi everyone,
There is a new game  by Gameloft.I tried ripping models from it.After extracting the obb I got the models in .bdae format and textures in.tga format.
I tried using ASSR exporters to convert them into different formats but they won't do anything.
So can anyone here help in converting them to suitable formats?

Sample: [https://app.box.com/s/9rjd59du8bhszv4nmh2qnzhpp5o5u9gp](https://app.box.com/s/9rjd59du8bhszv4nmh2qnzhpp5o5u9gp)
## Post #2
- Username: lolbas
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Nov 18, 2015 11:59 pm
- Post datetime: 2019-02-10T13:18:15+00:00
- Post Title: Gameloft-Car Legends Tycoon .bdae/.tga

BDAE is very complicated format with ~1000 possible versions of it. I do work on parsing them but heck, it is very complicated. I doubt anyone has a suitable tool for this.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-12T15:31:28+00:00
- Post Title: Gameloft-Car Legends Tycoon .bdae/.tga

1. Unzip bdae/tga files with WinRAR;
2. Decompress the resulted files with this BMS script:
[http://aluigi.altervista.org/bms/gcbf_versus.bms](http://aluigi.altervista.org/bms/gcbf_versus.bms)
Or use this modified one:


 gcbf_versus.zip
Modification: preserve orignal extension. (571 Bytes) Downloaded 58 times


3. Retry with whatever tools you used.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-12T16:45:25+00:00
- Post Title: Gameloft-Car Legends Tycoon .bdae/.tga

> Reply from Bigchillghost
>
> 3. Retry with whatever tools you used.quick'n dirty:



little_endian_quantized_ucp-bdae.png (201.37 KiB) Viewed 177 times



0xA500 1008
Vb1
24 12
0x8190 378
020000
0x0 255
## Post #5
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-02-12T17:41:55+00:00
- Post Title: Gameloft-Car Legends Tycoon .bdae/.tga

Okay I decompressed the bdae then I found little_endian_quantized.bdae. I used this particular bdae file in ASSR exporters but it says "magic numbers do not match".
So I used the BMS script by BigChillghost on this bdae and got little_endian_quantized_ucp.bdae . This file is also not converted in ASSR exporters.
I found a Noesis script by Acewell for gameloft .bdae so I tried it but it too does not import this bdae.

As for the textures, the TGA files won't extract but this is only for some textures. Some can be extracted by renaming to zip but the resultant .ktx files I got are not opening in PvrTexTool. 

For the ones which don't decompress I used the script given by BigChillghost and got a decompressed TGA. I renamed it to ktx and it was importable in PVRTexTool.

Some textures I got but some are not importable.Models are not importable yet.

I'm sorry if i'm unable to explain properly.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-13T00:37:00+00:00
- Post Title: Gameloft-Car Legends Tycoon .bdae/.tga

> Reply from taruncreation
>
> 
So I used the BMS script by BigChillghost on this bdae and got little_endian_quantized_ucp.bdae . This file is also not converted in ASSR exporters.
I found a Noesis script by Acewell for gameloft .bdae so I tried it but it too does not import this bdae.
Not a surprise.

> Reply from taruncreation
>
> 
Some can be extracted by renaming to zip but the resultant .ktx files I got are not opening in PvrTexTool.
When speaking of "resulted files"  those ktx files are included as well.
