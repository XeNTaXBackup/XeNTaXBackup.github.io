## Post #1
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-11-29T11:24:55+00:00
- Post Title: SkyRoads compressed levels

Hi all,

I'm trying to reverse engineer the compression algorithm used by the DOS game SkyRoads to compress its levels.  I've attached four example files, both compressed and decompressed.  The decompressed versions were obtained from a DOSBox memory dump, so there are extra trailing 0x00 bytes.

The first 222 bytes of the compressed files [are known](http://www.shikadi.net/moddingwiki/SkyRoads_level_format) and are unrelated to the compression, so the compressed data starts at offset 222 in a level file.

Each file has a "decompressed size" field stored in another file (the archive file these level files were extracted from.)  These values are: road1=770, road2=1610, road6=672, road28=3276.  The output data seems to stop after this many bytes plus 0x2C, so I am not certain whether the first 0x2C bytes in the decompressed file are actually part of the decompressed data.  I included it because it is different for each level so it may be relevant.

If you wish to experiment further, you can [download the full version](http://www.classicdosgames.com/game/SkyRoads.html) (it's been released as freeware), open roads.lzs in a hex editor, go to offset 0x02CB and you will be at the start of road1.lzs.  (So you will want to seek a futher 222 bytes to offset 0x03A9 to get to the start of the compressed level data.)  This is the first level, and the one loaded by the game if you launch it and keep bashing the Enter key until you're in a level.

If you're using the DOSBox debugger, you can grab a dump of the decompressed level by breaking into the debugger as soon as the level starts and running the command "memdumpbin ds:1600 1000".  This is how I produced the attached files containing the decompressed level data.

If anyone is able to take a look at this and see if they can work out what the compression algorithm might be, I would really appreciate it!  The file extensions suggest something like LZSS but it doesn't look like this to me, and none of the standard LZSS decompressors expand it.
[skyroads-decompressed-examples.zip](https://xentaxbackup.github.io/file/6809_skyroads-decompressed-examples.zip)
## Post #2
- Username: Tahg
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 03, 2013 9:26 am
- Post datetime: 2013-12-06T10:07:00+00:00
- Post Title: SkyRoads compressed levels

This uses a simple bit aligned algorithm. Define getbits(x) to get x bits from a stream of bytes, where the msb of each source byte is the first bit read, and the lsb of each destination value is the last bit read.  The following is rough pseudocode to decompress the stream, but should be sufficient.

```
width2 = getbyte()
width3 = getbyte()
index = 0
while (index < length) {
  if (getbits(1) == 0) {
    dist = 2 + getbits(width2)
    count = 1 + getbits(width1)
    copy count bytes from index - dist to index, add count to index
  }
  else if(getbits(1) == 0) {
    dist = 2 + (1 << width2) getbits(width3)
    count = 1 + getbits(width1)
    copy count bytes from index - dist to index, add count to index
  }
  else copy 8 bits from input to index, add 1 to index
}

```
## Post #3
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-12-07T03:23:43+00:00
- Post Title: SkyRoads compressed levels

Fantastic, many thanks!  I had to adjust the code a little - where you have "count = 1 + getbits..." I had to change it to "2 +" and then it worked perfectly.

Thanks to this, hopefully it won't be too long now before SkyRoads levels can be edited in Camoto!
## Post #4
- Username: Tahg
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Dec 03, 2013 9:26 am
- Post datetime: 2013-12-07T13:17:41+00:00
- Post Title: SkyRoads compressed levels

Ah yes, I even manually checked the first few bytes, but apparently even with that I still got the post wrong.  Glad you figured out my mistake.
## Post #5
- Username: Malvineous
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Oct 16, 2010 12:34 pm
- Post datetime: 2013-12-07T23:30:20+00:00
- Post Title: SkyRoads compressed levels

No worries, thanks again.  I've put your code and an explanation in the [SkyRoads compression](http://www.shikadi.net/moddingwiki/SkyRoads_compression) article on the ModdingWiki.  I've also found that the image files use the same compression algorithm, so I've been able to start reverse engineering some other files too.
