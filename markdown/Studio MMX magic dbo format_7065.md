## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-27T18:22:12+00:00
- Post Title: Studio MMX magic dbo format

MMX has created several adult FPS (though by "adult" I mean a couple videos that you get as a reward when you...beat the game lol so it's really just FPS with a couple videos thrown into it to try to entice people into buying it)

All of the models use the same format, I think. Low-poly.
The format for the non-skinned meshes seem pretty straightforward but there are so many odd integers here and there. I also haven't figured out how to determine the number of meshes.

Anyways enjoy.
I've gotten some outline of the format but it's full of unk's.

Here's a cabinet (single named mesh)



EDIT: revised outline. Found that some meshes have named frames, others do not have names (maybe for single mesh models)

Ok, there appears to be some significance to the following integers: 0x66, 0x67, 0x68.

If an 0x08 follows after 0x67, you can expect to read a certain number of dwords, and then see an 0x68, then run into a string. If you see 0x66, you end up reading a matrix. Will need to get more samples to verify.

It's possible that two 0x67 0x08 appear in a row, so you would end up reading two strings before going into the vertex section.

0x66 is always followed by 0x40, which is the size of the following matrix

```

dword unk (could be length of the idstring)
char_8 idstring (MAGICDBO)
dword unk
dword null
dword null
dword unk
dword filesize - 68
dword unk
dword unk
dword unk
dword unk
dword unk
float_16 world_matrix

dword unk #67

struct mesh {
	dword unk1

	if unk1 == 8: #named mesh or frame
		dword null
		dword null
		dword unk
		dword unk
		dword unk
		dword unk
		
		dword charLen
		charLen meshName (or frameName?)

		dword unk
		dword unk
		float_16 local_matrix
		dword_2 unk

	dword_5 unks
	dword vertSize possibly
	dword_2 unk
	dword numVertices
	dword_2 unks
	dword_numIndices
	dword_5

	struct vertex {
	  float_8
	}
	
	dword unk
	dword FaceSectionSize
	struct face {
		short_3 v1, v2, v3
	}
#material section follows
}

#maybe more

```

[Star Guardian.rar](https://xentaxbackup.github.io/file/4547_Star Guardian.rar)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-28T11:33:14+00:00
- Post Title: Studio MMX magic dbo format

Its a standard chunk based format

Schene_Name_Size long
Scne_Name Schene_Name_Size
Unk01 long
then for the rest of the file it goes
Chunk ID long
Chunk ID Size long
Chunk Data
Then that chunk data may contain sub chunks that follow the same format.
That is it all you need to do is map the id's
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-28T13:12:47+00:00
- Post Title: Studio MMX magic dbo format

oh, I get it. Most of the unknowns make sense then.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-09T19:12:39+00:00
- Post Title: Studio MMX magic dbo format

As chrrox mentioned this is just a chunk-based format, so I started looking at what each chunk might be.

There are a lot of chunks, and many of them I have no clue about.
The chunks I currently wrote code to actually do something (rather than just skip it) are:

0x01 - just indicates the beginning of the model (just skip)
0x65 - sometimes has a name, sometimes not
0x66 - matrix of some sort
0x67 - if chunksize > 8, parse vertices and faces
0x80 - start of material section (just skip)
0x8D - texture name (may or may not have anything

Note that there are chunks from 0x65 all the way to 0x9f.
[mcsb.JPG](https://xentaxbackup.github.io/file/4603_mcsb.JPG)
