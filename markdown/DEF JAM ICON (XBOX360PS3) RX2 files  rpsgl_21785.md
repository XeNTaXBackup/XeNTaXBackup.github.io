## Post #1
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2020-02-21T18:38:31+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

Hello there! 
I still searching for some help with that game, some guys from 
zenhax help me a lot with DEF JAM ICON 
big respect for beedy and Acewell   

Now we have awesome plugins:
Noesis Model importer (.rx2) by beedy ( clothes, environment, hair and other) (.rx2)
Noesis Texture importer (.rx2) by Acewell, same from beedy (.rpsgl) 

 But I still want to get main characters and girls (without bugs) models, maybe
someone can check examples and can help, cause now we on a finish line..  

Example of xbox360 main character model - luda_mob_base.rx2
from ps3 - luda_mob_base.rpsgl

Maybe someone know how to fix or check it in model researcher,
cause beedy said quanity edges and verticles isnt correct.
That problem beacuse files maybe have morphs.

Also I found some old tools for NBA with .rx2 file format
maybe it will be helpful 
[https://forums.nba-live.com/downloads.php?cat=1](https://forums.nba-live.com/downloads.php?cat=1)

original topic is here
[https://zenhax.com/viewtopic.php?f=7&t=9490&start=40](https://zenhax.com/viewtopic.php?f=7&t=9490&start=40)

```
https://www.sendspace.com/file/y0y9sb
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-27T08:15:55+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

> Reply from JimmyJ ↑Sat Feb 22, 2020 2:38 am at Sat Feb 22, 2020 2:38 am
>
> Maybe someone know how to fix or check it in model researcher,
cause beedy said quanity edges and verticles isnt correct.MR is too hard for me...  
I prefer hex2obj, result (test.obj) shown in blender
.



part_479_481.png (89.49 KiB) Viewed 522 times


Beedy is right, there's some fiddeling with the face indices but once you've extracted the parts from .rx2 using his bms script it's not too hard any more. (Didn't care for uvs so far.)

output from quickbms:

```
  0002ae90 36         part480_000200eb_faceindex6
  0006bd00 20176      part481_00010031
```


FIs: part479_00010031, triangle strips with 0xFFFF marker
verts:  part481_00010031, vCount= 388, FVFsize= 52
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-27T13:48:47+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

For the uvs: the biggest part494 seems to need some submesh detection (other than just every 500 FIs):
.



part494_38_00010031.jpg (189.28 KiB) Viewed 482 times
## Post #4
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2020-02-27T14:26:33+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

> Reply from shakotay2 ↑Thu Feb 27, 2020 9:48 pm at Thu Feb 27, 2020 9:48 pm
>
> 
Fir the uvs: the biggest part494 seems to need some submesh detection (other than just every 500 FIs):
.
part494_38_00010031.jpg
Wow.. still wait beedy to see it

Thanks for help, it really helpfull 

Face of character now without bugs?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-27T14:53:40+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

dunny what you mean with "bugs" - it looks like so:
.



part494_head.png (91.99 KiB) Viewed 477 times
## Post #6
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2020-02-27T14:59:32+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

> Reply from shakotay2 ↑Thu Feb 27, 2020 10:53 pm at Thu Feb 27, 2020 10:53 pm
>
> 
dunny what you mean with "bugs" - it looks like so:
.
part494_head.png
yeah it look correct,
maybe I make mistake, bugs - I mean strange positions of faces or verticles.
## Post #7
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2020-02-27T20:24:01+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

I don't understand the def jam structure. I have the scripts for NHL and some FIFA games with rx2 extension the structure is more straightforward. In there the verts and faces are stored in a row for example first face part (part100_00010031 and part101_0002007_faceindex0) and first vertex part (part103_00010031 and part104_0002005_vertexindex0) so I can make a script with a range loop to read all meshes to construct the model. In def jam package luda_mob_base.rx2 there is only 9 face parts but 11 vertex part and I don't know which parts should be read in same time for example part529_000200eb_faceindex8 and part531_000200ea_vertexindex10 matches. Compared to other games that I have the working script it should be faceindex10 and vertexindex10. I can't make range loop for the Noesis script to read indices 8 and 10 same time. 

In shakotay2's first example there is faceindex6 and vertexindex0. Impossible write a loop to read indices 6 and 0 in same time. Im sure that type 000200eb is faces and 000200ea is vertex in the index table. But don't know compared to other rx2 formats the number of face and vertex parts doesn't match.



fpart8andvpart10.png (91.64 KiB) Viewed 431 times


F: part528_00010031
V: part530_00010031
## Post #8
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2020-02-27T22:12:10+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

Beedy greetings!  

shakotay2 thank you for samples. I work on it in 3d max,
now I finish with head, render in marmoset.
[luda_head.jpg](https://xentaxbackup.github.io/file/17581_luda_head.jpg)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-28T11:58:10+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

> Reply from Beedy ↑Fri Feb 28, 2020 4:24 am at Fri Feb 28, 2020 4:24 am
>
> In def jam package luda_mob_base.rx2 there is only 9 face parts but 11 vertex part and I don't know which parts should be read in same time for example part529_000200eb_faceindex8 and part531_000200ea_vertexindex10 matches.yeah, there's some fiddeling required - maybe there's some "rule of combining" to be detected? 

(Great work, btw, you did so far with your scripts, Beedy! I really appreciate it!)

I'd suggest to get all point clouds from the part_ files, then all face indices. Then think about how to combine them. Maybe there's a table for this in the rx2 file(s)?
.



part453_00010031_from_girl_mfor_mod_mfor-rx2.png (51.25 KiB) Viewed 368 times
## Post #10
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2020-02-29T23:54:33+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

Meanwhile, I finish Luda model
[luda1.jpg](https://xentaxbackup.github.io/file/17605_luda1.jpg)
## Post #11
- Username: GuruSangha
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 12, 2020 8:06 pm
- Post datetime: 2020-11-16T09:46:58+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

is there a max script for skate 1,2,3 and def jam icon models
or any modding tutorial on youtube for def jam icon and skate 3
please let me know

Thanks
## Post #12
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2021-04-26T15:48:32+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

From PS3 rpsgl girls with "_blend" eyes morphs

Edit:2021-04-27
Here is a blend file to import characters (GIRLS) from this game. 
You need to install Blender version 249 32 bits and Python version 2.6 32 bits.
[https://www.mediafire.com/file/1vsq69ty ... D.zip/file](https://www.mediafire.com/file/1vsq69tyyxutnov/Blender249%255BDefJamIcon%255D%255BPS3%255D%255Brpsgl%255D%255B2021-04-21%255D.zip/file)
[img.png](https://xentaxbackup.github.io/file/19965_img.png)
## Post #13
- Username: JimmyJ
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Dec 21, 2011 8:54 am
- Post datetime: 2021-06-08T05:11:59+00:00
- Post Title: DEF JAM ICON (XBOX360/PS3) RX2 files / rpsgl

> Reply from Szkaradek123 ↑Mon Apr 26, 2021 11:48 pm at Mon Apr 26, 2021 11:48 pm
>
> 
From PS3 rpsgl girls with "_blend" eyes morphs

Edit:2021-04-27
Here is a blend file to import characters (GIRLS) from this game. 
You need to install Blender version 249 32 bits and Python version 2.6 32 bits.
https://www.mediafire.com/file/1vsq69ty ... D.zip/file

Greetings! Thank you a lot for script. Also, already found a way how to get main characters, cause Beedy finished a script, but all characters have a same model, but ingame it was other geometry, check this topics maybe it will be helped for better understanding
[viewtopic.php?f=16&t=23584](https://forum.xentax.com/viewtopic.php?f=16&t=23584)
[https://zenhax.com/viewtopic.php?f=7&t=9490&start=60](https://zenhax.com/viewtopic.php?f=7&t=9490&start=60)
