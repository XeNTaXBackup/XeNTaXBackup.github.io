## Post #1
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2011-09-12T12:09:58+00:00
- Post Title: Telltale games d3dmesh

Hi guys, is anyone know how to import 3D3MESH from telltale game into 3ds max ?
P.S Google didn't help
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-12T23:20:11+00:00
- Post Title: Telltale games d3dmesh

imm I open it before but can't remember with what, maybe you can try with GameBryo
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-12T23:35:21+00:00
- Post Title: Telltale games d3dmesh

their method for storing faces is weird everything else is dead simple.
## Post #4
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2011-09-13T13:18:52+00:00
- Post Title: Telltale games d3dmesh

> Reply from CriticalError
>
> imm I open it before but can't remember with what, maybe you can try with GameBryo
I can't find the GameBryo
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-13T14:19:47+00:00
- Post Title: Telltale games d3dmesh

they are not gamebryo that is bad information
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-09-13T16:06:34+00:00
- Post Title: Telltale games d3dmesh

File format:(not finished)

```
dword[1] - unk1
unk1 x {
dword[1] - size
char[size]
word[2]
}
dword[1] - unk2
dword[1] - size
char[size]
byte[25]
offset - get offset
dword[1] - seek
go to offset+seek
offset - get offset
dword[1] - seek
go to offset+seek
word[1] - unk3
word[1] - unk4
word[1] - unk5
word[1] - unk6
word[1] - unk7
word[1] - unk8
word[1] - unk9
word[1]/3 - num triangles
word[1] - unk10
word[1] - unk11
word[1] - unk12
num triangles x {
word[3]
}
word[1] - unk13
word[1] - num vertices
word[1] - unk14
word[1] - unk15
word[1] - unk16
word[1] - unk17
word[1] - unk18
byte[1]
num vertices x {
float[3]
}





```

Simple Blender249 importer for geometry:
[import-sam-and-max-2011-09-13.zip](https://xentaxbackup.github.io/file/4713_import-sam-and-max-2011-09-13.zip)
## Post #7
- Username: Carpethop
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Sep 12, 2011 8:02 pm
- Post datetime: 2011-09-14T13:30:16+00:00
- Post Title: Telltale games d3dmesh

> Reply from Szkaradek123
>
> File format:(not finished)
Code: Select allchar[4]
dword[1] - unk1
unk1 x {
dword[1] - size
char[size]
word[2]
}
dword[1] - unk2
dword[1] - size
char[size]
byte[25]
offset - get offset
dword[1] - seek
go to offset+seek
offset - get offset
dword[1] - seek
go to offset+seek
word[1] - unk3
word[1] - unk4
word[1] - unk5
word[1] - unk6
word[1] - unk7
word[1] - unk8
word[1] - unk9
word[1]/3 - num triangles
word[1] - unk10
word[1] - unk11
word[1] - unk12
num triangles x {
word[3]
}
word[1] - unk13
word[1] - num vertices
word[1] - unk14
word[1] - unk15
word[1] - unk16
word[1] - unk17
word[1] - unk18
byte[1]
num vertices x {
float[3]
}





Simple Blender249 importer for geometry:
Don't work for me    give's me this error [http://uppix.com/f-________________4e70ac39000d28e7.png](http://uppix.com/f-________________4e70ac39000d28e7.png)
