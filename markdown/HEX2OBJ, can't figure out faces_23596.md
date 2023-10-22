## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T01:04:30+00:00
- Post Title: HEX2OBJ, can't figure out faces

So I'm trying to convert models from Offroad Legends. I'm trying to convert the .geo file from the "MAZ" truck by myself. Vertices are okay, but the faces are snake eyes. So far I've got a black hole that sucks all the faces to the middle...

Eek.
Here's what the truck is supposed to look like, for reference.
 
Here's the settings for hex2obj, I have no idea if these are wrong, hex is such a new world for me.

Btw changing the Flcnt doesn't do anything, it just removes that error
So yeah, can anybody help?
Here's the file in question: [https://www.mediafire.com/file/bjp716h6 ... s.geo/file](https://www.mediafire.com/file/bjp716h61h8p8i0/maz_chassis.geo/file)
## Post #2
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T01:07:03+00:00
- Post Title: HEX2OBJ, can't figure out faces

Turns out I just had to switch the mode to "DW" and make the face number reduce by itself. And I get a good model output! Close this thread down, please.
## Post #3
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-03-16T04:35:54+00:00
- Post Title: HEX2OBJ, can't figure out faces

maz_chassis.geo.png (17.29 KiB) Viewed 47 times
## Post #4
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-16T12:48:09+00:00
- Post Title: HEX2OBJ, can't figure out faces

> Reply from reh ↑Tue Mar 16, 2021 12:35 pm at Tue Mar 16, 2021 12:35 pm
>
> 
maz_chassis.geo.png

thanks, how did you find the face indice count? (also how did you find the uvs?)
                                   ↑
ignore that, it appears your count has less polys and more incomplete than mine
