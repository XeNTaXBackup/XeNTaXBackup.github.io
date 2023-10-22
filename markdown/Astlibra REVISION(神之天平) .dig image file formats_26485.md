## Post #1
- Username: asasasasasbc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 07, 2017 2:19 pm
- Post datetime: 2023-02-18T15:42:52+00:00
- Post Title: Astlibra REVISION(神之天平) .dig image file formats

Hi everyone, I am a modder that is working on modding Astlibra revision.
I figured out how to decrypt its .dxa files and decryped its image files.
However, its image files cannot be loaded by any software. 
This file format (.DIG) starts with magic number DIMG (44 49 47 4D). I checked the image file via 010 editor and could not figure out its actual binary format. I also checked the game's previous 2021 free version, and that version's game doesn't use this kind of .dig image file formats, it just use png.
Is this image file compressed or crypted?
Could anybody help me about this format? So that I can make modding tools for this game! Any help is appreciated!
I uploaded one decrypted image file as attachment(star.zip). Feel free to check it out!

By Forsakensilver
[star.zip](https://xentaxbackup.github.io/file/23428_star.zip)
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-02-18T18:27:30+00:00
- Post Title: Astlibra REVISION(神之天平) .dig image file formats

@asasasasasbc: It's compressed with deflate. In the sample layout is simple: header + zero (maybe type) + image sizes + decompressed size + compressed size + offset to compressed block + compressed block. It can be extracted, for example, with offzip (offzip -a -z -15), extracted data would be raw image of some format(s).
## Post #3
- Username: asasasasasbc
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 07, 2017 2:19 pm
- Post datetime: 2023-02-18T18:49:18+00:00
- Post Title: Astlibra REVISION(神之天平) .dig image file formats

> Reply from Spiritovod ↑Sun Feb 19, 2023 2:27 am at Sun Feb 19, 2023 2:27 am
>
> 
@asasasasasbc: It's compressed with deflate. In the sample layout is simple: header + zero (maybe type) + image sizes + decompressed size + compressed size + offset to compressed block + compressed block. It can be extracted, for example, with offzip (offzip -a -z -15), extracted data would be raw image of some format(s).
Thank you very much! I can get some raw image data now, after some programming I guess I would be able to make the modding tool (your name will be added to the credit list)! 
Sincerely
Forsakensilver
