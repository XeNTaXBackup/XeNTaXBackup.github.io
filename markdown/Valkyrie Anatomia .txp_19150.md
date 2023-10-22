## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-06T11:20:14+00:00
- Post Title: Valkyrie Anatomia .txp

I am looking at the textures from a mobile game called Valkyrie Anatomia, but I couldn't find the image format used. .txp textures all have the "GLTP" (0x5) tag near the beginning, followed by image width and height (2 bytes each). There is also the texture name at 0x30. I don't know what other values in the header should mean. Texture names have ".tga" in them, so these might actually be targa images. Still file names can be deceiving 

I am hoping someone more experienced can take a look. I have attached 2 .txp samples.

Thank you.
[va_tex_samples.rar](https://xentaxbackup.github.io/file/15282_va_tex_samples.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-07T02:22:34+00:00
- Post Title: Valkyrie Anatomia .txp

i almost want to say these samples are crunch compressed but with a custom header,
though i'm not really familiar with what square-enix does to their mobile game graphics.
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-12-07T11:22:21+00:00
- Post Title: Valkyrie Anatomia .txp

I haven't thought of crunch at all. I will check out the library to learn how I can use it. Thanks for the info.

Edit : Looks like KTX format can also use crunch compression. So these might also be ETC/ETC2 with crunch. I have seen ETC textures in other Square games.

The custom header doesn't make it easier too. I think I will try to understand the header first. There might be offsets/sizes for mip map data, because the header is larger for higher resolution textures. Also possibly some flags for the format used.
