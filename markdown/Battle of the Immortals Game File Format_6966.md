## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-13T00:54:50+00:00
- Post Title: Battle of the Immortals Game File Format

Battle of the Immortals its the 1st game i see of the New Mmorpg dont have the textures encrypted, i think the skel, animation and mesh are stored in the *.M4F files also each model have a cfg file, good luck to everyone.



File Formats:

Textures: *.DDS
Mesh, Skel and Ani: *M4F (maybe packed on this file)

Download to Test
[http://www.megaupload.com/?d=FSYKO15P](http://www.megaupload.com/?d=FSYKO15P)
## Post #2
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-15T07:31:23+00:00
- Post Title: Battle of the Immortals Game File Format

> Reply from Rimbros
>
> Battle of the Immortals its the 1st game i see of the New Mmorpg dont have the textures encrypted, i think the skel, animation and mesh are stored in the *.M4F files also each model have a cfg file, good luck to everyone.



File Formats:

Textures: *.DDS
Mesh, Skel and Ani: *M4F (maybe packed on this file)

Download to Test
http://www.megaupload.com/?d=FSYKO15Pa friend working in it, him have 85% program done, very soon are up
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-15T16:52:37+00:00
- Post Title: Battle of the Immortals Game File Format

Will he release the source? Or file format?
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-15T19:23:40+00:00
- Post Title: Battle of the Immortals Game File Format

> Reply from finale00
>
> Will he release the source? Or file format?not source, only packer and unpacker tool.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-15T19:29:25+00:00
- Post Title: Battle of the Immortals Game File Format

Oh I see. That will be useful also.
## Post #6
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-07-24T06:57:52+00:00
- Post Title: Battle of the Immortals Game File Format

> Reply from CriticalError
>
> a friend working in it, him have 85% program done, very soon are up
No news?
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-24T08:05:07+00:00
- Post Title: Battle of the Immortals Game File Format

Oh yeah, those M4F files look very parsable. Vertices and indices are clearly visible. Models look nice too. If they don't finish it I'll probably work one too as I finish up alibat.
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-24T17:02:25+00:00
- Post Title: Battle of the Immortals Game File Format

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-07-26T22:20:10+00:00
- Post Title: Battle of the Immortals Game File Format

Good job finale, i never see this format before *..m4f
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-19T12:29:31+00:00
- Post Title: Battle of the Immortals Game File Format

nobody found a way to import m4f files into max,blender? I get unpacker and anyway is the same, sqp unpacker/packerget same files like En Client :S.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T13:24:42+00:00
- Post Title: Battle of the Immortals Game File Format

Guess I'll look at it now lol I've been busy trying to improve my program to support modding plugins as well as conversion plugins.

The header has an offset table with what appears to be counts of whatever section it is.

There are 14 dwords, which is basically 7 sections (a count and an offset for each).

The first pair of dwords are the numTex and the texOffset. Each texture name is 292 bytes long, and contains unicode characters (most likely chinese, GB2312 or something like that)

The third pair of dwords are the numMesh and meshOffset. Each mesh is defined sequentially, starting with the name, followed by a lot of dwords. The name is 80 bytes long, followed by FF FF FF FF, followed by 17 dwords, followed by 72 bytes of 00's. We can probably just say that's 18 dwords.

A quick search for vertex offsets leads me to believe that those 17 dwords are also counts and offsets, amongst other things.
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-19T13:36:48+00:00
- Post Title: Battle of the Immortals Game File Format

> Reply from finale00
>
> Guess I'll look at it now lol I've been busy trying to improve my program to support modding plugins as well as conversion plugins.

The header has an offset table with what appears to be counts of whatever section it is.

There are 14 dwords, which is basically 7 sections (a count and an offset for each).

The first pair of dwords are the numTex and the texOffset. Each texture name is 292 bytes long, and contains unicode characters (most likely chinese, GB2312 or something like that)

The third pair of dwords are the numMesh and meshOffset. Each mesh is defined sequentially, starting with the name, followed by a lot of dwords. The name is 80 bytes long, followed by FF FF FF FF, followed by 17 dwords, followed by 72 bytes of 00's. We can probably just say that's 18 dwords.

A quick search for vertex offsets leads me to believe that those 17 dwords are also counts and offsets, amongst other things.good interesting view, the truth is appreciated and sorry, there is not an easy job but you are one of the more experience here in the forum and ask why good simply because the game has very good models, good will wait for new news take care.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T13:46:26+00:00
- Post Title: Battle of the Immortals Game File Format

mesh stores vertCount, faceCount, normCount, uvCount, along with their offsets. Some other counts I am not sure of.

Looks like

```
   char_80 name
   dword unk
   dword matNum
   dword_4 ???
   dword_2 vertCount, vertOffset
   dword_2 faceCount, faceOffset
   dword_2 normCount, normOffset
   dword_2 weightCount, weightOffset
   dword_2 uvCount, uvOffset
   dword_2 boneIndexCount, boneIndexOffset
   byte_72 padding
}

struct Vertex {
   float_3 coords
}

struct Face {
   word_3 indices
}

struct Normal {
   float_3 normals
}

struct UV {
   float_3 uv
}

struct weights {
   float_3 weights
}

struct boneIndex {
   byte index
}

```

[undead.JPG](https://xentaxbackup.github.io/file/4642_undead.JPG)
## Post #14
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-19T13:51:25+00:00
- Post Title: Battle of the Immortals Game File Format

> Reply from finale00
>
> mesh stores vertCount, faceCount, normCount, uvCount, along with their offsets. Some other counts I am not sure of.

Looks like
Code: Select allstruct Mesh {
   char_80 name
   dword_6 unk
   dword_2 vertCount, vertOffset
   dword_2 faceCount, faceOffset
   dword_2 normCount, normOffset
   dword_2 unk
   dword_2 unk
   dword_2 unk
   byte_72 padding
}


Didn't figure out the material section so I don't know which is the UV. There are then two additional counts/offsets that I am not sure of.wow you rock man, gratz for new job still waiting  i'm not pro for make it alone so thats the problem  anyway thanks again for your support.
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T14:04:21+00:00
- Post Title: Battle of the Immortals Game File Format

The boneCount and offset is the fourth pair of dwords in the header.

```

dword idstring "C9 8D 32 01"
dword numTex
dword texOffset
dword num
dword offset
dword numMesh
dword meshOffset
dword numBone
dword boneOffset
dword num2
dword offset2
dword_4 null
dword num3
dword offset3

```


num3 is sometimes 0. Don't know.

```
	char_80 name
	...
}

```


Multiple meshes may have the same name. These need to be dealt with appropriately. They might be assigning materials per mesh rather than per face.
[haw.JPG](https://xentaxbackup.github.io/file/4643_haw.JPG)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T14:54:07+00:00
- Post Title: Re: Battle of the Immortals Game File Format

The section after the textures is unknown, but looks like this. It is the second pair of dwords in the offset table.

```
	dword_8 ??
	dword_2 count, offset
	dword_8 null
	
	*seek to offset*
	count unk {
		byte_64 ???
	}
}

```
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-20T02:19:28+00:00
- Post Title: Re: Battle of the Immortals Game File Format

The second dword in the mesh struct is the material index.
The last pair of dwords in the mesh struct references bone indices.
[boi_heilong.jpg](https://xentaxbackup.github.io/file/4645_boi_heilong.jpg)
## Post #18
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-08-20T02:21:47+00:00
- Post Title: Re: Battle of the Immortals Game File Format

> Reply from finale00
>
> The second dword in the mesh struct is the material index.
The last pair of dwords in the mesh struct references bone indices.lol you crazy!!!! I love you god u.u perfect model and texture gratz again for news you rock.
## Post #19
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-20T02:29:27+00:00
- Post Title: Re: Battle of the Immortals Game File Format

Looks like there's only one more unknown left in the mesh, so I guess that would be the weights. I mean, can't really be anything else.

The number of bone indices == number of vertices. I'm not sure what that means. Each vertex has 3 weights (numVerts * 3 floats). Ok I really don't understand bones to figure out that part.
## Post #20
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-23T14:52:57+00:00
- Post Title: Re: Battle of the Immortals Game File Format

And could you please make a script or Noesis plugin for viewing/converting models from Battles Of Immortals?
## Post #21
- Username: KillMeOnceMore
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 18, 2018 10:03 pm
- Post datetime: 2018-11-18T14:09:21+00:00
- Post Title: Re: Battle of the Immortals Game File Format

I know this is a old thread, but recently I found a set of source code that was origin from where battle of immortal was made.
The model tool(mdxstudio.exe) is for mdx2 but extremely similar to pwm3/m4f format. (Find it under client folder for compiled ver)
I am hoping someone can figure out a model tool for pwm3/m4f. 

Uses vs2005. For dxd8.h error, use vc++ dir to link DX9SDK for include & lib.
[https://mega.nz/#F!lGo03C6a!u97BE1huki64rbB1c6lBiw](https://mega.nz/#F!lGo03C6a!u97BE1huki64rbB1c6lBiw)

Wish you guys all the best and goodluck!
## Post #22
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-18T15:48:27+00:00
- Post Title: Re: Battle of the Immortals Game File Format

> Reply from KillMeOnceMore
>
> I know this is a old thread, but recently I found a set of source code that was origin from where battle of immortal was made.Hello, rider-of-dead-horses  
You won't expect someone to download 844 MB just to get a VS project, do you?

The format is simple, though, so we don't need that project that much, imho:



chunjie_female-M4F.png (178.26 KiB) Viewed 76 times


H2O files, body and face:

0xD5CC 900
Vb1
12 99
0xCA98 239
020000
0xF33C 8

0x1021B 690
Vb1
12 99
0xFBA3 138
020000
0x1146F 8
