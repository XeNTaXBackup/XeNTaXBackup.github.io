## Post #1
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2016-03-25T09:03:00+00:00
- Post Title: picture compression algo help

Hi, does anybody have any idea what this compression can be?

What I found:
 - lossless image compression
 - word at offset 8 is x resolution
 - word at offset 10 is y resolution
 - packed data starts at 0x18

In the attachment are 3 files, packed , unpacked and bmp of a small black picture.

thank you in advance

[http://www75.zippyshare.com/v/7xv1pMrV/file.html](http://www75.zippyshare.com/v/7xv1pMrV/file.html)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-25T11:32:55+00:00
- Post Title: picture compression algo help

reminds me of pcx:

0x0080   F0 03 F0 01 F0 03 F0 03  F0 01 F0 03 F0 03 F0 01   ð.ð.ð.ð.ð.ð.ð.ð.

How did you create that black.packed file?
## Post #3
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2016-03-25T12:03:12+00:00
- Post Title: picture compression algo help

I did not create black.packed  it's as I got it.

There is no problem converting unpacked version to bitmap, that's what I did, compression is the problem.

I tought of RLE at first, but it does not seem to be....
## Post #4
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2016-03-29T10:01:34+00:00
- Post Title: picture compression algo help

Hmm, where is this used? some game art?
Did they not supply an encoder as I gather your intent is to understand it and create own encoder than try decode them since got tool for it already.

If you have additional compressed files to compare than just this one with blank data could confirm more the layout.
## Post #5
- Username: peter2005
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Mar 25, 2016 3:26 pm
- Post datetime: 2016-03-31T19:24:18+00:00
- Post Title: picture compression algo help

yes, it's a game art 

You are right, there is no public encoder, but I hope it's some sort of known compression. 

Nonblank example file here:

> http://www27.zippyshare.com/v/D8cMx3a1/file.html
## Post #6
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2016-04-01T16:10:19+00:00
- Post Title: picture compression algo help

Looks like custom RLE method with similarities to PCX yet not entirely, else holds 24 bit color data between rle packets.
