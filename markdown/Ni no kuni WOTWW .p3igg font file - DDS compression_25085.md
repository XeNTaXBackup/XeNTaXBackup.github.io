## Post #1
- Username: goder2910
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Jun 04, 2011 9:36 pm
- Post datetime: 2022-02-23T07:59:34+00:00
- Post Title: Ni no kuni WOTWW .p3igg font file - DDS compression

Hi everyone!

Trying to add some new characters to the font image file of this old game on PS4 but got stuck at reimporting back to game.
Although .p3igg 's size is double bigger than old version (PS3 version) but the format is same (no compression, raw image), so i can view p3igg as DDS file normally with no problem. 
However, the problem is reimporting or recreating p3igg file.
After modifying the dds file, i tried to export as below DDS compression as much as i can, remove the header but nothing works.
DXT1, DXT3, DXT5, Non-Compression
Game always is crashing when start up, or garbage text is displayed , v..vv.
Problem is the pixel or binary data is not same structure with original .p3igg file

Anyone can help me to check which compression type of p3igg file or show me the way how to recreating .p3igg ?
Tried this importer/exporter from github but nothing work.
[https://github.com/wmltogether/Ninokuni-Images-Tool](https://github.com/wmltogether/Ninokuni-Images-Tool)

The script using palette data that is exported from .p3igg to create a range of pixel to make a new .dds file but i think the problem is font file doesn't have palette.
Modified the code but no hope.

BTW, here are converted .dds file, original .p3igg, .p3img file.
[Ni no kuni](https://www.mediafire.com/file/qwxp1ny1zemc0tz/NinoKuniRemastered_fontfile.rar/file)
Hope you guys help me !

Thanks in advance!
