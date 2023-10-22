## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-10T23:20:52+00:00
- Post Title: DDS image?

hey i can't figure out how to view these images, it seems my dds plugins dont work on it? i tried modifying the header to DXT, to 1, 3, and 5. but had no result.

i tried some of the other compressions like ARGB32, 16.. p8 but nothing seems to display the image properly

anyone wanna take a crack at it?
[http://www.tjbp.net/upload/Bandages.zip](http://www.tjbp.net/upload/Bandages.zip)
## Post #2
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-11T00:47:59+00:00
- Post Title: DDS image?

Look at the bytes. Instead of RGB+Alpha there are RGB RGB alpha alpha or 6 bytes + 2 instead of 3 bytes + 1 maybe some next-gen stuff or it pairs the 32 bit argb into 64 bit. Anyway it looks to be argb and not DXT. The 0x00527000.dds file shows it is 256X512, pairing would extend the 256 to 512 making the texture 512x512

 Don't know where that header came from though. Must be some new stuff.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-11T02:30:28+00:00
- Post Title: DDS image?

oh wow, well thankyou for solving the problem ^_^

these are indeed from a new gen system (XBOX360), I was looking into modding the texture, so i pulled all the textures out of this xboxlive update file with my hex editor.

But was stumped when I was unable to figure out this mystery format >_<

anyway here are the other extracted textures, incase you were interested in what I got. theres still 1-3 textures missing, since I got a hex-head-ache after a few hours :p
[Download bandages.rar](http://putstuff.putfile.com/78505/7339454)
## Post #4
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-11T04:40:54+00:00
- Post Title: DDS image?

I see some say unswizzled and are correct DDS files. Did you do that? Did you create a tool to convert to standard DDS?
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-11T16:42:55+00:00
- Post Title: DDS image?

i'm not a programmer, but what i have done is imported a swizzled image, and ran a paintshop script to unswizzle it, painshop, then compresses it again, using a standard DDS header
## Post #6
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-11T22:29:51+00:00
- Post Title: DDS image?

Nice but I don't have Paintshop, sounds like a great feature though. You may not be a programmer but if you can manipulate your graphics program to unravel these textures that's a great talent. Makes me wonder if other game textures can be edited in a similar manner. 


I don't suppose Photoshop does that?
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-12T00:25:42+00:00
- Post Title: DDS image?

not that i'm aware.

this feature in paintshop allows me to record every modification i make to an image. so i can batch convert, or unswizzle dds images at once. ^_^ still takes longer then a conventional program which would arrange the bytes properly

heres a graphical repsentation of what paintshop does. is it was done via a code converter, it have 10 done by then.
## Post #8
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-15T22:24:06+00:00
- Post Title: DDS image?

If you can tell me the arrangement I should be able to get you something useable. I don't know about the indexed DXTs but the others should be doable.
 I looked at the byte arrangement but didn't see the pattern. If you can tell me how many bytes to read left to right or how many to read top to bottom to get where you need to be.
## Post #9
- Username: Mike
- Rank: n00b
- Number of posts: 10
- Joined date: Sun May 13, 2007 3:46 am
- Post datetime: 2007-05-17T14:40:13+00:00
- Post Title: DDS image?

The format is 64bit ARGB.
It you have photoshop, just open it as "raw" with following parameter.
-Width, Height: 128 pixels
-Depth: 16bit (per channel)
-ByteOrder: Mac (big endian)
-Header: 128byte
[0x00B20000.jpg](https://xentaxbackup.github.io/file/1160_0x00B20000.jpg)
## Post #10
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-18T05:15:19+00:00
- Post Title: DDS image?

WOW WOW WOW

awesome man, i had almost given up on this. i can't believe it was that simple, as 64bit!! haha

also here is an example of a common pixel arrangment for unswizzling using paintshop
[](http://img132.imageshack.us/img132/56/unswizzle256x256azq9.jpg)
[](http://img261.imageshack.us/img261/9929/unswizzle256x256bqb1.jpg)
[](http://img515.imageshack.us/img515/2050/unswizzle256x256ctz9.jpg)
[](http://img176.imageshack.us/img176/7555/unswizzle256x256dnw5.jpg)
[](http://img201.imageshack.us/img201/9462/unswizzle256x256eiu8.jpg)



clearly there is an algo to this all, so before coding something my paintshop can do.. it might be wise to crack this first
## Post #11
- Username: kaczhou
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2007 3:38 pm
- Post datetime: 2007-05-22T01:58:08+00:00
- Post Title: DDS image?

chinese word ?


 I speak a little  English
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-23T01:45:24+00:00
- Post Title: DDS image?

right....

anyway this swizzling seems to be present on 3/5 xbox360 games using DDS texture formats
