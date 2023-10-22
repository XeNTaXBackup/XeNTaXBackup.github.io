## Post #1
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-08-23T15:05:36+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

hello all
how to import models from kao the kangaroo?
please
i tried find vertex information but don't know where they are
link to a demo:
[http://download.exdat.com/file/kao_demo ... 12933.html](http://download.exdat.com/file/kao_demo.zip/index-12933.html)
you need to click download and enter the code
and script for quickbms to pak file

```
math pEOCDR -= 12
goto pEOCDR

get CDR_NUM long
get CDR_PTR long
idstring "T8FM"   ## assumed magic

goto CDR_PTR

for i = 1 to CDR_NUM

  getdstring R_NAME 80
  get R_POS long
  get R_SIZE long

  log R_NAME R_POS R_SIZE

next i
```
## Post #2
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-03T10:48:03+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

this let me although someone will write where they are vertices
script alone write
please
## Post #3
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2012-09-06T23:12:57+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

> Reply from Bogus
>
> this let me although someone will write where they are vertices
script alone write
please

The format is a little strange for the vertexes, what I think is the case is that there is a face index, interspersed with other information at the beginning of the file, followed by the vertexes BUT the vertexes use some types of frames (for animations), so it might be something like every say 40th vertex is a real vertex. Something like that. Like me look more into this. But thank you for the extraction script, which is helping alot.
## Post #4
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2012-09-07T05:56:43+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

this not well
## Post #5
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2014-01-10T12:52:49+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

to facilitate I give here link to this models
[http://www.sendspace.com/file/bfbbxf](http://www.sendspace.com/file/bfbbxf)
## Post #6
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2014-01-17T13:34:50+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

if anyone me help?
please
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-01-18T09:35:23+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

why don't you use your own creative power?
try

```
   for i in xrange(numVerts):      
      verts.append(struct.unpack('fff', file.read(3*4)))
      file.read(4)
      file.read(64)
```
on angel output.bin - it's not the solution but it's a progress.

Also then why don't you upload your python script? (it's yours, isn't it?)
## Post #8
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2018-07-02T17:54:36+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

ok here is result
I had to print output to a file because not was can be seen was cut

744 vertices at 0x5644L
## Post #9
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2018-07-02T17:56:48+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

edit:
New link to kao.pak file from demo version.

[https://www.sendspace.com/file/4f9kvq](https://www.sendspace.com/file/4f9kvq)

Script for quickbms in first post.

I write a script for noesis, only I do not know how to skip unknown values with a faces at the beginning of the file, with vertices are null bytes.

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("Kao the Kangaroo", ".bin")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    bs = NoeBitStream(data)
    Header = bs.readBytes(4)
    if Header != b'T83d':
        return 0
    return 1

def noepyLoadModel(data, mdlList):
    noesis.logPopup()
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    bs.seek(0x0C, NOESEEK_ABS)
    nummeshes = bs.readInt()
    print("number of meshes", nummeshes)
    numfaces = bs.readInt()
    print("number of faces", numfaces)
    numanims = bs.readInt()
    print("number of animations", numanims)
    bs.seek(0x4C, NOESEEK_ABS)

    for i in range (0, nummeshes):
        numverts = bs.readInt()
        print("number of vertices", numverts)
        unknown = bs.readInt()
        meshname= (bs.readBytes(32).decode("ASCII").rstrip("\0"))
        print(meshname)
        unknown2 = bs.readInt()

    rapi.rpgClearBufferBinds()
    return 1
```
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-02T22:10:03+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

well, Bogus, you don't give up, I really like that.  

For your Noesis script, dunno whether the vertex counts you get in the for loop are correct (often it's 3 only).
In general I'd say it doesn't make much sense to care for meshes here as long as you don't have the correct counts.

From the output.bin it seem they have different FVF sizes (angel, FVF size=80, iirc).
For the eskimo and the snowman it seems to be 16. As soon as you found the correct FVF size you can identify the vertex block length and divide it by the FVF size to get the vertex count (for that block).

The problem is the FIs (face indices). It's triangle strips (with bytes to skip) but dunno whether I got them correctly.

edit: well, seems I confused myself with tristrips, because the culling showed a decent mesh. Of course, it's standard triangles  , and the snowman looks much better then.

The "Eskimo" looks rather weird. For the snowman it seems I'm on the right track (toggled face culling in Noesis).



eskimo-snowman.outout-bin.jpg (136.75 KiB) Viewed 190 times



btw: no, you can't get this with hex2obj directly, I had to manipulate the FIs block in the output.bin files
## Post #11
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2018-07-02T23:14:43+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

What is FVF?
This look wrong, you can use kao_tools.exe made by Flower35 Radek krzyskow.
[http://www.mediafire.com/file/cimodczub ... _tools.exe](http://www.mediafire.com/file/cimodczub8xwyuk/KAO_tools.exe)
or denis editor, also made by Flower35
[http://www.mediafire.com/file/834zhti26 ... Wizard.zip](http://www.mediafire.com/file/834zhti265yi220/denis_Wizard.zip)
With this tools models looks better.
How to implement for loop for vertices?
I have skip null bytes with NOESEEK_REL?
What values are between faces, vertex normals probably no?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-03T06:28:22+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

> Reply from Bogus
>
> What is FVF?flexible vertex format

> This look wrong,nope, the eskimo is just uncomplete, the snowman is ok, more or less  

> With this tools models looks better.yeah, and Flower35 has spend much time on creating them.
My approach was just a, well, not 15 min, but 90 min job.

> How to implement for loop for vertices?to be displayed as a mesh? This is simple, Noesis uses a buffer for such. There's a myriad of py samples where you can see how to do it.

> I have skip null bytes with NOESEEK_REL?yep

> What values are between faces, vertex normals probably no?dunno. You don't need them (skip)
## Post #13
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2018-07-03T15:05:04+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

I not have idea how should look script.
Faces are between unknown values, if the faces were next to each other, would be easier.
## Post #14
- Username: Flower35
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 09, 2014 2:34 am
- Post datetime: 2018-07-05T10:03:52+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

Hi there! 

"denis Wizard" can display any "Kao the Kangaroo" model with complete list of keyframes. This game uses vertices group animations.

I still haven't completed model or worldmap documentation, but I could post some C++ syntax functions for reading data from files.

If you want to talk more, please visit Kao's Discord server:
[https://discord.gg/B33jjUu](https://discord.gg/B33jjUu)

Currently I am working on displaying skeletal animations from "Kao the Kangroo: Round 2".

Best regards!
[462006205628547072.jpg](https://xentaxbackup.github.io/file/14548_462006205628547072.jpg)
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-07-05T16:33:57+00:00
- Post Title: [request] kao the kangaroo .bin .msh files

> Reply from Bogus
>
> I not have idea how should look script.
Faces are between unknown values, if the faces were next to each other, would be easier.I really don't like python, but here you go (script is for the Kao snowman, and ONLY the snowman):

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("Kao-snowman", ".bin")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    bs = NoeBitStream(data)
    idstring = bs.readUInt()
    if idstring != 0x64333854:
        print("not a Kao file!")
        return 0
    return 1

def noepyLoadModel(data, mdlList):    
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    #rapi.rpgClearBufferBinds()
    bs.seek(0xD0, NOESEEK_ABS)
    size = 0x1970 - 0xD0
    idxbuf_tmp = bs.readBytes(size)

    numFaces = size // 16
    print("numFaces", numFaces)
    idxBuf = []
    for i in range(numFaces):
        idx = idxbuf_tmp[i*16] + idxbuf_tmp[i*16 + 1]*256
        idxBuf.append(idx)
        idx = idxbuf_tmp[i*16 + 4] + idxbuf_tmp[i*16 + 5]*256
        idxBuf.append(idx)
        idx = idxbuf_tmp[i*16+ 8] + idxbuf_tmp[i*16 + 9]*256
        idxBuf.append(idx)

    #print(idxBuf)

    bs.seek(0x1970, NOESEEK_ABS)
    vertsCount = 170
    VertBuf = bs.readBytes(vertsCount * 64)
    b = struct.pack('H' * len(idxBuf), *idxBuf)

    rapi.rpgBindPositionBufferOfs(VertBuf, noesis.RPGEODATA_FLOAT, 16, 0)
    rapi.rpgCommitTriangles(b, noesis.RPGEODATA_USHORT, numFaces*3, noesis.RPGEO_TRIANGLE, 1)

    mdl = rapi.rpgConstructModel()
    mdlList.append(mdl)

    return 1
```
It should give you the idea for other meshes. (You might improve it to automatically read the vertexCount.)
As you can see the snowman looks a little bit weird. It's up to you to improve this, I'm off for now.



Kao-snowman.jpg (22.98 KiB) Viewed 148 times
## Post #16
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2018-07-05T17:20:41+00:00
- Post Title: Re: [request] kao the kangaroo .bin .msh files

Good job, thank you shakotay2, at least this gives me a hint.
## Post #17
- Username: Flower35
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Sep 09, 2014 2:34 am
- Post datetime: 2018-07-05T20:52:14+00:00
- Post Title: Re: [request] kao the kangaroo .bin .msh files

Here is a quick documentation for Kao1 animmesh files:
[https://drive.google.com/file/d/1g0gnnV ... sp=sharing](https://drive.google.com/file/d/1g0gnnVEoytfd3wPh1dZGZ6geV5HMrOqI/view?usp=sharing)
## Post #18
- Username: Bogus
- Rank: advanced
- Number of posts: 75
- Joined date: Sat Oct 30, 2010 6:57 pm
- Post datetime: 2018-08-12T18:25:03+00:00
- Post Title: Re: [request] kao the kangaroo .bin .msh files

Small progress, vertices can be read, but problem is with faces, with 1 object and 1 vertex group works but with more than 1 vertex group is error and i not know, how to implement dummy object.
Only vertices works.

```
Noesis Python Error
---------------------------
Traceback (most recent call last):
  File "D:\bogus pliki\noesis\plugins\python\fmt_Kao_the_Kangaroo.py", line 54, in noepyLoadModel
    rapi.rpgCommitTriangles(FaceBuff, noesis.RPGEODATA_USHORT, numfaces, noesis.RPGEO_TRIANGLE, 1)
RuntimeError: Number of indices must be evenly divisible by 3 with RPGEO_TRIANGLE

---------------------------
OK   
---------------------------

```

Here is current noesis script

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("Kao the Kangaroo", ".bin")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    return 1

def noepyCheckType(data):
    bs = NoeBitStream(data)
    Header = bs.readBytes(4)
    if Header != b'T83d':
        return 0
    return 1

def noepyLoadModel(data, mdlList):
    noesis.logPopup()
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    bs.seek(0x0C, NOESEEK_ABS)
    nummeshes = bs.readInt()
    print("number of meshes", nummeshes)
    numfaces = bs.readInt()
    print("number of faces", numfaces)
    numanims = bs.readInt()
    print("number of animations", numanims)
    bs.seek(0x4C, NOESEEK_ABS)

    for i in range(nummeshes):
        numverts = bs.readInt()
        print("number of vertices", numverts)
        numvertgroups = bs.readInt()
        print("number of vertex groups", numvertgroups)
        meshname= (bs.readBytes(32).decode("ASCII").rstrip("\0"))
        print(meshname)
        unknown = bs.readInt()

    for i in range(nummeshes):
        faces = []
        size = bs.readBytes(16*numfaces)
        for j in range(numfaces):
            idx = size[j*16] + size[j*16 + 1]*256
            faces.append(idx)
            idx = size[j*16 + 4] + size[j*16 + 5]*256
            faces.append(idx)
            idx = size[j*16+ 8] + size[j*16 + 9]*256
            faces.append(idx)
        print(faces)
        FaceBuff = struct.pack('H' * len(faces), *faces)
        for j in range(numvertgroups):
            VertBuff = bs.readBytes(numverts * 16)
            rapi.rpgBindPositionBufferOfs(VertBuff, noesis.RPGEODATA_FLOAT, 16, 0)
            rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, numverts, noesis.RPGEO_POINTS, 1)

    mdl = rapi.rpgConstructModel()
    mdlList.append(mdl)

    rapi.rpgClearBufferBinds()
    return 1
```
