## Post #1
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-20T21:28:39+00:00
- Post Title: Just Dance 2014 (png.ckd/tga.ckd XBOX 360)

Hello, i've recently extracted Xbox files from Just Dance 2014, i've tried to removing the first 44 bytes and renaming to .dds but it doesn't have a DDS header if you check in a hex editor, so i don't know what format it is. I will send an example of a .tga.ckd file to see if anyone can help me.  File: [http://www28.zippyshare.com/v/NSN2YXX1/file.html](http://www28.zippyshare.com/v/NSN2YXX1/file.html)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-20T23:00:24+00:00
- Post Title: Just Dance 2014 (png.ckd/tga.ckd XBOX 360)

000000ea.png (111.92 KiB) Viewed 202 times


512x512 dxt5 typical X360 big-endian data with 360 tiling
96 byte header with light obfuscation regarding the width and height, need more samples to reveal how it is stored
## Post #3
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-21T08:36:59+00:00
- Post Title: Just Dance 2014 (png.ckd/tga.ckd XBOX 360)

> Reply from AceWell
>
> 000000ea.png
512x512 dxt5 typical X360 big-endian data with 360 tiling
60 byte header with light obfuscation regarding the width and height, need more samples to reveal how it is stored
 Do you also need an example of .png.ckd? If yes, then [http://www105.zippyshare.com/v/yTmpGn9O/file.html](http://www105.zippyshare.com/v/yTmpGn9O/file.html) By the way, how can i open these and convert to png how you did?
## Post #4
- Username: diimashups
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jun 17, 2016 5:00 am
- Post datetime: 2017-06-21T13:48:53+00:00
- Post Title: Just Dance 2014 (png.ckd/tga.ckd XBOX 360)

> Reply from AceWell
>
> The attachment 000000ea.png is no longer available
512x512 dxt5 typical X360 big-endian data with 360 tiling
60 byte header with light obfuscation regarding the width and height, need more samples to reveal how it is stored Hi, i've already figured out how to open the files in Noesis, but whenever i open a image (a pictogram) from the database files it gets cropped to 128x128, the original should be 256x256, and it's not a full texture.
[Screenshot_8.png](https://xentaxbackup.github.io/file/13018_Screenshot_8.png)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-21T16:53:07+00:00
- Post Title: Just Dance 2014 (png.ckd/tga.ckd XBOX 360)

how do you know which ones are "png.ckd" or "tga.ckd"? both of your samples have a dat extension   
i need more than the 2 samples to make a script though, maybe 10-15 would be good.
