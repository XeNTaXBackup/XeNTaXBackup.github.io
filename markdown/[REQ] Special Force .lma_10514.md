## Post #1
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2013-06-15T05:33:00+00:00
- Post Title: [REQ] Special Force .lma

This game is a popular MMOFPS game in the world, and we have sff unpacker to unpack its archive files, but nobody can't open its models 'cause those files are .lma and maybe they were encrypted  and i found their structure are different from .lma of Granado Espada, so guys, would you mind helping me to open them in 3dsmax or Noesis or some programs else . Also they have .fxa files and i think FaceFX of Unreal Engine is the best choice but i don't have that tools  Anyway, sorry about my bad Eng 

This is sample:
.FXA :m e d i a f i r e.com/?m5g7s5sff3s2sf8
.LMA : Attachments

There are some screenshots:



And some textures that i have extracted, they are in .jpg format



[sf_a_ak47s.7z](https://xentaxbackup.github.io/file/6470_sf_a_ak47s.7z)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-06T03:13:04+00:00
- Post Title: [REQ] Special Force .lma

first submesh of sf_a_g_ak47s.LMA  



sf_a_g_ak47s_LMA.png (31.35 KiB) Viewed 122 times



looks like there is a 52 byte header before the vertex block of each submesh
0x3457 - vertex count for first submesh 
0x345b - face count for first submesh

the real start address for the vertex block should be 0x3477 but
this produces a 2d model in Hex2obj instead of 3d model because
Hex2obj was written to parse position values first in the stride
## Post #3
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-08-06T15:28:53+00:00
- Post Title: [REQ] Special Force .lma

> Reply from AceWell
>
> first submesh of sf_a_g_ak47s.LMA  
sf_a_g_ak47s_LMA.png

looks like there is a 52 byte header before the vertex block of each submesh
0x3457 - vertex count for first submesh 
0x345b - face count for first submesh

the real start address for the vertex block should be 0x3477 but
this produces a 2d model in Hex2obj instead of 3d model because
Hex2obj was written to parse position values first in the stride

wow, that's great  I will take a look on this file soon
