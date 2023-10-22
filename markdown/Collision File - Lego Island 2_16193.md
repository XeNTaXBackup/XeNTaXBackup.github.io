## Post #1
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-24T19:27:03+00:00
- Post Title: Collision File - Lego Island 2

Hi guys,

here I have an extracted collision file from Lego Island 2: The Brickster's Revenge. Do you have any idea?
[https://www.file-upload.net/download-12 ... s.col.html](https://www.file-upload.net/download-12460002/Rocks.col.html)

The files for this game are segmented into sections like "INDL" (for indices), "VERT" (for vertices), "GRPL" (for objects) etc. The same applies for this one. Sections for this one are "CBBX" (maybe for Cubebox?), GRDP (groupdata... !?) and GRDC.

It looks like, CBBX holds some vertex information and GRDP holds indices. Not getting through for now.  It could be possible that this file holds information abot several boundingboxes/boundingspheres, as the corresponding mesh looks like this:

[](http://abload.de/image.php?img=rocks6mumr.png)

Thanks ahead for your help!
## Post #2
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-25T12:37:58+00:00
- Post Title: Collision File - Lego Island 2

Why do you need collision from this game anyway ?
## Post #3
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-25T17:20:46+00:00
- Post Title: Collision File - Lego Island 2

> Reply from kellne
>
> Why do you need collision from this game anyway ?
???
To create new ones for custom models???
## Post #4
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-26T11:04:27+00:00
- Post Title: Collision File - Lego Island 2

Dont make mods for this game  This game is so DEAD you know !
Noone plays this game :/
## Post #5
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-26T16:04:49+00:00
- Post Title: Collision File - Lego Island 2

> Reply from kellne
>
> Dont make mods for this game  This game is so DEAD you know !
Noone plays this game :/
Sorry, but looks like you have nothing to contribute here. Please use another thread to annoy people.
## Post #6
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-26T16:27:33+00:00
- Post Title: Collision File - Lego Island 2

I am not annoying anyone.

Just tell me why do you want to MOD dead game ? :O
## Post #7
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-26T19:49:51+00:00
- Post Title: Collision File - Lego Island 2

> Reply from kellne
>
> I am not annoying anyone.

Just tell me why do you want to MOD dead game ? :O
You are annoying me. Dead game or not doesn't matter. You are probably too young to feel the nostalgically of childhood games.
## Post #8
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-04-26T23:03:52+00:00
- Post Title: Collision File - Lego Island 2

Hi,

Please remain respectful towards one and other. If you do not have anything constructive to post, please do not post or attempt to derail threads. This is just a reminder.

Cheers.
## Post #9
- Username: kellne
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Apr 25, 2017 8:29 pm
- Post datetime: 2017-04-27T21:17:44+00:00
- Post Title: Collision File - Lego Island 2

I know nostalgia.

I am 20 years old now, BOI ! 
I make MODs for GTA San Andreas, it is game from 2004  so I know nostalgia.

I am older than you for sure 
Do you have some mods to show ? :O
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-27T22:02:08+00:00
- Post Title: Collision File - Lego Island 2

> Reply from pivke
>
> here I have an extracted collision file from Lego Island 2: The Brickster's Revenge. Do you have any idea?
https://www.file-upload.net/download-12 ... s.col.html
i can't even get a decent point cloud with the data, but if this is just for collision you can take the higher
res mesh that you seem to have there in Blender and copy it then lower the polygon count and keep the
scale so that it will still encompass the high res mesh and use it as the collision mesh.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-28T06:09:44+00:00
- Post Title: Collision File - Lego Island 2

86 faces are supposed to be found?

Guess it's a matter of how to interpret the data.
This gives a sphere:
# Rocks.col
# v -0.192059 -0.126221 0.973233 1.180366 
# v 0.026208 -0.992000 -0.123484 -0.147430 
# v -0.833683 0.544194 -0.093942 1.673595 
v 0.942739 0.251820 0.218700 0.586671 
#  -107374176.000000  -107374176.000000  -107374176.000000  -107374176.000000 
# v -0.291675 -0.059341 0.954675 1.374485 
# v -0.935510 -0.190329 -0.297651 1.729657 
# v -0.187527 0.982252 0.003762 2.706966 
v 0.804263 -0.555480 0.211193 -1.518214 
#  -107374176.000000  -107374176.000000  -107374176.000000  -107374176.000000 

If you use the last column as position components (with 4th value commented out):
v 1.180366  -0.147430  1.673595 
#  0.586671 
v 1.374485  1.729657  2.706966 
#  -1.518214
v 2.685511  1.415948  1.310850 
#  0.056951

you get a maybe suiting point cloud but not sure.
## Post #12
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-28T21:11:34+00:00
- Post Title: Collision File - Lego Island 2

> Reply from kellne
>
> I know nostalgia.

I am 20 years old now, BOI ! 
I make MODs for GTA San Andreas, it is game from 2004  so I know nostalgia.

I am older than you for sure 
Do you have some mods to show ? :O
I'm 24 years old and I'm developing modding software for people like you. Sorry, but you are mentally at the age of 12, so stop trying to downgrade me.

@AceWell
Yep, tried to get a point cloud too, but the vertices were just screwed up. Thanks for the hint with the low poly thing, but I'm only interested in the file format to get collision files for new models back in game.

@shakotay2
You made a great job again, just as usual   I'm just curios about the data. Why didn't they just use boundingsphere center point + diameter?
## Post #13
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-28T21:29:52+00:00
- Post Title: Collision File - Lego Island 2

> Reply from shakotay2
>
> 86 faces are supposed to be found?

Guess it's a matter of how to interpret the data.
This gives a sphere:
# Rocks.col
# v -0.192059 -0.126221 0.973233 1.180366 
# v 0.026208 -0.992000 -0.123484 -0.147430 
# v -0.833683 0.544194 -0.093942 1.673595 
v 0.942739 0.251820 0.218700 0.586671 
#  -107374176.000000  -107374176.000000  -107374176.000000  -107374176.000000 
# v -0.291675 -0.059341 0.954675 1.374485 
# v -0.935510 -0.190329 -0.297651 1.729657 
# v -0.187527 0.982252 0.003762 2.706966 
v 0.804263 -0.555480 0.211193 -1.518214 
#  -107374176.000000  -107374176.000000  -107374176.000000  -107374176.000000 

If you use the last column as position components (with 4th value commented out):
v 1.180366  -0.147430  1.673595 
#  0.586671 
v 1.374485  1.729657  2.706966 
#  -1.518214
v 2.685511  1.415948  1.310850 
#  0.056951

you get a maybe suiting point cloud but not sure.
Tried to reconstruct your vertices, but wasn't able to? And how is it giving 86 faces for you?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-28T22:02:08+00:00
- Post Title: Collision File - Lego Island 2

there's 86 times the pattern 16x 0xCC so I thought there might be 86 faces

here's the obj for it:


 shak_log lastCol-Pos.zip
(1.95 KiB) Downloaded 12 times



> Reply from pivke
>
> Why didn't they just use boundingsphere center point + diameter?You need to know which software they used to created the collision shape files. Is it a genuine format (own format of the developer) or did they use something like PhysX?
## Post #15
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-28T22:09:24+00:00
- Post Title: Collision File - Lego Island 2

> Reply from shakotay2
>
> there's 86 times the pattern 16x 0xCC so I thought there might be 86 faces

here's the obj for it:
shak_log lastCol-Pos.zip
Seriously... can't find that? o0

Imported the original model to your collision file. Not looking like it's a bounding box or sphere   

(Enlarge image to see point cloud)

EDIT:
@shakotay2
They mostly used own formats (3D models, texture animations). And so I think they did here.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-28T22:31:32+00:00
- Post Title: Re: Collision File - Lego Island 2

I don't know more than you.  
This is the floats as they are to be found in the Rocks.col file:


 shak_log LegoIsl2-pos.zip
(6.52 KiB) Downloaded 12 times


Feel free to comment out the 'v' lines and uncomment others (i.e. replace '#' by 'v').

Maybe you need to interpret the first 3 values of the first 3 lines after 0xCC.. (-107374176.000000) as a 3x3 matrix for rotation, dunno.
## Post #17
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-28T22:42:56+00:00
- Post Title: Re: Collision File - Lego Island 2

Hm... 3x3 matrix sounds good. But for now nothing really makes any sense.
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-28T22:47:46+00:00
- Post Title: Re: Collision File - Lego Island 2

we would need a more regular object than rocks, such as a book, a chest, a plank or something like that
## Post #19
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2017-04-28T22:58:16+00:00
- Post Title: Re: Collision File - Lego Island 2

Found this:
[](http://abload.de/image.php?img=ghettoblaster78ack.png)

Downloadlink (OBJ + collision file)
*.col: [https://www.file-upload.net/download-12 ... r.col.html](https://www.file-upload.net/download-12468322/GhettoBlaster.col.html)
*.obj: [https://www.file-upload.net/download-12 ... r.obj.html](https://www.file-upload.net/download-12468321/GhettoBlaster.obj.html)
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-29T06:26:36+00:00
- Post Title: Re: Collision File - Lego Island 2

thx!
The devs swap the 0.0 0.0 1.0, 0.0 1.0 0.0 (and  1.0 0.0 0.0) lines so it's impossible to choose a position line here:

```
#  -1.000000 0.000000 0.000000 0.282570 
#  0.000000 -1.000000 0.000000 0.446649 
#  0.000000 0.902546 -0.430593 -0.000000 
v  0.000000 0.000000 1.000000 0.936200 // not a pos?

#  -1.000000 0.000000 0.000000 0.282570 
#  0.000000 0.000000 -1.000000 0.936200 
#  0.000000 1.000000 0.000000 0.446649 
v  0.000000 -0.902546 0.430593 -0.000000 

#  1.000000 0.000000 0.000000 0.282570 
#  0.000000 -1.000000 0.000000 0.446649 
#  0.000000 0.902546 0.430593 -0.000000 
v  0.000000 0.000000 -1.000000 0.936200  // not a pos?
```

I made swaps but with no result.
For example
v  0.000000 0.902546 -0.430593 -0.000000 
#  0.000000 0.000000 1.000000 0.936200 
for the first matrix.

Getting harder at the end where it's tedious to decide what might be position or rotation:

```
#  -0.469624 0.865624 0.173633 0.546529 
#  0.253564 -0.950512 0.179534 -0.375263 
v  0.631043 -0.381934 -0.675212 -0.479408 

#  -0.767704 0.255607 0.587619 0.526597 
#  -0.202973 -0.966781 0.155360 -0.322283 
#  -0.595184 0.055386 -0.801679 -0.278307 
v  0.640805 0.306224 0.703986 0.507457 

#  -0.802383 0.258495 0.537924 0.508752 
#  -0.325856 0.565373 -0.757741 0.112047 
#  0.547535 -0.039784 0.835837 0.309727 
v  -0.596810 -0.347533 -0.723214 -0.418951 
```


Or does the last column hold the position values?
(A comparision with the mesh in the obj file might give more insights...)

#  -1.000000 0.000000 0.000000 0.282570 
#  0.000000 -1.000000 0.000000 0.446649 
#  0.000000 0.902546 -0.430593 -0.000000 
v  0.000000 0.000000 1.000000 0.936200 

#  -1.000000 0.000000 0.000000 0.282570 
#  0.000000 0.000000 -1.000000 0.936200 
#  0.000000 1.000000 0.000000 0.446649 
v  0.000000 -0.902546 0.430593 -0.000000 

There's a good chance that the last column holds the position values because they are equal to these vertices:

first 4 vertices from mesh:
v -0.282570 -0.446649 0.936200
v -0.282570 0.446649 0.936200
v -0.282570 -0.446649 -0.936200
v -0.282570 0.446649 -0.936200
