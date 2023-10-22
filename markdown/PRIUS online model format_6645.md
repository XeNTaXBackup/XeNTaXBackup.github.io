## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-05-19T20:56:16+00:00
- Post Title: PRIUS online model format

Hi! Thanks to the tools on this page:

[http://www.geocities.jp/junk2ool/netgame.html](http://www.geocities.jp/junk2ool/netgame.html)

we can now see the model files from prius online.

I have attached a zip containing everything needed to analyze the model format:

[http://www.2shared.com/file/dWMEVNK7/adventurer.html](http://www.2shared.com/file/dWMEVNK7/adventurer.html)

632kb
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-05-20T22:18:36+00:00
- Post Title: PRIUS online model format

Thanks pixe greath contribution man.
## Post #3
- Username: tyb51
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 03, 2010 4:08 am
- Post datetime: 2011-06-03T21:03:10+00:00
- Post Title: PRIUS online model format

Very much thnx indeed. 
This is a huge step forward.

Although I don't realy know anything about this stuff, i think it can't be that hard to decifer a model.
Every model exists out of 2 files ive never seen before, and a bunch of textures.
The .cmi file is the mesh and the .mst looks like a note with specifications of the model: which textures and scale and thinks like that.
So seems pretty clear to me although i don't know how to go further then reading whats to read
## Post #4
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-06-04T13:07:55+00:00
- Post Title: PRIUS online model format

There might just be some kind of importer soon *hint* but time will tell
## Post #5
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-06-04T13:57:07+00:00
- Post Title: PRIUS online model format

thanks
## Post #6
- Username: tyb51
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 03, 2010 4:08 am
- Post datetime: 2011-06-05T10:47:37+00:00
- Post Title: PRIUS online model format

Hmm that seems promessing ^^
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-11T21:36:21+00:00
- Post Title: PRIUS online model format

thanks a lot for this great info and anyone have a importer?
## Post #8
- Username: bmobius
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 18, 2010 6:44 am
- Post datetime: 2011-06-23T01:34:40+00:00
- Post Title: PRIUS online model format

Any news in regards to that Prius Online model importer?
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-23T02:29:58+00:00
- Post Title: PRIUS online model format

not released yet  chrox still working in it? anyway thanks for try
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-01T03:18:47+00:00
- Post Title: PRIUS online model format

Spent about 20 mins comparing files and writing down some patterns.

mst files specify stuff to load and other properties. From this we can conclude that

cmi files contain models
cai files contain animations.

For the cmi file, the header and bone structs are parsed fine. The material section and the section after that is odd, but there is some pattern.

Each vertex struct is 21 bytes. Some files have 32 bytes.
To me, that's a weird number. Maybe there are half-floats involved? 

Face section is straightforward.

There are a bunch of shorts after the face section, equal to the number of faces.
Most of them are 1's, but I've seen some 2's and 8's (random). This most likely has something to do with the faces. I suggested maybe it's the material index used (like how direct3d .x files specify face material using indices), but most of the models only have one mesh and one material o.O

A character (which you expect to be multi-mesh) is broken down into different files, each with a single mesh, a bunch of bones, and one material.

```

#header
dword idstring (CMI\20)
word unk1
word unk2
word numBones

numBones bone { (maybe)
	word boneIndex?
	word charLen
	charLen boneName
	float_16 matrix
}

struct material {
	word unk (mat number?)
	word charLen
	charLen materialName
	word charLen
	charLen diffuseName
	word charLen
	charLen textureName (may not exist)
	word charLen
	charLen normalTex Name (may not exist)
	unk bytes
}

#unk section
(variable amount, unknown cause)

#vertex section
word numVerts

numVerts vertex { 
	21 or 32 bytes
}

#face section
dword numIndices (numFaces = numIndices / 3)
numFaces face {
   word_3 indices
}

numFaces materialUsed { (no idea)
   word matIndex? (1-based)
}

#unk section

```

[prius Online.7z](https://xentaxbackup.github.io/file/4561_prius Online.7z)
## Post #11
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-01T15:16:09+00:00
- Post Title: PRIUS online model format

wow very interesting finally nice work mate maybe somebody can give you a hand in it like chrox
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-01T23:33:40+00:00
- Post Title: PRIUS online model format

I was working on this format i am trying to find the mesh scale I believe the first "bone"
is actually a scale matrix but i am not quite sure how to apply this.
