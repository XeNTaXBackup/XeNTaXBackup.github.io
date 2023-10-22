## Post #1
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-18T00:01:23+00:00
- Post Title: Real Racing 3 (Android) .dds

I have recently started looking into files from the smartphone game Real Racing 3. I have managed to extract all textures in .dds.z format (it's just using deflate compression), but the .dds files themselves are a bit peculiar. Apparently they don't use  the usual DXT compression.

This is what I managed to get out of one file:


And this is what it's supposed to look like (notice the colors on the car):


Any help would be appreciated.
I can send some samples via PM.
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-18T00:23:08+00:00
- Post Title: Real Racing 3 (Android) .dds

Did you try using a hex editor on the dds file to change the DXT format?

Or you can send me one the dds files and I'll play around with it.

-- MDA
## Post #3
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-18T09:30:30+00:00
- Post Title: Real Racing 3 (Android) .dds

> Reply from MichaelDarkAngel
>
> Did you try using a hex editor on the dds file to change the DXT format?
I haven't tried that, but I don't think it would help much in this case - I forgot to mention that the dds files throw an error on every dds viewer/editor I've tried.

> Reply from MichaelDarkAngel
>
> Or you can send me one the dds files and I'll play around with it.
I've sent you some samples via PM.
## Post #4
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-18T10:59:24+00:00
- Post Title: Real Racing 3 (Android) .dds

Any chance you can provide the raw image data.  Whatever you are using to export may be pulling the data from the wrong offsets.

The reason you can't open the dds file with anything is due to an incorrect DDS header.  Once I fixed the FourCC I was able to open it, however it looked much like the image in your screenshot.  Which leads me to believe there may be image data missing.

-- MDA
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-18T13:20:28+00:00
- Post Title: Real Racing 3 (Android) .dds

I found out what the problem was - the file isn't corrupt, it just uses a strange texture compressor

Turns out some files from the game (usually car logos, wheels etc) use RGBA4444 and they open just fine. On the other hand, large textures (vehicle paintjobs, track textures etc) use an odd texture compression called ETC (Ericsson Texture Compression). You can tell them apart by finding ETC in the header (the working DDS files don't have it.)
[http://en.wikipedia.org/wiki/Ericsson_T ... ompression](http://en.wikipedia.org/wiki/Ericsson_Texture_Compression)
## Post #6
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2014-01-18T13:45:34+00:00
- Post Title: Real Racing 3 (Android) .dds

Was hoping it wasn't that.  But, since you have other textures exporting fine, that is most likely the issue.

Good Luck,

-- MDA
## Post #7
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-18T14:26:56+00:00
- Post Title: Real Racing 3 (Android) .dds

So I researched the format and I found out about a tool called Mali Texture Compression Tool. It used ETC-supporting formats like .pkm and .ktx, so I took the data from the .dds file, attached it to a .pkm header... et voilà!

[](http://imgur.com/SeB9CVp)

Unfortunately the program won't let me export the texture to any common format easily.

Notetheless, thanks MichaelDarkAngel for wanting to help!
