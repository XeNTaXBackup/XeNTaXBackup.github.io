## Post #1
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2015-06-25T06:11:37+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

Hello, everybody

I need help for Converting the models from Bloody Roar 3. The format is different from BR4, it doesn't look like a Renderware DFF format as in BR4 (I guess Eighting started using Renderware Engine from BR: Primal Fury afterwards.) Much looks like a standard "PS2 tri-stripes" model file but without chunks separator.

I tried using hex2obj, but I'm kinda lost at searching the UV/Vertices address

Here's the sample if needed:

[https://mega.co.nz/#!Cw0wUS5T!_41YhEc8O ... w_vGEdCa3o](https://mega.co.nz/#!Cw0wUS5T!_41YhEc8O2Rm48yI9uZfBcvSDWoHD0DUew_vGEdCa3o)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-25T09:38:58+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

> Reply from HirokiHiguchi69
>
> Much looks like a standard "PS2 tri-stripes" model file but without chunks separator.could you tell more about it? I've no time to check that out.

Talking about this data?

05D360   00 00 00 00 02 00 02 00  03 00 04 00 FF FF 02 00
05D370   03 00 FF FF 66 66 66 3F  CD CC CC 3D 00 00 00 00
...
05E000   00 00 00 00 02 00 02 00  31 00 32 00 FF FF 23 00
05E010   31 00 FF FF CD CC 4C 3E  CD CC 4C 3F 00 00 00 00

well: these seem to be too regular (even if I'd handled them as tri strips, I guess) as to be face indices:
f 5 6 4 
f 4 5 3 
f 4 5 3 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 106 115 99 
f 106 115 99 
f 106 115 99 
f 107 116 4 
f 107 116 4 
f 107 116 4 
f 107 117 4 
f 106 115 99 
f 106 115 99 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 106 115 99 
f 106 115 99 
f 116 117 4 
f 106 115 99 
f 6 98 5 
f 116 117 4 
f 107 117 4 
f 103 104 100 
f 103 104 100 
f 103 104 100 

> I tried using hex2obj, but I'm kinda lost at searching the UV/Vertices address



0000_TTM.JPG (42.51 KiB) Viewed 234 times

(point cloud)
## Post #3
- Username: BloodRaynare
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Jun 25, 2015 1:14 pm
- Post datetime: 2015-06-25T10:51:03+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

> Reply from shakotay2
>
> HirokiHiguchi69 wrote:Much looks like a standard "PS2 tri-stripes" model file but without chunks separator.could you tell more about it? I've no time to check that out.

Talking about this data?

05D360   00 00 00 00 02 00 02 00  03 00 04 00 FF FF 02 00
05D370   03 00 FF FF 66 66 66 3F  CD CC CC 3D 00 00 00 00
...
05E000   00 00 00 00 02 00 02 00  31 00 32 00 FF FF 23 00
05E010   31 00 FF FF CD CC 4C 3E  CD CC 4C 3F 00 00 00 00

well: these seem to be too regular (even if I'd handled them as tri strips, I guess) as to be face indices:
f 5 6 4 
f 4 5 3 
f 4 5 3 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 107 117 4 
f 106 115 99 
f 106 115 99 
f 106 115 99 
f 107 116 4 
f 107 116 4 
f 107 116 4 
f 107 117 4 
f 106 115 99 
f 106 115 99 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 116 117 4 
f 106 115 99 
f 106 115 99 
f 116 117 4 
f 106 115 99 
f 6 98 5 
f 116 117 4 
f 107 117 4 
f 103 104 100 
f 103 104 100 
f 103 104 100 
I tried using hex2obj, but I'm kinda lost at searching the UV/Vertices address
0000_TTM.JPG(point cloud)

Did the face indices address located at the end of the file? because that's what I'm thought when look some data that resembling scrambled alphabets at 0x628B0
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-25T12:24:21+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

ah, yeah, must have overlooked them. But they aren't too many and biggest face index seems to be 128 (0x7F+1).

Another idea would be to start from 0x5E0B4 but its DWORD DWORD WORD index here. Very strange.

Maybe pick up the smallest TTM you have and analyze its structure completely?
(Will take some time but at the end you'll know more...  )
## Post #5
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-07-04T03:01:25+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

Maybe it doesn't use indices and 3 pairs of verts each form a triangle.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-04T07:36:09+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

yeah, but which pairs?



0000_TTM-a.JPG (88.06 KiB) Viewed 196 times



From the first 100 vertices there's two simple 15 points mesh parts
which you could imagine how the faces would have to be build - then look for the belonging indices.

But I don't have the time for such.

edit: I've tried to give 0001.TTM some structure:
(pattern 1A cnt 00 01)

```
00 00 00 00  20 00 00 00  40 00 00 00  0F 00 0F 00  05 00 00 00  
60 03 00 00  40 04 00 00  60 04 00 00  0F 00 0F 00  05 00 00 00  1A 03 00 01  00 00 00 00  00 00 00 00  00 00 00 00  
00 00 00 00  40 00 00 00  60 00 00 00  0F 00 05 00  05 00 00 00  
00 04 00 00  C0 01 00 00  20 04 00 00  0F 00 05 00  05 00 00 00  

60 03 00 00  60 04 00 00  80 03 00 00  0F 00 05 00  05 00 00 00  1A 02 00 01  00 00 00 00  00 00 00 00  00 00 00 00  
80 00 00 00  A0 00 00 00  C0 00 00 00  05 00 05 00  0F 00 00 00  

60 00 00 00  C0 03 00 00  00 00 00 00  05 00 05 00  0F 00 00 00  1A 02 00 01  00 00 00 00  00 00 00 00  00 00 00 00  
80 00 00 00  C0 00 00 00  E0 00 00 00  05 00 0F 00  0F 00 00 00  

C0 01 00 00  00 04 00 00  E0 01 00 00  05 00 0F 00  0F 00 00 00  1A 06 00 01  00 00 00 00  00 00 00 00  00 00 00 00  
40 01 00 00  00 01 00 00  20 01 00 00  03 00 03 00  03 00 00 00  
60 01 00 00  40 01 00 00  00 01 00 00  03 00 03 00  03 00 00 00  
80 02 00 00  40 02 00 00  60 02 00 00  03 00 03 00  03 00 00 00  
A0 02 00 00  80 02 00 00  40 02 00 00  03 00 03 00  03 00 00 00  
00 03 00 00  C0 02 00 00  E0 02 00 00  03 00 03 00  03 00 00 00  

20 03 00 00  00 03 00 00  C0 02 00 00  03 00 03 00  03 00 00 00  1A 03 00 01  00 00 00 00  00 00 00 00  00 00 00 00  
40 00 00 00  20 00 00 00  80 01 00 00  05 00 0F 00  05 00 00 00  
C0 01 00 00  E0 01 00 00  00 02 00 00  05 00 0F 00  05 00 00 00  

40 03 00 00  60 03 00 00  80 03 00 00  05 00 0F 00  05 00 00 00  1A 04 00 01  00 00 00 00  00 00 00 00  00 00 00 00  
40 00 00 00  80 01 00 00  A0 01 00 00  05 00 05 00  05 00 00 00  
C0 01 00 00  00 02 00 00  20 02 00 00  05 00 05 00  05 00 00 00  
40 03 00 00  80 03 00 00  A0 03 00 00  05 00 05 00  05 00 00 00
...

```
found 339 lines with no senseful face indices.
The vertex count is 383 (0x17F)
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2016-03-18T03:03:03+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

Hello

using FurryFan's BMS script to unpack the "IMAGE00.DAT" I was able to look at the "TTM" files, which I assumed are models.
But there are other file types with the same base name, which makes me believe model components may be spread across other files.
SEQ: File Record?
TTM: Geometry?
TI: Textures?
MOT: Animation?

So far I have got mesh loading working for some static models like stages, but skinned meshes look pretty bad. 
I'm assuming I need the skeleton transforms in under to get the model vertex positions correct. 
And also I have not yet seen any texture map coordinates at all in the TTM, I'm starting to think they are in the TI (texture files)?

My Progress on the TTM format:
Block Structure
HEADER
MESH_TABLE
VERTEX_BUFFER
UNK_BLOCK01
UNK_BLOCK02
UNK_BLOCK03

The mesh table gives definitions for each object and contains a count and offset to a stream of draw commands for that object.
Certain draw commands are followed by 3 face positions repeated by a count given from the command.
The format of that would appear to be like <Vertex Colours> <Vertex Index> <Vertex BoneID> <Vertex Weight> ... but not sure?

I encountered two commands 0x11(Static) and 0x26(Skinned).
With 0x11 a series of 6 floats are missing that I assumed were floats, but when added up exceed 1.0 as a weight..

Below are some structures I made:

HEADER {
LONG fileid
LONG unk
LONG mesh_addr
LONG mesh_count
LONG buffer_addr
LONG buffer_count
LONG unk1_addr
LONG unk1_count
LONG unk2_addr
LONG unk2_count
LONG unk3_addr
LONG unk3_count
}
MESH_TABLE {
SHORT unk1
SHORT DRAW_COUNT
LONG DRAW_ADDR
LONG unk2
MATRIX4X4_32 transform
LONG unk3
LONG unk4
LONG unk5
LONG unk6
LONG unk7
LONG unk8
LONG unk9
LONG unk10
SHORT unk12
SHORT unk13
SHORT unk14
SHORT unk15
SHORT unk16
SHORT unk17
SHORT unk18
SHORT unk19
}
DRAW_HEADER {
BYTE type
SHORT count
BYTE flag
LONG unk1
LONG unk1
LONG unk1
}
DRAW_DATA {
LONG vertex1_colour_rgba
LONG vertex2_colour_rgba
LONG vertex3_colour_rgba
LONG vertex1_buffer_addr
LONG vertex2_buffer_addr
LONG vertex2_buffer_addr
SHORT unk1
SHORT unk2
SHORT unk3
SHORT unk4
FLOAT32 unk5
FLOAT32 unk6
FLOAT32 unk7
FLOAT32 unk8
FLOAT32 unk9
FLOAT32 unk10
}
VERTEX_BUFFER {
FLOAT32 x
FLOAT32 y
FLOAT32 z
FLOAT32 w
}
UNK_BLOCK01 {
LONG unk1
LONG index
LONG unk2
SHORT unk3
SHORT unk4
MATRIX4X4_32 transform
FLOAT32 unk5
FLOAT32 unk6
FLOAT32 unk7
FLOAT32 unk8
LONG unk9
LONG unk10
LONG unk11
LONG unk12
LONG unk13
LONG unk14
LONG unk15
LONG unk16
LONG unk17
LONG unk18
LONG unk19
LONG unk20
}
UNK_BLOCK03 {
SHORT unk
}
## Post #8
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2018-01-09T12:13:31+00:00
- Post Title: [HELP] Converting models from Bloody Roar 3

Hi, is there more progress in this model format? o.O
