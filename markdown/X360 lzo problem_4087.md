## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-01-26T12:47:59+00:00
- Post Title: X360 lzo problem

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-26T14:45:02+00:00
- Post Title: X360 lzo problem

here works perfectly:

```
idstring XPR2
get FILE_SIZE long
get HEADER_SIZE long
for FILE_OFFSET = 12 < HEADER_SIZE
    getdstring NAME 0x74
    get OFFSET long
    get SIZE long
    get ZSIZE long
    clog NAME OFFSET ZSIZE SIZE
    savepos FILE_OFFSET
next
```
I guess the problem was in how you assigned USIZE
## Post #3
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-01-26T23:02:31+00:00
- Post Title: X360 lzo problem

Thank you for the quick reply!
I know I can extract them with BMS but the result image are wrong!?
In the rar file are those original image, you can compare them and see only about first 100 bytes are wrong? Why!?
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-01-28T17:54:58+00:00
- Post Title: X360 lzo problem

I tested that XPR Express in XP and win98, no one can extract the images! But Xbox360 can display the images inside the archive correctly!

I wonder if aluigi or somebody else could take a look and that lzo method? Maybe it's a little modify one 'cause only the first few (~100) bytes are not correct!

Thanks
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-28T21:09:33+00:00
- Post Title: X360 lzo problem

the difference with the original is in the format in which the image is saved.
the original is a tga while the archived one is raw plus a "pseudo-header" of 0x80 bytes, so it's obvious that it's different
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2010-02-05T09:38:25+00:00
- Post Title: X360 lzo problem

Just come over to thank you for the help!

And actually the uncompressed data are not always raw image! It depand on the source!
If the source is DDS, it will become 0x80 "pseudo-header" + swizzled DDS data.
if the source is TGA, result in 0x80 "pseudo-header" + swizzled RAW data.
