## Post #1
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-08-15T13:39:49+00:00
- Post Title: Dark Sider 2 Model?

Can anyone make some script for extracting this game?Pm me if you need some sample
## Post #2
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-08-15T18:59:58+00:00
- Post Title: Dark Sider 2 Model?

> Reply from S0UZ
>
> Can anyone make some script for extracting this game?Pm me if you need some sample

Doesn't the game run on the same engine as spacemarine? if so, you might try the SM tools on it.
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-15T19:03:49+00:00
- Post Title: Dark Sider 2 Model?

I just got the game, love the art, but donn't know how to extract the .upak but should this not be in the Game Archive Research forum?



edit: SM tools ??

where can i find that?

edit2: use OffZip to open the archives

[http://aluigi.org/search.php?src=offzip](http://aluigi.org/search.php?src=offzip)


T.
## Post #4
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-08-16T13:34:38+00:00
- Post Title: Dark Sider 2 Model?

> Reply from TaylorMouse
>
> I just got the game, love the art, but donn't know how to extract the .upak but should this not be in the Game Archive Research forum?



edit: SM tools ??

where can i find that?

edit2: use OffZip to open the archives

http://aluigi.org/search.php?src=offzip


T.
What is the offset value to open it?
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-16T14:30:07+00:00
- Post Title: Dark Sider 2 Model?

I dono, haven't tried it yet, have you tested it with zero ?

Edit: tried the OffZip, doesn't do anything :/

Edit2:

My bad, it works!

```
offzip.exe -a media.upak "c:\Temp\Extracted" 0
```


just make sure your destination directory exists, takes about 10minutes to extract

T.
## Post #6
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-17T06:17:32+00:00
- Post Title: Dark Sider 2 Model?

anyone kowns witch tools can open those .bod files？
I mean darksider1or2's
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-17T08:10:38+00:00
- Post Title: Dark Sider 2 Model?

Nope, it seems that the .bod files are packages as well, since I did not find any textures for the characters, probably they are backed into these bod files...

Haven't looked at it thoroughly, yet.

T.
## Post #8
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-19T04:14:49+00:00
- Post Title: Dark Sider 2 Model?

yeah,you‘re right. darksiders 1&2’s 3dmodel is bod file,just some of charactor‘s dds textures can be exported by offzip in darksiders2。
I’m so like this game‘s model, but sadly there's no more people be interested in this great game in this forum.
I just waiting for a longtime from darksigers1,never lose my hope. LOL
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-19T05:16:28+00:00
- Post Title: Dark Sider 2 Model?

Sample .bod files?
Just send one of those archives mentioned at the beginning of the thread..
## Post #10
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-19T11:01:44+00:00
- Post Title: Dark Sider 2 Model?

Here is a BOD file, though, they vary very hard, from 100kb to 30MB!

I believe this one just contains dds files, not sure though

T.
[0a83d004.rar](https://xentaxbackup.github.io/file/5686_0a83d004.rar)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-19T19:27:31+00:00
- Post Title: Dark Sider 2 Model?

There's only materials and textures in that file. Send me an archive.
## Post #12
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-19T19:52:09+00:00
- Post Title: Dark Sider 2 Model?

this one maybe?
[3adf1004.rar](https://xentaxbackup.github.io/file/5691_3adf1004.rar)
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-19T20:19:58+00:00
- Post Title: Dark Sider 2 Model?

Ya there we go. Meshes don't look difficult. Just having to parse the mesh header and all that would be easier with multiple files.

Would need an archive so I can properly dump it to understand how the files are stored.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T03:56:53+00:00
- Post Title: Dark Sider 2 Model?

Ok I don't think offzip is extracting the files properly. All files should start with BOD. I don't think a single file should contain more than one BOD.
## Post #15
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-20T09:35:06+00:00
- Post Title: Dark Sider 2 Model?

yeah i think the -1 option might be needed.
then extract the files based on the header.
## Post #16
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-20T09:37:16+00:00
- Post Title: Re: Dark Sider 2 Model?

Yes, indeed, I also believe the OffZip should extract the files with a name and an extension, not a binary value and then the extension :/

wich makes it unclear what file we are dealing with...

Do we have the code of OffZip, or can we get it to make some changes to it?

I'm currently playing this game and sometimes I use 3D Ripper DX, and it does the job quite well, for models, not for textures.
These models do look amazing to study!

So how do we proceed?

T.
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T23:16:22+00:00
- Post Title: Re: Dark Sider 2 Model?

The hex is the location where the data starts. The extension is something it tries to assign based on the file signature or something.

I haven't tried other options in offzip though.
The upak archive itself doesn't seem to have any filenames (someone sent me a filecutter head/tail). There are several OPBK strings, so I thought maybe I'll just run offzip on one of them.

And it produces a file with several BOD strings. Not sure if that means they go together, but the one I have has one 3D model BOD and 3 material BOD's all in one file lol

And also this:

> {ID} is being all badass in {Region}
>
> {ID} is in an epic conflict with a boss
>
> {ID} executed a {Combo} hit combo with finesse
>
> {ID} is exploring around {Region}
>
> {ID} is fighting against {Creature} 
>
> {ID} has brought death to {Region}
>
> {ID} has died {Deaths} times
>
> {ID} idle {ID} killed {Kills} in {Region}
>
> {ID} is killing enemies in {Region}
>
> {ID} was last killed by a {Creature}
>
> {ID} just went up another experience level
>
> {ID} just leveled up a possessed weapon
>
> {ID} is navigating game menus
>
> {ID} has spent {GameTime} playing Darksiders II
>
> {ID} is traversing a path in {Region}

Haha pretty amusing.
But ya...doesn't seem to be any filenames. They probably group them together by the OBPK's though.
## Post #18
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-22T04:34:24+00:00
- Post Title: Re: Dark Sider 2 Model?

Darksiders2(pc)'s  upak files all in the file directory "media".In this directory I found a scripts.obsp file, it's like include some file directory name. maybe have a little help?
already upload that file.

///////////////////////this is the files list&size of  darksiders2(pc)'s "media" file directory //////////////////////////////
[anim_streams]                     
[sounds_streamed]                  
[video]                            
anim_streams.upak   470,758 KB     
maps.upak           982,538 KB     
media.upak          1,772,372 KB   
pc.mnfst            432 KB         
scripts.obsp        16,630 KB      
worldnodes32.bin    9,576 KB       
worlds.bin          48,262 KB  
/////////////////////////////////////////////////////////////////////

I'm very happy finale00 start work on this game,you're my hope ,thank U!!!!!!
[pc.mnfst.zip](https://xentaxbackup.github.io/file/5703_pc.mnfst.zip)
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T05:26:18+00:00
- Post Title: Re: Dark Sider 2 Model?

manifest file might be indexing into the upak files considering the structured strings and integers...

> already upload that file.

Where's the scripts.obsp file?
## Post #20
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-22T07:34:11+00:00
- Post Title: Re: Dark Sider 2 Model?

sorry,wrong file name,"pc.mnfst 432 KB"  this file
## Post #21
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-22T07:57:59+00:00
- Post Title: Re: Dark Sider 2 Model?

I think scripts.obsp is game's scripts package,if you think that's useful, you can download it from here:

[https://rapidshare.com/files/3126408618 ... s.obsp.rar](https://rapidshare.com/files/3126408618/scripts.obsp.rar)
## Post #22
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2012-08-22T08:09:56+00:00
- Post Title: Re: Dark Sider 2 Model?

The pc.mnfst and .upak files contain OBPK archives which in turn contain the files (uncompressed filetable + deflate compressed file data).
## Post #23
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-22T11:18:22+00:00
- Post Title: Re: Dark Sider 2 Model?

I'll try it again tonight

T.
## Post #24
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-23T07:00:50+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from Sir Kane
>
> The pc.mnfst and .upak files contain OBPK archives which in turn contain the files (uncompressed filetable + deflate compressed file data).

OBPK is package of PS3? I don't understand this infomation had any help?
## Post #25
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2012-08-23T08:29:38+00:00
- Post Title: Re: Dark Sider 2 Model?

Posted my extractor for DS2 there: [viewtopic.php?f=10&t=9475&p=77690#p77690](http://forum.xentax.com/viewtopic.php?f=10&t=9475&p=77690#p77690)
## Post #26
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-23T08:51:32+00:00
- Post Title: Re: Dark Sider 2 Model?

I uploaded a file.that's darksider1's war.oppc. it's still can be export a bod files, hope that's can be some help.

[https://rapidshare.com/files/3097280076/war.zip](https://rapidshare.com/files/3097280076/war.zip)
## Post #27
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-23T09:37:59+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from Sir Kane
>
> Posted my extractor for DS2 there: viewtopic.php?f=10&t=9475&p=77690#p77690

wow,that's a gread job!!!!
## Post #28
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-23T11:06:23+00:00
- Post Title: Re: Dark Sider 2 Model?

I used Sir Kane's tool export a lot of files, looks like .dcm is the model , like "SPACE MARINE",so I try "SPACE MARINE TOOLS 1.0" frome  [http://forums.relicnews.com/showthread. ... ack-v0.1.0](http://forums.relicnews.com/showthread.php?262094-TOOL-OPPC-Unpack-v0.1.0) ,but that script import 3dmax doesn't work.

I upload some files, include dcm&dds .....thank a lot  for those great tools

[https://rapidshare.com/files/2330191840 ... axea01.zip](https://rapidshare.com/files/2330191840/absolom_axea01.zip)
## Post #29
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-08-26T10:50:49+00:00
- Post Title: Re: Dark Sider 2 Model?

Any update,everyone?How to view these file?
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-26T20:56:17+00:00
- Post Title: Re: Dark Sider 2 Model?

Can someone upload some more? Thanks.
The dcm file is straightforward for the most part. Just need to identify what the structs are (might not be as straightforward)



Here's a quick layout of the file. I didn't look into the structures.
Noesis plugin in my dropbox. If you want to continue with that just go ahead.

```
   int[5]
   int[2]
   int
   float
   short
   int[5]
   float[6] bbox?
   byte
   short len
   byte[len] meshName?

   int
   int
   int numVerts
   int
   int numIdx
   int
   int index_buffer_size # numIdx * 2
   int index_size # 2

   short[numIdx] indices
   numVerts Vertex
   numVerts Unk1
   numVerts Unk2

   #EOF
}

struct Vertex {
   float[3] x, y, z
}

struct unk1 {
   20 bytes
}

struct unk2 {
   16 bytes
}

```


> Reply from amzerof6
>
> 
I upload some files, include dcm&dds .....thank a lot  for those great tools

https://rapidshare.com/files/2330191840 ... axea01.zip

Thanks, now the data makes a lot more sense...
## Post #31
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-08-27T08:49:20+00:00
- Post Title: Re: Dark Sider 2 Model?

finale00, you're awsome!!that's great job,thank u so much.
here, I uploaded some files,hope them can help you.

[https://rapidshare.com/files/560451903/ ... bsolom.zip](https://rapidshare.com/files/560451903/character_Boss_Absolom.zip)
[https://rapidshare.com/files/475632349/ ... one_00.zip](https://rapidshare.com/files/475632349/world_Zone_00.zip)
[https://rapidshare.com/files/3329364758/items.rar](https://rapidshare.com/files/3329364758/items.rar)
## Post #32
- Username: S0UZ
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Apr 05, 2011 6:46 pm
- Post datetime: 2012-08-27T14:00:34+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from finale00
>
> Can someone upload some more? Thanks.
The dcm file is straightforward for the most part. Just need to identify what the structs are (might not be as straightforward)


Here's a quick layout of the file. I didn't look into the structures.
Noesis plugin in my dropbox. If you want to continue with that just go ahead.
Code: Select allstruct dcm_file {
   int[5]
   int[2]
   int
   float
   short
   int[5]
   float[6] bbox?
   byte
   short len
   byte[len] meshName?

   int
   int
   int numVerts
   int
   int numIdx
   int
   int index_buffer_size # numIdx * 2
   int index_size # 2

   short[numIdx] indices
   numVerts Vertex
   numVerts Unk1
   numVerts Unk2

   #EOF
}

struct Vertex {
   float[3] x, y, z
}

struct unk1 {
   20 bytes
}

struct unk2 {
   16 bytes
}

amzerof6 wrote:
I upload some files, include dcm&dds .....thank a lot  for those great tools

https://rapidshare.com/files/2330191840 ... axea01.zip

Thanks, now the data makes a lot more sense...
Incredible man,hope the progress won't make more trouble for you and will be completed soon!
## Post #33
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-08-29T01:23:24+00:00
- Post Title: Re: Dark Sider 2 Model?

Nice guys.
## Post #34
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-08-31T20:47:00+00:00
- Post Title: Re: Dark Sider 2 Model?

See you've been busy Finale00!

Good job!

I've been on the ranch for the last 10 days, no internet there :/

Anyways, had a good time with the ponys 

I noticed that only the weapons work, and the tris are inverted.

But not complaining 

EDIT: Added death himself 


T.
[death.rar](https://xentaxbackup.github.io/file/5735_death.rar)
## Post #35
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-31T21:28:54+00:00
- Post Title: Re: Dark Sider 2 Model?

Ya I didn't actually do much. Just looked at it wrote down some structures and then threw up a pic.
Some people sent me some models which is good, though I haven't actually looked at them.
## Post #36
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-01T20:07:26+00:00
- Post Title: Re: Dark Sider 2 Model?

I did the import in MAX, 

and when I read the faces ( tris)

```
                    {
                        faces.Add(new Triangle()
                        {
                            a = br.ReadInt16() ,
                            b = br.ReadInt16() ,
                            c = br.ReadInt16() 
                        });
                    }

```


I had to flip the faces in max so I switched it to

```
                    {
                        faces.Add(new Triangle()
                        {
                            a = br.ReadInt16() ,
                            c = br.ReadInt16() ,
                            b = br.ReadInt16() 
                        });
                    }

```


so that b & c are switched and the model came out ok

T.

Continuing the research
## Post #37
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-08T19:28:57+00:00
- Post Title: Re: Dark Sider 2 Model?

Any progress to this??

T.
## Post #38
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-10T20:15:47+00:00
- Post Title: Re: Dark Sider 2 Model?

I found out that the models ( animated once ) start with a chunk, unkown to me yet, but then follows al set of bones

```
{
	int16 lenName			// length of bone name
	string boneName x 		// bone name
	69 bytes				// bone data 
		// always ends with FF
}

struct vfx
{
   int16 len;
   string name;
   25 bytes
}

```

and after this set of bone definitions, the same structure appears as in the weapons (ref absolom_axea01.dcm)
for the faces... but not for the vertices.;
:/

really want to beat this one...

T.
## Post #39
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-18T18:28:55+00:00
- Post Title: Re: Dark Sider 2 Model?

Stuck here ...

Any help is welcome...

T.
## Post #40
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-18T22:47:53+00:00
- Post Title: Re: Dark Sider 2 Model?

Been figuring out some of the dcm files ...
I'm  not saying this will work with all of them, but I based it on death.dcm, emberhulkA01.dcm and exhumeA1.dcm..

although the last file does not seem to have any bone data....

```
{
	Uint32 start 				// start position of the mesh data
	UInt32 nbrSubmeshes
	
	UInt32 submeshSets 			
	IndexSet[submeshSets] nIndices 	
	
	UInt32 vertexSets
	VertexSet[vertexSets] vertices
	
	byte[4] ffff
	Uint32 zero1
	Uint32 zero2
	byte[2] one
	
	UInt32 nVertices
	
	UInt32 unk
	UInt32 unk
	UInt32 unk
	
	UInt16 nBones
	Uint32 zero3
	
	
	
	...
	
	byte ff
}

struct IndexSet
{
	UInt16 nIndices
	UInt16 zero
}
struct VertexSet
{
	UInt16 nVertices
	UInt16 unk // FF
	
}


struct Bone
{
	int16 lenName			// length of bone name
	string boneName x 		// bone name
	// 69 bytes				// bone data
	float[3] 	unk1
	UInt32 		unk2 		// zero
	float[3] 	unk3
	UInt32 		unk4 		// zero
	float[3] 	unk5
	UInt32 		unk6 		// zero
	float[3] 	unk7
	UInt16 		unk8 		// zero
	Int16 		unk9
	Int16		unk10 
	UInt16 		unk11 		// zero
	byte		ff  		// FF or -1
	
}

struct Vfx
{
	int16 lenName			// length of visual fx name
	string fxName			// fx name
	//25 bytes				// fx data
	UInt32 	unk
	Uint32 	zero2
	Int16  	unk1
	Int16 	zero3
	Uint32 	zero4
	Int16 	unk2
	Int16 	zero5
	Uint32 	zero6
	byte	ff 				// always ends with FF
	
}

struct ModelData
{
	UInt32 chunkSize
	Uint32 chunkId
	Int16[nIndices] faceData
	
	float[nVertices] vertexData
	
}


```


Just hypothetically, nothing coded yet...

T.
## Post #41
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-18T23:58:03+00:00
- Post Title: Re: Dark Sider 2 Model?

Fortunately for you there are two types of models and their headers themselves are different slightly.
Of course, the vertex struct is completely different.

If you look at the absolom axe, you'll see it has the number of indices per mesh, followed by a single integer representing that many indices. Then you read the number of vertices per mesh...and then you read a signed int16 whose absolute value is the number of vertices. But then you read a short, an int -1, and then you read another integer which is the number of verts (except it's not negative).

Then you look at a model that you wrote with bones and it's different from what I said.

Presumably it's a difference between skinned/static meshes. Static meshes have a plain position buffer 3-floats each, while skinned meshes have this odd struct

```
   int ?
   float[3]
   float[3]
   float[3]
   float[3]
}

```


The int might be a bone ID, don't know.

The format for each mesh is

```
   int32 datasize (numIdx * 2)
   int32 structSize (2)

   int16[numIdx] idxBuff
   numVerts * 12 bytes
   numVerts Vertex
   numVerts * 16 bytes (a bunch of floats and zeroes)
   numVerts * 4 bytes (a byte of bytes)
}

```



I've uploaded a copy of the plugin I wrote, except it ONLY loads skinned meshes since I didn't parse the header lol
## Post #42
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-19T02:45:58+00:00
- Post Title: Re: Dark Sider 2 Model?

Ok the header is actually not what I thought it was.

After the index counts for the meshes, you then have number of vertex counts, followed by vertex counts.
However, this part is kind of weird. It looks like this

```
numVertCount {
   signed int32 numVerts
}

signed numVertCount2
numVertCount2 {
   signed int32 numVerts
   float ??
}

```


I don't understand why it's a signed value really, but if it's negative you just have to take the absolute value to get what you want. So I would probably just read everything as absolute signed integers.

Afterwards, you have the following struct that loops mesh times (the second integer). I guess these are the actual mesh structs, each holding references to the material it uses, the bones that are attached, and other things. The mesh data itself is stored afterwards.

```
  byte modelType # 0 or 1, static or skinned
  byte ?
  int numVerts
  int ?
  int ?
  int numSubMesh
  int numBones
  float[6] bbox
  numBones {
     byte ??
     int len
     byte[len] name
     float[16] matrix
     int ??
  }

  numSubMesh {
     byte ??
     int len
     byte[len] submesh name?
     int matNum
     int ?
     int numVerts
     int vertStart
     int numIdx
     int idxStart
  }
}

```


The idxStart and vertStart should be clear what they are for.

And then now you are at the start of the mesh data (offset stored in the first integer of the file)
I have updated my script to load pretty much all of the models without crashing.
[icegiant.jpg](https://xentaxbackup.github.io/file/5818_icegiant.jpg)
## Post #43
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-09-19T15:52:58+00:00
- Post Title: Re: Dark Sider 2 Model?

wow,amazing,finale00 !! I try your noesis plugin,most of model are fine,chars\item\world they all fine, just a few of them had error.
I must say that, thank u,thank u,thank u!!!!

I think .bmat include date of materials; .o3d include skin or bones ; .psystem is anim
Honest, just model & materials with UV that can satisfy me.

thanks again, if you need anything, just say it, I'll try my best.
## Post #44
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-19T17:53:56+00:00
- Post Title: Re: Dark Sider 2 Model?

Damn!! I wanted to beat this one   

But.. Finale00, nice one 

T.
## Post #45
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-09-19T18:17:55+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from TaylorMouse
>
> Damn!! I wanted to beat this one   

But.. Finale00, nice one 

T.

never give up ,man. darksider1 still no one done it.
## Post #46
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2012-09-19T19:53:17+00:00
- Post Title: Re: Dark Sider 2 Model?

Thanks a lot Finale00 awesome work!!! 
and TaylorMouse thanks for your hard work and for keeping the thread alive
## Post #47
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-19T20:15:00+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from TaylorMouse
>
> Damn!! I wanted to beat this one   

But.. Finale00, nice one 

T.

Still a lot of unk structs.
Don't know how the normals and UV's are stored at all.
Would have to print out the values and analyze them.
## Post #48
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-19T20:45:22+00:00
- Post Title: Re: Dark Sider 2 Model?

Of course I'm not givin up, I want it to work in my C# code too 

btw I verified this part:

```

```


this is indeed the Bounding Box !

T.
## Post #49
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-19T22:16:01+00:00
- Post Title: Re: Dark Sider 2 Model?

YES !! my c# code does it to!!

the Chancelor 



T.
## Post #50
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-19T22:48:12+00:00
- Post Title: Re: Dark Sider 2 Model?

Which library do you use to render? Ogre3D? Or do you export to obj and then just load it up somewhere?
## Post #51
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2012-09-20T02:35:26+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from TaylorMouse
>
> YES !! my c# code does it to!!

the Chancelor 



T.

Congratulation!! that's great
## Post #52
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-20T07:36:00+00:00
- Post Title: Re: Dark Sider 2 Model?

I have the code write out an mtl file and an obj file, then I import it into 3DS MAX 2010, then I took a screenshot to post here 

T.
## Post #53
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-21T22:13:28+00:00
- Post Title: Re: Dark Sider 2 Model?

Any tutorial for get this models, i am a noob.
## Post #54
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-22T15:03:34+00:00
- Post Title: Re: Dark Sider 2 Model?

well, 
buy the game
use the extraction tool in the forum to extract the models from their archive
download Naosis
get the py script from Finale00 dropbox ( get everything, it's great   )
start naosis and look at the models
export them to whatever
import them into your favorite 3D tool !

I'm making a little tool myself to do this in c# (convert to OBJ) but it is not finished yet...

T.
## Post #55
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2012-09-22T16:58:15+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from TaylorMouse
>
> well, 
buy the game
use the extraction tool in the forum to extract the models from their archive
download Naosis
get the py script from Finale00 dropbox ( get everything, it's great   )
start naosis and look at the models
export them to whatever
import them into your favorite 3D tool !

I'm making a little tool myself to do this in c# (convert to OBJ) but it is not finished yet...

T.

Where are extraction tool version final?

I did read all post but i have dude about this.

I did buy game today.
## Post #56
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-23T11:08:09+00:00
- Post Title: Re: Dark Sider 2 Model?

It was posted on page 2:

[http://sktest.aruarose.com/DS2Extract.rar](http://sktest.aruarose.com/DS2Extract.rar)

T.
## Post #57
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2012-09-24T09:55:29+00:00
- Post Title: Re: Dark Sider 2 Model?

great plugin finale00! unfortunately 32 characters make noesis crash . some are: darkwar.dcm, despair.dcm (death's horse), maker_shaman.dcm (blind priestess Muria) and uriel.dcm.
I haven't tested all weapons/items yet on crashes but some do.
hopefully there's some progress on uv's because these are some great models to study.
## Post #58
- Username: Silvist
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue May 31, 2011 1:30 pm
- Post datetime: 2012-09-25T10:26:23+00:00
- Post Title: Re: Dark Sider 2 Model?

Awesome job TaylorMouse!  I looked at this topic when it was at like page 2, and huge progress in last couple pages lol.  I myself am interested in the tool you are working on.  Cause I love working in 3ds max ^^  

Once again grats ^^
## Post #59
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-25T22:06:50+00:00
- Post Title: Re: Dark Sider 2 Model?

Still working on this one...

apparently, the textures are referenced in the .bmat files.

in the dcm file there is a reference to that file.

ex.: absolom.dcm has a reference to absolomA01.bmat
and in the .bmat file you will find all the textures required.

here is my c# class that reads out the necessary textures:

```
        {
            string file = fileName + ".bmat";
            Material mat = new Material();
            if (!File.Exists(file)) return null;

            using (BinaryReader br = new BinaryReader(new FileStream(file, FileMode.Open, FileAccess.Read)))
            {
                Debug.WriteLine("- " + br.ReadString(3)); // BOD
                br.ReadByte(); // FD
                
                int nbrTextures = br.ReadInt16();

                int unk1 = br.ReadInt16();
                uint unk2 = br.ReadUInt32();
                uint unk3 = br.ReadUInt32();

                int unk4 = br.ReadByte();
                int unk5 = br.ReadByte();
                uint unk6 = br.ReadUInt32();
                uint unk7 = br.ReadUInt32();

                int len = br.ReadInt16();
                br.ReadString(len); // Material
                br.ReadBytes(13);
                
                len = br.ReadInt16();
                br.ReadString(len); // Name
                br.ReadBytes(10);

                len = br.ReadInt16();
                br.ReadString(len); // Model name
                br.ReadBytes(9);

                len = br.ReadInt16();
                Debug.Write("  - " + br.ReadString(len) + ": "); // Shader Name
                br.ReadBytes(10);

                len = br.ReadInt16();
                Debug.WriteLine(br.ReadString(len)); // 
                br.ReadBytes(9);

                len = br.ReadInt16();
                br.ReadString(len); // parameters
                br.ReadBytes(16);

                len = br.ReadInt16();
                Debug.Write("  - " + br.ReadString(len) + ": " ); // Emissive map
                br.ReadBytes(15);

                len = br.ReadInt16();
                br.ReadString(len); // texture parameters
                br.ReadBytes(13);

                len = br.ReadInt16();
                br.ReadString(len); // value
                br.ReadBytes(10);

                len = br.ReadInt16();
                mat.EmisMap = br.ReadString(len) + ".dds";
                Debug.WriteLine(mat.EmisMap); // TEXTURE EMIS .dds
                br.ReadBytes(9);

                len = br.ReadInt16();
                br.ReadString(len); // UAddress Mode
                br.ReadBytes(14);

                len = br.ReadInt16();
                br.ReadString(len); // VAddress Mode
                br.ReadBytes(26);

                len = br.ReadInt16();
                br.ReadString(len); // Specular Color 
                br.ReadBytes(15);

                len = br.ReadInt16();
                br.ReadString(len); // Vector4 Parameter 
                br.ReadBytes(55);

                len = br.ReadInt16();
                br.ReadString(len); // EmissiveColor 
                br.ReadBytes(66);

                len = br.ReadInt16();
                Debug.Write( "  - " + br.ReadString(len) + ": ") ; // Diffuse Map 1
                br.ReadBytes(30);

                len = br.ReadInt16();
                mat.DiffMap = br.ReadString(len) + ".dds";
                Debug.WriteLine(mat.DiffMap); // TEXTURE DIFFUSE .dds
                br.ReadBytes(41);

                len = br.ReadInt16();
                Debug.Write("  - " + br.ReadString(len) + ": "); // Specular Map 
                br.ReadBytes(30);

                len = br.ReadInt16();
                mat.SpecMap = br.ReadString(len) + ".dds";
                Debug.WriteLine(mat.SpecMap ); // TEXTURE SPECULAR .dds
                br.ReadBytes(41);

                len = br.ReadInt16();
                Debug.Write("  - " + br.ReadString(len) + ": "); // Normal Map 
                br.ReadBytes(30);

                len = br.ReadInt16();
                mat.NormMap = br.ReadString(len) + ".dds";
                Debug.WriteLine(mat.NormMap); // TEXTURE NORMAL .dds
                br.ReadBytes(9);

                len = br.ReadInt16();
                br.ReadString(len); // SRGBTexture
                br.ReadBytes(23);

                len = br.ReadInt16();
                br.ReadString(len); // FloatParameters
                br.ReadBytes(25);

                br.Close();
            }

            mat.FileName = file;
            return mat;
        }

```

Sometimes the reference is before the bones, sometimes after it, and sometimes in the middle ( for statics )

I also noticed there is a UAddress Mode and a VAddress Mode, wandering if this has anything to do with the UV texture coordinates we don't seem to find :/

T.
## Post #60
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-28T07:41:14+00:00
- Post Title: Re: Dark Sider 2 Model?

Cleaned up my code and finally succeeded in adding the correct textures to the correct faces and have the multi-objects in obj format, pffff. 

Next on the list is to check why the despair.dcm file and the darkwar.dcm file are not in the same format... 



Only missing piece is the texture coordinates   

ANYONE can help???
## Post #61
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2012-10-02T10:59:38+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from TaylorMouse
>
> Cleaned up my code and finally succeeded in adding the correct textures to the correct faces and have the multi-objects in obj format, pffff. 

Next on the list is to check why the despair.dcm file and the darkwar.dcm file are not in the same format... 



Only missing piece is the texture coordinates   

ANYONE can help???

maybe using 3dripperdx with tosyk's uv-repair tool will help. good luck 

edit: be careful it's very slow and maybe can crash 3dsmax if you select too many objects!
[uv-repair-tools.rar](https://xentaxbackup.github.io/file/5870_uv-repair-tools.rar)
## Post #62
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-10-02T15:29:56+00:00
- Post Title: Re: Dark Sider 2 Model?

Doesn't the repair tool just change the UVW channels?
## Post #63
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-10-02T17:15:07+00:00
- Post Title: Re: Dark Sider 2 Model?

yes but some people..."who own max"....don't know how to do that....
## Post #64
- Username: joeyq
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jan 19, 2010 6:14 pm
- Post datetime: 2012-10-03T13:00:20+00:00
- Post Title: Re: Dark Sider 2 Model?

a couple of posts ago Taylormouse wrote:"I'm currently playing this game and sometimes I use 3D Ripper DX, and it does the job quite well, for models, not for textures." from which i assumed that he didn't know that the uv's weren't destroyed in 3dx ripper but on a different channel.
I'm not a programmer but maybe he can use 3dx ripper model data uv's to compare with  .dmc's data and figure out the uv's from there.
## Post #65
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-10-03T16:35:57+00:00
- Post Title: Re: Dark Sider 2 Model?

Damn, I didn't think of that , such a dumbass that I am   

Thnx

T.
## Post #66
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-10-08T10:08:52+00:00
- Post Title: Re: Dark Sider 2 Model?

Anybody may upload pc.mnfst(432kb) please? ....for some reason my file doesn't work with DS2Extractor ,maybe because i installed a DLC for this game and now it's 434kb. thank you.
## Post #67
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-08T15:03:47+00:00
- Post Title: Re: Dark Sider 2 Model?

Wasn't there a bms script?
Or at least it is open-source extractor right lol
## Post #68
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-10-08T15:27:06+00:00
- Post Title: Re: Dark Sider 2 Model?

I cant seem to open any of the models with Noesis tho. I can see a plugin for Darksiders on your plugins but only the DDS format for the graphics seem to show on the exported items.
I have used the exporter on this thread to output the whole media directory. Not sure if I need to uncompress anything else.


Edit: Kk wrong directory  all good now
## Post #69
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-10-08T16:04:22+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from finale00
>
> Wasn't there a bms script?
Or at least it is open-source extractor right lol

What do u mean? Did i miss something again? lol 
I know that there is only a bms script for the pck files, not for .upak format or i'm wrong?
## Post #70
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-10-16T15:07:35+00:00
- Post Title: Re: Dark Sider 2 Model?

After extracting with Noesis and Finalle´s plugins, did you guys manage to create the mapping for the textures? 
I am going thru the thread over and over but it doesnt seem like it, can anyone confirm?
## Post #71
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-10-16T16:11:12+00:00
- Post Title: Re: Dark Sider 2 Model?

Unfortunately we were not able ( well I wasn't anyways) to extract the uvw mapping coordinates, sorry

T.
## Post #72
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-10-17T16:04:23+00:00
- Post Title: Re: Dark Sider 2 Model?

Would it help if I posted a properly uvw mapped character or item? It is easily done with 3ds Ripper and the script posted above.
## Post #73
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-10-18T16:55:26+00:00
- Post Title: Re: Dark Sider 2 Model?

I already tried that, ... unsuccessfully

T.
## Post #74
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-10-19T12:01:53+00:00
- Post Title: Re: Dark Sider 2 Model?

well.. so actually the only way to obtain a uvmapped T posed model is to transfer the uv maps from a ripped model to the t posed one.
Obviously u need a perferct ripp to do this succesfully. ( each model need to have the same number of vertexes)
## Post #75
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-10-19T13:43:42+00:00
- Post Title: Re: Dark Sider 2 Model?

It's probably really trivial like half-floats or something.
## Post #76
- Username: matreco
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Feb 17, 2012 11:56 pm
- Post datetime: 2012-10-19T17:52:31+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from Ares722
>
> well.. so actually the only way to obtain a uvmapped T posed model is to transfer the uv maps from a ripped model to the t posed one.
Obviously u need a perferct ripp to do this succesfully. ( each model need to have the same number of vertexes)

It seems like it, if you want a perfect T form on the model. I havent tried it but it seems doable. Just a lot more hassle obviously.
## Post #77
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-11-11T19:44:51+00:00
- Post Title: Re: Dark Sider 2 Model?

I'm sorry for bumping this old thread but I would like to say the the size of media.upak after the decompression with ds extractor
(It 2.33 gb for me ),In case i missed some files.

Thank you.
## Post #78
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-09T23:13:43+00:00
- Post Title: Re: Dark Sider 2 Model?

any idea for sound i have dragon unpacker exporting but unreadble
## Post #79
- Username: warzonefury
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 31, 2013 10:43 pm
- Post datetime: 2013-01-31T17:28:23+00:00
- Post Title: Re: Dark Sider 2 Model?

Merci pour ce topic ! Ca m'a beaucoup aidé pour avoirle model 3D de Death  MERCI !!!

Thx for this post ! It helped me a lot to get the 3D model of Death  THANK YOU!
## Post #80
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2013-07-01T17:22:56+00:00
- Post Title: Re: Dark Sider 2 Model?

Could anyone send me some sample files?
## Post #81
- Username: gfhjkm11
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2012 7:38 pm
- Post datetime: 2014-03-21T22:59:37+00:00
- Post Title: Re: Dark Sider 2 Model?

Thx for this post ! It helped me a lot to get the 3D model of Death  THANK YOU!

Link for model [http://webfile.ru/82116eaed472945a7aee7e91bdcbb9a8](http://webfile.ru/82116eaed472945a7aee7e91bdcbb9a8)
## Post #82
- Username: Shadowmist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 06, 2014 3:51 am
- Post datetime: 2014-10-05T20:23:35+00:00
- Post Title: Re: Dark Sider 2 Model?

Hey guys! Is there any way to extract the animations or at least the bones with this? I see your structs account for the bone data but no actual bones are being found in Noesis. Am I doing something wrong or there's no way to extract the bone data at this point?

BTW, just registered
## Post #83
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2014-10-06T08:42:56+00:00
- Post Title: Re: Dark Sider 2 Model?

If you have 3ds max, you could use this script to get model with bones+weights.

[viewtopic.php?f=16&t=11574&hilit=darksiders+2](http://forum.xentax.com/viewtopic.php?f=16&t=11574&hilit=darksiders+2)
## Post #84
- Username: Shadowmist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 06, 2014 3:51 am
- Post datetime: 2014-10-07T16:03:13+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from zaramot
>
> If you have 3ds max, you could use this script to get model with bones+weights.

viewtopic.php?f=16&t=11574&hilit=darksiders+2

You are AMAZING!  Thanks a ton!!
## Post #85
- Username: Shadowmist
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 06, 2014 3:51 am
- Post datetime: 2014-10-11T18:23:12+00:00
- Post Title: Re: Dark Sider 2 Model?

Also, is there a way to extract the animations?
## Post #86
- Username: TheSlayerNL
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 17, 2014 2:10 am
- Post datetime: 2014-10-16T18:14:59+00:00
- Post Title: Re: Dark Sider 2 Model?

A friend of mine told me about this tool, which is awesome, but it doesn't work on DLC's. Is there a way to make it work for DLC's too? They seem to have their own mnfst file, tried using the tool but it just stops responding sadly  I can send the mnfst file for Argul's Tomb DLC (which has an awesome Dragon Boss) through PM if needed 

EDIT: here is a link of what the dragon looks like [http://www.ericspitler.com/frostbanedragonlow.html](http://www.ericspitler.com/frostbanedragonlow.html)
## Post #87
- Username: TheSlayerNL
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 17, 2014 2:10 am
- Post datetime: 2014-10-21T16:11:02+00:00
- Post Title: Re: Dark Sider 2 Model?

So it seems nobody cares for the DLC then? I really hope someone adds a fix for the DLC or makes it for Darksiders 1.
## Post #88
- Username: Yeti
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 01, 2014 1:57 am
- Post datetime: 2014-11-05T19:38:03+00:00
- Post Title: Re: Dark Sider 2 Model?

> Reply from Shadowmist
>
> Also, is there a way to extract the animations?

there is a [dead thread](http://forum.xentax.com/viewtopic.php?f=16&t=11051url) where someone was trying to extract the animation files to a readable format, if you can find anything useful towards being able to do so, please tell me
## Post #89
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2014-11-08T06:22:46+00:00
- Post Title: Re: Dark Sider 2 Model?

sorry as you use the extractor?
