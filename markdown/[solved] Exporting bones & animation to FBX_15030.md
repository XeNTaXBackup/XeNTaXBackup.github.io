## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T05:25:07+00:00
- Post Title: [solved] Exporting bones & animation to FBX

Good day everyone,

This is related to [this question](http://forum.xentax.com/viewtopic.php?f=16&t=14934). In that question, with the help of the answer of Mr shakotay2, I was able to extract the 3D object and exported it to a .obj and .mtl file. Now, I am working on getting the bones and animation. 

DISCLOSURE

I have not done this before so I do not know much. I also haven't done any 3D programming before. And lastly, animation math breaks my brain. 

WHAT I KNOW

In my efforts to complete this task, I have:

Read the book `3D Game Programming with Directx 11` by Mr Luna.
Read the book `Game Coding Complete` by Mike & Rez.
Read a lot of articles online related to `Vertex Skinning`, `Skeletal Animation`.

I am trying to understand how animation is done and coded, to be able to understand how a file could possibly be formatted.

I know the original format I used; .obj doesn't support bones and animation. So, now I'm considering using FBX.

THE GAME FORMAT

The models in the game are stored in 3 files:

- def.t16 - Texture archive, when extracted shows all the related textures of def.
- def.obj - Mesh archive, contains an array of meshes for def. Each mesh has `Faces, Vertex Indices, Vertex Normals, UV`.
- def.ani - Animation archive, all related animation for def.t16.

THE PET

From here on, I will be talking about a specific file: pet.obj and pet.ani. There are only 3 kinds of pets, and they are all birds that fly above the character:

In-game Animation (All 3 pets):



Notice that all 3 pets have the exact same animation. They also animate-in and animate-out when equipped and unequipped. So I'm thinking there are 3 animation for each pet. In, Out and Fly. (although In and Out could simply be a spiral rotate on the mesh) 

Model & Texture (For 1st Pet or index 0):



You can download the pet files [here](http://www.mediafire.com/download/57ppic1tdesd9ek/pet.zip). (I included export scripts in .py)

PET.OBJ

I have mapped most of the structures on pet.obj but there is a few more data that I'm guessing is the bind pose bone structure.

The structure for pet.obj that I have mapped so far:

```
struct PetFace {
    uint16 x 
    uint16 y 
    uint16 z 
}
    
struct PetVertex {
    float   x
    float   y
    float   z
    float   unknown // bone weight??
    uint32  unknown // face/vertex index??
    float   normal_x
    float   normal_y
    float   normal_z
    float   u 
    float   v 
 }
    
struct PetModel {
    byte[14]            header??
    byte[9124]          unknown // bind pose bones??
    	
    uint32                  face_count
    uint32                  face_count  
    uint32                  vertex_count
    uint32                  vertex_count 
    byte[12]                unknown // ??
    uint16                  texture_index
    byte[320]               unknown // ?? some floats
    PetFace[face_count]     faces
    PetVertex[vertex_count] vertices     
}
    
struct PetObjArchive {
    uint32               number_of_models
    uint16               unknown
    PetModel[length] models 
}

```


The data I have mapped is enough to export a full model with texture.

Is there any type of data I should expect for the unknown bytes? vertex weights or bind pose bones maybe?
What kind of structure does bones generally have?
PET.ANI

I don't really know what this file contains but I think it contains Animation data. Here is my understanding of the file:

```
    	float unknown1
    	float unknown2
    	float unknown3
    	float unknown4
    	float unknown5
    	float unknown6
    	float unknown7
    	float unknown8
    	float unknown9
    	float unknown10
    	float unknown11
    	float unknown12
    }
    
    struct AniData {
       uint16 unknown  // always 4, only shows every 4 entry
    	uint16 unknownX
    	uint16 unknownY	
    	
    	AniMatrix[unknownX*unknownY] animation_matrices (?)
    }
    
    struct PetAniArchive {
    	uint32 	number_of_animations? (not sure)
    	
    	AniData[number_of_animations*4] animation_data
    }
```


Of-course this is just a guess. Here is the first few bytes of the pet.ani file and how I got to guess the structure above:

```
    
    // AniData
    04 00       // uint16 - unknown = 4 dec.. 36/9 = 4 (only shows every 4 entries)
    1A 00 		// uint16 - unknown = 26 dec.. 26*85=2210.. 2210*48=106080 (total bytes for this animation matrix?)
    55 00 		// uint16 - unknown = 85 dec.. 26*85=2210.. 2210*48=106080 (total bytes for this animation matrix?)

    // AniMatrix (4x3??)
    00 00 80 3F // float   1.0
    E6 7F 98 37 // float?  1.8179369e-005
    24 07 67 38 // float?  5.5081342e-005
    
    D9 AE 98 37 // float?  1.8201232e-005
    C2 B1 51 3F // float   0.81911862
    08 D9 12 BF // float  -0.57362413
    
    24 07 67 B8 // float? -5.5081342e-005
    F4 D8 12 3F // float   0.57362294
    D1 B1 51 3F // float   0.81911951
    
    BE F8 8A B8 // float? -6.6266846e-005
    E8 80 D8 3F // float   1.6914339
    FF 94 C9 3F // float   1.5748595
    ...repeat 2210 times?
```



Again, I'm guessing that the animation is a 4x3 matrix... Note: Unknown1 only shows up for every 4 entries. 

I parse the file like this:

```
	total_entries = struct.unpack("<I", binary_file.read(4))[0]
	unk1r = 0
	
	for i in range(total_entries * 4):
		if unk1r == 0:
			unknown1 = struct.unpack("<H", binary_file.read(2))[0]
		unk1r = unk1r + 1	
		if unk1r == unknown1:
			unk1r = 0

		unknownX = struct.unpack("<H", binary_file.read(2))[0]
		unknownY = struct.unpack("<H", binary_file.read(2))[0]
		
		for ii in range(unknownX * unknownY):
			matrix = struct.unpack("<ffffffffffff", binary_file.read(48))[0]

```


Adding binary_file.tell() at the end of the script gives me the offset of the last byte of pet.ani. Which means the whole file got read.

How do I move forward?
What could the `unknown*` data possibly be? (I know some unknown could only be game data, but some could actually be used for the bones and animation right?)
How do I export to FBX? (Should I manually create the ASCII file or is there a library I could use?)

Thank you
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-10T06:08:34+00:00
- Post Title: [solved] Exporting bones & animation to FBX

Hi majidemo,

this is so GREAT. Really love to see someone who's truly engaged to understand how things work.

Other than many other newcomers in this forum who are either just leeching or - not really better-
permanently weeping for someone who helps them to get some 3D data analysed.
(Where "help" means that this someone should do ALL the work for them.)

Well, from a quick glance to what you've found out so far I guess those 12 floats might be a 3x3 rotation matrix and 3 floats for the position.

I've made some approaches so far to handle animations using md5anim format (simpler than fbx imho):
[viewtopic.php?f=16&t=12979&p=107315&hil ... im#p107315](http://forum.xentax.com/viewtopic.php?f=16&t=12979&p=107315&hilit=+md5anim#p107315)

(unfinished)
[viewtopic.php?f=16&t=14805&hilit=+md5anim](http://forum.xentax.com/viewtopic.php?f=16&t=14805&hilit=+md5anim)

btw: before it comes to animations it's required to build a skeleton, imho.
First step in building a skeleton is getting the bone names and their hierarchical structure (parent child relationship).

btw: it's very impressive to see that you've used python script to extract png images from the .t16 file - kudos
## Post #3
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T06:29:53+00:00
- Post Title: [solved] Exporting bones & animation to FBX

Hello Mr Shakotay2,

Thank you. I'll look into this. It seems like the format used by doom 3 right?

As for the bones I'm having a harder time because most of the books talked about animation directly with how the bones are used... There were only a few topic about the bone structure and hierarchy. I didn't understand how it would (generally) look like in binary data.

Are bone names required? or can they just be indices? (I didn't see any strings in the binary file)
I'm still looking for binary files that includes bone data. Where I can check how it is structured and get a grasp of what I should be looking for.

I'll update this once I get a better idea about bones. Thanks again.

-------------------
I saw this structure from a book (Introduction to 3D Game Programming with DirectX 9.0c: A Shader Approach)

```
   D3DXVECTOR3 pos;
   float zAngle;

   D3DXMATRIX toParentXForm;
   D3DXMATRIX toWorldXForm;
}

```

With that information, I'm thinking of looking for 16 bytes of pos + zAngle (4 floats). But I don't know how many bytes the D3DXMATRIX should be. I'll continue investigating.

-------------------
btw, this article is great. Gave me a better idea of how bones are structured in the file format: [http://tfc.duke.free.fr/coding/md5-specs-en.html](http://tfc.duke.free.fr/coding/md5-specs-en.html)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-10T06:59:37+00:00
- Post Title: [solved] Exporting bones & animation to FBX

> Reply from majidemo
>
> and hierarchy. But I don't understand how it (generally) would look like in binary data.here's the hierarchy table with the parent IDs from a brawler hkx file (starting at 0x2DE with FFFF = -1):



bones_hierarchy_Brawler.jpg (151.11 KiB) Viewed 314 times


But it's not always like that. Often the parent ids are located before the bone names/matrix.

> Are bone names required? or can they just be indexes? (I didn't see any strings in the binary file)indices should do - especially then there's only a few bones.
## Post #5
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T07:17:53+00:00
- Post Title: [solved] Exporting bones & animation to FBX

Thank you sir.

With that screenshot you just gave (brawler hkx). I saw this pattern on the file I'm analyzing:

```
5A F5 AD 40 CD 3B 2A 40 00 00 00 00 00 00 00 00  > unknown bytes (check update below)
00 00 00 00 00 00 00 00                         /

-1          0  // root bone?
FF FF FF FF 00 00 00 00 00 00 00 00 FF FF 00 00 
00 00 00 00 00 80 00 00 80 3F 00 00 00 00 00 00 
...318 bytes remaining

0           1  // GUESS: parent_id = 0, bone_id = 1
00 00 00 00 01 00 00 00 00 00 00 00 FF FF 00 00 
80 3F 00 00 00 80 00 00 00 00 00 00 00 00 00 00 
...318 bytes remaining

0           2  // GUESS: parent_id = 0, bone_id = 2
00 00 00 00 02 00 00 00 00 00 00 00 FF FF 00 00 
00 80 00 00 80 3F 00 00 00 00 00 00 00 00 00 00 
...318 bytes remaining

2           3  // GUESS: parent_id = 2, bone_id = 3
02 00 00 00 03 00 00 00 00 00 00 00 FF FF 00 00 
00 00 00 00 80 3F 00 00 00 80 00 00 00 00 43 67 
...318 bytes remaining

...repeat pattern 22 more times

```

That pattern was taken from pet.obj, the part: 
```
byte[9124] unknown // bind pose bones??
```


Noticed:

2 increasing numbers. indices?
Pattern gets repeated 26 times. number of bones? (odd for a simple bird to have that many bones...)

So this could be the root bone:

```
00 00 00 00 00 00 80 00 00 80 3F 00 00 00 00 
00 00 00 80 00 00 80 3F 00 00 00 80 00 00 00 
00 00 00 80 BF 00 00 00 80 00 00 00 00 00 00 
00 00 64 5D 0C BF CB A1 FD BF 00 00 00 00 00 
00 80 3F 00 00 00 00 00 00 00 00 00 00 80 BF 
00 00 00 00 00 00 00 00 00 00 80 3F 00 00 00 
00 00 00 00 00 00 00 80 3F 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 80 CB A1 FD 3F 64 
5D 0C BF 00 00 80 3F 00 00 80 3F 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 
3F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 80 3F 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 80 3F 00 00 00 00 
00 00 00 00 00 00 80 BF 00 00 00 00 00 00 00 
00 00 00 80 3F 00 00 00 00 00 00 00 00 00 00 
80 3F 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 80 CB A1 FD 3F 64 5D 0C BF 00 00 80 3F 
AF F0 67 38 0A FA 91 BE E6 5F 75 BF 00 00 00 
00 DD 11 99 37 E3 5F 75 3F 21 FA 91 BE 00 00 
00 00 00 00 80 3F EA FF 81 B5 16 AE 73 38 00 
00 00 00 00 00 00 80 70 2E 8A 42 29 8B 1E C2 
00 00 80 3F 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00
```
[/size]

--------------------------
UPDATE

Or maybe it should be (to cover the unknown bytes above):


```
A5 4E 38 C0 00 00 00 00 CD 3B 2A C0 A5 4E 38 
40 5A F5 AD 40 CD 3B 2A 40 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 FF FF FF FF 00 
00 00 00 00 00 00 00 FF FF 00 00 00 00 00 00 
00 80 00 00 80 3F 00 00 00 00 00 00 00 80 00 
00 80 3F 00 00 00 80 00 00 00 00 00 00 80 BF 
00 00 00 80 00 00 00 00 00 00 00 00 64 5D 0C 
BF CB A1 FD BF 00 00 00 00 00 00 80 3F 00 00 
00 00 00 00 00 00 00 00 80 BF 00 00 00 00 00 
00 00 00 00 00 80 3F 00 00 00 00 00 00 00 00 
00 00 80 3F 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 80 CB A1 FD 3F 64 5D 0C BF 00 00 
80 3F 00 00 80 3F 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 80 3F 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 
3F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 80 3F 00 00 00 00 00 00 00 00 00 
00 80 BF 00 00 00 00 00 00 00 00 00 00 80 3F 
00 00 00 00 00 00 00 00 00 00 80 3F 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 80 CB A1 
FD 3F 64 5D 0C BF 00 00 80 3F AF F0 67 38 0A 
FA 91 BE E6 5F 75 BF 00 00 00 00 DD 11 99 37 
E3 5F 75 3F 21 FA 91 BE 00 00 00 00 00 00 80 
3F EA FF 81 B5 

// bone index 0?
16 AE 73 38 00 00 00 00 00 00 00 80 70 2E 8A 
42 29 8B 1E C2 00 00 80 3F 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 01 
00 00 00 00 00 00 00 FF FF 00 00 80 3F 00 00 
00 80 00 00 00 00 00 00 00 00 00 00 00 80 00 
00 80 3F 00 00 00 80 00 00 00 00 00 00 00 00 
00 00 00 80 00 00 80 3F 00 00 00 00 00 00 00 
00 EF C9 C3 BC 64 5D 0C 3F 00 00 80 3F 00 00 
80 3F 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 80 3F 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 80 3F 00 00 00 
00 00 00 00 80 EF C9 C3 3C 64 5D 0C BF 00 00 
80 3F 00 00 80 3F 00 00 00 00 00 00 00 00 00 
00 00 00 00 00 00 00 00 00 80 3F 00 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 00 80 
3F 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
00 00 00 00 80 3F 00 00 00 00 00 00 00 00 00 
00 80 3F 00 00 00 00 00 00 00 00 00 00 80 3F 
00 00 00 00 00 00 00 00 00 00 80 BF 00 00 00 
00 00 00 00 00 00 00 00 00 00 00 00 00 A3 92 
FA BF 00 00 00 00 00 00 80 3F 00 00 80 3F 32 
F4 9A B7 F3 91 34 36 00 00 00 00 7A 95 A7 37 
FD FF 7F 3F 98 1A AD 33 00 00 00 00 3F 1B 43 
B6 0E B6 AA 33

```
[/size]
## Post #6
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T07:43:18+00:00
- Post Title: [solved] Exporting bones & animation to FBX

If my understanding (explained above) is right.

I would update my structure for PetModel into something like:

```
    byte[14]   Header
    byte[9100] Bones
    byte[24]   unknown

    ... 
}

```

The 1st Header looks like this:

```
1B 00 00 00 1A 00 05 00 0D 00 09 00 03 00

```

I believe each bone has 350 bytes. So 9100/350 = 26, 26 which is on the header. This could mean there are 26 bones.

But why would a bone have too much information? 350 bytes?
What's more odd is why would a simple bird have 26 bones? (model used biped?)
PET.OBJ


 Yellow - number of segment/data in this archive.
 Green - unknown
 Cyan - segment header
 Light Green - 1st bone for this segment
 Gray - 2nd bone... (partial)

-------------------------------
You're right about .md5mesh and .md5anim. Easier to understand and export to. Thanks for the suggestion.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-10T13:35:57+00:00
- Post Title: [solved] Exporting bones & animation to FBX

did you think about the obj files which you've extracted from the binary pet.obj file?
It's 3 x 9 (27= 0x1B), 3 different birds.
## Post #8
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T13:43:21+00:00
- Post Title: [solved] Exporting bones & animation to FBX

> Reply from shakotay2
>
> did you think about the obj files which you've extracted from the binary pet.obj file?
It's 3 x 9 (27= 0x1B), 3 different birds.
Yes I noticed. It looks like the same bird gets repeated 9 times. I'm not sure why. The first 4 bytes of the obj file is 27. And I believe it has 27 segments. So I deduced that 27/3(birds) is 9 entries per bird. But I don't understand why they would do that. Seems redundant?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-10T13:51:58+00:00
- Post Title: [solved] Exporting bones & animation to FBX

dunno - the 9 models are not identical. pet_12_mesh is a little bit bigger than pet_11_mesh, pet_21_mesh is much smaller than pet_20_mesh, for example.
## Post #10
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T13:54:26+00:00
- Post Title: [solved] Exporting bones & animation to FBX

> Reply from shakotay2
>
> dunno - the 9 models are not identical. pet_21_mesh is much smaller than pet_20_mesh, for example.
Gives me the idea that maybe they have 9 different meshes depending on the detail setting on the game? Or distance of the camera? Another guess would be, they actually have a larger bird as the level of the pet gets higher. Maybe I just did not notice while playing.

On another note. Do you have any more suggestion on the structure of the bone? Do you think my analogy above is right?
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-10T14:08:29+00:00
- Post Title: [solved] Exporting bones & animation to FBX

In this early state anything is pure presumption.
You could search for 00000000000000FFFF0000 (270 finds),
then check the numbers before it.

For the last find it's 16 000000 17 (000000).

Seems it's your 350 bytes blocks where 10 of them might belong together (27x10):
-1 0
0 1
0 2
2 3
3 4
4 5
0F 10
13 14
3 16
16 17

But if it the number pairs were bone ids there's too many missing (6..0E, 0x11, 0x12, 0x15).
## Post #12
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T15:10:51+00:00
- Post Title: [solved] Exporting bones & animation to FBX

> Reply from shakotay2
>
> In this early state anything is pure presumption.
You could search for 00000000000000FFFF0000 (270 finds),
then check the numbers before it.

For the last find it's 16 000000 17 (000000).

Seems it's your 350 bytes blocks where 10 of them might belong together (27x10):
-1 0
0 1
0 2
2 3
3 4
4 5
0F 10
13 14
3 16
16 17

But if it the number pairs were bone ids there's too many missing (6..0E, 0x11, 0x12, 0x15).
I'm not sure what you mean. I extracted the first instance of byte[9100] Bones. You can find it [here](http://pastebin.com/raw/LG5kWEXE).

Then I wrote this script to parse the parent_id and bone_id:

```
		binary_file.seek(40, 1)
		bones = struct.unpack("<II", binary_file.read(8))

		parent_id = bones[0]
		bone_id   = bones[1]
		
		print bones
		
		binary_file.seek(302, 1)

```

Which gave me:

```
(-1, 0)
(0, 1)
(0, 2)
(2, 3)
(3, 4)
(4, 5)
(4, 6)
(6, 7)
(7, 8)
(8, 9)
(4, 10)
(10, 11)
(11, 12)
(12, 13)
(3, 14)
(14, 15)
(15, 16)
(16, 17)
(3, 18)
(18, 19)
(19, 20)
(20, 21)
(3, 22)
(22, 23)
(13, 24)
(9, 25)

```

I didn't notice anything missing. The bone index is complete and incremental. The parent index makes sense because all of it is within the number of bones. Am I doing this wrong?
-------------------------
Searching for 000000000000FFFF on the first segment of data finds 27 instances, but the first one is just due to the -1 parent id. So there are only technically 26 real instances which I believe a pattern. And with 26 showing up again, I think it really means something specially as it is found on the header.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-10T15:26:56+00:00
- Post Title: [solved] Exporting bones & animation to FBX

> Reply from majidemo
>
> I'm not sure what you mean.yeah, I should have searched for 00000000000000FFFF, that gives 885 finds.

> Am I doing this wrong?guess: no.
We'd need to know what is wings and what is legs, now.

Something like this (wild guess, as always  ):
(-1, 0)
(0, 1)
(0, 2)
(2, 3)
(3, 4)
(4, 5)
(4, 6)
(6, 7)
(7, 
(8, 9)

(4, 10)   left wing
(10, 11)
(11, 12)
(12, 13)

(3, 14)   right wing
(14, 15)
(15, 16)
(16, 17)

(3, 18)   left tigh
(18, 19)
(19, 20)
(20, 21) left foot

(3, 22) right tigh
(22, 23)
(13, 24) this disturbs my thoughts
(9, 25)  this, too
## Post #14
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-10T15:34:18+00:00
- Post Title: [solved] Exporting bones & animation to FBX

> Reply from shakotay2
>
> majidemo wrote:I'm not sure what you mean.yeah, I should have searched for 00000000000000FFFF, that gives 885 finds.
Am I doing this wrong?guess: no.
We'd need to know what is wings and what is legs, now.
I'll look into it. Thank you for taking your time in helping me, as always. 
I'll update this reply as soon as I find out what all this 350 bytes (or some) per bone actually means.

-----------------------------
I did some trial and error on the values of the bones (trying to map any float from the 350 bytes). You can find the values of each bone [here](http://pastebin.com/raw/t6Nzgyjc).

Here are some results... (nothing much really)
## Post #15
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-11T09:04:16+00:00
- Post Title: [solved] Exporting bones & animation to FBX

Here is the file I generated for the index 0 Pet. (in case you needed it for reference)


```
commandline "Exported by majidemo w/ shakotay2"

numJoints 26
numMeshes 1

joints {
	"bone_0"	-1 ( 0.000000 1.000000 -0.000000 ) ( -0.000000 -0.000000 1.000000 )
	"bone_1"	0 ( 1.000000 0.000000 -0.000000 ) ( -0.000000 -0.000000 1.000000 )
	"bone_2"	0 ( -0.000000 0.000000 1.000000 ) ( 1.000000 -0.000000 0.000000 )
	"bone_3"	2 ( 0.000000 -0.000000 1.000000 ) ( 0.771107 -0.636706 -0.000000 )
	"bone_4"	3 ( 0.000000 -0.000000 1.000000 ) ( 0.987568 -0.157195 -0.000000 )
	"bone_5"	4 ( 0.000000 -0.000000 1.000000 ) ( 0.989017 -0.147803 -0.000000 )
	"bone_6"	4 ( 0.989017 0.000049 0.147836 ) ( -0.114047 0.636102 0.763126 )
	"bone_7"	6 ( 0.909711 -0.314122 -0.271586 ) ( -0.026728 0.608458 -0.793171 )
	"bone_8"	7 ( 0.552794 0.787791 -0.271620 ) ( -0.592232 0.142132 -0.793141 )
	"bone_9"	8 ( -0.281159 0.881071 0.380364 ) ( -0.131976 0.357022 -0.924700 )
	"bone_10"	4 ( -0.989017 -0.000049 0.147836 ) ( -0.114047 0.636102 -0.763126 )
	"bone_11"	10 ( -0.909711 0.314122 -0.271586 ) ( -0.026728 0.608458 0.793171 )
	"bone_12"	11 ( -0.552794 -0.787791 -0.271620 ) ( -0.592232 0.142132 0.793141 )
	"bone_13"	12 ( 0.281159 -0.881071 0.380364 ) ( -0.131976 0.357022 0.924700 )
	"bone_14"	3 ( -0.062046 -0.471245 0.879783 ) ( -0.965138 0.252918 0.067472 )
	"bone_15"	14 ( 0.202747 -0.429908 0.879804 ) ( -0.948540 -0.309373 0.067460 )
	"bone_16"	15 ( -0.000000 0.156399 -0.987694 ) ( -1.000000 -0.000000 -0.000000 )
	"bone_17"	16 ( 0.156399 0.000000 -0.987694 ) ( -0.000000 1.000000 0.000000 )
	"bone_18"	3 ( 0.062046 0.471245 0.879783 ) ( -0.965138 0.252918 -0.067472 )
	"bone_19"	18 ( -0.202747 0.429908 0.879804 ) ( -0.948540 -0.309373 -0.067460 )
	"bone_20"	19 ( 0.000000 -0.156399 -0.987694 ) ( -1.000000 -0.000000 0.000000 )
	"bone_21"	20 ( -0.156399 0.000000 -0.987694 ) ( -0.000000 1.000000 0.000000 )
	"bone_22"	3 ( 0.000000 -0.000000 1.000000 ) ( -0.544900 0.838501 0.000000 )
	"bone_23"	22 ( 0.000000 -0.000000 1.000000 ) ( -0.508793 0.860889 0.000000 )
	"bone_24"	13 ( 0.281171 -0.880760 0.381035 ) ( -0.131928 0.357778 0.924428 )
	"bone_25"	9 ( -0.281171 0.880760 0.381035 ) ( -0.131928 0.357778 -0.924428 )
}

mesh {
	shader "pet_t16/0.png"

	numverts 124
	vert 0 ( 0.801100 0.143500 ) 0 1
	vert 1 ( 0.773900 0.028200 ) 1 1
	vert 2 ( 0.824200 0.129000 ) 2 1
	vert 3 ( 0.742800 0.260800 ) 3 1
	vert 4 ( 0.974800 0.218300 ) 4 1
	vert 5 ( 0.838800 0.174600 ) 5 1
	vert 6 ( 0.851100 0.133600 ) 6 1
	vert 7 ( 0.218200 0.205800 ) 7 1
	vert 8 ( 0.289800 0.018600 ) 8 1
	vert 9 ( 0.291300 0.167500 ) 9 1
	vert 10 ( 0.212900 0.044100 ) 10 1
	vert 11 ( 0.161200 0.092800 ) 11 1
	vert 12 ( 0.154400 0.177700 ) 12 1
	vert 13 ( 0.257200 0.211700 ) 13 1
	vert 14 ( 0.217000 0.228700 ) 14 1
	vert 15 ( 0.182000 0.213300 ) 15 1
	vert 16 ( 0.234700 0.361400 ) 16 1
	vert 17 ( 0.492500 0.134600 ) 17 1
	vert 18 ( 0.473500 0.150500 ) 18 1
	vert 19 ( 0.415200 0.119300 ) 19 1
	vert 20 ( 0.447400 0.080400 ) 20 1
	vert 21 ( 0.506200 0.184500 ) 21 1
	vert 22 ( 0.560100 0.187300 ) 22 1
	vert 23 ( 0.499600 0.239600 ) 23 1
	vert 24 ( 0.558400 0.083700 ) 24 1
	vert 25 ( 0.605800 0.143000 ) 25 1
	vert 26 ( 0.671200 0.097300 ) 26 1
	vert 27 ( 0.655700 0.232700 ) 27 1
	vert 28 ( 0.742700 0.391000 ) 28 1
	vert 29 ( 0.616000 0.318100 ) 29 1
	vert 30 ( 0.625300 0.080200 ) 30 1
	vert 31 ( 0.621800 0.049900 ) 31 1
	vert 32 ( 0.614300 0.243300 ) 32 1
	vert 33 ( 0.445100 0.397400 ) 33 1
	vert 34 ( 0.517000 0.038700 ) 34 1
	vert 35 ( 0.517100 0.416700 ) 35 1
	vert 36 ( 0.534100 0.597300 ) 36 1
	vert 37 ( 0.755000 0.550500 ) 37 1
	vert 38 ( 0.915800 0.616200 ) 38 1
	vert 39 ( 0.437100 0.612900 ) 39 1
	vert 40 ( 0.624800 0.790400 ) 40 1
	vert 41 ( 0.728600 0.870600 ) 41 1
	vert 42 ( 0.674400 0.981900 ) 42 1
	vert 43 ( 0.741800 0.741200 ) 43 1
	vert 44 ( 0.812500 0.857700 ) 44 1
	vert 45 ( 0.858300 0.755400 ) 45 1
	vert 46 ( 0.912700 0.557000 ) 46 1
	vert 47 ( 0.964800 0.759100 ) 47 1
	vert 48 ( 0.933900 0.964600 ) 48 1
	vert 49 ( 0.886100 0.837300 ) 49 1
	vert 50 ( 0.792000 0.912200 ) 50 1
	vert 51 ( 0.433800 0.133400 ) 51 1
	vert 52 ( 0.349300 0.129000 ) 52 1
	vert 53 ( 0.392900 0.106100 ) 53 1
	vert 54 ( 0.699100 0.215300 ) 54 1
	vert 55 ( 0.544100 0.782000 ) 55 1
	vert 56 ( 0.530200 0.978100 ) 56 1
	vert 57 ( 0.270000 0.988500 ) 57 1
	vert 58 ( 0.517700 0.816500 ) 58 1
	vert 59 ( 0.287600 0.911300 ) 59 1
	vert 60 ( 0.471900 0.733800 ) 60 1
	vert 61 ( 0.316600 0.742200 ) 61 1
	vert 62 ( 0.081600 0.802400 ) 62 1
	vert 63 ( 0.079300 0.889400 ) 63 1
	vert 64 ( 0.305000 0.589600 ) 64 1
	vert 65 ( 0.237100 0.906100 ) 65 1
	vert 66 ( 0.289100 0.428800 ) 66 1
	vert 67 ( 0.061600 0.421200 ) 67 1
	vert 68 ( 0.077100 0.606600 ) 68 1
	vert 69 ( 0.237100 0.908900 ) 69 1
	vert 70 ( 0.055600 0.968700 ) 70 1
	vert 71 ( 0.059100 0.285000 ) 71 1
	vert 72 ( 0.755000 0.550500 ) 72 1
	vert 73 ( 0.912700 0.557000 ) 73 1
	vert 74 ( 0.801100 0.143500 ) 74 1
	vert 75 ( 0.824200 0.129000 ) 75 1
	vert 76 ( 0.773900 0.028200 ) 76 1
	vert 77 ( 0.742800 0.260800 ) 77 1
	vert 78 ( 0.838800 0.174600 ) 78 1
	vert 79 ( 0.974800 0.218300 ) 79 1
	vert 80 ( 0.851100 0.133600 ) 80 1
	vert 81 ( 0.218200 0.205800 ) 81 1
	vert 82 ( 0.291300 0.167500 ) 82 1
	vert 83 ( 0.289800 0.018600 ) 83 1
	vert 84 ( 0.212900 0.044100 ) 84 1
	vert 85 ( 0.161200 0.092800 ) 85 1
	vert 86 ( 0.154400 0.177700 ) 86 1
	vert 87 ( 0.257200 0.211700 ) 87 1
	vert 88 ( 0.217000 0.228700 ) 88 1
	vert 89 ( 0.182000 0.213300 ) 89 1
	vert 90 ( 0.234700 0.361400 ) 90 1
	vert 91 ( 0.492500 0.134600 ) 91 1
	vert 92 ( 0.415200 0.119300 ) 92 1
	vert 93 ( 0.560100 0.187300 ) 93 1
	vert 94 ( 0.605800 0.143000 ) 94 1
	vert 95 ( 0.558400 0.083700 ) 95 1
	vert 96 ( 0.655700 0.232700 ) 96 1
	vert 97 ( 0.616000 0.318100 ) 97 1
	vert 98 ( 0.625300 0.080200 ) 98 1
	vert 99 ( 0.614300 0.243300 ) 99 1
	vert 100 ( 0.517100 0.416700 ) 100 1
	vert 101 ( 0.534100 0.597300 ) 101 1
	vert 102 ( 0.755000 0.550500 ) 102 1
	vert 103 ( 0.915800 0.616200 ) 103 1
	vert 104 ( 0.624800 0.790400 ) 104 1
	vert 105 ( 0.728600 0.870600 ) 105 1
	vert 106 ( 0.741800 0.741200 ) 106 1
	vert 107 ( 0.812500 0.857700 ) 107 1
	vert 108 ( 0.858300 0.755400 ) 108 1
	vert 109 ( 0.886100 0.837300 ) 109 1
	vert 110 ( 0.792000 0.912200 ) 110 1
	vert 111 ( 0.530200 0.978100 ) 111 1
	vert 112 ( 0.517700 0.816500 ) 112 1
	vert 113 ( 0.471900 0.733800 ) 113 1
	vert 114 ( 0.081600 0.802400 ) 114 1
	vert 115 ( 0.305000 0.589600 ) 115 1
	vert 116 ( 0.079300 0.889400 ) 116 1
	vert 117 ( 0.237100 0.906100 ) 117 1
	vert 118 ( 0.289100 0.428800 ) 118 1
	vert 119 ( 0.077100 0.606600 ) 119 1
	vert 120 ( 0.061600 0.421200 ) 120 1
	vert 121 ( 0.237100 0.908900 ) 121 1
	vert 122 ( 0.059100 0.285000 ) 122 1
	vert 123 ( 0.755000 0.550500 ) 123 1

	numtris 202
	tri 0 0 1 2
	tri 1 2 3 0
	tri 2 2 4 5
	tri 3 5 3 2
	tri 4 2 1 6
	tri 5 6 4 2
	tri 6 6 1 0
	tri 7 0 5 6
	tri 8 5 4 6
	tri 9 0 3 5
	tri 10 7 8 9
	tri 11 8 7 10
	tri 12 11 10 7
	tri 13 7 12 11
	tri 14 8 11 12
	tri 15 12 9 8
	tri 16 7 9 13
	tri 17 13 14 7
	tri 18 15 7 14
	tri 19 7 15 12
	tri 20 13 12 15
	tri 21 12 13 9
	tri 22 13 16 14
	tri 23 14 16 15
	tri 24 15 16 13
	tri 25 17 18 19
	tri 26 17 19 20
	tri 27 21 22 23
	tri 28 17 24 25
	tri 29 25 26 27
	tri 30 28 29 27
	tri 31 30 31 26
	tri 32 24 17 20
	tri 33 29 23 32
	tri 34 23 29 33
	tri 35 30 34 31
	tri 36 22 18 17
	tri 37 35 33 29
	tri 38 36 35 37
	tri 39 33 35 36
	tri 40 37 35 38
	tri 41 36 39 33
	tri 42 40 39 36
	tri 43 35 29 38
	tri 44 40 41 42
	tri 45 43 44 41
	tri 46 45 43 37
	tri 47 46 47 37
	tri 48 47 48 49
	tri 49 45 44 43
	tri 50 41 50 42
	tri 51 48 42 50
	tri 52 50 49 48
	tri 53 19 18 51
	tri 54 51 52 19
	tri 55 20 19 53
	tri 56 52 53 19
	tri 57 49 44 45
	tri 58 49 50 44
	tri 59 27 54 28
	tri 60 26 54 27
	tri 61 27 29 32
	tri 62 55 40 42
	tri 63 43 36 37
	tri 64 27 32 25
	tri 65 32 23 22
	tri 66 24 34 30
	tri 67 20 34 24
	tri 68 25 24 30
	tri 69 25 30 26
	tri 70 32 22 25
	tri 71 25 22 17
	tri 72 43 41 40
	tri 73 43 40 36
	tri 74 39 40 55
	tri 75 47 49 45
	tri 76 47 45 37
	tri 77 18 22 21
	tri 78 56 57 58
	tri 79 59 58 57
	tri 80 60 59 61
	tri 81 59 60 58
	tri 82 58 57 56
	tri 83 57 58 59
	tri 84 61 59 60
	tri 85 58 60 59
	tri 86 62 63 64
	tri 87 64 63 65
	tri 88 66 67 68
	tri 89 68 62 64
	tri 90 69 70 63
	tri 91 64 63 62
	tri 92 63 64 65
	tri 93 62 68 64
	tri 94 68 67 66
	tri 95 68 66 64
	tri 96 64 66 68
	tri 97 66 71 67
	tri 98 67 71 66
	tri 99 46 37 72
	tri 100 72 73 46
	tri 101 74 75 76
	tri 102 75 74 77
	tri 103 75 78 79
	tri 104 78 75 77
	tri 105 75 80 76
	tri 106 80 75 79
	tri 107 80 74 76
	tri 108 74 80 78
	tri 109 78 80 79
	tri 110 74 78 77
	tri 111 81 82 83
	tri 112 83 84 81
	tri 113 85 81 84
	tri 114 81 85 86
	tri 115 83 86 85
	tri 116 86 83 82
	tri 117 81 87 82
	tri 118 87 81 88
	tri 119 89 88 81
	tri 120 81 86 89
	tri 121 87 89 86
	tri 122 86 82 87
	tri 123 87 88 90
	tri 124 88 89 90
	tri 125 89 87 90
	tri 126 91 92 18
	tri 127 91 20 92
	tri 128 21 23 93
	tri 129 91 94 95
	tri 130 94 96 26
	tri 131 28 96 97
	tri 132 98 26 31
	tri 133 95 20 91
	tri 134 97 99 23
	tri 135 23 33 97
	tri 136 98 31 34
	tri 137 93 91 18
	tri 138 100 97 33
	tri 139 101 102 100
	tri 140 33 101 100
	tri 141 102 103 100
	tri 142 101 33 39
	tri 143 104 101 39
	tri 144 100 103 97
	tri 145 104 42 105
	tri 146 106 105 107
	tri 147 108 102 106
	tri 148 46 102 47
	tri 149 47 109 48
	tri 150 108 106 107
	tri 151 105 42 110
	tri 152 48 110 42
	tri 153 110 48 109
	tri 154 92 51 18
	tri 155 51 92 52
	tri 156 20 53 92
	tri 157 52 92 53
	tri 158 109 108 107
	tri 159 109 107 110
	tri 160 96 28 54
	tri 161 26 96 54
	tri 162 96 99 97
	tri 163 55 42 104
	tri 164 106 102 101
	tri 165 96 94 99
	tri 166 99 93 23
	tri 167 95 98 34
	tri 168 20 95 34
	tri 169 94 98 95
	tri 170 94 26 98
	tri 171 99 94 93
	tri 172 94 91 93
	tri 173 106 104 105
	tri 174 106 101 104
	tri 175 39 55 104
	tri 176 47 108 109
	tri 177 47 102 108
	tri 178 18 21 93
	tri 179 111 112 57
	tri 180 59 57 112
	tri 181 113 61 59
	tri 182 59 112 113
	tri 183 112 111 57
	tri 184 57 59 112
	tri 185 61 113 59
	tri 186 112 59 113
	tri 187 114 115 116
	tri 188 115 117 116
	tri 189 118 119 120
	tri 190 119 115 114
	tri 191 121 116 70
	tri 192 115 114 116
	tri 193 116 117 115
	tri 194 114 115 119
	tri 195 119 118 120
	tri 196 119 115 118
	tri 197 115 119 118
	tri 198 118 120 122
	tri 199 120 118 122
	tri 200 46 123 102
	tri 201 123 46 73

	numweights 124
	weight 0 16 1.000000 ( 0.418200 -0.533300 0.203600 )
	weight 1 16 1.000000 ( 0.320100 0.178100 0.022100 )
	weight 2 16 1.000000 ( 0.504900 -0.445200 0.470500 )
	weight 3 16 1.000000 ( 0.196300 -1.252000 0.012300 )
	weight 4 16 1.000000 ( 1.065200 -1.003100 0.023800 )
	weight 5 16 1.000000 ( 0.558100 -0.726700 0.160800 )
	weight 6 16 1.000000 ( 0.605500 -0.475200 0.206600 )
	weight 7 14 1.000000 ( 0.459100 -0.491800 0.881300 )
	weight 8 14 1.000000 ( 0.658200 -0.348200 1.375400 )
	weight 9 14 1.000000 ( 0.662300 -0.140000 0.982400 )
	weight 10 14 1.000000 ( 0.444400 -0.736100 1.308100 )
	weight 11 14 1.000000 ( 0.301000 -0.463200 1.179700 )
	weight 12 14 1.000000 ( 0.282200 -0.245600 0.955500 )
	weight 13 15 1.000000 ( 0.567500 -0.237400 0.865700 )
	weight 14 15 1.000000 ( 0.455900 -0.375800 0.820700 )
	weight 15 15 1.000000 ( 0.358600 -0.295400 0.861500 )
	weight 16 16 1.000000 ( 0.504900 -0.445200 0.470500 )
	weight 17 5 1.000000 ( 0.141400 -2.049300 4.866500 )
	weight 18 5 1.000000 ( 0.000000 -2.114500 4.735300 )
	weight 19 5 1.000000 ( 0.063700 -2.424000 4.795700 )
	weight 20 5 1.000000 ( 0.000000 -2.261200 5.047400 )
	weight 21 5 1.000000 ( 0.000000 -1.966100 4.607700 )
	weight 22 5 1.000000 ( 0.129900 -1.865000 4.632800 )
	weight 23 5 1.000000 ( 0.000000 -1.904700 4.385000 )
	weight 24 5 1.000000 ( 0.271600 -1.928900 5.153600 )
	weight 25 5 1.000000 ( 0.431000 -1.609900 4.927500 )
	weight 26 5 1.000000 ( 0.000000 -1.292900 5.267900 )
	weight 27 5 1.000000 ( 0.331100 -1.256400 4.606600 )
	weight 28 4 1.000000 ( 0.000000 -0.878500 3.963500 )
	weight 29 4 1.000000 ( 0.387500 -1.454700 4.083600 )
	weight 30 5 1.000000 ( 0.254000 -1.576600 5.257400 )
	weight 31 5 1.000000 ( 0.000000 -1.606400 5.436200 )
	weight 32 5 1.000000 ( 0.404000 -1.510600 4.447300 )
	weight 33 3 1.000000 ( 0.000000 -2.052200 3.536700 )
	weight 34 5 1.000000 ( 0.000000 -2.021200 5.333100 )
	weight 35 3 1.000000 ( 0.697900 -1.769900 3.485500 )
	weight 36 3 1.000000 ( 0.651500 -1.584500 2.622500 )
	weight 37 3 1.000000 ( 0.820200 -0.765500 3.110700 )
	weight 38 3 1.000000 ( 0.664600 -0.642000 3.718800 )
	weight 39 3 1.000000 ( 0.000000 -1.903400 2.446100 )
	weight 40 3 1.000000 ( 0.663900 -1.196800 1.728700 )
	weight 41 14 1.000000 ( 0.444400 -0.736100 1.308100 )
	weight 42 2 1.000000 ( 0.000000 -0.903200 1.316500 )
	weight 43 3 1.000000 ( 0.875100 -0.743000 1.844100 )
	weight 44 14 1.000000 ( 0.658200 -0.348200 1.375400 )
	weight 45 3 1.000000 ( 0.701000 -0.221000 2.066400 )
	weight 46 3 1.000000 ( -0.000000 -0.154200 3.263800 )
	weight 47 22 1.000000 ( -0.000000 0.180600 2.336300 )
	weight 48 22 1.000000 ( -0.000000 -0.029700 1.685300 )
	weight 49 22 1.000000 ( 0.605800 0.041500 1.735800 )
	weight 50 14 1.000000 ( 0.301000 -0.463200 1.179700 )
	weight 51 5 1.000000 ( 0.000000 -2.410900 4.723500 )
	weight 52 5 1.000000 ( 0.000000 -2.659900 4.687000 )
	weight 53 5 1.000000 ( 0.000000 -2.472600 4.895200 )
	weight 54 5 1.000000 ( 0.000000 -1.154700 4.748200 )
	weight 55 3 1.000000 ( 0.000000 -1.423300 1.731300 )
	weight 56 22 1.000000 ( 0.605800 0.041500 1.735800 )
	weight 57 22 1.000000 ( -0.000000 0.180600 2.336300 )
	weight 58 23 1.000000 ( 0.396300 1.366100 0.984900 )
	weight 59 23 1.000000 ( -0.000000 1.569800 1.238200 )
	weight 60 23 1.000000 ( 1.100100 2.659900 0.613200 )
	weight 61 23 1.000000 ( -0.000000 2.417200 0.727700 )
	weight 62 8 1.000000 ( 1.762800 -1.841000 3.526100 )
	weight 63 3 1.000000 ( 0.664600 -0.642000 3.718800 )
	weight 64 8 1.000000 ( 1.725600 -0.040300 3.609900 )
	weight 65 3 1.000000 ( 0.820200 -0.765500 3.110700 )
	weight 66 9 1.000000 ( 1.769500 1.155400 3.495500 )
	weight 67 9 1.000000 ( 2.129100 0.281900 1.942100 )
	weight 68 8 1.000000 ( 2.879800 -1.042200 2.387500 )
	weight 69 4 1.000000 ( 0.387500 -1.454700 4.083600 )
	weight 70 4 1.000000 ( 0.000000 -0.878500 3.963500 )
	weight 71 9 1.000000 ( 1.112400 2.323200 2.420700 )
	weight 72 3 1.000000 ( 0.664600 -0.642000 3.718800 )
	weight 73 4 1.000000 ( 0.000000 -0.878500 3.963500 )
	weight 74 20 1.000000 ( -0.418200 -0.533300 0.203600 )
	weight 75 20 1.000000 ( -0.504900 -0.445200 0.470500 )
	weight 76 20 1.000000 ( -0.320100 0.178100 0.022100 )
	weight 77 20 1.000000 ( -0.196300 -1.252000 0.012300 )
	weight 78 20 1.000000 ( -0.558100 -0.726700 0.160800 )
	weight 79 20 1.000000 ( -1.065200 -1.003100 0.023800 )
	weight 80 20 1.000000 ( -0.605500 -0.475200 0.206600 )
	weight 81 18 1.000000 ( -0.459100 -0.491800 0.881300 )
	weight 82 18 1.000000 ( -0.662300 -0.140000 0.982400 )
	weight 83 18 1.000000 ( -0.658200 -0.348200 1.375400 )
	weight 84 18 1.000000 ( -0.444400 -0.736100 1.308100 )
	weight 85 18 1.000000 ( -0.301000 -0.463200 1.179700 )
	weight 86 18 1.000000 ( -0.282200 -0.245600 0.955500 )
	weight 87 19 1.000000 ( -0.567500 -0.237400 0.865700 )
	weight 88 19 1.000000 ( -0.455900 -0.375800 0.820700 )
	weight 89 19 1.000000 ( -0.358600 -0.295400 0.861500 )
	weight 90 20 1.000000 ( -0.504900 -0.445200 0.470500 )
	weight 91 5 1.000000 ( -0.141400 -2.049300 4.866500 )
	weight 92 5 1.000000 ( -0.063700 -2.424000 4.795700 )
	weight 93 5 1.000000 ( -0.129900 -1.865000 4.632800 )
	weight 94 5 1.000000 ( -0.431000 -1.609900 4.927500 )
	weight 95 5 1.000000 ( -0.271600 -1.928900 5.153600 )
	weight 96 5 1.000000 ( -0.331100 -1.256400 4.606600 )
	weight 97 4 1.000000 ( -0.387500 -1.454700 4.083600 )
	weight 98 5 1.000000 ( -0.254000 -1.576600 5.257400 )
	weight 99 5 1.000000 ( -0.404000 -1.510600 4.447300 )
	weight 100 3 1.000000 ( -0.697900 -1.769900 3.485500 )
	weight 101 3 1.000000 ( -0.651500 -1.584500 2.622500 )
	weight 102 3 1.000000 ( -0.820200 -0.765500 3.110700 )
	weight 103 3 1.000000 ( -0.664600 -0.642000 3.718800 )
	weight 104 3 1.000000 ( -0.663900 -1.196800 1.728600 )
	weight 105 18 1.000000 ( -0.444400 -0.736100 1.308100 )
	weight 106 3 1.000000 ( -0.875100 -0.743000 1.844100 )
	weight 107 18 1.000000 ( -0.658200 -0.348200 1.375400 )
	weight 108 3 1.000000 ( -0.701000 -0.221000 2.066400 )
	weight 109 22 1.000000 ( -0.605800 0.041500 1.735800 )
	weight 110 18 1.000000 ( -0.301000 -0.463200 1.179700 )
	weight 111 22 1.000000 ( -0.605800 0.041500 1.735800 )
	weight 112 23 1.000000 ( -0.396300 1.366100 0.984900 )
	weight 113 23 1.000000 ( -1.100100 2.659900 0.613200 )
	weight 114 12 1.000000 ( -1.762800 -1.841000 3.526100 )
	weight 115 12 1.000000 ( -1.725600 -0.040300 3.609900 )
	weight 116 3 1.000000 ( -0.664600 -0.642000 3.718800 )
	weight 117 3 1.000000 ( -0.820200 -0.765500 3.110700 )
	weight 118 13 1.000000 ( -1.769500 1.155400 3.495500 )
	weight 119 12 1.000000 ( -2.879800 -1.042200 2.387500 )
	weight 120 13 1.000000 ( -2.129100 0.281900 1.942100 )
	weight 121 4 1.000000 ( -0.387500 -1.454700 4.083600 )
	weight 122 13 1.000000 ( -1.112400 2.323200 2.420700 )
	weight 123 3 1.000000 ( -0.664600 -0.642000 3.718800 )
}

```
[/size]
## Post #16
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-09-11T13:03:41+00:00
- Post Title: Re: Exporting bones & animation to FBX

Hi
About obj file.

After bone_id there are 5 matrices 4x4. (5 x 64 bytes)
For bone transform use first  as inverted matrix. 
Armature use absolute position for bones, not relative, so don't need multiply  bone with its parent. 

```
offset 4	(3,)
offset 6	(27, 0, 26, 5, 13, 9, 3)
offset 20	(-2.8798000812530518, 0.0, -2.6598999500274658, 2.8798000812530518, 5.4362001419067383, 2.6598999500274658)

bone id=0

offset 44	(0, 0, 0, 0, -1, 0, 0)
offset 72	(65535,)
offset 74	(0.0, -0.0, 1.0, 0.0, -0.0, 1.0, -0.0, 0.0, -1.0, -0.0, 0.0, 0.0, -0.54830002784729004, -1.9815000295639038, 0.0, 1.0) - use as inverted matrix
offset 138	(0.0, 0.0, -1.0, 0.0, 0.0, 1.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, -0.0, 1.9815000295639038, -0.54830002784729004, 1.0)
offset 202	(1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0)
offset 266	(0.0, 0.0, -1.0, 0.0, 0.0, 1.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, -0.0, 1.9815000295639038, -0.54830002784729004, 1.0)
offset 330	(5.5298845836659893e-05, -0.28511077165603638, -0.95849454402923584, 0.0, 1.8247339539811946e-05, 0.95849436521530151, -0.28511145710945129, 0.0, 1.0, -9.6857297648966778e-07, 5.8097844885196537e-05, 0.0, -0.0, 69.0906982421875, -39.635898590087891, 1.0)

bone id=1

offset 394	(0, 0, 0, 0, 0, 1, 0)
offset 422	(65535,)
offset 424	(1.0, -0.0, 0.0, 0.0, -0.0, 1.0, -0.0, 0.0, 0.0, -0.0, 1.0, 0.0, 0.0, -0.023900000378489494, 0.54830002784729004, 1.0) - use as inverted matrix
offset 488	(1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, -0.0, 0.023900000378489494, -0.54830002784729004, 1.0)
offset 552	(1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0)
offset 616	(0.0, 0.0, 1.0, 0.0, 0.0, 1.0, 0.0, 0.0, -1.0, 0.0, 0.0, 0.0, 0.0, -1.9575999975204468, 0.0, 1.0)
offset 680	(1.0, -1.8471942894393578e-05, 2.6907043775281636e-06, 0.0, 1.9977556803496554e-05, 0.99999982118606567, 8.0607776453689439e-08, 0.0, -2.9073123641865095e-06, 7.9493574389744026e-08, 1.0000001192092896, 0.0, -7.0832584242452867e-06, 64.9638671875, -39.63641357421875, 1.0)

bone id=2

offset 744	(0, 0, 0, 0, 0, 2, 0)
offset 772	(65535,)
offset 774	(-0.0, 1.0, 0.0, 0.0, 1.0, 0.0, -0.0, 0.0, 0.0, 0.0, -1.0, 0.0, -1.9815000295639038, -0.0, -0.62940001487731934, 1.0) - use as inverted matrix
offset 838	(-0.0, 1.0, -0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 0.0, -1.0, 0.0, -0.0, 1.9815000295639038, -0.62940001487731934, 1.0)
offset 902	(1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0)
offset 966	(0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.081099987030029297, 0.0, 0.0, 1.0)
offset 1030	(-2.2470583644462749e-05, 0.95854431390762329, -0.28494349122047424, 0.0, 1.0, 8.7463713498436846e-06, 9.7682801424525678e-05, 0.0, 5.3326890338212252e-05, -0.28498372435569763, -0.95853233337402344, 0.0, 4.490266292123124e-06, 69.067550659179688, -39.713729858398437, 1.0)
offset 1094	(0, 0, 0, 0, 2, 3, 0)

offset 1122	(65535,)
....

```


About ani file.
Armature use absolute position for bones. 
It is important . You must multiply each bone frame transform (matrix 4x3) with bone position from armature from obj file.
[pet.zip](https://xentaxbackup.github.io/file/11694_pet.zip)
## Post #17
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-11T13:34:22+00:00
- Post Title: Re: Exporting bones & animation to FBX

> Reply from Szkaradek123
>
> Hi
About obj file.

After bone_id there are 5 matrices 4x4. (5 x 64 bytes)
For bone transform use first  as inverted matrix. 
Armature use absolute position for bones, not relative, so don't need multiply  bone with its parent. 

About ani file.
Armature use absolute position for bones. 
It is important . You must multiply each bone frame transform (matrix 4x3) with bone position from armature from obj file.
Thank you for the information, I didn't understand much of what you said, yet, but I'll certainly look into it. I'm currently trying to export it to md5mesh+md5anim using a python script I wrote. Hopefully with your information I can finally understand the structure and write exporter in any format i'd like. I really really thank you.

btw; wow. saw the blender file, well done.

> Reply from shakotay2
>
> 
(13, 24) this disturbs my thoughts
(9, 25)  this, too
I finally understood what you meant by this. Funny 

------
Few questions:

What is an inverse matrix and how do I use it if I'm writing a exporter to md5mesh? Is the answer here relevant? (I'm guessing I need to compute the position and orientation used by md5mesh joints from the inverse matrix?)
If the 4x4 matrix after the bone_id is the inverse matrix, what are the 4 remaining 4x4 matrices? What are they for?

------
Changed a few things on the joint data and got this. Close, but still can't get the bone right. What am I missing?


```
	"bone_0"	-1 ( -0.000000 -0.548300 1.981500 ) ( 0.000000 0.000000 0.000000 )
	"bone_1"	0 ( -0.000000 -0.548300 0.023900 ) ( 0.000000 0.000000 0.000000 )
	"bone_2"	0 ( -0.000000 -0.629400 1.981500 ) ( 0.000000 0.000000 0.000000 )
	"bone_3"	2 ( -0.000000 -0.626800 2.582000 ) ( 0.000000 0.000000 0.000000 )
	"bone_4"	3 ( -0.000000 -1.452000 3.582500 ) ( 0.000000 0.000000 0.000000 )
	"bone_5"	4 ( -0.000000 -1.591700 4.459700 ) ( 0.000000 0.000000 0.000000 )
	"bone_6"	4 ( 0.182500 -1.030700 3.591700 ) ( 0.000000 0.000000 0.000000 )
	"bone_7"	6 ( 0.853200 -0.966900 3.514400 ) ( 0.000000 0.000000 0.000000 )
	"bone_8"	7 ( 1.824000 -1.409200 3.485900 ) ( 0.000000 0.000000 0.000000 )
	"bone_9"	8 ( 2.350400 -0.850900 2.921900 ) ( 0.000000 0.000000 0.000000 )
	"bone_10"	4 ( -0.182600 -1.030700 3.591700 ) ( 0.000000 0.000000 0.000000 )
	"bone_11"	10 ( -0.853300 -0.967000 3.514400 ) ( 0.000000 0.000000 0.000000 )
	"bone_12"	11 ( -1.824100 -1.409200 3.485900 ) ( 0.000000 0.000000 0.000000 )
	"bone_13"	12 ( -2.350500 -0.850900 2.921900 ) ( 0.000000 0.000000 0.000000 )
	"bone_14"	3 ( 0.521600 -0.629400 1.981500 ) ( 0.000000 0.000000 0.000000 )
	"bone_15"	14 ( 0.453400 -0.349600 0.919700 ) ( 0.000000 0.000000 0.000000 )
	"bone_16"	15 ( 0.558700 -0.475900 0.427000 ) ( 0.000000 0.000000 0.000000 )
	"bone_17"	16 ( 0.659600 -1.113400 0.023900 ) ( 0.000000 0.000000 0.000000 )
	"bone_18"	3 ( -0.521700 -0.629400 1.981500 ) ( 0.000000 0.000000 0.000000 )
	"bone_19"	18 ( -0.453400 -0.349600 0.919700 ) ( 0.000000 0.000000 0.000000 )
	"bone_20"	19 ( -0.558700 -0.475900 0.427000 ) ( 0.000000 0.000000 0.000000 )
	"bone_21"	20 ( -0.640800 -0.994200 0.023900 ) ( 0.000000 0.000000 0.000000 )
	"bone_22"	3 ( -0.000000 -0.000500 2.098800 ) ( 0.000000 0.000000 0.000000 )
	"bone_23"	22 ( -0.000000 1.491700 1.127800 ) ( 0.000000 0.000000 0.000000 )
	"bone_24"	13 ( -1.425700 2.275500 2.487900 ) ( 0.000000 0.000000 0.000000 )
	"bone_25"	9 ( 1.425600 2.275500 2.487900 ) ( 0.000000 0.000000 0.000000 )
}
```
[/size]
## Post #18
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-09-11T15:06:35+00:00
- Post Title: Re: Exporting bones & animation to FBX

It needs to convert matrix rotation part to quaternion

quaternion = qx,qy,qz,qw 

Rotation values for md5mesh are qx,qy,qz

Here is a code from exporter for Blender. [http://www.katsbits.com/tools/#md5](http://www.katsbits.com/tools/#md5)

```
  def to_md5mesh(self):
    buf= "\t\"%s\"\t" % (self.name)
    parentindex = -1
    if self.parent:
        parentindex=self.parent.id
    buf=buf+"%i " % (parentindex)
    
    pos1, pos2, pos3= self.matrix[3][0], self.matrix[3][1], self.matrix[3][2]
    buf=buf+"( %f %f %f ) " % (pos1*scale, pos2*scale, pos3*scale)
    #qx, qy, qz, qw = matrix2quaternion(self.matrix)
    #if qw<0:
    #    qx = -qx
    #    qy = -qy
    #    qz = -qz
    m = self.matrix
    bquat = self.matrix.toQuat()
    bquat.normalize()
    qx = bquat.x
    qy = bquat.y
    qz = bquat.z
    if bquat.w > 0:
        qx = -qx
        qy = -qy
        qz = -qz
    buf=buf+"( %f %f %f )\t\t// " % (qx, qy, qz)
    if self.parent:
        buf=buf+"%s" % (self.parent.name)    
    
    buf=buf+"\n"
    return buf
```


Here is my version of bones md5mesh

```
joints {
	"26"	-1 ( 0.000000 0.000000 0.000000 ) ( -0.000000 -0.000000 -0.000000 )		// 
	"0"	-1 ( 0.000000 1.981500 -0.548300 ) ( -0.000000 -0.707107 -0.000000 )		// 
	"1"	1 ( 0.000000 0.023900 -0.548300 ) ( -0.000000 -0.000000 -0.000000 )		// 0
	"2"	1 ( -0.000000 1.981500 -0.629400 ) ( 0.707107 0.707107 0.000000 )		// 0
	"3"	3 ( -0.000000 2.582000 -0.626800 ) ( -0.665415 -0.665415 0.239214 )		// 2
	"4"	4 ( -0.000000 3.582500 -1.452000 ) ( -0.704906 -0.704906 0.055750 )		// 3
	"5"	5 ( -0.000000 4.459700 -1.591700 ) ( -0.705163 -0.705163 0.052400 )		// 4
	"6"	5 ( 0.182500 3.591700 -1.030700 ) ( 0.337005 0.025043 0.069747 )		// 4
	"7"	7 ( 0.853200 3.514400 -0.966900 ) ( 0.926233 -0.080525 -0.196622 )		// 6
	"8"	8 ( 1.824000 3.485900 -1.409200 ) ( 0.858083 -0.251678 0.400326 )		// 7
	"9"	9 ( 2.350400 2.921901 -0.850900 ) ( 0.577359 0.107529 0.793106 )		// 8
	"25"	10 ( 1.425600 2.487901 2.275500 ) ( 0.577292 0.107869 0.793065 )		// 9
	"10"	5 ( -0.182600 3.591700 -1.030700 ) ( 0.025043 0.337005 0.938582 )		// 4
	"11"	12 ( -0.853300 3.514400 -0.967000 ) ( 0.080525 -0.926233 -0.311363 )		// 10
	"12"	13 ( -1.824100 3.485900 -1.409200 ) ( -0.251678 0.858084 0.200224 )		// 11
	"13"	14 ( -2.350501 2.921900 -0.850900 ) ( 0.107529 0.577360 0.161480 )		// 12
	"24"	15 ( -1.425701 2.487900 2.275499 ) ( 0.107868 0.577294 0.161697 )		// 13
	"14"	4 ( 0.521600 1.981500 -0.629400 ) ( -0.079983 0.266685 0.678161 )		// 3
	"15"	17 ( 0.453400 0.919700 -0.349600 ) ( -0.267927 0.064124 0.628104 )		// 14
	"16"	18 ( 0.558700 0.427000 -0.475900 ) ( 0.704928 -0.704928 0.055466 )		// 15
	"17"	19 ( 0.659601 0.023900 -1.113400 ) ( 0.537680 -0.459238 -0.459239 )		// 16
	"18"	4 ( -0.521700 1.981500 -0.629400 ) ( 0.266685 -0.079983 0.680132 )		// 3
	"19"	21 ( -0.453400 0.919700 -0.349600 ) ( 0.064124 -0.267926 0.727728 )		// 18
	"20"	22 ( -0.558699 0.427000 -0.475900 ) ( -0.704928 0.704928 0.055466 )		// 19
	"21"	23 ( -0.640799 0.023900 -0.994201 ) ( 0.459239 -0.537680 -0.537680 )		// 20
	"22"	4 ( -0.000000 2.098800 -0.000500 ) ( 0.337305 0.337305 0.621470 )		// 3
	"23"	25 ( 0.000001 1.127800 1.491700 ) ( 0.350431 0.350431 0.614165 )		// 22
}

```
## Post #19
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-11T15:22:54+00:00
- Post Title: Re: Exporting bones & animation to FBX

Thanks, I'll try to figure it out. I'll use the export script as reference.

btw; Why do you have 27 bones, where did you get the 27th? Why do I only see a pattern for 26 bones?

edit; If I may ask? How did you export to .blend file? Did you script it inside blender?
## Post #20
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-11T15:42:00+00:00
- Post Title: Re: Exporting bones & animation to FBX

I tried converting the matrix into a quaternion:

```
			bdata = struct.unpack("<ffffiiihffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffff", binary_file.read(350))
			parent_id = bdata[4]
			bone_id   = bdata[5]
			
			m1 = [bdata[24], bdata[25], bdata[26], bdata[27]]
			m2 = [bdata[28], bdata[29], bdata[30], bdata[31]]
			m3 = [bdata[32], bdata[33], bdata[34], bdata[35]]
			m4 = [bdata[36], bdata[37], bdata[38], bdata[39]]
			matrix = Matrix44([m1,m2,m3,m4])
			quat = matrix.quaternion
			matrix.quaternion.normalise()
			
			if quat[3] > 0:
				quat[0] = -quat[0]
				quat[1] = -quat[1]
				quat[2] = -quat[2]

			s_bones = s_bones + "\t\"bone_%d\"\t%d ( %f %f %f ) ( %f %f %f )\n" % (bone_id, parent_id, bdata[36]*1.0, bdata[38]*1.0, bdata[37]*1.0, quat[0], quat[2], quat[1])
```

The result:



```
commandline "Exported by majidemo w/ shakotay2"

numJoints 26
numMeshes 1

joints {
	"bone_0"	-1 ( -0.000000 -0.548300 1.981500 ) ( -0.000000 -0.000000 -0.707107 )
	"bone_1"	0 ( -0.000000 -0.548300 0.023900 ) ( -0.000000 -0.000000 -0.000000 )
	"bone_2"	0 ( -0.000000 -0.629400 1.981500 ) ( 0.707107 0.000000 0.707107 )
	"bone_3"	2 ( -0.000000 -0.626800 2.582000 ) ( -0.665415 -0.239214 -0.665415 )
	"bone_4"	3 ( -0.000000 -1.452000 3.582500 ) ( -0.704906 -0.055750 -0.704906 )
	"bone_5"	4 ( -0.000000 -1.591700 4.459700 ) ( -0.705163 -0.052400 -0.705163 )
	"bone_6"	4 ( 0.182500 -1.030700 3.591700 ) ( -0.337002 -0.069761 -0.025048 )
	"bone_7"	6 ( 0.853200 -0.966900 3.514400 ) ( -0.926236 -0.196608 -0.080585 )
	"bone_8"	7 ( 1.824000 -1.409200 3.485900 ) ( -0.858089 -0.400315 -0.251668 )
	"bone_9"	8 ( 2.350400 -0.850900 2.921900 ) ( -0.577349 -0.793114 -0.107584 )
	"bone_10"	4 ( -0.182600 -1.030700 3.591700 ) ( -0.025048 -0.938582 -0.337002 )
	"bone_11"	10 ( -0.853300 -0.967000 3.514400 ) ( -0.080585 -0.311348 -0.926236 )
	"bone_12"	11 ( -1.824100 -1.409200 3.485900 ) ( -0.251668 -0.200238 -0.858089 )
	"bone_13"	12 ( -2.350500 -0.850900 2.921900 ) ( -0.107584 -0.161444 -0.577349 )
	"bone_14"	3 ( 0.521600 -0.629400 1.981500 ) ( -0.080110 -0.678146 -0.266682 )
	"bone_15"	14 ( 0.453400 -0.349600 0.919700 ) ( -0.267946 -0.628096 -0.064045 )
	"bone_16"	15 ( 0.558700 -0.475900 0.427000 ) ( -0.704928 -0.055466 -0.704928 )
	"bone_17"	16 ( 0.659600 -1.113400 0.023900 ) ( -0.537680 -0.459239 -0.459239 )
	"bone_18"	3 ( -0.521700 -0.629400 1.981500 ) ( -0.266682 -0.680133 -0.080110 )
	"bone_19"	18 ( -0.453400 -0.349600 0.919700 ) ( -0.064045 -0.727735 -0.267946 )
	"bone_20"	19 ( -0.558700 -0.475900 0.427000 ) ( -0.704928 -0.055466 -0.704928 )
	"bone_21"	20 ( -0.640800 -0.994200 0.023900 ) ( -0.459239 -0.537680 -0.537680 )
	"bone_22"	3 ( -0.000000 -0.000500 2.098800 ) ( -0.337305 -0.621470 -0.337305 )
	"bone_23"	22 ( -0.000000 1.491700 1.127800 ) ( -0.350431 -0.614165 -0.350431 )
	"bone_24"	13 ( -1.425700 2.275500 2.487900 ) ( -0.107910 -0.161669 -0.577286 )
	"bone_25"	9 ( 1.425600 2.275500 2.487900 ) ( -0.577286 -0.793069 -0.107910 )
}

mesh {
	shader "pet_t16/0.png"

	numverts 124
	vert 0 ( 0.801100 0.143500 ) 0 1
	vert 1 ( 0.773900 0.028200 ) 1 1
	vert 2 ( 0.824200 0.129000 ) 2 1
	vert 3 ( 0.742800 0.260800 ) 3 1
	vert 4 ( 0.974800 0.218300 ) 4 1
	vert 5 ( 0.838800 0.174600 ) 5 1
	vert 6 ( 0.851100 0.133600 ) 6 1
	vert 7 ( 0.218200 0.205800 ) 7 1
	vert 8 ( 0.289800 0.018600 ) 8 1
	vert 9 ( 0.291300 0.167500 ) 9 1
	vert 10 ( 0.212900 0.044100 ) 10 1
	vert 11 ( 0.161200 0.092800 ) 11 1
	vert 12 ( 0.154400 0.177700 ) 12 1
	vert 13 ( 0.257200 0.211700 ) 13 1
	vert 14 ( 0.217000 0.228700 ) 14 1
	vert 15 ( 0.182000 0.213300 ) 15 1
	vert 16 ( 0.234700 0.361400 ) 16 1
	vert 17 ( 0.492500 0.134600 ) 17 1
	vert 18 ( 0.473500 0.150500 ) 18 1
	vert 19 ( 0.415200 0.119300 ) 19 1
	vert 20 ( 0.447400 0.080400 ) 20 1
	vert 21 ( 0.506200 0.184500 ) 21 1
	vert 22 ( 0.560100 0.187300 ) 22 1
	vert 23 ( 0.499600 0.239600 ) 23 1
	vert 24 ( 0.558400 0.083700 ) 24 1
	vert 25 ( 0.605800 0.143000 ) 25 1
	vert 26 ( 0.671200 0.097300 ) 26 1
	vert 27 ( 0.655700 0.232700 ) 27 1
	vert 28 ( 0.742700 0.391000 ) 28 1
	vert 29 ( 0.616000 0.318100 ) 29 1
	vert 30 ( 0.625300 0.080200 ) 30 1
	vert 31 ( 0.621800 0.049900 ) 31 1
	vert 32 ( 0.614300 0.243300 ) 32 1
	vert 33 ( 0.445100 0.397400 ) 33 1
	vert 34 ( 0.517000 0.038700 ) 34 1
	vert 35 ( 0.517100 0.416700 ) 35 1
	vert 36 ( 0.534100 0.597300 ) 36 1
	vert 37 ( 0.755000 0.550500 ) 37 1
	vert 38 ( 0.915800 0.616200 ) 38 1
	vert 39 ( 0.437100 0.612900 ) 39 1
	vert 40 ( 0.624800 0.790400 ) 40 1
	vert 41 ( 0.728600 0.870600 ) 41 1
	vert 42 ( 0.674400 0.981900 ) 42 1
	vert 43 ( 0.741800 0.741200 ) 43 1
	vert 44 ( 0.812500 0.857700 ) 44 1
	vert 45 ( 0.858300 0.755400 ) 45 1
	vert 46 ( 0.912700 0.557000 ) 46 1
	vert 47 ( 0.964800 0.759100 ) 47 1
	vert 48 ( 0.933900 0.964600 ) 48 1
	vert 49 ( 0.886100 0.837300 ) 49 1
	vert 50 ( 0.792000 0.912200 ) 50 1
	vert 51 ( 0.433800 0.133400 ) 51 1
	vert 52 ( 0.349300 0.129000 ) 52 1
	vert 53 ( 0.392900 0.106100 ) 53 1
	vert 54 ( 0.699100 0.215300 ) 54 1
	vert 55 ( 0.544100 0.782000 ) 55 1
	vert 56 ( 0.530200 0.978100 ) 56 1
	vert 57 ( 0.270000 0.988500 ) 57 1
	vert 58 ( 0.517700 0.816500 ) 58 1
	vert 59 ( 0.287600 0.911300 ) 59 1
	vert 60 ( 0.471900 0.733800 ) 60 1
	vert 61 ( 0.316600 0.742200 ) 61 1
	vert 62 ( 0.081600 0.802400 ) 62 1
	vert 63 ( 0.079300 0.889400 ) 63 1
	vert 64 ( 0.305000 0.589600 ) 64 1
	vert 65 ( 0.237100 0.906100 ) 65 1
	vert 66 ( 0.289100 0.428800 ) 66 1
	vert 67 ( 0.061600 0.421200 ) 67 1
	vert 68 ( 0.077100 0.606600 ) 68 1
	vert 69 ( 0.237100 0.908900 ) 69 1
	vert 70 ( 0.055600 0.968700 ) 70 1
	vert 71 ( 0.059100 0.285000 ) 71 1
	vert 72 ( 0.755000 0.550500 ) 72 1
	vert 73 ( 0.912700 0.557000 ) 73 1
	vert 74 ( 0.801100 0.143500 ) 74 1
	vert 75 ( 0.824200 0.129000 ) 75 1
	vert 76 ( 0.773900 0.028200 ) 76 1
	vert 77 ( 0.742800 0.260800 ) 77 1
	vert 78 ( 0.838800 0.174600 ) 78 1
	vert 79 ( 0.974800 0.218300 ) 79 1
	vert 80 ( 0.851100 0.133600 ) 80 1
	vert 81 ( 0.218200 0.205800 ) 81 1
	vert 82 ( 0.291300 0.167500 ) 82 1
	vert 83 ( 0.289800 0.018600 ) 83 1
	vert 84 ( 0.212900 0.044100 ) 84 1
	vert 85 ( 0.161200 0.092800 ) 85 1
	vert 86 ( 0.154400 0.177700 ) 86 1
	vert 87 ( 0.257200 0.211700 ) 87 1
	vert 88 ( 0.217000 0.228700 ) 88 1
	vert 89 ( 0.182000 0.213300 ) 89 1
	vert 90 ( 0.234700 0.361400 ) 90 1
	vert 91 ( 0.492500 0.134600 ) 91 1
	vert 92 ( 0.415200 0.119300 ) 92 1
	vert 93 ( 0.560100 0.187300 ) 93 1
	vert 94 ( 0.605800 0.143000 ) 94 1
	vert 95 ( 0.558400 0.083700 ) 95 1
	vert 96 ( 0.655700 0.232700 ) 96 1
	vert 97 ( 0.616000 0.318100 ) 97 1
	vert 98 ( 0.625300 0.080200 ) 98 1
	vert 99 ( 0.614300 0.243300 ) 99 1
	vert 100 ( 0.517100 0.416700 ) 100 1
	vert 101 ( 0.534100 0.597300 ) 101 1
	vert 102 ( 0.755000 0.550500 ) 102 1
	vert 103 ( 0.915800 0.616200 ) 103 1
	vert 104 ( 0.624800 0.790400 ) 104 1
	vert 105 ( 0.728600 0.870600 ) 105 1
	vert 106 ( 0.741800 0.741200 ) 106 1
	vert 107 ( 0.812500 0.857700 ) 107 1
	vert 108 ( 0.858300 0.755400 ) 108 1
	vert 109 ( 0.886100 0.837300 ) 109 1
	vert 110 ( 0.792000 0.912200 ) 110 1
	vert 111 ( 0.530200 0.978100 ) 111 1
	vert 112 ( 0.517700 0.816500 ) 112 1
	vert 113 ( 0.471900 0.733800 ) 113 1
	vert 114 ( 0.081600 0.802400 ) 114 1
	vert 115 ( 0.305000 0.589600 ) 115 1
	vert 116 ( 0.079300 0.889400 ) 116 1
	vert 117 ( 0.237100 0.906100 ) 117 1
	vert 118 ( 0.289100 0.428800 ) 118 1
	vert 119 ( 0.077100 0.606600 ) 119 1
	vert 120 ( 0.061600 0.421200 ) 120 1
	vert 121 ( 0.237100 0.908900 ) 121 1
	vert 122 ( 0.059100 0.285000 ) 122 1
	vert 123 ( 0.755000 0.550500 ) 123 1

	numtris 202
	tri 0 0 1 2
	tri 1 2 3 0
	tri 2 2 4 5
	tri 3 5 3 2
	tri 4 2 1 6
	tri 5 6 4 2
	tri 6 6 1 0
	tri 7 0 5 6
	tri 8 5 4 6
	tri 9 0 3 5
	tri 10 7 8 9
	tri 11 8 7 10
	tri 12 11 10 7
	tri 13 7 12 11
	tri 14 8 11 12
	tri 15 12 9 8
	tri 16 7 9 13
	tri 17 13 14 7
	tri 18 15 7 14
	tri 19 7 15 12
	tri 20 13 12 15
	tri 21 12 13 9
	tri 22 13 16 14
	tri 23 14 16 15
	tri 24 15 16 13
	tri 25 17 18 19
	tri 26 17 19 20
	tri 27 21 22 23
	tri 28 17 24 25
	tri 29 25 26 27
	tri 30 28 29 27
	tri 31 30 31 26
	tri 32 24 17 20
	tri 33 29 23 32
	tri 34 23 29 33
	tri 35 30 34 31
	tri 36 22 18 17
	tri 37 35 33 29
	tri 38 36 35 37
	tri 39 33 35 36
	tri 40 37 35 38
	tri 41 36 39 33
	tri 42 40 39 36
	tri 43 35 29 38
	tri 44 40 41 42
	tri 45 43 44 41
	tri 46 45 43 37
	tri 47 46 47 37
	tri 48 47 48 49
	tri 49 45 44 43
	tri 50 41 50 42
	tri 51 48 42 50
	tri 52 50 49 48
	tri 53 19 18 51
	tri 54 51 52 19
	tri 55 20 19 53
	tri 56 52 53 19
	tri 57 49 44 45
	tri 58 49 50 44
	tri 59 27 54 28
	tri 60 26 54 27
	tri 61 27 29 32
	tri 62 55 40 42
	tri 63 43 36 37
	tri 64 27 32 25
	tri 65 32 23 22
	tri 66 24 34 30
	tri 67 20 34 24
	tri 68 25 24 30
	tri 69 25 30 26
	tri 70 32 22 25
	tri 71 25 22 17
	tri 72 43 41 40
	tri 73 43 40 36
	tri 74 39 40 55
	tri 75 47 49 45
	tri 76 47 45 37
	tri 77 18 22 21
	tri 78 56 57 58
	tri 79 59 58 57
	tri 80 60 59 61
	tri 81 59 60 58
	tri 82 58 57 56
	tri 83 57 58 59
	tri 84 61 59 60
	tri 85 58 60 59
	tri 86 62 63 64
	tri 87 64 63 65
	tri 88 66 67 68
	tri 89 68 62 64
	tri 90 69 70 63
	tri 91 64 63 62
	tri 92 63 64 65
	tri 93 62 68 64
	tri 94 68 67 66
	tri 95 68 66 64
	tri 96 64 66 68
	tri 97 66 71 67
	tri 98 67 71 66
	tri 99 46 37 72
	tri 100 72 73 46
	tri 101 74 75 76
	tri 102 75 74 77
	tri 103 75 78 79
	tri 104 78 75 77
	tri 105 75 80 76
	tri 106 80 75 79
	tri 107 80 74 76
	tri 108 74 80 78
	tri 109 78 80 79
	tri 110 74 78 77
	tri 111 81 82 83
	tri 112 83 84 81
	tri 113 85 81 84
	tri 114 81 85 86
	tri 115 83 86 85
	tri 116 86 83 82
	tri 117 81 87 82
	tri 118 87 81 88
	tri 119 89 88 81
	tri 120 81 86 89
	tri 121 87 89 86
	tri 122 86 82 87
	tri 123 87 88 90
	tri 124 88 89 90
	tri 125 89 87 90
	tri 126 91 92 18
	tri 127 91 20 92
	tri 128 21 23 93
	tri 129 91 94 95
	tri 130 94 96 26
	tri 131 28 96 97
	tri 132 98 26 31
	tri 133 95 20 91
	tri 134 97 99 23
	tri 135 23 33 97
	tri 136 98 31 34
	tri 137 93 91 18
	tri 138 100 97 33
	tri 139 101 102 100
	tri 140 33 101 100
	tri 141 102 103 100
	tri 142 101 33 39
	tri 143 104 101 39
	tri 144 100 103 97
	tri 145 104 42 105
	tri 146 106 105 107
	tri 147 108 102 106
	tri 148 46 102 47
	tri 149 47 109 48
	tri 150 108 106 107
	tri 151 105 42 110
	tri 152 48 110 42
	tri 153 110 48 109
	tri 154 92 51 18
	tri 155 51 92 52
	tri 156 20 53 92
	tri 157 52 92 53
	tri 158 109 108 107
	tri 159 109 107 110
	tri 160 96 28 54
	tri 161 26 96 54
	tri 162 96 99 97
	tri 163 55 42 104
	tri 164 106 102 101
	tri 165 96 94 99
	tri 166 99 93 23
	tri 167 95 98 34
	tri 168 20 95 34
	tri 169 94 98 95
	tri 170 94 26 98
	tri 171 99 94 93
	tri 172 94 91 93
	tri 173 106 104 105
	tri 174 106 101 104
	tri 175 39 55 104
	tri 176 47 108 109
	tri 177 47 102 108
	tri 178 18 21 93
	tri 179 111 112 57
	tri 180 59 57 112
	tri 181 113 61 59
	tri 182 59 112 113
	tri 183 112 111 57
	tri 184 57 59 112
	tri 185 61 113 59
	tri 186 112 59 113
	tri 187 114 115 116
	tri 188 115 117 116
	tri 189 118 119 120
	tri 190 119 115 114
	tri 191 121 116 70
	tri 192 115 114 116
	tri 193 116 117 115
	tri 194 114 115 119
	tri 195 119 118 120
	tri 196 119 115 118
	tri 197 115 119 118
	tri 198 118 120 122
	tri 199 120 118 122
	tri 200 46 123 102
	tri 201 123 46 73

	numweights 124
	weight 0 16 1.000000 ( 0.418200 -0.533300 0.203600 )
	weight 1 16 1.000000 ( 0.320100 0.178100 0.022100 )
	weight 2 16 1.000000 ( 0.504900 -0.445200 0.470500 )
	weight 3 16 1.000000 ( 0.196300 -1.252000 0.012300 )
	weight 4 16 1.000000 ( 1.065200 -1.003100 0.023800 )
	weight 5 16 1.000000 ( 0.558100 -0.726700 0.160800 )
	weight 6 16 1.000000 ( 0.605500 -0.475200 0.206600 )
	weight 7 14 1.000000 ( 0.459100 -0.491800 0.881300 )
	weight 8 14 1.000000 ( 0.658200 -0.348200 1.375400 )
	weight 9 14 1.000000 ( 0.662300 -0.140000 0.982400 )
	weight 10 14 1.000000 ( 0.444400 -0.736100 1.308100 )
	weight 11 14 1.000000 ( 0.301000 -0.463200 1.179700 )
	weight 12 14 1.000000 ( 0.282200 -0.245600 0.955500 )
	weight 13 15 1.000000 ( 0.567500 -0.237400 0.865700 )
	weight 14 15 1.000000 ( 0.455900 -0.375800 0.820700 )
	weight 15 15 1.000000 ( 0.358600 -0.295400 0.861500 )
	weight 16 16 1.000000 ( 0.504900 -0.445200 0.470500 )
	weight 17 5 1.000000 ( 0.141400 -2.049300 4.866500 )
	weight 18 5 1.000000 ( 0.000000 -2.114500 4.735300 )
	weight 19 5 1.000000 ( 0.063700 -2.424000 4.795700 )
	weight 20 5 1.000000 ( 0.000000 -2.261200 5.047400 )
	weight 21 5 1.000000 ( 0.000000 -1.966100 4.607700 )
	weight 22 5 1.000000 ( 0.129900 -1.865000 4.632800 )
	weight 23 5 1.000000 ( 0.000000 -1.904700 4.385000 )
	weight 24 5 1.000000 ( 0.271600 -1.928900 5.153600 )
	weight 25 5 1.000000 ( 0.431000 -1.609900 4.927500 )
	weight 26 5 1.000000 ( 0.000000 -1.292900 5.267900 )
	weight 27 5 1.000000 ( 0.331100 -1.256400 4.606600 )
	weight 28 4 1.000000 ( 0.000000 -0.878500 3.963500 )
	weight 29 4 1.000000 ( 0.387500 -1.454700 4.083600 )
	weight 30 5 1.000000 ( 0.254000 -1.576600 5.257400 )
	weight 31 5 1.000000 ( 0.000000 -1.606400 5.436200 )
	weight 32 5 1.000000 ( 0.404000 -1.510600 4.447300 )
	weight 33 3 1.000000 ( 0.000000 -2.052200 3.536700 )
	weight 34 5 1.000000 ( 0.000000 -2.021200 5.333100 )
	weight 35 3 1.000000 ( 0.697900 -1.769900 3.485500 )
	weight 36 3 1.000000 ( 0.651500 -1.584500 2.622500 )
	weight 37 3 1.000000 ( 0.820200 -0.765500 3.110700 )
	weight 38 3 1.000000 ( 0.664600 -0.642000 3.718800 )
	weight 39 3 1.000000 ( 0.000000 -1.903400 2.446100 )
	weight 40 3 1.000000 ( 0.663900 -1.196800 1.728700 )
	weight 41 14 1.000000 ( 0.444400 -0.736100 1.308100 )
	weight 42 2 1.000000 ( 0.000000 -0.903200 1.316500 )
	weight 43 3 1.000000 ( 0.875100 -0.743000 1.844100 )
	weight 44 14 1.000000 ( 0.658200 -0.348200 1.375400 )
	weight 45 3 1.000000 ( 0.701000 -0.221000 2.066400 )
	weight 46 3 1.000000 ( -0.000000 -0.154200 3.263800 )
	weight 47 22 1.000000 ( -0.000000 0.180600 2.336300 )
	weight 48 22 1.000000 ( -0.000000 -0.029700 1.685300 )
	weight 49 22 1.000000 ( 0.605800 0.041500 1.735800 )
	weight 50 14 1.000000 ( 0.301000 -0.463200 1.179700 )
	weight 51 5 1.000000 ( 0.000000 -2.410900 4.723500 )
	weight 52 5 1.000000 ( 0.000000 -2.659900 4.687000 )
	weight 53 5 1.000000 ( 0.000000 -2.472600 4.895200 )
	weight 54 5 1.000000 ( 0.000000 -1.154700 4.748200 )
	weight 55 3 1.000000 ( 0.000000 -1.423300 1.731300 )
	weight 56 22 1.000000 ( 0.605800 0.041500 1.735800 )
	weight 57 22 1.000000 ( -0.000000 0.180600 2.336300 )
	weight 58 23 1.000000 ( 0.396300 1.366100 0.984900 )
	weight 59 23 1.000000 ( -0.000000 1.569800 1.238200 )
	weight 60 23 1.000000 ( 1.100100 2.659900 0.613200 )
	weight 61 23 1.000000 ( -0.000000 2.417200 0.727700 )
	weight 62 8 1.000000 ( 1.762800 -1.841000 3.526100 )
	weight 63 3 1.000000 ( 0.664600 -0.642000 3.718800 )
	weight 64 8 1.000000 ( 1.725600 -0.040300 3.609900 )
	weight 65 3 1.000000 ( 0.820200 -0.765500 3.110700 )
	weight 66 9 1.000000 ( 1.769500 1.155400 3.495500 )
	weight 67 9 1.000000 ( 2.129100 0.281900 1.942100 )
	weight 68 8 1.000000 ( 2.879800 -1.042200 2.387500 )
	weight 69 4 1.000000 ( 0.387500 -1.454700 4.083600 )
	weight 70 4 1.000000 ( 0.000000 -0.878500 3.963500 )
	weight 71 9 1.000000 ( 1.112400 2.323200 2.420700 )
	weight 72 3 1.000000 ( 0.664600 -0.642000 3.718800 )
	weight 73 4 1.000000 ( 0.000000 -0.878500 3.963500 )
	weight 74 20 1.000000 ( -0.418200 -0.533300 0.203600 )
	weight 75 20 1.000000 ( -0.504900 -0.445200 0.470500 )
	weight 76 20 1.000000 ( -0.320100 0.178100 0.022100 )
	weight 77 20 1.000000 ( -0.196300 -1.252000 0.012300 )
	weight 78 20 1.000000 ( -0.558100 -0.726700 0.160800 )
	weight 79 20 1.000000 ( -1.065200 -1.003100 0.023800 )
	weight 80 20 1.000000 ( -0.605500 -0.475200 0.206600 )
	weight 81 18 1.000000 ( -0.459100 -0.491800 0.881300 )
	weight 82 18 1.000000 ( -0.662300 -0.140000 0.982400 )
	weight 83 18 1.000000 ( -0.658200 -0.348200 1.375400 )
	weight 84 18 1.000000 ( -0.444400 -0.736100 1.308100 )
	weight 85 18 1.000000 ( -0.301000 -0.463200 1.179700 )
	weight 86 18 1.000000 ( -0.282200 -0.245600 0.955500 )
	weight 87 19 1.000000 ( -0.567500 -0.237400 0.865700 )
	weight 88 19 1.000000 ( -0.455900 -0.375800 0.820700 )
	weight 89 19 1.000000 ( -0.358600 -0.295400 0.861500 )
	weight 90 20 1.000000 ( -0.504900 -0.445200 0.470500 )
	weight 91 5 1.000000 ( -0.141400 -2.049300 4.866500 )
	weight 92 5 1.000000 ( -0.063700 -2.424000 4.795700 )
	weight 93 5 1.000000 ( -0.129900 -1.865000 4.632800 )
	weight 94 5 1.000000 ( -0.431000 -1.609900 4.927500 )
	weight 95 5 1.000000 ( -0.271600 -1.928900 5.153600 )
	weight 96 5 1.000000 ( -0.331100 -1.256400 4.606600 )
	weight 97 4 1.000000 ( -0.387500 -1.454700 4.083600 )
	weight 98 5 1.000000 ( -0.254000 -1.576600 5.257400 )
	weight 99 5 1.000000 ( -0.404000 -1.510600 4.447300 )
	weight 100 3 1.000000 ( -0.697900 -1.769900 3.485500 )
	weight 101 3 1.000000 ( -0.651500 -1.584500 2.622500 )
	weight 102 3 1.000000 ( -0.820200 -0.765500 3.110700 )
	weight 103 3 1.000000 ( -0.664600 -0.642000 3.718800 )
	weight 104 3 1.000000 ( -0.663900 -1.196800 1.728600 )
	weight 105 18 1.000000 ( -0.444400 -0.736100 1.308100 )
	weight 106 3 1.000000 ( -0.875100 -0.743000 1.844100 )
	weight 107 18 1.000000 ( -0.658200 -0.348200 1.375400 )
	weight 108 3 1.000000 ( -0.701000 -0.221000 2.066400 )
	weight 109 22 1.000000 ( -0.605800 0.041500 1.735800 )
	weight 110 18 1.000000 ( -0.301000 -0.463200 1.179700 )
	weight 111 22 1.000000 ( -0.605800 0.041500 1.735800 )
	weight 112 23 1.000000 ( -0.396300 1.366100 0.984900 )
	weight 113 23 1.000000 ( -1.100100 2.659900 0.613200 )
	weight 114 12 1.000000 ( -1.762800 -1.841000 3.526100 )
	weight 115 12 1.000000 ( -1.725600 -0.040300 3.609900 )
	weight 116 3 1.000000 ( -0.664600 -0.642000 3.718800 )
	weight 117 3 1.000000 ( -0.820200 -0.765500 3.110700 )
	weight 118 13 1.000000 ( -1.769500 1.155400 3.495500 )
	weight 119 12 1.000000 ( -2.879800 -1.042200 2.387500 )
	weight 120 13 1.000000 ( -2.129100 0.281900 1.942100 )
	weight 121 4 1.000000 ( -0.387500 -1.454700 4.083600 )
	weight 122 13 1.000000 ( -1.112400 2.323200 2.420700 )
	weight 123 3 1.000000 ( -0.664600 -0.642000 3.718800 )
}
```
[/size]
## Post #21
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-09-11T16:25:23+00:00
- Post Title: Re: Exporting bones & animation to FBX

If helps,  here is a blend file for import first mesh and first animation. 

Use for Blender 249 (very old version of this software) and Python 26.
Install Blender and Python, doubleclick Blend249.blend and in Blender Text Window press alt+p.
Select obj file and than ani. 
What tool  are you using for export models to Doom format ?


....btw; Why do you have 27 bones, where did you get the 27th? Why do I only see a pattern for 26 bones?....
-one bone for mesh
[Blender249[pet][obj][ani][2016-09-11].zip](https://xentaxbackup.github.io/file/11696_Blender249[pet][obj][ani][2016-09-11].zip)
## Post #22
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-11T16:41:10+00:00
- Post Title: Re: Exporting bones & animation to FBX

> Reply from Szkaradek123
>
> If helps,  here is a blend file for import first mesh and first animation. 

Use for Blender 249 (very old version of this software) and Python 26.
Install Blender and Python, doubleclick Blend249.blend and in Blender Text Window press alt+p.
Select obj file and than ani. 
What tool  are you using for export models to Doom format ?
Thanks. I'll try this out. 

I didn't use any tool to export, I just wrote a script in python that reads my pet.obj file then writes the .md5mesh file.

If you'd like to see my export script, you can check it [here](http://pastebin.com/YRqj1DRQ).
## Post #23
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-09-11T17:07:46+00:00
- Post Title: Re: Exporting bones & animation to FBX

I think is problem with this section

```
		# add number of vertwieghts
		md5mesh = md5mesh + "\n\tnumweights %d\n" % vert_length	
		md5mesh = md5mesh + s_weyts

```


You must calculating 's_weyts' . It is not pure 3 floats from obj file as vertex position. It is more complex .
Be carefull, this md5mesh format is not easy.
## Post #24
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-12T13:07:46+00:00
- Post Title: Re: Exporting bones & animation to FBX

> Reply from Szkaradek123
>
> I think is problem with this section
Code: Select all		
		# add number of vertwieghts
		md5mesh = md5mesh + "\n\tnumweights %d\n" % vert_length	
		md5mesh = md5mesh + s_weyts


You must calculating 's_weyts' . It is not pure 3 floats from obj file as vertex position. It is more complex .
Be carefull, this md5mesh format is not easy.
I see. Thank you for the information.

I'm currently doing 2 things at the moment:

 Rewriting the blender script you provided so it will work with the latest version of blender.
 And, fixing my export_to_md5mesh python script.

As for the fixing of my python script. I updated it as follows:

```
d_bones.append(bdata)

...(some other code)

bdata = d_bones[segment[4]]
m1 = [bdata[8],  bdata[9], bdata[10], bdata[11]]
m2 = [bdata[12], bdata[13], bdata[14], bdata[15]]
m3 = [bdata[16], bdata[17], bdata[18], bdata[19]]
m4 = [bdata[20], bdata[21], bdata[22], bdata[23]]
inverted_matrix = pyrr.Matrix44([m1,m2,m3,m4])
vector = pyrr.matrix44.apply_to_vector(inverted_matrix, pyrr.Vector3([segment[0], segment[1], segment[2]]))
			
s_weyts = s_weyts + "\tweight %d %d %f ( %f %f %f )\n" % (vi, segment[4], segment[3], vector[0]*1.0, vector[2]*1.0, vector[1]*1.0)

```


Which gave me the result:



I guess, its getting closer. What else could I be missing?


```
	weight 0 16 1.000000 ( 0.223400 0.034720 0.147748 )
	weight 1 16 1.000000 ( 0.404900 -0.683269 0.133379 )
	weight 2 16 1.000000 ( -0.043500 -0.038736 0.048337 )
	weight 3 16 1.000000 ( 0.414700 0.709870 0.479322 )
	weight 4 16 1.000000 ( 0.403200 0.599928 -0.417813 )
	weight 5 16 1.000000 ( 0.266200 0.247620 0.039818 )
	weight 6 16 1.000000 ( 0.220400 0.006628 -0.046334 )
	weight 7 14 1.000000 ( 1.100712 -0.132541 -0.064470 )
	weight 8 14 1.000000 ( 0.647999 0.019938 0.211606 )
	weight 9 14 1.000000 ( 1.079984 0.094530 0.286667 )
	weight 10 14 1.000000 ( 0.627583 -0.224092 -0.163564 )
	weight 11 14 1.000000 ( 0.829797 0.041600 -0.169972 )
	weight 12 14 1.000000 ( 1.102679 0.177619 -0.099245 )
	weight 13 15 1.000000 ( 0.047063 0.062823 0.149536 )
	weight 14 15 1.000000 ( 0.100785 0.007330 -0.016807 )
	weight 15 15 1.000000 ( 0.022801 0.104734 -0.061829 )
	weight 16 16 1.000000 ( -0.043500 -0.038736 0.048337 )
	weight 17 5 1.000000 ( 0.469966 0.392448 0.141400 )
	weight 18 5 1.000000 ( 0.349844 0.476324 0.000000 )
	weight 19 5 1.000000 ( 0.455326 0.773497 0.063700 )
	weight 20 5 1.000000 ( 0.680199 0.575283 0.000000 )
	weight 21 5 1.000000 ( 0.201711 0.348413 0.000000 )
	weight 22 5 1.000000 ( 0.211593 0.244714 0.129900 )
	weight 23 5 1.000000 ( -0.027617 0.320603 0.000000 )
	weight 24 5 1.000000 ( 0.736118 0.230936 0.271600 )
	weight 25 5 1.000000 ( 0.465352 -0.051142 0.431000 )
	weight 26 5 1.000000 ( 0.755160 -0.414972 0.000000 )
	weight 27 5 1.000000 ( 0.095728 -0.353329 0.331100 )
	weight 28 4 1.000000 ( 0.286112 -0.626261 0.000000 )
	weight 29 4 1.000000 ( 0.495295 -0.076104 0.387500 )
	weight 30 5 1.000000 ( 0.786707 -0.132836 0.254000 )
	weight 31 5 1.000000 ( 0.967948 -0.129791 0.000000 )
	weight 32 5 1.000000 ( -0.024251 -0.078377 0.404000 )
	weight 33 3 1.000000 ( 1.643736 0.491273 0.000000 )
	weight 34 5 1.000000 ( 0.927288 0.295692 0.000000 )
	weight 35 3 1.000000 ( 1.424513 0.306189 0.697900 )
	weight 36 3 1.000000 ( 0.641003 0.712702 0.651500 )
	weight 37 3 1.000000 ( 0.495995 -0.229674 0.820200 )
	weight 38 3 1.000000 ( 0.886272 -0.712086 0.664600 )
	weight 39 3 1.000000 ( 0.708025 1.070923 0.000000 )
	weight 40 3 1.000000 ( -0.295063 0.982832 0.663900 )
	weight 41 14 1.000000 ( 0.627583 -0.224092 -0.163564 )
	weight 42 2 1.000000 ( -0.665000 0.273800 0.000000 )
	weight 43 3 1.000000 ( -0.495015 0.559428 0.875100 )
	weight 44 14 1.000000 ( 0.647999 0.019938 0.211606 )
	weight 45 3 1.000000 ( -0.655958 0.015370 0.701000 )
	weight 46 3 1.000000 ( 0.224833 -0.798531 0.000000 )
	weight 47 22 1.000000 ( 0.022439 0.297825 0.000000 )
	weight 48 22 1.000000 ( 0.200832 -0.362631 0.000000 )
	weight 49 22 1.000000 ( 0.233016 -0.281490 0.605800 )
	weight 50 14 1.000000 ( 0.829797 0.041600 -0.169972 )
	weight 51 5 1.000000 ( 0.381982 0.771213 0.000000 )
	weight 52 5 1.000000 ( 0.382686 1.022872 0.000000 )
	weight 53 5 1.000000 ( 0.560916 0.806857 0.000000 )
	weight 54 5 1.000000 ( 0.220741 -0.474841 0.000000 )
	weight 55 3 1.000000 ( -0.148845 1.155832 0.000000 )
	weight 56 22 1.000000 ( 0.233016 -0.281490 0.605800 )
	weight 57 22 1.000000 ( 0.022439 0.297825 0.000000 )
	weight 58 23 1.000000 ( -0.035421 -0.186926 0.396300 )
	weight 59 23 1.000000 ( 0.011065 0.134779 0.000000 )
	weight 60 23 1.000000 ( 1.267515 0.151359 1.100100 )
	weight 61 23 1.000000 ( 1.000321 0.126447 0.000000 )
	weight 62 8 1.000000 ( -0.310778 0.216287 0.220120 )
	weight 63 3 1.000000 ( 0.886272 -0.712086 0.664600 )
	weight 64 8 1.000000 ( 0.674675 -0.880302 -0.817830 )
	weight 65 3 1.000000 ( 0.495995 -0.229674 0.820200 )
	weight 66 9 1.000000 ( 1.994698 0.315410 -0.783239 )
	weight 67 9 1.000000 ( 1.268306 -0.193350 0.803848 )
	weight 68 8 1.000000 ( 1.449299 0.455683 0.384352 )
	weight 69 4 1.000000 ( 0.495295 -0.076104 0.387500 )
	weight 70 4 1.000000 ( 0.286112 -0.626261 0.000000 )
	weight 71 9 1.000000 ( 3.431340 -0.284969 -0.057863 )
	weight 72 3 1.000000 ( 0.886272 -0.712086 0.664600 )
	weight 73 4 1.000000 ( 0.286112 -0.626261 0.000000 )
	weight 74 20 1.000000 ( 0.223400 0.034720 -0.147748 )
	weight 75 20 1.000000 ( -0.043500 -0.038736 -0.048337 )
	weight 76 20 1.000000 ( 0.404900 -0.683269 -0.133379 )
	weight 77 20 1.000000 ( 0.414700 0.709870 -0.479322 )
	weight 78 20 1.000000 ( 0.266200 0.247620 -0.039818 )
	weight 79 20 1.000000 ( 0.403200 0.599928 0.417813 )
	weight 80 20 1.000000 ( 0.220400 0.006628 0.046334 )
	weight 81 18 1.000000 ( 1.100718 -0.132494 0.064558 )
	weight 82 18 1.000000 ( 1.079991 0.094577 -0.286579 )
	weight 83 18 1.000000 ( 0.648005 0.019985 -0.211518 )
	weight 84 18 1.000000 ( 0.627589 -0.224045 0.163652 )
	weight 85 18 1.000000 ( 0.829803 0.041647 0.170060 )
	weight 86 18 1.000000 ( 1.102685 0.177666 0.099333 )
	weight 87 19 1.000000 ( 0.047063 0.062823 -0.149536 )
	weight 88 19 1.000000 ( 0.100785 0.007330 0.016807 )
	weight 89 19 1.000000 ( 0.022801 0.104734 0.061829 )
	weight 90 20 1.000000 ( -0.043500 -0.038736 -0.048337 )
	weight 91 5 1.000000 ( 0.469966 0.392448 -0.141400 )
	weight 92 5 1.000000 ( 0.455326 0.773497 -0.063700 )
	weight 93 5 1.000000 ( 0.211593 0.244714 -0.129900 )
	weight 94 5 1.000000 ( 0.465352 -0.051142 -0.431000 )
	weight 95 5 1.000000 ( 0.736118 0.230936 -0.271600 )
	weight 96 5 1.000000 ( 0.095728 -0.353329 -0.331100 )
	weight 97 4 1.000000 ( 0.495295 -0.076104 -0.387500 )
	weight 98 5 1.000000 ( 0.786707 -0.132836 -0.254000 )
	weight 99 5 1.000000 ( -0.024251 -0.078377 -0.404000 )
	weight 100 3 1.000000 ( 1.424513 0.306189 -0.697900 )
	weight 101 3 1.000000 ( 0.641003 0.712702 -0.651500 )
	weight 102 3 1.000000 ( 0.495995 -0.229674 -0.820200 )
	weight 103 3 1.000000 ( 0.886272 -0.712086 -0.664600 )
	weight 104 3 1.000000 ( -0.295140 0.982896 -0.663900 )
	weight 105 18 1.000000 ( 0.627589 -0.224045 0.163652 )
	weight 106 3 1.000000 ( -0.495015 0.559428 -0.875100 )
	weight 107 18 1.000000 ( 0.648005 0.019985 -0.211518 )
	weight 108 3 1.000000 ( -0.655958 0.015370 -0.701000 )
	weight 109 22 1.000000 ( 0.233016 -0.281490 -0.605800 )
	weight 110 18 1.000000 ( 0.829803 0.041647 0.170060 )
	weight 111 22 1.000000 ( 0.233016 -0.281490 -0.605800 )
	weight 112 23 1.000000 ( -0.035421 -0.186926 -0.396300 )
	weight 113 23 1.000000 ( 1.267515 0.151359 -1.100100 )
	weight 114 12 1.000000 ( -0.310833 0.216208 -0.220147 )
	weight 115 12 1.000000 ( 0.674620 -0.880381 0.817803 )
	weight 116 3 1.000000 ( 0.886272 -0.712086 -0.664600 )
	weight 117 3 1.000000 ( 0.495995 -0.229674 -0.820200 )
	weight 118 13 1.000000 ( 1.994726 0.315322 0.783277 )
	weight 119 12 1.000000 ( 1.449243 0.455604 -0.384379 )
	weight 120 13 1.000000 ( 1.268334 -0.193438 -0.803810 )
	weight 121 4 1.000000 ( 0.495295 -0.076104 -0.387500 )
	weight 122 13 1.000000 ( 3.431368 -0.285058 0.057901 )
	weight 123 3 1.000000 ( 0.886272 -0.712086 -0.664600 )

```
[/size]
## Post #25
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-09-12T17:41:26+00:00
- Post Title: Re: Exporting bones & animation to FBX

Here is a md5mesh exported from Blender



```
commandline ""

numJoints 26
numMeshes 1

joints {
	"0"	-1 ( 0.000000 1.981500 -0.548300 ) ( -0.000000 -0.707107 -0.000000 )		// 
	"1"	0 ( 0.000000 0.023900 -0.548300 ) ( -0.000000 -0.000000 -0.000000 )		// 0
	"2"	0 ( -0.000000 1.981500 -0.629400 ) ( -0.707107 -0.707107 -0.000000 )		// 0
	"3"	2 ( -0.000000 2.582000 -0.626800 ) ( -0.665415 -0.665415 0.239214 )		// 2
	"4"	3 ( -0.000000 3.582500 -1.452000 ) ( -0.704906 -0.704906 0.055750 )		// 3
	"5"	4 ( -0.000000 4.459700 -1.591700 ) ( -0.705163 -0.705163 0.052400 )		// 4
	"6"	4 ( 0.182500 3.591700 -1.030700 ) ( 0.337001 0.025043 0.069747 )		// 4
	"7"	6 ( 0.853200 3.514400 -0.966900 ) ( 0.926234 -0.080524 -0.196621 )		// 6
	"8"	7 ( 1.824000 3.485901 -1.409199 ) ( 0.858089 -0.251673 0.400317 )		// 7
	"9"	8 ( 2.350400 2.921903 -0.850898 ) ( 0.577365 0.107529 0.793103 )		// 8
	"25"	9 ( 1.425603 2.487895 2.275501 ) ( 0.577278 0.107868 0.793075 )		// 9
	"10"	4 ( -0.182600 3.591700 -1.030700 ) ( 0.025044 0.337003 0.938583 )		// 4
	"11"	11 ( -0.853300 3.514400 -0.967000 ) ( 0.080525 -0.926234 -0.311361 )		// 10
	"12"	12 ( -1.824100 3.485898 -1.409201 ) ( -0.251675 0.858086 0.200220 )		// 11
	"13"	13 ( -2.350500 2.921897 -0.850901 ) ( 0.107524 0.577361 0.161476 )		// 12
	"24"	14 ( -1.425699 2.487899 2.275498 ) ( 0.107874 0.577294 0.161686 )		// 13
	"14"	3 ( 0.521600 1.981500 -0.629400 ) ( -0.079981 0.266685 0.678161 )		// 3
	"15"	16 ( 0.453400 0.919700 -0.349600 ) ( -0.267927 0.064124 0.628104 )		// 14
	"16"	17 ( 0.558701 0.427000 -0.475899 ) ( 0.704929 -0.704927 0.055467 )		// 15
	"17"	18 ( 0.659602 0.023900 -1.113399 ) ( 0.537683 -0.459237 -0.459237 )		// 16
	"18"	3 ( -0.521700 1.981500 -0.629400 ) ( 0.266684 -0.079984 0.680132 )		// 3
	"19"	20 ( -0.453398 0.919700 -0.349601 ) ( 0.064125 -0.267927 0.727728 )		// 18
	"20"	21 ( -0.558697 0.427000 -0.475901 ) ( -0.704928 0.704928 0.055467 )		// 19
	"21"	22 ( -0.640798 0.023900 -0.994201 ) ( 0.459241 -0.537680 -0.537678 )		// 20
	"22"	3 ( -0.000000 2.098800 -0.000500 ) ( 0.337305 0.337305 0.621470 )		// 3
	"23"	24 ( -0.000000 1.127800 1.491700 ) ( 0.350431 0.350431 0.614165 )		// 22
}

mesh {
	shader ""

	numverts 124
	vert 0 ( 0.801100 0.143500 ) 0 1
	vert 1 ( 0.773900 0.028200 ) 1 1
	vert 2 ( 0.824200 0.129000 ) 2 1
	vert 3 ( 0.742800 0.260800 ) 3 1
	vert 4 ( 0.974800 0.218300 ) 4 1
	vert 5 ( 0.838800 0.174600 ) 5 1
	vert 6 ( 0.851100 0.133600 ) 6 1
	vert 7 ( 0.218200 0.205800 ) 7 1
	vert 8 ( 0.289800 0.018600 ) 8 1
	vert 9 ( 0.291300 0.167500 ) 9 1
	vert 10 ( 0.212900 0.044100 ) 10 1
	vert 11 ( 0.161200 0.092800 ) 11 1
	vert 12 ( 0.154400 0.177700 ) 12 1
	vert 13 ( 0.257200 0.211700 ) 13 1
	vert 14 ( 0.217000 0.228700 ) 14 1
	vert 15 ( 0.182000 0.213300 ) 15 1
	vert 16 ( 0.234700 0.361400 ) 16 1
	vert 17 ( 0.492500 0.134600 ) 17 1
	vert 18 ( 0.473500 0.150500 ) 18 1
	vert 19 ( 0.415200 0.119300 ) 19 1
	vert 20 ( 0.447400 0.080400 ) 20 1
	vert 21 ( 0.506200 0.184500 ) 21 1
	vert 22 ( 0.560100 0.187300 ) 22 1
	vert 23 ( 0.499600 0.239600 ) 23 1
	vert 24 ( 0.558400 0.083700 ) 24 1
	vert 25 ( 0.605800 0.143000 ) 25 1
	vert 26 ( 0.671200 0.097300 ) 26 1
	vert 27 ( 0.655700 0.232700 ) 27 1
	vert 28 ( 0.742700 0.391000 ) 28 1
	vert 29 ( 0.616000 0.318100 ) 29 1
	vert 30 ( 0.625300 0.080200 ) 30 1
	vert 31 ( 0.621800 0.049900 ) 31 1
	vert 32 ( 0.614300 0.243300 ) 32 1
	vert 33 ( 0.445100 0.397400 ) 33 1
	vert 34 ( 0.517000 0.038700 ) 34 1
	vert 35 ( 0.517100 0.416700 ) 35 1
	vert 36 ( 0.534100 0.597300 ) 36 1
	vert 37 ( 0.755000 0.550500 ) 37 1
	vert 38 ( 0.915800 0.616200 ) 38 1
	vert 39 ( 0.437100 0.612900 ) 39 1
	vert 40 ( 0.624800 0.790400 ) 40 1
	vert 41 ( 0.728600 0.870600 ) 41 1
	vert 42 ( 0.674400 0.981900 ) 42 1
	vert 43 ( 0.741800 0.741200 ) 43 1
	vert 44 ( 0.812500 0.857700 ) 44 1
	vert 45 ( 0.858300 0.755400 ) 45 1
	vert 46 ( 0.912700 0.557000 ) 46 1
	vert 47 ( 0.964800 0.759100 ) 47 1
	vert 48 ( 0.933900 0.964600 ) 48 1
	vert 49 ( 0.886100 0.837300 ) 49 1
	vert 50 ( 0.792000 0.912200 ) 50 1
	vert 51 ( 0.433800 0.133400 ) 51 1
	vert 52 ( 0.349300 0.129000 ) 52 1
	vert 53 ( 0.392900 0.106100 ) 53 1
	vert 54 ( 0.699100 0.215300 ) 54 1
	vert 55 ( 0.544100 0.782000 ) 55 1
	vert 56 ( 0.530200 0.978100 ) 56 1
	vert 57 ( 0.270000 0.988500 ) 57 1
	vert 58 ( 0.517700 0.816500 ) 58 1
	vert 59 ( 0.287600 0.911300 ) 59 1
	vert 60 ( 0.471900 0.733800 ) 60 1
	vert 61 ( 0.316600 0.742200 ) 61 1
	vert 62 ( 0.081600 0.802400 ) 62 1
	vert 63 ( 0.079300 0.889400 ) 63 1
	vert 64 ( 0.305000 0.589600 ) 64 1
	vert 65 ( 0.237100 0.906100 ) 65 1
	vert 66 ( 0.289100 0.428800 ) 66 1
	vert 67 ( 0.061600 0.421200 ) 67 1
	vert 68 ( 0.077100 0.606600 ) 68 1
	vert 69 ( 0.237100 0.908900 ) 69 1
	vert 70 ( 0.055600 0.968700 ) 70 1
	vert 71 ( 0.059100 0.285000 ) 71 1
	vert 72 ( 0.755000 0.550500 ) 72 1
	vert 73 ( 0.912700 0.557000 ) 73 1
	vert 74 ( 0.801100 0.143500 ) 74 1
	vert 75 ( 0.824200 0.129000 ) 75 1
	vert 76 ( 0.773900 0.028200 ) 76 1
	vert 77 ( 0.742800 0.260800 ) 77 1
	vert 78 ( 0.838800 0.174600 ) 78 1
	vert 79 ( 0.974800 0.218300 ) 79 1
	vert 80 ( 0.851100 0.133600 ) 80 1
	vert 81 ( 0.218200 0.205800 ) 81 1
	vert 82 ( 0.291300 0.167500 ) 82 1
	vert 83 ( 0.289800 0.018600 ) 83 1
	vert 84 ( 0.212900 0.044100 ) 84 1
	vert 85 ( 0.161200 0.092800 ) 85 1
	vert 86 ( 0.154400 0.177700 ) 86 1
	vert 87 ( 0.257200 0.211700 ) 87 1
	vert 88 ( 0.217000 0.228700 ) 88 1
	vert 89 ( 0.182000 0.213300 ) 89 1
	vert 90 ( 0.234700 0.361400 ) 90 1
	vert 91 ( 0.492500 0.134600 ) 91 1
	vert 92 ( 0.415200 0.119300 ) 92 1
	vert 93 ( 0.560100 0.187300 ) 93 1
	vert 94 ( 0.605800 0.143000 ) 94 1
	vert 95 ( 0.558400 0.083700 ) 95 1
	vert 96 ( 0.655700 0.232700 ) 96 1
	vert 97 ( 0.616000 0.318100 ) 97 1
	vert 98 ( 0.625300 0.080200 ) 98 1
	vert 99 ( 0.614300 0.243300 ) 99 1
	vert 100 ( 0.517100 0.416700 ) 100 1
	vert 101 ( 0.534100 0.597300 ) 101 1
	vert 102 ( 0.755000 0.550500 ) 102 1
	vert 103 ( 0.915800 0.616200 ) 103 1
	vert 104 ( 0.624800 0.790400 ) 104 1
	vert 105 ( 0.728600 0.870600 ) 105 1
	vert 106 ( 0.741800 0.741200 ) 106 1
	vert 107 ( 0.812500 0.857700 ) 107 1
	vert 108 ( 0.858300 0.755400 ) 108 1
	vert 109 ( 0.886100 0.837300 ) 109 1
	vert 110 ( 0.792000 0.912200 ) 110 1
	vert 111 ( 0.530200 0.978100 ) 111 1
	vert 112 ( 0.517700 0.816500 ) 112 1
	vert 113 ( 0.471900 0.733800 ) 113 1
	vert 114 ( 0.081600 0.802400 ) 114 1
	vert 115 ( 0.305000 0.589600 ) 115 1
	vert 116 ( 0.079300 0.889400 ) 116 1
	vert 117 ( 0.237100 0.906100 ) 117 1
	vert 118 ( 0.289100 0.428800 ) 118 1
	vert 119 ( 0.077100 0.606600 ) 119 1
	vert 120 ( 0.061600 0.421200 ) 120 1
	vert 121 ( 0.237100 0.908900 ) 121 1
	vert 122 ( 0.059100 0.285000 ) 122 1
	vert 123 ( 0.755000 0.550500 ) 123 1

	numtris 202
	tri 0 0 2 1
	tri 1 3 2 0
	tri 2 2 5 4
	tri 3 5 2 3
	tri 4 2 6 1
	tri 5 6 2 4
	tri 6 1 6 0
	tri 7 0 6 5
	tri 8 5 6 4
	tri 9 0 5 3
	tri 10 7 9 8
	tri 11 8 10 7
	tri 12 11 7 10
	tri 13 7 11 12
	tri 14 8 12 11
	tri 15 12 8 9
	tri 16 7 13 9
	tri 17 13 7 14
	tri 18 15 14 7
	tri 19 7 12 15
	tri 20 13 15 12
	tri 21 12 9 13
	tri 22 13 14 16
	tri 23 14 15 16
	tri 24 15 13 16
	tri 25 17 19 18
	tri 26 17 20 19
	tri 27 21 23 22
	tri 28 17 25 24
	tri 29 25 27 26
	tri 30 28 27 29
	tri 31 30 26 31
	tri 32 24 20 17
	tri 33 29 32 23
	tri 34 23 33 29
	tri 35 30 31 34
	tri 36 22 17 18
	tri 37 35 29 33
	tri 38 36 37 35
	tri 39 33 36 35
	tri 40 37 38 35
	tri 41 36 33 39
	tri 42 40 36 39
	tri 43 35 38 29
	tri 44 40 42 41
	tri 45 43 41 44
	tri 46 45 37 43
	tri 47 46 37 47
	tri 48 47 49 48
	tri 49 45 43 44
	tri 50 41 42 50
	tri 51 48 50 42
	tri 52 50 48 49
	tri 53 19 51 18
	tri 54 51 19 52
	tri 55 20 53 19
	tri 56 52 19 53
	tri 57 49 45 44
	tri 58 49 44 50
	tri 59 27 28 54
	tri 60 26 27 54
	tri 61 27 32 29
	tri 62 55 42 40
	tri 63 43 37 36
	tri 64 27 25 32
	tri 65 32 22 23
	tri 66 24 30 34
	tri 67 20 24 34
	tri 68 25 30 24
	tri 69 25 26 30
	tri 70 32 25 22
	tri 71 25 17 22
	tri 72 43 40 41
	tri 73 43 36 40
	tri 74 39 55 40
	tri 75 47 45 49
	tri 76 47 37 45
	tri 77 18 21 22
	tri 78 56 58 57
	tri 79 59 57 58
	tri 80 60 61 59
	tri 81 59 58 60
	tri 82 58 56 57
	tri 83 57 59 58
	tri 84 61 60 59
	tri 85 58 59 60
	tri 86 62 64 63
	tri 87 64 65 63
	tri 88 66 68 67
	tri 89 68 64 62
	tri 90 69 63 70
	tri 91 64 62 63
	tri 92 63 65 64
	tri 93 62 64 68
	tri 94 68 66 67
	tri 95 68 64 66
	tri 96 64 68 66
	tri 97 66 67 71
	tri 98 67 66 71
	tri 99 46 72 37
	tri 100 72 46 73
	tri 101 74 76 75
	tri 102 75 77 74
	tri 103 75 79 78
	tri 104 78 77 75
	tri 105 75 76 80
	tri 106 80 79 75
	tri 107 80 76 74
	tri 108 74 78 80
	tri 109 78 79 80
	tri 110 74 77 78
	tri 111 81 83 82
	tri 112 83 81 84
	tri 113 85 84 81
	tri 114 81 86 85
	tri 115 83 85 86
	tri 116 86 82 83
	tri 117 81 82 87
	tri 118 87 88 81
	tri 119 89 81 88
	tri 120 81 89 86
	tri 121 87 86 89
	tri 122 86 87 82
	tri 123 87 90 88
	tri 124 88 90 89
	tri 125 89 90 87
	tri 126 91 18 92
	tri 127 91 92 20
	tri 128 21 93 23
	tri 129 91 95 94
	tri 130 94 26 96
	tri 131 28 97 96
	tri 132 98 31 26
	tri 133 95 91 20
	tri 134 97 23 99
	tri 135 23 97 33
	tri 136 98 34 31
	tri 137 93 18 91
	tri 138 100 33 97
	tri 139 101 100 102
	tri 140 33 100 101
	tri 141 102 100 103
	tri 142 101 39 33
	tri 143 104 39 101
	tri 144 100 97 103
	tri 145 104 105 42
	tri 146 106 107 105
	tri 147 108 106 102
	tri 148 46 47 102
	tri 149 47 48 109
	tri 150 108 107 106
	tri 151 105 110 42
	tri 152 48 42 110
	tri 153 110 109 48
	tri 154 92 18 51
	tri 155 51 52 92
	tri 156 20 92 53
	tri 157 52 53 92
	tri 158 109 107 108
	tri 159 109 110 107
	tri 160 96 54 28
	tri 161 26 54 96
	tri 162 96 97 99
	tri 163 55 104 42
	tri 164 106 101 102
	tri 165 96 99 94
	tri 166 99 23 93
	tri 167 95 34 98
	tri 168 20 34 95
	tri 169 94 95 98
	tri 170 94 98 26
	tri 171 99 93 94
	tri 172 94 93 91
	tri 173 106 105 104
	tri 174 106 104 101
	tri 175 39 104 55
	tri 176 47 109 108
	tri 177 47 108 102
	tri 178 18 93 21
	tri 179 111 57 112
	tri 180 59 112 57
	tri 181 113 59 61
	tri 182 59 113 112
	tri 183 112 57 111
	tri 184 57 112 59
	tri 185 61 59 113
	tri 186 112 113 59
	tri 187 114 116 115
	tri 188 115 116 117
	tri 189 118 120 119
	tri 190 119 114 115
	tri 191 121 70 116
	tri 192 115 116 114
	tri 193 116 115 117
	tri 194 114 119 115
	tri 195 119 120 118
	tri 196 119 118 115
	tri 197 115 118 119
	tri 198 118 122 120
	tri 199 120 122 118
	tri 200 46 102 123
	tri 201 123 73 46

	numweights 124
	weight 0 18 1.000000 ( 0.223400 0.147750 0.034720 )
	weight 1 18 1.000000 ( 0.404900 0.133381 -0.683268 )
	weight 2 18 1.000000 ( -0.043500 0.048337 -0.038736 )
	weight 3 18 1.000000 ( 0.414699 0.479324 0.709871 )
	weight 4 18 1.000000 ( 0.403201 -0.417811 0.599929 )
	weight 5 18 1.000000 ( 0.266200 0.039819 0.247620 )
	weight 6 18 1.000000 ( 0.220400 -0.046332 0.006628 )
	weight 7 16 1.000000 ( 1.100712 -0.064402 -0.132538 )
	weight 8 16 1.000000 ( 0.647999 0.211638 0.019940 )
	weight 9 16 1.000000 ( 1.079985 0.286716 0.094534 )
	weight 10 16 1.000000 ( 0.627582 -0.163513 -0.224091 )
	weight 11 16 1.000000 ( 0.829797 -0.169932 0.041602 )
	weight 12 16 1.000000 ( 1.102679 -0.099202 0.177621 )
	weight 13 17 1.000000 ( 0.047063 0.149538 0.062825 )
	weight 14 17 1.000000 ( 0.100785 -0.016801 0.007333 )
	weight 15 17 1.000000 ( 0.022801 -0.061828 0.104735 )
	weight 16 18 1.000000 ( -0.043500 0.048337 -0.038736 )
	weight 17 5 1.000000 ( 0.469966 0.141400 0.392448 )
	weight 18 5 1.000000 ( 0.349844 0.000000 0.476324 )
	weight 19 5 1.000000 ( 0.455326 0.063700 0.773497 )
	weight 20 5 1.000000 ( 0.680199 0.000000 0.575283 )
	weight 21 5 1.000000 ( 0.201712 0.000000 0.348413 )
	weight 22 5 1.000000 ( 0.211593 0.129900 0.244714 )
	weight 23 5 1.000000 ( -0.027617 0.000000 0.320603 )
	weight 24 5 1.000000 ( 0.736118 0.271600 0.230936 )
	weight 25 5 1.000000 ( 0.465352 0.431000 -0.051142 )
	weight 26 5 1.000000 ( 0.755160 0.000000 -0.414972 )
	weight 27 5 1.000000 ( 0.095728 0.331100 -0.353329 )
	weight 28 4 1.000000 ( 0.286112 0.000000 -0.626261 )
	weight 29 4 1.000000 ( 0.495295 0.387500 -0.076104 )
	weight 30 5 1.000000 ( 0.786707 0.254000 -0.132836 )
	weight 31 5 1.000000 ( 0.967948 0.000000 -0.129791 )
	weight 32 5 1.000000 ( -0.024251 0.404000 -0.078376 )
	weight 33 3 1.000000 ( 1.643736 0.000000 0.491273 )
	weight 34 5 1.000000 ( 0.927288 0.000000 0.295692 )
	weight 35 3 1.000000 ( 1.424513 0.697900 0.306189 )
	weight 36 3 1.000000 ( 0.641003 0.651500 0.712702 )
	weight 37 3 1.000000 ( 0.495995 0.820200 -0.229674 )
	weight 38 3 1.000000 ( 0.886272 0.664600 -0.712086 )
	weight 39 3 1.000000 ( 0.708025 0.000000 1.070923 )
	weight 40 3 1.000000 ( -0.295063 0.663900 0.982832 )
	weight 41 16 1.000000 ( 0.627582 -0.163513 -0.224091 )
	weight 42 2 1.000000 ( -0.665000 -0.000000 0.273800 )
	weight 43 3 1.000000 ( -0.495015 0.875100 0.559428 )
	weight 44 16 1.000000 ( 0.647999 0.211638 0.019940 )
	weight 45 3 1.000000 ( -0.655958 0.701000 0.015370 )
	weight 46 3 1.000000 ( 0.224833 0.000000 -0.798531 )
	weight 47 24 1.000000 ( 0.022439 0.000000 0.297825 )
	weight 48 24 1.000000 ( 0.200832 0.000000 -0.362631 )
	weight 49 24 1.000000 ( 0.233016 0.605800 -0.281490 )
	weight 50 16 1.000000 ( 0.829797 -0.169932 0.041602 )
	weight 51 5 1.000000 ( 0.381982 0.000000 0.771213 )
	weight 52 5 1.000000 ( 0.382686 0.000000 1.022873 )
	weight 53 5 1.000000 ( 0.560916 0.000000 0.806857 )
	weight 54 5 1.000000 ( 0.220742 0.000000 -0.474841 )
	weight 55 3 1.000000 ( -0.148845 0.000000 1.155832 )
	weight 56 24 1.000000 ( 0.233016 0.605800 -0.281490 )
	weight 57 24 1.000000 ( 0.022439 0.000000 0.297825 )
	weight 58 25 1.000000 ( -0.035421 0.396300 -0.186926 )
	weight 59 25 1.000000 ( 0.011065 0.000000 0.134779 )
	weight 60 25 1.000000 ( 1.267515 1.100100 0.151359 )
	weight 61 25 1.000000 ( 1.000321 0.000000 0.126447 )
	weight 62 8 1.000000 ( -0.310775 0.220123 0.216283 )
	weight 63 3 1.000000 ( 0.886272 0.664600 -0.712086 )
	weight 64 8 1.000000 ( 0.674662 -0.817838 -0.880293 )
	weight 65 3 1.000000 ( 0.495995 0.820200 -0.229674 )
	weight 66 9 1.000000 ( 1.994700 -0.783244 0.315267 )
	weight 67 9 1.000000 ( 1.268303 0.803871 -0.193438 )
	weight 68 8 1.000000 ( 1.449306 0.384365 0.455702 )
	weight 69 4 1.000000 ( 0.495295 0.387500 -0.076104 )
	weight 70 4 1.000000 ( 0.286112 0.000000 -0.626261 )
	weight 71 9 1.000000 ( 3.431335 -0.057822 -0.285211 )
	weight 72 3 1.000000 ( 0.886272 0.664600 -0.712086 )
	weight 73 4 1.000000 ( 0.286112 0.000000 -0.626261 )
	weight 74 22 1.000000 ( 0.223400 -0.147745 0.034718 )
	weight 75 22 1.000000 ( -0.043500 -0.048334 -0.038737 )
	weight 76 22 1.000000 ( 0.404900 -0.133375 -0.683270 )
	weight 77 22 1.000000 ( 0.414700 -0.479320 0.709869 )
	weight 78 22 1.000000 ( 0.266200 -0.039815 0.247619 )
	weight 79 22 1.000000 ( 0.403200 0.417815 0.599928 )
	weight 80 22 1.000000 ( 0.220400 0.046336 0.006627 )
	weight 81 20 1.000000 ( 1.100719 0.064487 -0.132486 )
	weight 82 20 1.000000 ( 1.079990 -0.286631 0.094585 )
	weight 83 20 1.000000 ( 0.648004 -0.211551 0.019990 )
	weight 84 20 1.000000 ( 0.627590 0.163600 -0.224041 )
	weight 85 20 1.000000 ( 0.829803 0.170018 0.041653 )
	weight 86 20 1.000000 ( 1.102685 0.099287 0.177674 )
	weight 87 21 1.000000 ( 0.047063 -0.149541 0.062824 )
	weight 88 21 1.000000 ( 0.100785 0.016798 0.007333 )
	weight 89 21 1.000000 ( 0.022801 0.061825 0.104735 )
	weight 90 22 1.000000 ( -0.043500 -0.048334 -0.038737 )
	weight 91 5 1.000000 ( 0.469966 -0.141400 0.392448 )
	weight 92 5 1.000000 ( 0.455326 -0.063700 0.773497 )
	weight 93 5 1.000000 ( 0.211593 -0.129900 0.244714 )
	weight 94 5 1.000000 ( 0.465352 -0.431000 -0.051142 )
	weight 95 5 1.000000 ( 0.736118 -0.271600 0.230936 )
	weight 96 5 1.000000 ( 0.095728 -0.331100 -0.353329 )
	weight 97 4 1.000000 ( 0.495295 -0.387500 -0.076104 )
	weight 98 5 1.000000 ( 0.786707 -0.254000 -0.132836 )
	weight 99 5 1.000000 ( -0.024251 -0.404000 -0.078376 )
	weight 100 3 1.000000 ( 1.424513 -0.697900 0.306189 )
	weight 101 3 1.000000 ( 0.641003 -0.651500 0.712702 )
	weight 102 3 1.000000 ( 0.495995 -0.820200 -0.229674 )
	weight 103 3 1.000000 ( 0.886272 -0.664600 -0.712086 )
	weight 104 3 1.000000 ( -0.295140 -0.663900 0.982896 )
	weight 105 20 1.000000 ( 0.627590 0.163600 -0.224041 )
	weight 106 3 1.000000 ( -0.495015 -0.875100 0.559428 )
	weight 107 20 1.000000 ( 0.648004 -0.211551 0.019990 )
	weight 108 3 1.000000 ( -0.655958 -0.701000 0.015370 )
	weight 109 24 1.000000 ( 0.233016 -0.605800 -0.281490 )
	weight 110 20 1.000000 ( 0.829803 0.170018 0.041653 )
	weight 111 24 1.000000 ( 0.233016 -0.605800 -0.281490 )
	weight 112 25 1.000000 ( -0.035421 -0.396300 -0.186926 )
	weight 113 25 1.000000 ( 1.267516 -1.100100 0.151359 )
	weight 114 13 1.000000 ( -0.310836 -0.220145 0.216198 )
	weight 115 13 1.000000 ( 0.674628 0.817807 -0.880362 )
	weight 116 3 1.000000 ( 0.886272 -0.664600 -0.712086 )
	weight 117 3 1.000000 ( 0.495995 -0.820200 -0.229674 )
	weight 118 14 1.000000 ( 1.994728 0.783285 0.315199 )
	weight 119 13 1.000000 ( 1.449239 -0.384391 0.455654 )
	weight 120 14 1.000000 ( 1.268334 -0.803834 -0.193497 )
	weight 121 4 1.000000 ( 0.495295 -0.387500 -0.076104 )
	weight 122 14 1.000000 ( 3.431370 0.057852 -0.285252 )
	weight 123 3 1.000000 ( 0.886272 -0.664600 -0.712086 )
}


```
## Post #26
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-12T18:38:02+00:00
- Post Title: Re: Exporting bones & animation to FBX

> Reply from majidemo
>
> I'm currently doing 2 things at the moment:

 Rewriting the blender script you provided so it will work with the latest version of blender.
You're the "most bravehearted guy" I've ever seen.  

Would take me ages to just understand this one single python line:
boneMatrix=Blender.Object.Get('armature').getData().bones[str(k)].matrix['ARMATURESPACE']

(There's a reason why I truly hate python script: I'm too dumb for it.  )

str(k) creates a string from a number(?) but I guess [string] is not an array index?
(Oh, no, in fact I don't want to know it....)
## Post #27
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2016-09-13T08:33:05+00:00
- Post Title: Re: Exporting bones & animation to FBX

I can't thank both of you enough. I was not able to make my export_to_md5mesh work right but the blender script I wrote with export to fbx works well enough for what I need. I'll close this thread as solved. 

I'll be back soon for other questions that might arise as I continue analysing the files. Cheers!

Thank you, thank you.

@mr. Shakotay2, I believe the string index is allowed by python dictionaries (bit like JSON)
