## Post #1
- Username: hatoving
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 18, 2023 10:01 am
- Post datetime: 2023-07-18T02:09:35+00:00
- Post Title: Textures from SIMULACRA

Hi, everyone! I'm pretty new to ripping textures from PC games, so if something seems utterly dumb and/or very simple to you in this post, be aware that I have no zero experience in all of this, so I apologize in advance.

There's a game called SIMULACRA that's made in libGDX (coded in Java I presume). 

The weird thing about this game is that while you can easily rip the video and audio files from the "support.assets" file, the same can't be said for the texture files.

Weirdly enough, they all are in a format called ".texture", and I have no idea what to do with it if I want to rip the original graphic out of it. I searched around every single corner of the internet, and I basically found nothing. I'm not sure if this is libGDX's way of securing texture files, or if it's a custom thing, or something like that.

(Note, the same can be said for Sara is Missing, SIMULACRA's predecessor. I took a gander at another game that was made using libGDX and strangely, that game just used normal .png files.)

Here's an .texture file if you want to take look for yourself: [https://drive.google.com/file/d/15VEQcH ... sp=sharing](https://drive.google.com/file/d/15VEQcHstrUkgQCHZTtLlbz8KRjy2AsMM/view?usp=sharing)

I don't know how libGDX works, or if I'm just being dumb, but it would be greatly appreciated if somebody helped me. Thanks!
-hatoving
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-18T20:57:33+00:00
- Post Title: Textures from SIMULACRA

Hi, your "play.png.texture" file has 2 ZLIB streams. To get the image first you need to use offzip [http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)
like this:

```
offzip.exe -a play.png.texture
```


Then you can use TextureFinder [viewtopic.php?t=15540](https://forum.xentax.com/viewtopic.php?t=15540)
on the extracted file to view the image data 
[https://imgur.com/a/4UJAPKz](https://imgur.com/a/4UJAPKz)
## Post #3
- Username: hatoving
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 18, 2023 10:01 am
- Post datetime: 2023-07-18T21:23:14+00:00
- Post Title: Textures from SIMULACRA

Thanks a lot! I'll try it out as soon as I have the time to do so.
