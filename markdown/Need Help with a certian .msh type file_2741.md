## Post #1
- Username: jocsive
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 17, 2007 4:46 pm
- Post datetime: 2007-08-04T09:09:59+00:00
- Post Title: Need Help with a certian .msh type file

Ok it is not just your avarage .msh(mesh) its somehow in coded, a friend of mine built a proggie that can see this type of mesh file. But i can't get it in an editable format.

I am hoping someone here might be able to help.

I added one of the files.

Thanks.

Attachment:
[http://www.speedyshare.com/797886501.html](http://www.speedyshare.com/797886501.html)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-04T12:16:32+00:00
- Post Title: Need Help with a certian .msh type file

You didn't attach anything.
If your friend created that tool, he should be able to also convert it, shouldn't he?
## Post #3
- Username: jocsive
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 17, 2007 4:46 pm
- Post datetime: 2007-08-04T21:36:26+00:00
- Post Title: Need Help with a certian .msh type file

Uhh sorry about that, it said it attached maybe some error.

Anyway, the proggie he made only views the models and can put the texture on too. He can not convert them because he can't figure them out
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-05T08:30:48+00:00
- Post Title: Need Help with a certian .msh type file

If he's able to create a model viewer he must have knowledge about the format. So why can't he convert it?
Maybe he can post the specs for the format to help converting it.
## Post #5
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-05T21:22:06+00:00
- Post Title: Need Help with a certian .msh type file

the format should be quite easy, OGRE variation. I have a quick look (less than 10 min)  and get this:

Hope this help!

```
dword	nFaces	//Face count
word	nmtl	//Material count
struct face {
 byte X 3	uknByte	//should be 1 byte for each vert
 dword X 3	uknLong	//should be 1 value for each vert
 float X 3 	vert1	//position x, y, z
 float X 3 	vert2	//position x, y, z
 float X 3 	vert3	//position x, y, z
 float X 2 	uv1	//texture coordinate u, v
 float X 2 	uv2	//texture coordinate u, v
 float X 2 	uv3	//texture coordinate u, v
 float X 3 	norl1	//normal x, y, z ?
 float X 3 	norl2	//normal x, y, z ?
 float X 3 	norl3	//normal x, y, z ?
 float X 3	??
 float X 3	??
 float X 3	??
} face[nFaces]
struct Material {
 float X 3	colAmbient	//color r g b
 float X 3	colDiffuse	//color r g b
 float X 3	colSpecular	//color r g b
 char[]	textureName
 dword	ukn
 byte X 8	ukn2
}

```
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-06T17:58:41+00:00
- Post Title: Need Help with a certian .msh type file

jocsive, It is better to upload the files here so more people can take a look at those! I do it for you this time!

And here are the format. Same that I didn't spent too much time on them so I'm not sure how far I have got!

```
char[3]		header	//ANI
dword		nFrames	//Frames count / ?? not sure maybe Bones
dword		nBones	//Bones count \ ?? not sure maybe Frames
struct translation {
 float X 3		PosXYZ
 float X 4		QuatXYZW
}	// total nBones * nFrames

```


```
char[3]		header	//AX2
dword		nFrames	//Framescount 
dword		nVerts	//Verts count
struct Vertpool {
 float X 7		??
} Vertpool[nVerts]
dword		ukn	//0xFFFFFFFF ?? terminator
struct faceIndex {
 dword		//maybe tri-strip ?? don't know the face count
}

```


```
char[3]		header	//MX2
dword		??
dword		nukn	//unknown count
byte		??
struct Section1 {
 dword		??
 dword		??
 float		??
} Section1[nukn]
struct Section2 {
 float X 3		??
} Section2[nukn]
dword		nukn2	//unknown count 2
struct Section3 {
 float X 3		??
} Section3[nukn2]
dword		nukn3	//unknown count 3
struct Section4 {
 float X 2		??
} Section4[nukn3]
dword		nukn4	//unknown count 4
struct Section4 {
 dword		ntxt	//length of texture's name
 char[ntxt]		stex	//texture's name
 byte X 72		??
} Section4[nukn3]

```

[unknown_format.rar](https://xentaxbackup.github.io/file/1303_unknown_format.rar)
## Post #7
- Username: jocsive
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 17, 2007 4:46 pm
- Post datetime: 2007-08-07T21:55:13+00:00
- Post Title: Need Help with a certian .msh type file

Ok this is where we are.




The ball you see there at the end of the cart, its supposed to be a man, but in the game there is animation on the man, so he does not apper here.
Thats where we are stuck now. Anyone no what we are missing?
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-09T08:40:50+00:00
- Post Title: Need Help with a certian .msh type file

What kinds of help do you needed?

In your picture, which type of models are you displaying? msh, abx or mbx?

And what game is that?
## Post #9
- Username: jocsive
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 17, 2007 4:46 pm
- Post datetime: 2007-08-09T08:59:28+00:00
- Post Title: Need Help with a certian .msh type file

Its .mbx, i attached that model.

I need help with why the man is not displaying, he had animation on him in the game and the cart does'nt so it appers. What we are trying to do is get the man to apper.

The game is called thang online, [http://www.thang.ongameport.com](http://www.thang.ongameport.com)
[cart.rar](https://xentaxbackup.github.io/file/1310_cart.rar)
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-09T15:19:20+00:00
- Post Title: Need Help with a certian .msh type file

Interesting! So you know the format of mbx!

Could you share what you got already? So I don't have to start from the beginning.

Send me the model files you used in your viewer if you don't mind because I don't want to download the whole game-client just for that!
## Post #11
- Username: jocsive
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 17, 2007 4:46 pm
- Post datetime: 2007-08-12T12:00:15+00:00
- Post Title: Need Help with a certian .msh type file

Ok my friend made up this info about the file. This is the file you see in the image, which is .mbx.

even though he can read the "faces" the bits that have some animation points or animation come out like a meatball.

Here is some info about the file

```

char[3]      header   //MX1
dword X 6    ??
byte X 1     ??
dword   nFaces        //Face count
struct face {
 dword        ntxt    //length of texture's name
 char[ntxt]   stex    //texture's name
 dword X 3    ??
 float X 2    uv1     //texture coordinate u, v
 float X 2    uv2     //texture coordinate u, v
 float X 2    uv3     //texture coordinate u, v
 float X 3    ??
 float X 3    ??
 float X 3    ??
 float X 3    norl1   //normal x, y, z
 float X 3    norl2   //normal x, y, z
 float X 3    norl3   //normal x, y, z
 float X 3    vert1   //position x, y, z
 float X 3    vert2   //position x, y, z
 float X 3    vert3   //position x, y, z
} face[nFaces]

------------------------------------------------------------------
MBX version 2 INFO

char[3]      header   //MX2

other than that... format unknown... :-\
```


I attached the info about the file and the file in a rar.

I greatly appreciated your help.

here are some download links for the file
[http://sharebee.com/b5d6b31d](http://sharebee.com/b5d6b31d)

mirror - [http://www.speedyshare.com/654768453.html](http://www.speedyshare.com/654768453.html)[/code]
[File info and file.rar](https://xentaxbackup.github.io/file/1314_File info and file.rar)
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-13T22:50:43+00:00
- Post Title: Need Help with a certian .msh type file

I did a quick test on that cart.mbx. And I'm sure that there are no animation or the man inside! They must be in separate files!

and the whole MX1 format should be like this!

```
float X 6    bbox     //bounding box [x,y,z] [x,y,z]
byte X 1     padbyte  //no use??
dword        nFaces   //Face count 
struct face { 
 dword        nshd    //length of shader name 
 char[nshd]   sshd    //shader name 
 dword X 3    boneidx //Bone index(should have external bones file as well) 
 float X 2    uv1     //texture coordinate u, v 
 float X 2    uv2     //texture coordinate u, v 
 float X 2    uv3     //texture coordinate u, v 
 float X 3    vc1     //Vert color  r g b
 float X 3    vc2     //Vert color  r g b
 float X 3    vc3     //Vert color  r g b
 float X 3    norl1   //normal x, y, z 
 float X 3    norl2   //normal x, y, z 
 float X 3    norl3   //normal x, y, z 
 float X 3    vert1   //position x, y, z 
 float X 3    vert2   //position x, y, z 
 float X 3    vert3   //position x, y, z 
} face[nFaces] 

```
## Post #13
- Username: feczo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 12, 2007 7:56 pm
- Post datetime: 2007-08-14T06:13:28+00:00
- Post Title: Need Help with a certian .msh type file

Hello fatduck,

I made the neat little app the above screenshot made of   and trying to solve the mysteries of these files aswell. My progress is greatly slowed that i'm a novice at 3D coding (trying in Delphi+GLScene)

The MX1 format description you made is great, i would never guessed the bounding box and vert colors but i was about to post about the skeletal info - just solved that mystery over the weekend. Atm i'm into reading how to handle that in GLScene   

About the skeleton info i think its in the ABX files - which has 2 versions aswell. I had not much time to look into it but at first sight the AX1 file looks pretty similar to AX2, except i think the "faceIndex" can be the "skeletal structure" parent-child relation... thats only a guess though. I added the animation file of the cart.mbx to this post for viewing.

I think there was a developer change at some point and the new developer added these new formats. I kinda can tell which update introduced the version 2 files   

Thanks for all the help you gave it really helped a LOT  
[cart_stand001.zip](https://xentaxbackup.github.io/file/1315_cart_stand001.zip)
## Post #14
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-14T20:28:32+00:00
- Post Title: Need Help with a certian .msh type file

This cart_stand001.abx is a mesh with vertices animation

The AX1 format is the same as AX2 except the faces are build with triangles (3 verts per face)

```
dword      ukn      //??
dword      nFrames  //Frames count 
dword      nVerts   //Verts count 
struct FrameMeshVerts {
 struct Vertpool { 
  float X 3       //position xyz
  dword      ??   //not sure if it is dword
  float      ??
  dword      ??   //not sure if it is dword
  float      ??
 } Vertpool[nVerts] 
} FrameMeshVerts[nFrames]
dword      ukn   //0xFFFFFFFF ?? terminator 
struct face { 
 dword      idx1
 dword      idx2
 dword      idx3
}
```
## Post #15
- Username: feczo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 12, 2007 7:56 pm
- Post datetime: 2007-08-15T06:44:17+00:00
- Post Title: Need Help with a certian .msh type file

There are more than 3 dwords after the FFs... are you sure its not like the *.ani files?   
My guess is something like this:

```
dword      padding  // always 0s?
dword      nFrames  // Frames count
dword      nBones   // Bones count
struct animation {
  struct translation { 
    float X 3      PosXYZ 
    float X 4      QuatXYZW 
  } translation[nBones]
} animation[nFrames]
dword      ??       // seems to be FFFFFFFF all the time...
struct boneidx {
 dword          pBone  // my guess this is the bone structure
} boneidx[nBones]

```
## Post #16
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-08-15T10:19:18+00:00
- Post Title: 

I'm not sure if I'm right or not because I didn't actually 'study' the format   

Your verison make great sense. But the bones structure doesn't match the mesh?   
If this abx file is for different meshes then fine, if not then you have to figure out what wrong in mbx/abx then!

Try more abx for sure the format.
## Post #17
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2007-12-01T19:05:50+00:00
- Post Title: 

Feczo,

How did you read the color information from the .shd (bitmap ?) file ?

(Are you from Hungary ?)
