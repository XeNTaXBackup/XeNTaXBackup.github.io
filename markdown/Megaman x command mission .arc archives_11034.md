## Post #1
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2013-12-11T06:54:57+00:00
- Post Title: Megaman x command mission .arc archives

Trying to extract models from this game. i looked in the disc and extracted the .AFS files but now i have a lot of ARC files. with no way to extracted them. here is one of the files.[http://www.mediafire.com/download/12r06 ... /s0002.arc](http://www.mediafire.com/download/12r06763rgrkp8v/s0002.arc) thanks to anyone that can or will help.
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-12-11T07:47:11+00:00
- Post Title: Megaman x command mission .arc archives

The file you provided is a container for graphic files.(tim2)
Use game graphic studio and scan for graphic files.
There are 25 textures in this file.
## Post #3
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2013-12-11T08:36:28+00:00
- Post Title: Megaman x command mission .arc archives

> Reply from deepshit
>
> The file you provided is a container for graphic files.(tim2)
Use game graphic studio and scan for graphic files.
There are 25 textures in this file.
hello thanks for the reply. can you look into this file then [http://www.mediafire.com/download/3shd1 ... 81/d60.rar](http://www.mediafire.com/download/3shd1iu2fc56n81/d60.rar)
it was located in the npc (none playable character) folder. so there has to be a model in there. and i use game graphic studio on it and it said (there's no need to search for more graphic files there).

thanks again for the help.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-11T12:44:53+00:00
- Post Title: Megaman x command mission .arc archives

> Reply from spartan00j
>
> [...] so there has to be a model in there.there's some structure:
[](http://www.pic-upload.de/view-21594799/d60_.jpg.html)
but the face indices are weird.

Anyway you might  use this H2O file
0x19390 8000
VB0
0x0
0xA100 848
1210
with hex2obj.

(iirc the max counts were 16470 for the face indices and 1673 for the verts.)
## Post #5
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2013-12-11T15:48:03+00:00
- Post Title: Megaman x command mission .arc archives

> Reply from shakotay2
>
> spartan00j wrote:[...] so there has to be a model in there. there's some structure:

but the face indices are weird.

Anyway you might  use this H2O file
0x19390 8000
VB0
0x0
0xA100 848
1210
with hex2obj.

(iirc the max counts were 16470 for the face indices and 1673 for the verts.)
what!! wow!!! how did you extract the arc file?
plus this next file may help. that both from the npc folder both one is ps2 version and the other is gamecude version
[http://www.mediafire.com/download/60utc ... 0201_2.rar](http://www.mediafire.com/download/60utcsog1mld1z2/s0201_2.rar)
good luck and thank you so much for your help.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-11T18:42:40+00:00
- Post Title: Megaman x command mission .arc archives

> Reply from spartan00j
>
> what!! wow!!! how did you extract the arc file?
[viewtopic.php?f=29&p=90779#p90779](http://forum.xentax.com/viewtopic.php?f=29&p=90779#p90779)

> plus this next file may help.nope, not really.
Imho d60.arc is a better choice for further research.
## Post #7
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2013-12-11T21:59:14+00:00
- Post Title: Megaman x command mission .arc archives

okay then keep me updated.
## Post #8
- Username: spartan00j
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Oct 31, 2010 10:57 am
- Post datetime: 2013-12-20T07:13:06+00:00
- Post Title: Megaman x command mission .arc archives

> Reply from shakotay2
>
> spartan00j wrote:what!! wow!!! how did you extract the arc file?
viewtopic.php?f=29&p=90779#p90779
plus this next file may help.nope, not really.
Imho d60.arc is a better choice for further research.

so anymore advances on it.
## Post #9
- Username: Resiliaxia
- Rank: beginner
- Number of posts: 22
- Joined date: Sat Jun 25, 2016 4:59 am
- Post datetime: 2018-06-23T04:02:27+00:00
- Post Title: Megaman x command mission .arc archives

Could somebody investigate this I can't open them and I tried many ways including szs, I really want to rip the 3D models.
Some model files both Ps2 and Gamecube included: [https://ufile.io/vmujs](https://ufile.io/vmujs)
