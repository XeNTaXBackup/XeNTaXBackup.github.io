## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-12-29T12:07:57+00:00
- Post Title: L.A. Noire heads

trying to explore this meshes with hex2obj without luck. feeling lack of knowledge i assumed that ackerman_head.chunk mesh has several meshes inside and first of them starts from 0x66A4 and ends at 0x725C

but after that tutorial leads me in a totaly mess, where vertices and uvs flew away from logical area of where the data should stored, ex:

> v -832981766051521080000000000000000000.000000 -0.000004 -0.002124 
>
> v 0.002808 -0.000001 0.000000 
>
> v 0.000000 0.000000 -56217600459076175000000000000000000.000000 
>
> v -4307986335116815300000000000000000000.000000 -0.000379 -0.000030 
>
> v 0.000109 -0.000000 0.000000 
>
> v 0.000000 0.000000 -24052315832927675000000000000000000.000000 
>
> v -11001165024864064000000000000000000000.000000 -0.000111 -0.000001

can anyone help me with [this](http://www.mediafire.com/download/kwqts5gx8qkfyrc/case_heads.7z)?
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-29T13:23:44+00:00
- Post Title: L.A. Noire heads

> Reply from Tosyk
>
> but after that tutorial leads me in a totaly mess, where vertices and uvs flew away from logical area of where the data should stored, ex:the tutorial is assumed to be used on simple models only as L.A. Noire heads are not.

For more complex models there are further steps to be observed:
use TextureFinder to get a clue whether/where texture data might be contained
after you got the face indices list (what mostly seems to be the easiest part)
scroll carefully through the model file to determine different sections

If you know from the max face index that there should be 1000 vertices for example
you can calculate the size of a continuous vertex section: 0x2EE0 for floats
or 0x1770 for half floats in sequential mode. (For the blocked mode the size is
1000 * VBsize of course.)

For L.A. Noire I found the normals blocks so far; start addresses may be incorrect!
adams_head:
[](http://www.pic-upload.de/view-21773305/adams_head.jpg.html)
For ackerman_head the H2O file is:
0x66A4 1500
VB1
36 99
0x3B38 309
0202

After knowing the normals section it may be easier to find the vertex positions.
Eiterh in the smae block or in another section.
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-12-29T14:11:56+00:00
- Post Title: L.A. Noire heads

Quickly checked Adam's head, vertices appears to be shorts so the UV's. Vertex start at 0x3150, vertex size 36 bytes.
[adams.jpg](https://xentaxbackup.github.io/file/6880_adams.jpg)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-29T14:29:01+00:00
- Post Title: L.A. Noire heads

enabling of the "cut" button is required, too.
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-12-29T15:44:38+00:00
- Post Title: L.A. Noire heads

Wow, this looks great, will continue research later this evening.
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-12-30T13:07:51+00:00
- Post Title: L.A. Noire heads

can u point me where is my error? for adams_head.chunk

can't get any positive result.

also I understand diferent sections in the files:

"garbage"
texture
vertextes
faces
texture dxt1 with mipmaps
normals?
"garbage"
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-30T14:22:18+00:00
- Post Title: L.A. Noire heads

use WordAll

And then switch the cut button from "noCut" to "cut".
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2013-12-30T23:50:04+00:00
- Post Title: L.A. Noire heads

so i found this for adams_head.chunk:



works perfectly, i found and extract it textures.

also, i assumed that vertex buffer consists of 24 bytes pattern and first float_3 it's CoordXYZ

now, how can i found uvs?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-22T15:50:25+00:00
- Post Title: L.A. Noire heads

(sry for this abandoned thread - as a known member of RodH club we like to grab it again  )
yeah, see: Tosyk was right using half floats for the uvs (never could have imagined this ugly square uv map to give a decent head):



Adam_head.jpg (149.9 KiB) Viewed 232 times


btw. FVF size is 36 here (former "VB size"). Also the "cut" option has been cut (ha-ha) from newer versions of hex2obj.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-04-22T19:51:30+00:00
- Post Title: L.A. Noire heads

here's a short (and ugly) maxscrript to load Adam's head chunk.
As you may know I prefer doing it in 'C' but Tosyk requested a maxscript:
(works for THIS head only!)

```
    hf=readshort fstream #unsigned
    sign = bit.get hf 16
    exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
    fraction = bit.and hf (bit.hexasint "03FF")
    if sign==true then sign = 1 else sign = 0
    exponentF = exponent + 127
    outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
    (bit.shift exponentF 23)) (bit.shift sign 31)
    return bit.intasfloat outputasfloat*2
    )


vertArray=#()
faceArray =#()
UVarray=#()

function ReadModelFile fName=
(     
    format "-- START READING MODEL FILE --\n"
    stream = fOpen fname "rb"          -- Open the file for reading
    fSeek stream 0x194 #seek_set
    vertCount = readlong stream       -- vertex count of (first) submesh
    faceCnt     = readlong stream
    vertStride= 36
	
    --print ("@ 0x"+ bit.intAsHex(ftell stream) as string)		

    fSeek stream 0x3150 #seek_set	-- vertex block
    for i=1 to vertCount do (		--
       x  = readShort stream #signed
       y  = readShort stream #signed
       z  = readShort stream #signed
       fSeek stream (26) #seek_cur
       tu  = readHalfFloat stream; tv  = readHalfFloat stream
       append vertArray ([x,y,z]/127.0)	
	   --format "v %\n" vertArray[i]
       append UVarray [tu,tv,0]		       
    )
    print ("@ 0x"+ bit.intAsHex(ftell stream) as string)
	
    for x = 1 to faceCnt do (
        fa= readshort stream #unsigned
        fb= readshort stream #unsigned
        fc= readshort stream #unsigned
            format "f % % %\n" fa fb fc
        append faceArray[fa+1,fb+1,fc+1]	
	)	
    msh = mesh vertices:vertArray faces:faceArray
    msh.numTVerts = vertCount
    buildTVFaces msh
    for j = 1 to vertCount do setTVert msh j UVarray[j]
    for j = 1 to faceCnt do setTVFace msh j faceArray[j]

    fClose stream
)

-- entry point --

ClearListener()
fname = getOpenFileName \
caption:" open L.A. Noire 3D Model" \
types:"3D Model (*.chunk)|*.chunk"
--historyCategory:"3D Model chunk
format "fname: %\n" fname
   
ReadModelFile fname
```


For other chunk files you'll need to adjust the start address of the vertices block (0x3150 here)
and (possibly) the address of the vertex count: 0x194



Adams_head_MS.jpg (183.29 KiB) Viewed 218 times
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2016-04-29T19:30:32+00:00
- Post Title: L.A. Noire heads

> Reply from shakotay2
>
> here's a short (and ugly) maxscrript to load Adam's head chunk.I'm greatly appreciate for this, shakotay
