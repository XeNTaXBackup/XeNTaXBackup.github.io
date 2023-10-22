## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-03-25T00:35:37+00:00
- Post Title: (NDS) Shin Megami Tensei: Strange Journey CMP files

These are image and texture files used by SMT: Strange Journey. Uncertain of the format and seem compressed.
[CMPs.rar](https://xentaxbackup.github.io/file/2885_CMPs.rar)
## Post #2
- Username: Barubary
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2009 7:21 pm
- Post datetime: 2010-03-29T22:39:01+00:00
- Post Title: (NDS) Shin Megami Tensei: Strange Journey CMP files

The files are compressed with the DS's default RLE compression, which you can decompress with [DSDecmp](http://www.propl.nl/random/DSDecmp.zip).
The given files are all archives containing image files (GFNT) in a format [TiledGGD](http://code.google.com/p/tiledggd/) can display by default. (although the format description in Bindings.xml says it's a Space Puzzle Bobble format, it seems to work fine for these as well)
## Post #3
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-03-31T06:27:29+00:00
- Post Title: (NDS) Shin Megami Tensei: Strange Journey CMP files

Thanks! Can the archives be dumped of content or just by hex editor copy and paste? Either/or works.

I've noted in the enemy FBINs there are GFAN, which I believe are animation, and GTSF, which serve an unknown purpose.
## Post #4
- Username: Barubary
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jun 15, 2009 7:21 pm
- Post datetime: 2010-03-31T22:43:44+00:00
- Post Title: (NDS) Shin Megami Tensei: Strange Journey CMP files

You could manually extract the files easily, but [this tool](http://www.propl.nl/random/NinUnpack.zip) will dump them for you. (drag & drop any number of FBIN files onto it, or run from the command line with any number of FBIN as arguments. Also works for NARC files.) (windows only)

GTFS probably store the data about the poses of the sprites, similar to NCER files.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2010-04-01T07:48:53+00:00
- Post Title: (NDS) Shin Megami Tensei: Strange Journey CMP files

Thanks! I'm able to view all graphics now for SMT: SJ, some of the GFNT files were compressed and had to change the extension to get the output file, works really good. And I believe you are right about the GTFS files.
