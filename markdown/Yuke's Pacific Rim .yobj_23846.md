## Post #1
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-05-08T18:23:38+00:00
- Post Title: Yuke's Pacific Rim .yobj

Hello, everyone, I need some help with a model format I've been taking a look at.

I've been wanting to see if I could try to extract the models from a now unavailable Pacific Rim game. However, I have not been able to extract the model data itself.
I've already extracted the files from their .pac files using a PAC extractor, but I've found nothing regarding a .yobj converter/importer (for Blender, at least).

All I really need help with is finding some kind of converter for the .yobj files, that converts them to a format useable in Blender.


I figured this would be a good place to ask, but if it isn't, just let me know.

And if you do need samples for whatever reason, here you go. It's one of the kaiju in-game.
[https://www.mediafire.com/file/hyhr17ui ... .YOBJ/file](https://www.mediafire.com/file/hyhr17ui28i21it/0.YOBJ/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-08T20:26:07+00:00
- Post Title: Yuke's Pacific Rim .yobj

looks funny:
.



0-Yobj.png (63.38 KiB) Viewed 97 times
## Post #3
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-05-08T23:15:34+00:00
- Post Title: Yuke's Pacific Rim .yobj

Something's definitely wrong there, but It's for sure the right model file. Maybe it has to do with the face/vertex indices? (I wouldn't exactly know, as I'm not too acquainted with hex side of model extraction just yet.)


To give a better idea how it should look:
[https://i.pinimg.com/originals/1e/fd/c3 ... 97b477.jpg](https://i.pinimg.com/originals/1e/fd/c3/1efdc369bd2c19f8a1f34336b697b477.jpg)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-09T08:13:09+00:00
- Post Title: Yuke's Pacific Rim .yobj

Yeah, see, thought it's some kind of landscape or such.  
.



PacificRim-0-YOBJ.png (143.31 KiB) Viewed 85 times


(one submesh only)
## Post #5
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-05-09T15:06:11+00:00
- Post Title: Yuke's Pacific Rim .yobj

I can't seem to find the indices for the other submeshes.

Any idea where they may be? Tried looking for similar patterns but I can't seem to find anything that stands out.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-09T16:36:03+00:00
- Post Title: Yuke's Pacific Rim .yobj

try

0x15112C 20411
Vb1
28 99
0x96F48 9529
121000
0x0 255

(copy above 6 lines into a text file and name it whatever.H2O)
## Post #7
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-05-09T17:22:50+00:00
- Post Title: Yuke's Pacific Rim .yobj

Seems to import everything aside from the other arm and legs.

I'll be seeing if I can locate the last submesh(es) myself, If anything, I'll come back here.
