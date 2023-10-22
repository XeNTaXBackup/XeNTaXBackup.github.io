## Post #1
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2013-10-24T02:42:50+00:00
- Post Title: [REQUEST] Black Deserts models .pac format

Hi i unpacked black desert model and texture in this thread 
[viewtopic.php?f=10&t=10879&hilit=pac](http://forum.xentax.com/viewtopic.php?f=10&t=10879&hilit=pac)

Texture files are dds file. So i can open with 3ds max,xnviewer or photoshop plugin
But i don't know open model.pac format files 

Here's some sample. Plz help
[http://pan.baidu.com/s/1ehPbV](http://pan.baidu.com/s/1ehPbV)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-24T23:39:39+00:00
- Post Title: [REQUEST] Black Deserts models .pac format

With newest (unreleased) version of hex2obj you'll get this:
[](http://www.pic-upload.de/view-21123843/pac-head_.jpg.html)

(some errorness faces)

edit: ha, stupid me -  it's no triangle strips.
[](http://www.pic-upload.de/view-21123985/pac_head_ok.jpg.html)
You can use the old hex2obj version from here:
[viewtopic.php?f=29&t=10894](http://forum.xentax.com/viewtopic.php?f=29&t=10894)
## Post #3
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2013-10-25T05:48:09+00:00
- Post Title: [REQUEST] Black Deserts models .pac format

thx I got mesh data. 
But damaged in uv and difficult use calculating hex2obj.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-10-25T08:57:27+00:00
- Post Title: [REQUEST] Black Deserts models .pac format

> Reply from systembest
>
> thx I got mesh data. 
But damaged in uvI know - it's half floats:
[](http://www.pic-upload.de/view-21125382/pac_head_UV.jpg.html)
[phw_00_head_0001.pac.zip](http://www.uploadmb.com/dw.php?id=1382691092)

> and difficult use calculating hex2obj.Could you be more specifc, please?
(If you mean the indices count for the head - it's 9510.)
