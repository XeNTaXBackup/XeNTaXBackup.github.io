## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-08-17T01:21:19+00:00
- Post Title: Converting argb1555 to RGBA32

I have some idea what the format is: 5 bits per pixel, with 1 bit for alpha.
I have to extract the RGBA values from each byte accordingly.

Assuming two bytes B1 and B2 side by side, assuming the following pattern

```

```


So I'd just do some bitmasking

A: B1 & 0b10000000
R: B1 & 0b01111100
G: B1 & 0b00000011 | B2 & 0b11100000
B: B2 & 0b00011111

Or basically

R = B1 & 0x7C
G = B1 & 0x03 | B2 & 0xE0
B = B2 & 0x1F

But then how should I be shifting the bits to get the correct value?

Here is an example of a 640x480 image encoded in ARGB1555
[pic219.zip](https://xentaxbackup.github.io/file/6557_pic219.zip)
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-17T04:32:21+00:00
- Post Title: Converting argb1555 to RGBA32

rgba = rapi.imageDecodeRaw(sourceData, width, height, "a1r5g5b5")
## Post #3
- Username: finale00
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-08-17T04:57:44+00:00
- Post Title: Converting argb1555 to RGBA32

Here is a lovely right-click context tool script that will let you decode images from a simple format string:

[http://code.google.com/p/noesis-plugins ... wdecode.py](http://code.google.com/p/noesis-plugins-official/source/browse/trunk/Rich/tool_rawdecode.py)

It looks like your image is actually b5g5r5p1, by the way. The p is pad, because that alpha bit is otherwise always 0 in that image, so you just throw it away.
