## Post #1
- Username: Carpethop
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-07-04T22:04:50+00:00
- Post Title: JADE Game Engine .bin file pack-tool v1.0

JADE Game Engine .bin file pack-tool v1.0 by xor37h/hitmen

With this tool you can decompress and recompress the extracted .bin files
from the extracted KingKongTheGame_clean.bf bigfile on the 360 kiosk disc.

< link expired >

It should (but doesn't have to) work on other packed .bin files using the JADE game engine like:
– Beyond Good & Evil
– Prince of Persia: The Sands of Time
– Prince of Persia: Warrior Within
– Prince of Persia: The Two Thrones
– Peter Jackson's King Kong: The Official Game of the Movie
– Rayman Raving Rabbids
– TMNT
– Rayman Raving Rabbids 2
– Naruto: Rise of a Ninja
– Naruto: The Broken Bond
– James Cameron's Avatar: The Game (Wii version)
– Prince of Persia: The Forgotten Sands (Wii / PSP version)
[jadepack.zip](https://xentaxbackup.github.io/file/6501_jadepack.zip)
## Post #2
- Username: jadebin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 25, 2015 9:23 pm
- Post datetime: 2015-12-25T13:26:48+00:00
- Post Title: JADE Game Engine .bin file pack-tool v1.0

Thanks.

In Beyond Good & Evil, the LZO block header doesn't include the filesize field. So it's this:

```
{
//    uint32 filesize;
    uint32 unpacked_block;
    uint32 packed_block;
} header;

```


Another point of note: In the original protected BG&E PC CD version the ff8*.bin files look to be encrypted or something up until offset 0x7d000 in each file. The GOG version is clean.

I've uploaded the ZIP elsewhere to make it easier for people to download without having to register here:
[http://www.filedropper.com/jadepack](http://www.filedropper.com/jadepack)
[http://s000.tinyupload.com/index.php?fi ... 9214962880](http://s000.tinyupload.com/index.php?file_id=52686641589214962880)
[http://www.filehosting.org/file/details ... depack.zip](http://www.filehosting.org/file/details/530415/jadepack.zip)
[http://www.megafileupload.com/e83x/jadepack.zip](http://www.megafileupload.com/e83x/jadepack.zip)
## Post #3
- Username: Turbogoat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 19, 2011 8:48 pm
- Post datetime: 2019-03-27T19:03:25+00:00
- Post Title: JADE Game Engine .bin file pack-tool v1.0

> Reply from jadebin ↑Fri Dec 25, 2015 9:26 pm at Fri Dec 25, 2015 9:26 pm
>
> 
Thanks.

In Beyond Good & Evil, the LZO block header doesn't include the filesize field. So it's this:
Code: Select allstatic struct header
{
//    uint32 filesize;
    uint32 unpacked_block;
    uint32 packed_block;
} header;


Another point of note: In the original protected BG&E PC CD version the ff8*.bin files look to be encrypted or something up until offset 0x7d000 in each file. The GOG version is clean.

I've uploaded the ZIP elsewhere to make it easier for people to download without having to register here:
http://www.filedropper.com/jadepack
http://s000.tinyupload.com/index.php?fi ... 9214962880
http://www.filehosting.org/file/details ... depack.zip
http://www.megafileupload.com/e83x/jadepack.zip

All prince of persia games .bin's generate empty files. Commenting out uint32 filesize; makes the whole compilation fail. Even if you comment out all the leftover code that uses .filesize after compilation it still fails. Could you please compile a working .exe for POP?
## Post #4
- Username: GameReader
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 02, 2023 6:43 am
- Post datetime: 2023-03-02T01:01:37+00:00
- Post Title: JADE Game Engine .bin file pack-tool v1.0

> Reply from Turbogoat ↑Thu Mar 28, 2019 3:03 am at Thu Mar 28, 2019 3:03 am
>
> 
All prince of persia games .bin's generate empty files. Commenting out uint32 filesize; makes the whole compilation fail. Even if you comment out all the leftover code that uses .filesize after compilation it still fails. Could you please compile a working .exe for POP?

FYI for future viewers (like me), this QuickBMS script worked for me on a newer Jade engine game, unlike the above Jadepack program: [viewtopic.php?p=56476#p56476](https://forum.xentax.com/viewtopic.php?p=56476#p56476)
Hope it helps someone.
