## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-11-23T03:04:56+00:00
- Post Title: Fatal Fake + Crucis

Fate/stay night game.
characters stored in CDT format, stages in STG format.
Both are the same format except characters store bones/weights.
Textures are stored in the file as well (all DDS)

Update 2011-12-10: Crucis Fatal Fake available a couple posts down.
Update 2011-12-12: Noesis plugin (WIP) available for Crucis [here](http://forum.xentax.com/viewtopic.php?p=63444#p63444)
Update 2011-12-19: Crucis plugin now handle textures.

Unstable internet atm so no samples.
I've gotten the geometry with textures but don't know anything else.

The models aren't THAT great, but maybe someone might like them.



EDIT: just realized the unknown structs are wrong. I wrote this up and then started writing code but then didn't go back and update this after I worked it out.

```
Fatal Fake CDT - character models

struct Vertex {
	float_3 vx, vy, vz
	dword_3 ?
	float_3
	float_3
}

Struct Face {
	word_3 v1, v2, v3
}

struct unk1 {
	
	dword count
	dword_count ?
	word unk
	if unk1 == 0
		float
	else
		unk2
}

struct unk2 {
	byte_23
	dword numVerts
	
	numVerts {
		float_5
		byte (0 or 1)
	}
	
	dword count
	count {
		dword_2
		float_8
	}
	byte 0
	float ?
}

====

float_2 ??

word len
len name
dword numMesh
float ?

struct mesh? {
	word len
	len name
	dword ?
	dword numVerts
	byte ?
	numVerts Vertex
	dword ??
	dword numSections #face sections
	
	numSections FaceSection {
		dword numIndex / 3
		numIndex Face
		dword ?
		word len
		len sectionName
        }
	struct unk1
	
}

dword numTex
struct Texture {
	word len
	len TexName
	dword_2 texSize
	texSize texData
}

dword numMat

numMat Material {
	float_16
	dword ?
	word len
	len matName
	dword_5 ??
	dword_numTex
  numTex {
		word len
		len texName
	}
}

dword numBones
Bone struct {
...
}

```
## Post #2
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2011-11-23T07:13:33+00:00
- Post Title: Fatal Fake + Crucis

I have this game and i know this game have lots of fans, amazing release finale, thanks.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-10T15:01:10+00:00
- Post Title: Fatal Fake + Crucis

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-13T01:17:25+00:00
- Post Title: Fatal Fake + Crucis

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-18T04:52:06+00:00
- Post Title: Fatal Fake + Crucis

Noesis plugin for Fatal Fake CDT.
Archer seems to be stored in a different format though; maybe will look into it some time later.

Again, no bones or animations until I take some time to figure out how that works.

[Link](http://xtsukihime.webs.com/Noesis%20Plugins/fmt_FatalFake_cdt.py)

You will need the Sanae3D interface for this version, although I'm only using it for one function at the moment..............
## Post #6
- Username: zelda803
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 04, 2012 6:21 pm
- Post datetime: 2012-05-05T05:41:01+00:00
- Post Title: Fatal Fake + Crucis

I downloaded your python script put it in noesis python folder and when i try to load python i get following error

Traceback(most recent call last): File "C:\noesisv3872\fmt_crucisFatalFake_lmd.py", line 4, in <module> from Sanae3D.Sanae import SanaeObject ImportError:No module named Sanae3D.Sanae

Same error for "fmt_FatalFake_cdt.py" as well.

So far I was able to dump files from UI.la and chr.la using a program called dumplarc and have got .col/.ffso/.fsp/.glo/.lmd/.lmtp/.trc/.cpuo from chr.la and .dds files from UI.la . Problem is all of these files cannot be opened right now under noesis.

On a separate note is it possible to extract these models in different 3d modeling format that can be used in programs such as Maya?

Thanks in advance
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-05-05T09:33:02+00:00
- Post Title: Fatal Fake + Crucis

Updated script to be stand-alone.
Just export using noesis.
## Post #8
- Username: BlenderAnimator
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 22, 2022 5:29 am
- Post datetime: 2023-01-29T09:40:03+00:00
- Post Title: Fatal Fake + Crucis

How did you even get the CDT files?
