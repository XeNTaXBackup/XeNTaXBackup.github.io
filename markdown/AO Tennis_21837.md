## Post #1
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2020-03-04T07:36:09+00:00
- Post Title: AO Tennis

Hi, someone can check this models game format please? I've found a tool to extract all
Is "msh", any chance to have an importer? thank you in advance
[https://www.mediafire.com/file/u8zjia0e ... 8.msh/file](https://www.mediafire.com/file/u8zjia0eh2ure80/88.msh/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-04T10:21:42+00:00
- Post Title: AO Tennis

using hex2obj (view link in my sig) for creating a point cloud:
.



88-msh.png (22.64 KiB) Viewed 55 times

Looks promising but that's all. Using more points (31442) doesn't give better results. Face indices (01000000 skipped) don't fit, too.
Maybe another vertex start address to be used?

0x0 500
Vb1
48 99
0xA4 31442
020000
0x0 255
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-03-05T04:46:38+00:00
- Post Title: AO Tennis

The structure seems simple:

```
long	Cnt1

long	EntryOffset // relative to the offset of this field
long	EntryCnt

long	VertDataOffset // relative to the offset of this field
long	VertDataSize

long	StringEntryOffset // relative to the offset of this field
long	stringNum

long	subMeshEntryOffset // relative to the offset of this field
long	subMeshCnt

long	unknownCnt // 

for i = 0 < EntryCnt // sizeof = 16
	char	AttrName[12]
	word	DataBlockID?
	word	VecSize?
	
for i = 0 < Vcount // sizeof = 48
	float	Position[3]
	word	unknown[2]
	float	Normal[3]
	long	NULL
	float	Tangent[3]
	word	unknown[2]
	
for i = 0 < stringNum // sizeof = 24
	long	stringOffset // relative to the offset of this field
	long	unknown[5]
	
for i = 0 < subMeshCnt // sizeof = 12
	long	stride
	long	subMeshVcount
	long	unknownOffset

for i = 0 < unknownCnt // sizeof = 8
	long	vertIdx
	long	x1
	
for i = 0 < unknownCnt // sizeof = 16
	byte	unknown[16]
	
for i = 0 < stringNum
	string	aString

```

But I doubt there're any explicit face indices. Probably a different kind of implicit storage.



1st.png (219.06 KiB) Viewed 34 times
