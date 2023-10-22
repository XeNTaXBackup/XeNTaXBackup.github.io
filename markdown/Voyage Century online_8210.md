## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-07T06:06:48+00:00
- Post Title: Voyage Century online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-07T06:35:37+00:00
- Post Title: Voyage Century online

All strings are null-terminated. I call it "string" type in the format.

EDIT: Found the number of faces per face group. It's stored with the material info. Or whatever the struct it. I guess you can call it "face group info". Just store it somewhere and then retrieve it when you're ready to parse the index buffers.

EDIT2: there goes another struct. Looks like there are matrices in unkStruct2.

EDIT3: vertices appear to be 36 bytes long. Or at least, one type anyways. And it's taking shape. Some of the faces are wrong though. I've added the script to my dropbox.



```
struct unkStruct1 {
   dword number
   52 bytes
}

struct unkStruct2 {
   108 bytes
}

struct materialInfo {
   dword[3]
   float[4]
   dword 
   dword numFaces
   dword[5]
   float[11]
   dword
}

struct Vertex {
   float[3] vx, vy, vz
   float[3] nx, ny, nz
   byte[4] ?
   float[2] tu, tv
}

##File Start##
   
char[4] idstring "50.1"
dword meshType (0, 2)
dword 
dword numStrings
dword count1
dword numMat
dword 
dword
dword count2
dword numFaceGroups
dword total indices
dword
float[3]

string[numStrings] bunch of strings related to material and textures..
dword[numStrings] ??
dword[count1] ??
numMat unkStruct1
count2 unkStruct2
numFaceGroups material_info

numFaceGroups {
   word[numIdx*2] indices **
}

dword vertType #0 == vertSize 36 bytes, 1 == 44 bytes
dword sectionSize #numVerts = sectionSize / vertSize
numVerts Vertex

#more

```
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-07T07:32:15+00:00
- Post Title: Voyage Century online

nice work finale, I added to my queue list, I have to much clients you posted for test so well, I think can test it soon as posible, thanks for support again.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-07T07:40:33+00:00
- Post Title: Voyage Century online

Found the vertType.

It is the integer right before the sectionSize for the vert section.

type 0 == 36 bytes, type 1 == 44 bytes.
Might be more. All weapons are loaded now though I am still running into the same problem with the faces (some are wrong)

No textures atm cause I don't know how the materials work.



EDIT: vertType 4 has 44 bytes as well, but the vertex struct is different.

```
float ?
dword ?
float[3] nx, ny, nz
byte[4] ?
float[2] tu, tv

```


EDIT: vertType 5 has 52 bytes.

```
float ?
dword ?
float[3] nx, ny, nz
byte[4] ?
float[2]
float[2]

```


And right after finding that, it looks like some faces are unwinded in a different order.
I don't know where the flag is but it's probably stored with the face info.
