## Post #1
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-12-05T21:08:50+00:00
- Post Title: ZRM Hazard Ops MARS UPK file.

Hello there forum, I am trying to unlock this game, and have been for about a year now, it's for an unreal 3 game called one of three names MARs is what i will call it. 

the UPK's do not look encrypted, you can open them with note pad ++ and see the data inside is readable English text.
But any time I try to use Umodel to import or export it, it says it is encrypted and the header is wrong. 
it gets stranger when you try to unpack the UPK with a UPK unpacking tool it says it can not lead the namelist. 

I'm so stuck I don't know what else to do, here is a sample, open one open them all. 
I would really appreciate any help on this one. 

I have possible AES keys too, but they are for UE4 games. 
0x000000000000000067E6096A85AE67BB72F36E3C3AF54FA57F520E518C68059B
0xA0BB9101F0020601C003060190FF050130000601D00006018B44240800000000
0x50BE910150380601F038060190390601303A0601D03A0601703B0601103C0601
0x8CC091017064060110600601E06406015065060160600601C065060180660601
0xA0C49101A0AD060140AE060160B2060110AF060190AF060160B0060130B10601
0x8CC0910120DB0601D0DB060180DC060140DD060100DE060180DE0601F0E60601
0x50BE910110EC0601C0EC060180ED060130EE060110EF0601C0EF060170F00601
0x00000000000000800000000000000080FFFFFFFFFFFFFFFF0000000000000000
0xD89E05C15D9DBBCB07D57C362A299A6217DD70305A01599139590EF7D8EC2F15
0x08C9BCF367E6096A3BA7CA8485AE67BB2BF894FE72F36E3CF1361D5F3AF54FA5
0x0000000000000000000000000000000000000000000000000000000000000000
0xC7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C7C700000000
[CH_PC_Female.rar](https://xentaxbackup.github.io/file/23107_CH_PC_Female.rar)
## Post #2
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-12-07T22:00:56+00:00
- Post Title: ZRM Hazard Ops MARS UPK file.

I can confirm thanks to Vlad_265's help, that the files are not encrypted. and only the header is not being read properly.
## Post #3
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-12-09T19:44:06+00:00
- Post Title: ZRM Hazard Ops MARS UPK file.

More information thanks to the gildor forums.

"Part of packages header is encrypted, that's why it doesn't work in umodel. And the game is using rsa encryption for that part, divided into three blocks, though for some reason it works properly only for the first block."

I'm not sure what this means. but if someone knows more It would appreciate it.
## Post #4
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-12-09T19:52:37+00:00
- Post Title: ZRM Hazard Ops MARS UPK file.

Hello Forum, I made a new thread for this since the project has changed a bit. Vlad_256 has done a wonderful job creating a plug in to import the UPK 3d model and bones.

but when it comes to the textures. He believes they are compressed in some way. 
he tried many different methods to decompress them but nothing worked. here is the information he gave me. 
and here is the sample files as well. (any character should work)
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1aOxIcG2Nh8dzSDUe1hOB-tGmzI2mvkCs?usp=share_link)

The following information was used on file
"CH_PC_Soldier_M_DLC2.upk"

VectorParameterValues 0 458768

offset 250560(decimal) 
he tried 
"i tried dxt1, dxt3, dxt5, PVRTC, ETC1, BC1, DXT2, BC2, BC3, BC4, BC5, ETC2 RGB, ETC2 RGBA, and uncompress rgba8888 and e.t.c"

I'm unsure of where to go form here and so is he. would anyone be able to offer some help?
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-01-07T17:10:55+00:00
- Post Title: ZRM Hazard Ops MARS UPK file.

You can find partially working solution for the game [here](https://www.gildor.org/smf/index.php/topic,8036.msg44582.html#msg44582) (only upk and mars files are supported).
