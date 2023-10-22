## Post #1
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2021-06-29T02:01:43+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

[https://mega.nz/file/2OZ2QRKZ#y7jp37uk4 ... onOOK1w4Xc](https://mega.nz/file/2OZ2QRKZ#y7jp37uk4lmZ6AkDNGAv9Lg3vTm4J6IIGonOOK1w4Xc)

Another idea I had was to extract player pictures from NHL Faceoff 2001 via a tool, but I am not sure which tool to use, as they are inconveniently placed inside a .dat file, which I never know how to open. I had this exact problem with Madden NFL as well. Does anyone know how to open these pesky files?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-05T13:18:11+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

Well, you can use TextureFinder to see images [https://i.imgur.com/gKgtFlw.png](https://i.imgur.com/gKgtFlw.png)

And the file format of this DAT file is described here [http://wiki.xentax.com/index.php/NHL_FaceOff_2001_DAT](http://wiki.xentax.com/index.php/NHL_FaceOff_2001_DAT)
## Post #3
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2021-07-05T18:14:46+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

Thanks, but how am I supposed to figure out the palettes for any of the other images?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-05T18:45:02+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

> Reply from jlnhlfan ↑Tue Jul 06, 2021 2:14 am at Tue Jul 06, 2021 2:14 am
>
> 
Thanks, but how am I supposed to figure out the palettes for any of the other images?

Each entry starts with the "SolWorks Tex" string. You can add 96 bytes to this string's offset and you'll get palette offset. 
Easiest way to get those offsets is to use Hex Workshop for searching and just do some calculations.
## Post #5
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2021-07-08T16:01:38+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

> Reply from ikskoks ↑Tue Jul 06, 2021 2:45 am at Tue Jul 06, 2021 2:45 am
>
> 
jlnhlfan wrote: ↑Tue Jul 06, 2021 2:14 am
Thanks, but how am I supposed to figure out the palettes for any of the other images?


Each entry starts with the "SolWorks Tex" string. You can add 96 bytes to this string's offset and you'll get palette offset. 
Easiest way to get those offsets is to use Hex Workshop for searching and just do some calculations.

Still kinda confused.
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-09T08:38:23+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

> Still kinda confused.

Sorry, you should add 95 instead of 96, my mistake.
Here is detailed instruction how to proceed.

1. Open DAT file in Hex Workshop
2. Search for "SolWorks Tex" strings with CTRL+F
3. Add 95 to each offset you find
4. Put that value in TextureFinder

So the first four would be:
1. 0 + 95 = 95
2. 18432 + 95 = 18527
3. 36864 + 95 = 36959
4. 55296 + 95 = 55391


And here how it looks for second image [https://i.imgur.com/aYPVdLc.png](https://i.imgur.com/aYPVdLc.png)
## Post #7
- Username: jlnhlfan
- Rank: beginner
- Number of posts: 38
- Joined date: Thu Dec 10, 2020 4:00 am
- Post datetime: 2021-07-09T14:48:59+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

Strange. The next offset I find is 4800.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-09T17:15:06+00:00
- Post Title: NHL Faceoff 2001 PMUGS.DAT

It's not 4800, it's 0x4800 which is exactly the same as 18432 in DEC.

You can use online converter for this [https://www.rapidtables.com/convert/num ... cimal.html](https://www.rapidtables.com/convert/number/hex-to-decimal.html)
