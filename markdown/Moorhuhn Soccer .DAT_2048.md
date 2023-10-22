## Post #1
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T15:26:23+00:00
- Post Title: Moorhuhn Soccer *.DAT

Hi again    

[http://rapidshare.de/files/29991733/M1f.zip.html](http://rapidshare.de/files/29991733/M1f.zip.html)

PXR , Mr.Mouse , Watto thanks
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-19T16:00:06+00:00
- Post Title: Moorhuhn Soccer *.DAT

Are you sure thats a game file? =X

for me it looks like a Compressed Shockwave Flash file.
## Post #3
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2006-08-19T16:20:52+00:00
- Post Title: Moorhuhn Soccer *.DAT

Sure .. this file from this game 
[mr.PNG](https://xentaxbackup.github.io/file/798_mr.PNG)
## Post #4
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-19T16:52:00+00:00
- Post Title: Moorhuhn Soccer *.DAT

Could the game actually use Flash files for GFX? =O

just a thought..... can someone else get into this and either
slap me on the nose or confirm my Flash theory :X
## Post #5
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-19T16:52:22+00:00
- Post Title: Moorhuhn Soccer *.DAT

> Reply from Strobe
>
> Are you sure thats a game file? =X

for me it looks like a Compressed Shockwave Flash file.
Looks indeed like a Compressed Shockwave Flash file.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-19T16:53:52+00:00
- Post Title: Moorhuhn Soccer *.DAT

* PXR comes to save my day * ;D
## Post #7
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2006-08-19T17:52:43+00:00
- Post Title: Moorhuhn Soccer *.DAT

And actually, from offset 8; there's zlib compressed data to the end of the file. I thought I could have written an BMS-script for this, but it wasn't possible (or is it Mr.Mouse?).
## Post #8
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-08-19T18:12:34+00:00
- Post Title: Moorhuhn Soccer *.DAT

I loaded the CWS file into IExplorer. dumped the RAM 
so that the Flash file would be decompressed.

running jaeder naub over the dump.
the output was around 400 small JPEG files.

however.....the JPEG files has fine headers, but after about 64 bytes of
data is scrambled. but im positivly sure this is the main use for the file,
i belive they are using the this as graphic package.

And i think these are real JPEGs, just that they have been extra compressed.
(especially as they had no gain at all when i zipped them). they have both correct Start and End headers as real JPEG files. the image data though
not Standard.
[cwsripped.zip](https://xentaxbackup.github.io/file/802_cwsripped.zip)
