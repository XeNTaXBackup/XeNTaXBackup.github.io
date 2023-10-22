## Post #1
- Username: XAceMillenniumX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Dec 30, 2017 4:21 am
- Post datetime: 2017-12-29T20:32:33+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

I'm trying to port vehicles from the game mentioned above to Burnout Paradise. My current test is the Ferrari Dino, the first car in the game. I've successfully extracted all textures from the vehicle, but i'm having trouble with the 3d model. I've picked the face indices and vertices and put them in a separate file. Used hex2obj to visualize the model but couldn't get the meshes displayed correctly. It might be because the model is sequential (because it doesn't seem to have a vertex block) and i don't really know where the UVs start at.
## Post #2
- Username: XAceMillenniumX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Dec 30, 2017 4:21 am
- Post datetime: 2017-12-29T20:38:25+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

Also, i wanted to post the hex file with all face indices and vertices but Xentax doesn't allow .dat files
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-30T02:05:40+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

> Reply from XAceMillenniumX
>
> i wanted to post the hex file with all face indices and vertices but Xentax doesn't allow .dat files
you gotta zip it up first
## Post #4
- Username: XAceMillenniumX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Dec 30, 2017 4:21 am
- Post datetime: 2017-12-30T15:37:47+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

> Reply from AceWell
>
> XAceMillenniumX wrote:i wanted to post the hex file with all face indices and vertices but Xentax doesn't allow .dat files  
you gotta zip it up first

Just realized it, but i think it's late now. Hope i still get a reply.
[MODEL.zip](https://xentaxbackup.github.io/file/13745_MODEL.zip)
## Post #5
- Username: XAceMillenniumX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Dec 30, 2017 4:21 am
- Post datetime: 2018-01-03T14:44:28+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

Ok... Probably no one will see this but. I think i was wrong when i said the model was sequential. Within the file i found something that seems to be vertex blocks. It ends with 4 bytes of 00 00 80 3f (1.0 float), and the vertex in question has a size of 24. However, when i set the FVF to 24 and UV pos to 12 (24 - 8 + 4) it gets messier than previously. And more over, the start of the vertices block doesn't seem to have vertex blocks. Just coordinates but you don't know when it ends. Further you find the vertex i'm mentioning initially. I set the vertices start address where they are but it didn't help me either.
## Post #6
- Username: XAceMillenniumX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Dec 30, 2017 4:21 am
- Post datetime: 2018-01-04T23:51:55+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

I can still hope someone will reply.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-09T05:53:27+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

i can't get anything but point clouds, the indices algo eludes me, too many repeats there  



model_dat.png (15.38 KiB) Viewed 60 times
## Post #8
- Username: XAceMillenniumX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Dec 30, 2017 4:21 am
- Post datetime: 2018-01-09T19:49:13+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

> Reply from AceWell
>
> i can't get anything but point clouds, the indices algo eludes me, too many repeats there  
model_dat.png

Hum, that's weird. I'm sure model.dat has all the vertices required to build the model. Guess i will try to build the model using the file extracted from the zlib stream, instead of the model itself. I could have posted it here if files longer than 256kb were allowed.
## Post #9
- Username: XAceMillenniumX
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Dec 30, 2017 4:21 am
- Post datetime: 2018-01-09T20:02:12+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

With the whole file i got something something similar to yours, but more complete and yet a mess (not a proper model).
[Dino.rar](https://xentaxbackup.github.io/file/13771_Dino.rar)
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-01-10T00:26:23+00:00
- Post Title: Ripping 3D models from Outrun 2006 Coast 2 Coast:

> Reply from XAceMillenniumX
>
> I'm sure model.dat has all the vertices required to build the model.
yes it has all vertices to build complete model, but it has submeshes with at least 2 different strides (24, 32), 
my image displays only one submesh but it doesn't matter because face indices are either broken or an algo unfamiliar to me.
nothing more i can do here, good luck!
