## Post #1
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-05-20T20:36:21+00:00
- Post Title: Lost Planet (PC) .tex format

Hi
Does anybody know something about this format?

It is from Lost Planet PC demo game, developer Capcom

demo: 
```
http://www.gamespot.com/news/6170818.html
```


It is some version of packed dds image, I suppose...
Image included
[lost_planet_tex.jpg](https://xentaxbackup.github.io/file/1171_lost_planet_tex.jpg)
## Post #2
- Username: Slaii
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jun 26, 2006 2:28 am
- Post datetime: 2007-05-20T20:39:36+00:00
- Post Title: Lost Planet (PC) .tex format

I added several files, so you do not need to download the whole demo...

Have a lok at it... thx
[logo.rar](https://xentaxbackup.github.io/file/1172_logo.rar)
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-21T20:18:13+00:00
- Post Title: Lost Planet (PC) .tex format

well thats easy enough, drop a real dds header on it, dependant on the dword it gives you, dxt1, dxt5, p8 etc.. and thats that
## Post #4
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-22T03:58:57+00:00
- Post Title: Lost Planet (PC) .tex format

Mario_Kart is correct about placing the DDS header, I did however notice some problems to that. It looks as though the original files header is not the same length for every texture and the graphics dimensions are not DDS compatible. In other words the width and height are not powers of 2. I was able to create a dummy DDS files and attach the header to the Dolby logo graphic and then changes the attached header's dimensions to the original header's dimensions. For instance the original was C0 01 X B0 00 which is 448X176 but since neither are a power of 2 I saved a dummy DDS at 512X256 and then removed the games file header and attached the dummy DDS header. Then I changed the bytes for dimensions 512X256 to the needed 448X176 in the modified texture. This allows you to edit the texture in Photoshop but it will only save back as a power of 2 DDS.

 I suppose the edited texture can be saved as raw (because of the dimensions needed) and the headerless data reinserted onto the original header.
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-22T07:19:24+00:00
- Post Title: Lost Planet (PC) .tex format

DDS size is not in power of 2 is the new feature of DX10. If you download the DX9 domo. The DDS texture will be in the power of 2.

nVidia should have a tool to export this new DDS.
## Post #6
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2007-05-23T01:43:26+00:00
- Post Title: Lost Planet (PC) .tex format

nothing really new plugin wise on there site. though now DX10 scares me   

btw, you sure this extra length, just wasn't mips
## Post #7
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2007-05-23T03:21:47+00:00
- Post Title: Lost Planet (PC) .tex format

> DDS size is not in power of 2 is the new feature of DX10

True but the current Photoshop DDS plugin I have does not support DX10. I had trouble before with multiples of 2 in graphics instead of powers of 2, will be glad to see a plugin show up for this.

> btw, you sure this extra length, just wasn't mips

 I'm not sure why the headers were diffrent sizes but it did look like some headers had more info than others but I saw no mips in the graphics themselves.
 If your refering to the 448X176 that is the correct dimensions with no mips. I looked at 3 graphics. Which included two logos, the Dolby appeared to be alpha only with no mips but none were powers of 2.
