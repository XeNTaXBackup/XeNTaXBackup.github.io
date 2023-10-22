## Post #1
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-18T00:07:59+00:00
- Post Title: Battlefield 4 chunk meshes

inside the file *.mesh we can found the name of the 3d model chunk



the models are not compressed.

[http://www.mediafire.com/download/ogu86 ... e1u/mp.rar](http://www.mediafire.com/download/ogu86lit1yxje1u/mp.rar)

maybe someone can analyze and convert the models

thanks
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-18T07:55:06+00:00
- Post Title: Battlefield 4 chunk meshes

that's too easy, isn't it?
[](http://www.pic-upload.de/view-21370565/headgear.jpg.html)

H2O file:
0xDD10 3780
VB1
36 32
0x0 1144
0202

(Search for UV data might be more difficult.)
edit: nope - UVpos is 32
## Post #3
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-19T00:18:36+00:00
- Post Title: Battlefield 4 chunk meshes

thanks for this, was easy but I don't know how to calculate the VB size.

note: the name of the lod00 models inside the mesh file are in 0xC8 position.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-19T09:20:21+00:00
- Post Title: Battlefield 4 chunk meshes

Vertex Block size should be the same for most models in the game.

You don't need to calculate it - it's just experience, finding patterns:

[](http://www.pic-upload.de/view-21380234/BF4_mesh_VBlock.jpg.html)

VBsize is the distance (offset in bytes) between the patterns.
(ehm, yes, in the 2nd pattern I missed the first zero.  )
## Post #5
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-20T07:26:02+00:00
- Post Title: Battlefield 4 chunk meshes

thanks for the simple explanation!   

other thing.... some meshes look like this , specifically head meshes.



I'm doing something wrong? (VB: 36)

here is the chunk model:

[http://www.mediafire.com/download/o3ed1 ... 3702ff.rar](http://www.mediafire.com/download/o3ed1srocmj9bx8/e55f35a738900edac8e3ca83983702ff.rar)

thanks
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-20T09:55:09+00:00
- Post Title: Battlefield 4 chunk meshes

You did not take care of submeshes in face index list: 0x1D840, 0x1D8DC, 0x2269A etc.. 

glasses SM0:
0x1D840 78
VB1
36 32
0x0 28
0202

head SM1:
0x1D8DC 9951
VB1
36 32
0x3F0 2103
0202

startaddress of head to be calculated as addr[SM+1]= addr[SM]+28*36
SM is previous submesh, so addr[0]=0x0 here; addr[1]= 0 + 0x3F0

addr[2]= addr[1]+vertsCount[1] *36= 0x3F0 + 2103*36= 0x12BAC

[](http://www.pic-upload.de/view-21388737/safety_glasses.jpg.html)
## Post #7
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-21T01:46:31+00:00
- Post Title: Battlefield 4 chunk meshes

thanks! all submeshes imported
## Post #8
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2013-11-21T05:25:51+00:00
- Post Title: Battlefield 4 chunk meshes

Great work guys...
since the files aren't compressed, is it possible to get skeletal information as well?
## Post #9
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-21T07:30:37+00:00
- Post Title: Battlefield 4 chunk meshes

I found other head models where I can't define the VB block. (some head models use VB40)
the file structure looks a little bit different

here are some chunks:

[http://www.mediafire.com/download/uqcr1 ... /Heads.rar](http://www.mediafire.com/download/uqcr17tw0vxr54w/Heads.rar)

note: ninja ripper extract head meshes with deformity but with HEX2OBJ I can export heads in perfect condition.
## Post #10
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2013-11-21T07:39:19+00:00
- Post Title: Battlefield 4 chunk meshes

> Reply from artworkplay
>
> Great work guys...
since the files aren't compressed, is it possible to get skeletal information as well?

binds and skeletal structure are in different files but I don't know where are this files
## Post #11
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2013-12-03T14:46:11+00:00
- Post Title: Battlefield 4 chunk meshes

Guys! Is it possible to get mesh using this method from NFS:Rivals since it's running on the same engine as BF4?
I posted a topic here with attachment: [viewtopic.php?f=10&t=10997](http://forum.xentax.com/viewtopic.php?f=10&t=10997)
I can't ripp 3d mesh from the game, only textures can be grabbed, I use Ninja ripper 1.1.4.
