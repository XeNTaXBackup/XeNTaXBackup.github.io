## Post #1
- Username: Ted Pearl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 30, 2015 10:08 am
- Post datetime: 2015-11-30T02:24:07+00:00
- Post Title: Unity 5.2 .tex file with 60 byte header??

I'm exploring some .tex files from a Unity 5.2 game, and they appear to have a 60 byte header instead of the standard 56 byte header. But that's not it. Even truncating the header and trying to load the raw image data into Gimp is unsuccessful. The first 16 bytes seem to suggest the DxT1 format, but then it gets weird after that. Is there something obvious I'm missing here, or else, does anyone have any ideas what's different about this format?


 sharedassets4~WIP_Texture.zip
(5.11 KiB) Downloaded 22 times
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-30T02:35:38+00:00
- Post Title: Unity 5.2 .tex file with 60 byte header??

Yeah TextureFinder reads it as an upside down 512x512 dxt1 texture with mip maps and it has a custom header with the first 8 bytes storing the width and height.
## Post #3
- Username: Ted Pearl
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 30, 2015 10:08 am
- Post datetime: 2015-11-30T03:29:48+00:00
- Post Title: Unity 5.2 .tex file with 60 byte header??

Wow, TextureFinder is awesome. I shifted 4 bytes to account for the extra 4 bytes in the header and got the exact texture. Still gotta work on dimensions, as 512px truncates the mip maps, but you got me over the big hurdle. Appreciate it!
