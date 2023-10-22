## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T15:31:54+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

I need help converting the .IDP file from Rocket Cars (iOS). The texture file is a PVR (Which I can extract,) and there's an XML file that tells what the game can do with it. The file size is 328 KB.

Sample (Car, Buster): [https://www.mediafire.com/file/k9e0uhjq ... r.zip/file](https://www.mediafire.com/file/k9e0uhjqdv0eewu/Buster.zip/file)


I use Blender, Windows 10.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-18T16:41:41+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

Simple mesh format (and maybe I got the lowest lod only):
.



car-idp.png (115.64 KiB) Viewed 74 times
## Post #3
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T16:59:16+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

It does appear to be the model used in the game when you're driving, and it is a mobile game (which explains a low polycount)
But I do see that a few faces are messed up .
## Post #4
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-18T17:19:17+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from ReVolt ↑Sat Jun 19, 2021 12:59 am at Sat Jun 19, 2021 12:59 am
>
> 
It does appear to be the model used in the game when you're driving, and it is a mobile game (which explains a low polycount)
But I do see that a few faces are messed up .

Which faces are messed up?
## Post #5
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T17:20:08+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from dimis9138 ↑Sat Jun 19, 2021 1:19 am at Sat Jun 19, 2021 1:19 am
>
> 
ReVolt wrote: ↑Sat Jun 19, 2021 12:59 am
It does appear to be the model used in the game when you're driving, and it is a mobile game (which explains a low polycount)
But I do see that a few faces are messed up .


Which faces are messed up?
## Post #6
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T17:23:50+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

I just realized that might be the boost effect  (Still don't know how to chop up the mesh, as there is no instructions on the XML file (not the boost effect, it's actually the fender thingy where the wheels go)

Still wondering where the side of the car (windows?) and the wheels are.
## Post #7
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-06-18T17:39:32+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from ReVolt ↑Sat Jun 19, 2021 1:23 am at Sat Jun 19, 2021 1:23 am
>
> 
I just realized that might be the boost effect  (Still don't know how to chop up the mesh, as there is no instructions on the XML file (not the boost effect, it's actually the fender thingy where the wheels go)

Still wondering where the side of the car (windows?) and the wheels are.

I think those are flat planes cause they might not be meant to be seen. A real picture of the car ingame would help. Wheels might be separate because they might be modular/used in more cars?
## Post #8
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T17:58:16+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from dimis9138 ↑Sat Jun 19, 2021 1:39 am at Sat Jun 19, 2021 1:39 am
>
> 
ReVolt wrote: ↑Sat Jun 19, 2021 1:23 am
I just realized that might be the boost effect  (Still don't know how to chop up the mesh, as there is no instructions on the XML file (not the boost effect, it's actually the fender thingy where the wheels go)

Still wondering where the side of the car (windows?) and the wheels are.


I think those are flat planes cause they might not be meant to be seen. A real picture of the car ingame would help. Wheels might be separate because they might be modular/used in more cars?

It's actually this part:


Screenshots of the cars ingame (warning, lot of pictures!)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-18T18:28:17+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from ReVolt ↑Sat Jun 19, 2021 1:23 am at Sat Jun 19, 2021 1:23 am
>
> Still wondering where the side of the car (windows?) and the wheels are.There's about 15 assumed sub meshes (i.e start of face indices) so you'll need a script to get them all:
.



7th_sub_mesh.png (70.71 KiB) Viewed 57 times
## Post #10
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T18:29:42+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from shakotay2 ↑Sat Jun 19, 2021 2:28 am at Sat Jun 19, 2021 2:28 am
>
> 
ReVolt wrote: ↑Sat Jun 19, 2021 1:23 amStill wondering where the side of the car (windows?) and the wheels are.
There's about 15 assumed sub meshes (i.e start of face indices) so you'll need a script to get them all:
.
7th_sub_mesh.png

What script do I use ?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-18T18:34:32+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

Guess, you need to write it.  Noesis (or blender) python. Or, with basic C-knowledge you could try out this (click up arrow):

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 
(.IDP not implemented so far.)
## Post #12
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T18:41:19+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from shakotay2 ↑Sat Jun 19, 2021 2:34 am at Sat Jun 19, 2021 2:34 am
>
> 
Guess, you need to write it.  Noesis (or blender) python. Or, with basic C-knowledge you could try out this (click up arrow):
shakotay2 wrote: ↑Mon Mar 06, 2017 6:01 pm
(.IDP not implemented so far.)

I will wait for a Blender, Python, 3D Object Converter (or other language) script.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-18T19:45:23+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

I was too lazy to update the Make_obj project so simply created some H2O files using the Make_H2O project (obsolete)
(well, it doesn't care for the sub mesh offsets):
.



car_idp_all.png (193.44 KiB) Viewed 47 times
## Post #14
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-06-18T20:47:18+00:00
- Post Title: (Looking 4 Script) Rocket Cars - IDP File

> Reply from shakotay2 ↑Sat Jun 19, 2021 3:45 am at Sat Jun 19, 2021 3:45 am
>
> 
I was too lazy to update the Make_obj project so simply created some H2O files using the Make_H2O project (obsolete)
(well, it doesn't care for the sub mesh offsets):
.
car_idp_all.png

Weird!
