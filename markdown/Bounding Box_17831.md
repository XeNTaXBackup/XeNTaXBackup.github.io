## Post #1
- Username: javiecholson188
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 17, 2018 12:28 pm
- Post datetime: 2018-03-17T04:32:02+00:00
- Post Title: Bounding Box

Hi,

im deeply in some reversing stuff for an old 3D game. I'm sure that I've found the bounding box data. It's represented as the following:

float CenterX;
float CenterZ;
float CenterY;

float Unknown;
float Unknown;
float Unknown; 
float Unknown;

Did someone of you ever see 4 floats representing a bounding box? I'm just confused right now... "top,down,right,left" ist just working for 2D as we know. Maybe someone has a little tip that is getting me into the right direction. The first Unknown is probably MaximumX, second Unknown is MaximumY, but then nothing makes sense )-:

Thanks in advance!
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-17T12:08:04+00:00
- Post Title: Bounding Box

It is hard to say anything without seeing the data. It can be that 3 of those floats are for the size (width, height, depth) and one of them is something else. If you think that first and the second are MaxX/MaxY, it can be that the other two are MinX/MinY.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-17T13:49:26+00:00
- Post Title: Bounding Box

thought i was having deja vu at first until....  
[viewtopic.php?f=16&t=17362&hilit=bounding+box](http://forum.xentax.com/viewtopic.php?f=16&t=17362&hilit=bounding+box)
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-03-17T14:52:45+00:00
- Post Title: Bounding Box

well... if it really is a bounding box, the only thing i can think of is this sort of representation. a quaternion vector. extend with an angle axis for the arbitrary rotations. the second extend vector is the exact mirror of it.



the fancy render is just a gimmick. 

edit: rethinking this, it doesn't work. you can't or it's complicated to pin the rotation axis to get a starting angle to form the box from an absolute point. it can 'shear' the box shape. so... i'm sure this not bounding box data, but... perhaps bones or just the position and rotation data for the bbox. the sizes of it should be somethingwhere else.
