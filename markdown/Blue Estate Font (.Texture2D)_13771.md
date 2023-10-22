## Post #1
- Username: GhostSpy
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Sep 14, 2014 9:47 pm
- Post datetime: 2016-01-07T10:33:03+00:00
- Post Title: Blue Estate Font (*.Texture2D)

Hi.
Font file from blue estate have texture2d format. 
Extractable with umodel but this time can't import-able.
By the way extracable file is not seen by the game. I searching to open and close tool/script for texture2d file.
Thanks a lot!

same files enclosed
[BlueEstate - fonts .7z](https://xentaxbackup.github.io/file/10272_BlueEstate - fonts .7z)
## Post #2
- Username: GRiNDERKILLER
- Rank: veteran
- Number of posts: 92
- Joined date: Thu Jul 12, 2012 7:24 pm
- Post datetime: 2016-01-31T16:23:54+00:00
- Post Title: Blue Estate Font (*.Texture2D)

You need decent HEX editor and some knowledge.

Open font file in HEX editor and remove first 305 bytes, then go to on end of file and again remove 52 bytes from end. Now you have sorted RAW data of font.
Now you must put valid DDS header on start of file and save it as dds.

All those textures are DXT5.

And for reimport, if this game loads uncompressed files you can "simply" put edited fonts into the upk through HEX. But you must again remove DDS header and put back previously removed data.

EDiT: I convert them for you see attachment.
[BlueEstate - fonts_conv.7z](https://xentaxbackup.github.io/file/10396_BlueEstate - fonts_conv.7z)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-21T18:36:18+00:00
- Post Title: Blue Estate Font (*.Texture2D)

i made a Noesis script to open those *.Texture2D samples  


 tex_BlueEstateFont_Texture2D.zip
(561 Bytes) Downloaded 100 times
