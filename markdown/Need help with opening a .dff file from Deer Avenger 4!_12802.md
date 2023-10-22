## Post #1
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2015-04-29T17:32:35+00:00
- Post Title: Need help with opening a .dff file from Deer Avenger 4!

Hi,
I am trying to remodell the main caracter of Deer Avenger 4 but I would like to use the original model as base. So if possible i would like to open the dff file somehow in 3ds max. I tried many of the .dff importers but none of them worked. It would be a really big help if anyone could give me a nice script for 3ds max.

Thanks in advance.


Files:
[https://www.dropbox.com/s/ufkdh0obb8g3j ... o.rar?dl=0](https://www.dropbox.com/s/ufkdh0obb8g3jb1/bambo.rar?dl=0)

Edit:
I could kinda import it into zmodeller but it gives wierd results. Any ideas?

Log:ZModeler is ready.
Error: AutoSeek (begin at 0x18) position rescue  from 0x24 to 0x1C. Total -8 bytes misread.
Error: AutoSeek (begin at 0x2B04) position rescue  from 0xF7A4 to 0x12918. Total 12660 bytes misread.
Error: AutoSeek (begin at 0x129D0) position rescue  from 0x129E8 to 0x129E4. Total -4 bytes misread.
importAtomic: ID:0116, size=0x009A20, Position=0x016620
Texture "bambo.tga" was not found in "[search list]". file:TexturesService.cpp line:460
Error: AutoSeek (begin at 0x18) position rescue  from 0x24 to 0x1C. Total -8 bytes misread.
Error: AutoSeek (begin at 0xF4) position rescue  from 0x1384 to 0x1740. Total 956 bytes misread.
Texture "atomicsphere.tga" was not found in "[search list]". file:TexturesService.cpp line:460
Error: AutoSeek (begin at 0x18) position rescue  from 0x24 to 0x1C. Total -8 bytes misread.
Error: AutoSeek (begin at 0x2B04) position rescue  from 0xF7A4 to 0x12918. Total 12660 bytes misread.
Error: AutoSeek (begin at 0x129D0) position rescue  from 0x129E8 to 0x129E4. Total -4 bytes misread.
importAtomic: ID:0116, size=0x009A20, Position=0x016620
Error: AutoSeek (begin at 0x18) position rescue  from 0x24 to 0x1C. Total -8 bytes misread.
Error: AutoSeek (begin at 0x2B04) position rescue  from 0xF7A4 to 0x12918. Total 12660 bytes misread.
Error: AutoSeek (begin at 0x129D0) position rescue  from 0x129E8 to 0x129E4. Total -4 bytes misread.
importAtomic: ID:0116, size=0x009A20, Position=0x016620
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-29T21:15:30+00:00
- Post Title: Need help with opening a .dff file from Deer Avenger 4!

> Reply from traderain
>
> It would be a really big help if anyone could give me a nice script for 3ds max.yeah. But did you do a search in the forum to provide more helpful infos?
For example: [viewtopic.php?f=16&t=12496&p=102885&hilit=dff#p102885](http://forum.xentax.com/viewtopic.php?f=16&t=12496&p=102885&hilit=dff#p102885)

> Edit:
>
> I could kinda import it into zmodeller but it gives wierd results. Any ideas?
using hex2obj shows this. Still weird but you could fiddle around a little bit to improve the result (edit: done).
(0xDEFC is start of normals. It's 0x94E0 + 1581x12 (dec.))



bambo.JPG (174.39 KiB) Viewed 83 times
## Post #3
- Username: traderain
- Rank: beginner
- Number of posts: 39
- Joined date: Fri Aug 29, 2014 1:48 am
- Post datetime: 2015-04-30T18:10:42+00:00
- Post Title: Need help with opening a .dff file from Deer Avenger 4!

Thank you very much. I am still kinda new to this forum so sorry for being a little dumb with my first topics.
