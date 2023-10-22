## Post #1
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-03-07T19:45:08+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

I am currently working on the compression that is used on some of the files in KOC2 on the PS2, and I am pretty sure it uses a form of LZSS and possibly RLE as well in the compression.  I noticed that the first byte is 0xFF, which should mean a run of eight bytes uncompressed, after that, it gets a little fuzzy, and I can't quite figure out the bit-scheme that it uses.  Hopefully someone like aluigi can help out on this, but I have both a compressed and uncompressed file so it can be found quicker.

Here is a screenshot of the start of each in the hex editor -

 

I've dumped the texture in memory, and the total uncompressed size is the same as the uncompressed size shown in the archive, as well as having a few areas where you can see that it is in fact the uncompressed file.  This is what the texture looks like -



picture.png (97.66 KiB) Viewed 260 times


Link Removed, No Longer Needed

Thanks for anyone's help that wants to help out.
## Post #2
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-03-09T13:35:46+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

It's just LZSS. I made a tool to decompress the files.
[http://sktest.aruarose.com/TM2Decompress.7z](http://sktest.aruarose.com/TM2Decompress.7z)

The archive also contains a fixed File00000000, as the provided one was too large.
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-03-10T18:12:36+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

Thank you SO much for this.  I guess the source code I had for LZSS was wrong, because I tried just the standard LZSS, or at least the source code I had, and it would never work correctly.  In fact, the LZSS in quick BMS wouldn't work either, so I am not sure if it is standard LZSS or not.  You don't happen to have the compression source code for this do you.  I can work with decompressed files, but would be so much better if I could recompress them.  Thanks again!!!

I'll be using the source code you provided in my program.

BTW, for credits, do you want me to say Sir Kane, or something else?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-10T18:36:11+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

in quickbms I guess it's enough to specify the 0xff initializer:

```
comtype lzss "12 4 2 2 0xff"
```
## Post #5
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-03-10T18:39:26+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

> Reply from aluigi
>
> in quickbms I guess it's enough to specify the 0xff initializer:
Code: Select allcomtype lzss "12 4 2 2 0xff"
That's what my problem was, and probably the problem I had with the source code I had.  Thanks for pointing that out.  I'll have to see then how to do the compression from that.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-03-10T20:36:58+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

quickbms does it automatically while reimporting I guess.
anyway you can force it:
comtype lzss_compress "12 4 2 2 0xff"
## Post #7
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-03-10T20:54:35+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

> Reply from aluigi
>
> quickbms does it automatically while reimporting I guess.
anyway you can force it:
comtype lzss_compress "12 4 2 2 0xff"
Yeah, there are other files, not TIM2, that are compressed, and they don't always necessarily start with 0xFF, but his code decompresses them all accurately.  I am in the middle of changing his code to accept an input buffer, and use an output buffer, instead of file streams, because I don't want to be reading and writing temp files for the buffer for my program, although his code as it is now is good for writing out an uncompressed file stream, which I can use for extracting out uncompressed files from the main archive, other than it takes a file stream input, I will still have to change it to accept a regular input buffer from my program.  I will most likely add the functionality I need and make it into a dll file to use in my program.  I'll have to figure out the recompression scheme later on, but for now, being able to decompress the info is good enough, I can allocate space in the main archive for larger files already, so replacing them with uncompressed files will work, but isn't the best way to do it.
## Post #8
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-03-11T17:43:33+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

Compared to like the decompressor found here: [http://my.execpc.com/~geezer/code/lzss.c](http://my.execpc.com/~geezer/code/lzss.c), the only changes are the length being stored in the upper four bits/the rest of the offset being in the lower four bits and the -1 on the position when reading from the buffer. So it might be easy to take the compression code from there and make it work the same.
## Post #9
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-03-11T21:14:47+00:00
- Post Title: King of Colosseum II PS2 - A new LZSS/RLE type compression format

> Reply from Sir Kane
>
> Compared to like the decompressor found here: http://my.execpc.com/~geezer/code/lzss.c, the only changes are the length being stored in the upper four bits/the rest of the offset being in the lower four bits and the -1 on the position when reading from the buffer. So it might be easy to take the compression code from there and make it work the same.
Ok, thanks.
