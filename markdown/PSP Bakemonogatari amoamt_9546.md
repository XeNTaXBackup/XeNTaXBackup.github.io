## Post #1
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-08-25T12:58:31+00:00
- Post Title: PSP Bakemonogatari amo/amt

Hi, guys
I would be able to browse models, but most do not have such knowledge.

.amt (textures)
.amo (meshes)
I will send you PM with sample.
Any help would be greatly appreciated. 

Thanks,
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-25T17:24:19+00:00
- Post Title: PSP Bakemonogatari amo/amt

Samples plz.

I don't care if senjougahara looks toon-ish.
## Post #3
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2012-08-25T18:21:23+00:00
- Post Title: PSP Bakemonogatari amo/amt

hi alon, how can u extract cpk files
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-25T18:41:56+00:00
- Post Title: PSP Bakemonogatari amo/amt

There are several ID's in there, starting with that #AMO. The O probably stands for "object". It then holds offsets to "#AMG" tags, which probably stands for "group"

There are no indices, so they could be implicit triangles (if that's what they're called I don't know the terminology)

Here's a BMS script to separate the AMG chunks out to make it easier to compare.

```

idstring "#AMO"
goto 24
get MESHES long
goto 48
for i = 0 < MESHES
  get offset1 long
  get offset2 long
  
  math size = offset2
  math size -= offset1
  
  string NAME p= "mesh%03d.amg" i
  log NAME OFFSET1 SIZE
next i

```


Here is the format of the AMO
Padding refers to 16-byte alignment

I don't know how the vertices are stored. I tried a couple random offsets when binding the positions but didn't come up with anything useful. These are obviously characters based on the names all over the file.

Here is a vertex dump if anyone can see any patterns. They are stored as 32 byte structs, so presumably 8 floats. 

[http://pastebin.com/ZazisQ80](http://pastebin.com/ZazisQ80)

And the plugin I am writing: [https://www.dropbox.com/sh/7stlpd4qvkq3 ... PSP_amo.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/IMiohhuFWI/fmt_BakemonogatariPSP_amo.py)

```
char[4] "#AMO"
int
int
int
int numBones?
int
int numMesh
int
int
int bone Offset?
byte[?] padding

#mesh offsets
int[numMesh] meshOfs

# bone related
???

# ok whatever just skip to meshes
numMesh Mesh

# then the bone offset from before
char[32] boneNames

struct Mesh {
   idstring "#AMG"
   int
   int
   int
   int numBones?
   int
   int
   int boneOfs? (relative to start of current chunk)

   numBones {
      80 bytes # ???
   } 

   int
   int
   int
   int
   int
   int unkOfs (past the vertex buffers)
   byte[] padding

   byte[32] some struct
   byte[48] just skipping
   int
   int
   short
   int numGroups (number of vertex groups)
   short

   numGroups VertexGroup

   # some more stuff after
}

struct VertexGroup {
   int
   int
   int
   short numVerts
   short ?

   numVerts Vertex {
      float[8] ?
   }
}

```
## Post #5
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-08-26T09:20:16+00:00
- Post Title: PSP Bakemonogatari amo/amt

> Reply from epopoe
>
> hi alon, how can u extract cpk files
You'll need quickbms plus the cpk.bms script in here.
[viewtopic.php?p=46509#p46509](http://forum.xentax.com/viewtopic.php?p=46509#p46509)
## Post #6
- Username: alon
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Mon Nov 29, 2010 5:38 pm
- Post datetime: 2012-08-26T14:01:43+00:00
- Post Title: PSP Bakemonogatari amo/amt

> Reply from finale00
>
> Code: Select all# Header
char[4] "#AMO"
int
int
int
int numBones?
int
int numMesh
int
int
int bone Offset?
byte[?] padding

#mesh offsets
int[numMesh] meshOfs

# bone related
???

# ok whatever just skip to meshes
numMesh Mesh

# then the bone offset from before
char[32] boneNames

struct Mesh {
   idstring "#AMG"
   int
   int
   int
   int numBones?
   int
   int
   int boneOfs? (relative to start of current chunk)

   numBones {
      80 bytes # ???
   } 

   int
   int
   int
   int
   int
   int unkOfs (past the vertex buffers)
   byte[] padding

   byte[32] some struct
   byte[48] just skipping
   int
   int
   short
   int numGroups (number of vertex groups)
   short

   numGroups VertexGroup

   # some more stuff after
}

struct VertexGroup {
   int
   int
   int
   short numVerts
   short ?

   numVerts Vertex {
      float[8] ?
   }
}

I have a questions.	
How can I know the results of the AMO?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-26T20:51:24+00:00
- Post Title: PSP Bakemonogatari amo/amt

My noesis plugin has function that writes out the contents of the file.
Well, almost. I only use it to write out things like vertex data and index data to make sure it makes sense.
## Post #8
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-26T23:24:20+00:00
- Post Title: PSP Bakemonogatari amo/amt

Seems, like that same type of files used in Dragon Ball Z Budokai 3,
but would need samples to confirm this.
IGNORE THESE SCRIPTS, the format is too different from Dragon Ball, to be used with theses scripts.
Here is a quick script, that will convert the AMG files, into .3ds files, but let me know if you get anything out of this, as I will modify the script, so that it, makes the .3ds files, to fit, instead of just using the template blank.3ds:
[http://ps23dformat.wikispaces.com/file/ ... /blank.3ds](http://ps23dformat.wikispaces.com/file/view/blank.3ds/357312188/blank.3ds)
First script will convert AMG files into subAMG files it is a quickBMS script:

```
ImpType Standard ;
Set F Long 04 ;
GoTo F 0 ;
Get S Long 0 ;
GoTo S 0 ;
SavePos S 0 ;
Set F Long 16 ;
GoTo F 0 ;
Get N Long 0 ;
Math N *= 80 ;
Math N += S ;
GoTo N 0 ;
SavePos S 0 ;
Math S += 16 ;
GoTo S 0 ;
SavePos S 0 ;
SavePos V 0 ;
Get qNumber Long 0 ;
Get qOffset Long 0 ;
Math qNumber -= 1 ;
Math S += qOffset ;
GoTo S 0 ;
SavePos S 0 ;
For T = 1 To qNumber ;
Get FO Long 0 ;
SavePos K 0 ;
Get CS Long 0 ;
Math CS -= FO ;
Set NUM long T ;
GoTo FO 0 ;
string QQ = SubAMG. ;
string QQ += NUM ;
Math FO += V ;
Log QQ FO CS 0 ;
GoTo K 0 ;
Next T ;
Set TT long qNumber ;
Math TT += 1 ;
Math qNumber *= 4 ;
Math qNumber += S ;
GoTo qNumber 0 ;
Get Start Long 0 ;
Math Start += V ;
Set L Long 28 ;
GoTo L 0 ;
Get L Long 0 ;
Math L -= Start
string VV = SubAMG. ;
string VV += TT ;
Log VV Start L 0 ;
</bms>
```


Next script will convert subamg files, into .3ds file, put the blank.3ds file in the same folder, and run the quick BMS script with the commandline paramater -w 
(needs to be a lowercase w)
then when asked for the other file type in blank.3ds:

```
open FDDE ? 1
GoTo 110 1 ;
For LS = 0 < 27768 ;
Put GG Long 1 ;
Put GG Long 1 ;
Put GG Long 1 ;
Next LS ;
Set TotalVertexCount long 1 ;
Get Z ASIZE 0 ;
GoTo 0 0 ;
Get Type Long 0 ;
If Type == 437 ;
set VertexType long 48 ;
Elif Type == 436 ;
set VertexType long 32 ;
Elif Type == 400 ;
set VertexType long 16 ;
Endif ;
GoTo 160 0 ;
SavePos Q 0 ;
set T long 0 ;
For T = 0 < Z ;
GoTo Q 0 ;
Math Q += 12 ;
GoTo Q 0 ;
Get H Long 0 ;
If H == 0 ;
CleanExit ;
EndIf
Math Q += 8 ;
GoTo Q 0 ;
Get SectionVertexes Long 0 ;
Math Q += 12 ;
GoTo Q 0 ;
SavePos VertexStart 0 ;
Math B = VertexType ;
Math B *= SectionVertexes ;
Math Y = SectionVertexes ;
Math Fox = VertexStart ;
Math AdjVertexTypeJump = VertexType ;
Math AdjVertexTypeJump -= 12 ;
For Deer = 1 < Y ;
GoTo Fox 0 ;
Get XVertex Long 0 ;
Get YVertex Long 0 ;
Get ZVertex Long 0 ;
GoTo AdjVertexTypeJump 0 SEEK_CUR ;
SavePos Fox 0 ;
Math PolarBear = TotalVertexCount ;
Math PolarBear *= 12 ;
Math Bear = Deer ;
Math Bear *= 12 ;
Math Bear += PolarBear ;
Math Bear += 110 ;
GoTO Bear 1 ;
Put XVertex Long 1 ;
Put YVertex Long 1 ;
Put ZVertex Long 1 ;
Next Deer ;
Math T = 0 ;
Math T += B ;
Math T += VertexStart ;
Math Q = T ;
Math TotalVertexCount += SectionVertexes ;
Next T ;
</bms>
```


And here is my version of AMO to AMG, just incase it does not work with the other posters AMG:

```
ImpType Standard ;
Set F Long 04 ;
GoTo F 0 ;
Get S Long 0 ;
GoTo S 0 ;
SavePos S 0 ;
GoTo S 0 ;
SavePos Z 0 ;
Set F Long 24 ;
GoTo F 0 ;
Get N Long 0 ;
Math N -= 1 ;
GoTo S 0 ;
For T = 1 To N ;
Get FO Long 0 ;
SavePos K 0 ;
Get CS Long 0 ;
Math CS -= FO ;
Set NUM long T ;
GoTo FO 0 ;
Set QH Long 01 ;
Math QH += FO ;
GoTo QH 0 ;
GetDString QQ 3 0 ;
string QQ += . ;
string QQ += NUM ;
Log QQ FO CS 0 ;
GoTo K 0 ;
Next T ;
Set TT long N ;
Math TT += 1 ;
Math N *= 4 ;
Math N += Z ;
GoTo N 0 ;
Get N Long 0 
Set J Long 36 ;
GoTo J 0 ;
Get J Long 0 ;
Math J -= N
GoTo N 0 ;
Set QH Long 01 ;
Math QH += N ;
GoTo QH 0 ;
GetDString QQ 3 0 ;
string QQ += . ;
string QQ += TT ;
Log QQ N J 0 ;
</bms>
```


Let me have sample files, and let me know if you want a much better quickbms script, that will convert the UV cords as well, as generate a "perfect" .3ds file of the name of your choosing.
The AMG types are probably different then the ones from dragon ball, but one type has Vertexes/UV/Normals, one type has Vertexes/UV, and one type just has Vertexes.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-26T23:47:00+00:00
- Post Title: PSP Bakemonogatari amo/amt

Furry: is there an article on ps23d that explains how the vertices are "typically" stored and how the faces are done?

LOL I think I've asked this before but I don't remember where to go back and look at what you might have written.
## Post #10
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-27T11:35:18+00:00
- Post Title: PSP Bakemonogatari amo/amt

> Reply from finale00
>
> Furry: is there an article on ps23d that explains how the vertices are "typically" stored and how the faces are done?

LOL I think I've asked this before but I don't remember where to go back and look at what you might have written.
In dragon ball this could be a vertex header:
00 00 00 17 00 00 00 00 00 00 00 00 00 C0 49 6C 
00 00 00 00 18 00 00 00 00 00 00 00 00 00 00 00

The 17/14 means to stop the last section.
The 49, means the next section is 49, lines of 16bytes long.
The 18 means there are 0x18 vertexes in the next section.
It is a tristrip, meaning you connect the first vertex, to the second, to the third. Then the second, to the third, to the fourth, ect, up until, the 0x16 to the 0x17, to the 0x18.
In dragonball a type of section could be:
1E 79 B7 3E 96 F7 04 40 19 67 BD 3F 00 00 80 3F -Vertex1
C2 93 04 3F B9 36 27 BF D3 6A 0D 3F 00 00 80 3F-Normal 1
00 00 71 3F 00 00 FE 3E 00 00 80 3F 00 00 00 00-UV 1
DA C1 E1 3B FA 45 04 40 20 5E C4 3F 00 00 80 3F -Vertex 2
85 40 7D BD 5A 50 7E BF 77 92 C5 BD 00 00 80 3F-Normal 2
00 00 5D 3F 00 00 EE 3E 00 00 80 3F 00 00 00 00 UV2
40 2E C7 BE 37 C9 05 40 AA 19 BD 3F 00 00 80 3F-Vertex 3
2A 12 09 BF B6 6E 25 BF F8 35 0B 3F 00 00 80 3F-Normal 3
00 00 47 3F 00 00 FE 3E 00 00 80 3F 00 00 00 00-UV 3
ect....
So you would connect Vertex 1, to Vertex2, to Vertex 3
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-27T16:32:16+00:00
- Post Title: PSP Bakemonogatari amo/amt

ah right, ya I think I remember you said that before.
Did you get anything? The positions looked kind of weird so I didn't really try to add faces.
## Post #12
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-08-27T20:56:48+00:00
- Post Title: PSP Bakemonogatari amo/amt

> Reply from finale00
>
> ah right, ya I think I remember you said that before.
Did you get anything? The positions looked kind of weird so I didn't really try to add faces.
After this:
struct VertexGroup {
   int
   int
   int
   short numVerts
   short ?
The format is 4ByteUVCords(U,V), 4ByteNormals(X,Y,Z), 4ByteVertexes(X,Y,Z)

for example: 
UVCOORDS GREEN
NORMALS RED
VERTEXES BLUE
First Vertex
6C 14 23 3F FC 17 8B 3E 
00 00 00 00 35 2F 86 BE 49 0D 77 3F 
50 59 86 3E D0 90 37 3F 12 DB 2B 3F 
Second Vertex
B8 93 1D 3F 64 89 92 3E 
00 00 00 00 2A 52 71 BE 24 CA 78 3F 
03 5C 7A 3E F8 85 34 3F 84 48 2A 3F

You connect the first vertex to the second vertex, to the third, that is a face.
Then connect the second vertex, to the third vertex, to the fourth vertex, that is another face
.....
Then connect the third last vertex in the group, to the second last vertex in the group, to the last vertex in the group,
that is the last face for that vertex group.

But to render in one-sided programs such as computers, the face list needs to be made so that everyother face is flipped over.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-27T21:06:01+00:00
- Post Title: PSP Bakemonogatari amo/amt

Thanks I will try it out   
For faces, I think it is ok to just leave turn off face-culling, although it is not a real solution I guess....
## Post #14
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2012-12-22T06:12:55+00:00
- Post Title: PSP Bakemonogatari amo/amt

How do you get the amo/amt?
## Post #15
- Username: LuchiaL
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jun 30, 2012 3:35 pm
- Post datetime: 2012-12-23T12:40:12+00:00
- Post Title: PSP Bakemonogatari amo/amt

extract the cpk with quickbms

i got null files,but when i check it with hxd they are amo/amt files
## Post #16
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2012-12-24T04:11:30+00:00
- Post Title: Re: PSP Bakemonogatari amo/amt

hxd?
## Post #17
- Username: LuchiaL
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jun 30, 2012 3:35 pm
- Post datetime: 2012-12-24T05:09:36+00:00
- Post Title: Re: PSP Bakemonogatari amo/amt

hex editor.
## Post #18
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2013-11-16T05:15:14+00:00
- Post Title: Re: PSP Bakemonogatari amo/amt

> Reply from LuchiaL
>
> extract the cpk with quickbms

i got null files,but when i check it with hxd they are amo/amt files

There are 3 cpk files in total:
\INSDIR\rom.cpk
\USRDIR\rom\rom.cpk
\USRDIR\rom\exrom.cpk
Did you only go with \USRDIR\rom\rom.cpk? What's about the other 2 cpk files? I still don't know how to unpack them.

Btw, I got a bunch of _NULL_/_NULL_ too. Did they rename automatically while unpacking the cpk or what?
## Post #19
- Username: loriscangini
- Rank: advanced
- Number of posts: 53
- Joined date: Sun Jan 09, 2011 10:45 pm
- Post datetime: 2014-07-28T09:56:38+00:00
- Post Title: Re: PSP Bakemonogatari amo/amt

I have a problem!
I have extracted the .cpk using quickbms, but I obtained a lot of _NULL_ files, now I don't know what to do!

I tried to open them with HxD and rename some of them to .amo, but when I open them with Noesis I obtain only random little white boxes (I think that they are vertex)!

Is there someone who can help me?
Thanks!
