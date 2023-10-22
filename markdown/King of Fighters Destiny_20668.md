## Post #1
- Username: wrathofgod
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 15, 2019 7:54 am
- Post datetime: 2019-06-15T00:17:57+00:00
- Post Title: King of Fighters Destiny

There's a very interesting Chinese only mobile game based on King of Fighters. The sprites are the main attraction here; A lot of sprites from the old school days of KoF were upscaled and shaded to be more modern looking, the results are amazing and I wanted to have them for some projects I'm working on. It took me a while to figure out how to rip the graphics though, as most of them are PKM encoded, but I found out how to convert them simply by removing the garbage data from the beginning of them using a hex editor and running the file through etc1tool, part of the Android development SDK.

Most of the images convert just fine after removing the garbage, but some of them have a peculiar string of text at the start saying "PVR!", which lead me to believe that it was just a PVR file that can be converted using PVRTexToolCLI, but it acts as though it doesn't recognize it. I think it's because it's been encoded somehow, then converted into a PVR file, but I'm no expert on this stuff.

[https://ibb.co/h8ZLSzh](https://ibb.co/h8ZLSzh)

I'm pretty much at the end of my rope here and I've been researching this all day. These PVR files contain important frames of animation (mainly the idle and walking animations) and it makes most of the character near on useless because those are vital animations. If anybody has any suggestions for me, it would be very greatly appreciated. Here's a sample file of a .DT0 that has the PVR! header in hex, like the image above.

[https://gofile.io/?c=4vtO3b](https://gofile.io/?c=4vtO3b)

(If anybody wants me to upload these files to somewhere else, let me know.)
## Post #2
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2019-06-22T10:42:56+00:00
- Post Title: King of Fighters Destiny

Looks like raw RGBA image data (colours are a bit wonky, so maybe this is YUV, or maybe it's supposed to use palette lookup?): [https://cdn.discordapp.com/attachments/ ... estiny.png](https://cdn.discordapp.com/attachments/449840053049360388/591938725852741642/kof-destiny.png)

Offsets in header:
0xD7: Width (1024)
0xDB: Height (1024)

The other data in the header is probably a list of coordinates for each frame in the sprite sheet. And this particular sprite sheet is a bit weird, the idle and running animations are scaled up.

Edit: If you're looking for the raw graphical assets, then it looks like someone did that here: [http://mugenguild.com/forum/topics/the- ... 817.0.html](http://mugenguild.com/forum/topics/the-king-of-fighters-destiny-android-graphics-rip-182817.0.html)

The way it's stored seems a bit unfortunate. The idle and running animations are all lossless but scaled up, and the other sprites are stored in what looks like DXT (which is lossy), so it's all lossy in one way or another.
