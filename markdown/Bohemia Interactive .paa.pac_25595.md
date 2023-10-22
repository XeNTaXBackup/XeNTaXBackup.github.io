## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-07-07T16:14:11+00:00
- Post Title: Bohemia Interactive *.paa/*.pac

[https://mega.nz/folder/ULQkgZxa#F3-8iP6SJ7yJqGQDzYra3A](https://mega.nz/folder/ULQkgZxa#F3-8iP6SJ7yJqGQDzYra3A)

It seems that Bohemia Interactive *.paa/*.pac files are encrypted or compressed
I used TextureFinder, but it's impossible to get proper textures
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-07T22:18:18+00:00
- Post Title: Bohemia Interactive *.paa/*.pac

Yes, they can be compressed with RLE, LZO and LZSS (depending on type).

Format is known and it's described here [http://wiki.xentax.com/index.php/Bohemi ... ve_PAA_PAC](http://wiki.xentax.com/index.php/Bohemia_Interactive_PAA_PAC)

Your samples can be viewed/converted with Texture Viewer and Pal2PacE from BI Tools.
