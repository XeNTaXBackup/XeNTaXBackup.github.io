## Post #1
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2021-02-04T09:43:26+00:00
- Post Title: Artifex Mundi .stex images

Hi guys,

This is Artifex Mundi (Godot Engine) textures. .stex extension. I need help with export import image files. Thanks...

[https://www.dosya.tc/server33/dh9pjq/font_en0.stex.html](https://www.dosya.tc/server33/dh9pjq/font_en0.stex.html)
## Post #2
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2021-02-04T14:55:12+00:00
- Post Title: Artifex Mundi .stex images

I have been exposed to this format 8 years ago, when I was working on a game translation and localization project. At the time, I was very confused about the compression algorithm. Finally, my friend helped me to disassemble the main program and use the assembly code of the game to decompress the data. I have never figured out what the compression algorithm is.
Today I saw this format and I remembered it. I searched for related information and found that someone had figured it out. It turned out to be LZ4 compression.

Thanks to personperson for the compressed format information.
[viewtopic.php?f=33&t=22640](https://forum.xentax.com/viewtopic.php?f=33&t=22640)

So I wrote a script to help you import and export. Hope it helps you.
My current method is to decompress the data, modify it and import it back, and remove the compression flag.
I did that in my project at the time and it worked.

**Edited""
Added DXT5 Support.
[fmt_ArtifexMundi_stex.zip](https://xentaxbackup.github.io/file/19538_fmt_ArtifexMundi_stex.zip)
## Post #3
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2021-02-04T23:05:07+00:00
- Post Title: Artifex Mundi .stex images

Working great. Thanks
## Post #4
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2021-02-13T15:08:22+00:00
- Post Title: Artifex Mundi .stex images

Allen,

Script does'nt work on some files. What is the problem? I am attaching a sample file...


 files.zip
(215.69 KiB) Downloaded 26 times



> Reply from Allen ↑Thu Feb 04, 2021 10:55 pm at Thu Feb 04, 2021 10:55 pm
>
> 
I have been exposed to this format 8 years ago, when I was working on a game translation and localization project. At the time, I was very confused about the compression algorithm. Finally, my friend helped me to disassemble the main program and use the assembly code of the game to decompress the data. I have never figured out what the compression algorithm is.
Today I saw this format and I remembered it. I searched for related information and found that someone had figured it out. It turned out to be LZ4 compression.

Thanks to personperson for the compressed format information.
viewtopic.php?f=33&t=22640

So I wrote a script to help you import and export. Hope it helps you.
My current method is to decompress the data, modify it and import it back, and remove the compression flag.
I did that in my project at the time and it worked.
fmt_ArtifexMundi_stex.zip
## Post #5
- Username: Allen
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Feb 17, 2012 4:49 pm
- Post datetime: 2021-02-14T10:14:49+00:00
- Post Title: Artifex Mundi .stex images

> Reply from oyunceviri ↑Sat Feb 13, 2021 11:08 pm at Sat Feb 13, 2021 11:08 pm
>
> 
Allen,

Script does'nt work on some files. What is the problem? I am attaching a sample file...
Updated, they are in DXT5 format. 
I still remember that there should be other formats, but many years have passed and I don’t have more samples. 
It can work for the current game.
## Post #6
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2021-02-27T15:26:14+00:00
- Post Title: Artifex Mundi .stex images

Working!!! Thanks Allen.
