## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-01-04T20:36:34+00:00
- Post Title: Time Crisis 1 [PSOne] .ulz (LZR?)

Hello there again, I've been trying to translate Time Crisis 1 for PSOne with the help of a friend, this friend managed to break all the compression formats for this game... except for one.

[Here's the file so you can check it out.](http://www.sendspace.com/file/ncc3db)

Then again, I don't know anything about the system, only that what is depacked are TIM files, unknown if they have a CLUT or not. (We've found some CLUTless TIMs on the format). so here's what the friend had to say:
The compression is some sort of LZR.

> First four bytes mark ULZ+0x1A
>
> Next, 2 with zeroes
>
> The next one is supposedly the compression format. The rest of the files is 2, but on these two is 0.
>
> Next byte tells the amount of bits used to compress data.
>
> 4 bytes for the offset of uncompressed data, next 4 bytes for the compressed data.
>
> Next is the compression flags: For compression, the flags are read first; if it's 1, you must take one uncompressed byte, from where one of the offsets was targeting, 0 means two bytes of compressed data.
>
> The last part is where the system is incorrect.

I hope someone can help me out.
## Post #2
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-01-05T11:57:47+00:00
- Post Title: Time Crisis 1 [PSOne] .ulz (LZR?)

The contents of this post was deleted because of possible forum rules violation.
