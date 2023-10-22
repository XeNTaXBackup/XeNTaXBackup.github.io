## Post #1
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-12-04T22:07:12+00:00
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
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2017-12-05T04:03:05+00:00
- Post Title: Bounding Box

The four floats could represent a bounding sphere. x, y, and z being the position and w being the scale.
## Post #3
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-12-05T18:41:58+00:00
- Post Title: Bounding Box

> Reply from killercracker
>
> The four floats could represent a bounding sphere. x, y, and z being the position and w being the scale.
Thank you very much for throwing in that idea! But it is definitely representing a bounding box )-:
