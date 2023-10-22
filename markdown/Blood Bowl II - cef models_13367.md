## Post #1
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-09-26T10:33:31+00:00
- Post Title: Blood Bowl II - cef models

Just installed blood bowl II, not a super game, though it has some awesome models 

Once you installed it, you can extract the package files (.cpk) files easy, using my extraction tool, found here : [viewtopic.php?f=21&t=13359&hilit=blood+bowl+II](http://forum.xentax.com/viewtopic.php?f=21&t=13359&hilit=blood+bowl+II)

the static 3D models have the cef extension and here is a max script to import them

be aware, this is just early testing so it will not work for all the models, only thing it support atm is vertices and indices, no uv mapping yet

also I enlarged the model for max purposes, else all models look very tiny

here is the script ( for now)

```

fn SkipBytes stream nBytesToSkip = 
(
    fseek stream nBytesToSkip #seek_cur
)

fn ReadStringZeroEnded stream =
(
	
    local b = ReadByte stream
	local s = bit.IntAsChar(b)
    local str = s
	while (b != 0x0 ) do
	(
        b = ReadByte stream
    	s = bit.IntAsChar(b)
		if ( b !=0x0) then str+=s
	)
	return str
)

file = @"D:\Games\Blood Bowl 2\Extracted\ExtractedModels\ball_0.cef"

bin = fOpen file "rb" 

fseek bin 95 #seek_set

modelName = ReadStringZeroEnded bin

SkipBytes bin 120

position = ReadStringZeroEnded bin

SkipBytes bin 35

nVertSize = ReadLong bin

SkipBytes bin 10

nVertexSets  = ReadLong bin

nVertices = nVertSize / 16

verts =#()
for v = 1 to nVertices do
(
    x = readFloat bin
    y = readFloat bin
    z = readFloat bin 
    scaling = 30
    append verts [x * scaling,y * scaling,z * scaling]
    
    SkipBytes bin 4
)

ftell bin

SkipBytes bin 24 -- PAK
SkipBytes bin 44 -- NORMAL
SkipBytes bin 44 -- TANGENT
SkipBytes bin 44 -- TEXCOORD

ftell bin

nTexSize = ReadLong bin

print nTexSize

SkipBytes bin 10

SkipBytes bin nTexSize --> TO DO
SkipBytes bin 28

ftell bin

indice = ReadStringZeroEnded bin
SkipBytes bin 37
nIndexSize = ReadLong bin

SkipBytes bin 10

nIndexSets  = ReadLong bin

nIndices = nIndexSize / 6

tris = #()
for t = 1 to nIndices do
(
    a = readShort bin
    b = readShort bin
    c = readShort bin
    append tris [ a + 1, b + 1, c + 1]
)    

theMesh = mesh name:modelName vertices:verts faces:tris

fClose bin

```


so here is my first result of the blood bowl ball:
[bbii_ball.PNG](https://xentaxbackup.github.io/file/9789_bbii_ball.PNG)
## Post #2
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2015-09-27T14:53:38+00:00
- Post Title: Blood Bowl II - cef models

Nice work.

So is this a new custom format of their own making? They are no longer using Gamebryo and NIF?
## Post #3
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-09-27T19:31:47+00:00
- Post Title: Blood Bowl II - cef models

I don't know about the gamebryo, but it is not NIF

T.
## Post #4
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2015-09-27T20:08:57+00:00
- Post Title: Blood Bowl II - cef models

It seems like they have indeed ditched Gamebryo for a new engine. I can't find any info on what it is though. I've never heard of the CEF format either. I wonder if it's all their own in-house creation.
## Post #5
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-09-28T20:59:40+00:00
- Post Title: Blood Bowl II - cef models

I figured out some additional stuff, yet the models that contain multiple meshes and bones, ... keep on crashing on me... see very slow progress there

Better game than the first though

T.
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2015-09-29T11:01:06+00:00
- Post Title: Blood Bowl II - cef models

It is funny, because I recommend your thread to you:

[viewtopic.php?f=16&t=11056&hilit=Aarklash+Legacy](http://forum.xentax.com/viewtopic.php?f=16&t=11056&hilit=Aarklash+Legacy)
## Post #7
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-02T11:23:38+00:00
- Post Title: Blood Bowl II - cef models

? I don't understand, btw, I never continued the aarklash stuff...

the i3 doc, doesn't work

T.
## Post #8
- Username: Hairless Wookiee
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Oct 26, 2011 7:05 pm
- Post datetime: 2015-10-02T12:18:43+00:00
- Post Title: Blood Bowl II - cef models

I assume he is suggesting it is the same engine (appears to be Cyanide's own in-house creation), therefore he was recommending the only thread which appears to have any info on the format, which was of course by you. How much similarity is there with what they did for Aarklash Legacy?
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2015-10-03T22:14:00+00:00
- Post Title: Blood Bowl II - cef models

Quit some simalarities, cause I kinda based the initial idea on that, but it went sideways pretty quickly :p

T.
## Post #10
- Username: xelanizul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 13, 2017 6:43 pm
- Post datetime: 2017-05-13T09:45:26+00:00
- Post Title: Blood Bowl II - cef models

TaylorMouse, do you have any progress?
## Post #11
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-05-13T10:24:59+00:00
- Post Title: Blood Bowl II - cef models

Did you try the latest version of 3D Object Converter?

It supports the Cyanide Studio's game engine (Aarklash: Legacy; Blood Bowl 2; Confrontation; Dogs of War Online) .cef format.
## Post #12
- Username: xelanizul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 13, 2017 6:43 pm
- Post datetime: 2017-05-15T09:35:14+00:00
- Post Title: Blood Bowl II - cef models

Karpati, 3D Object Converter don*t understend CPK files from Blood Bowl 2
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2017-05-15T11:15:32+00:00
- Post Title: Blood Bowl II - cef models

> Reply from xelanizul
>
> Karpati, 3D Object Converter don*t understend CPK files from Blood Bowl 2

It is normally, because it supports the .CEF format!
## Post #14
- Username: xelanizul
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Feb 13, 2017 6:43 pm
- Post datetime: 2017-06-16T20:36:31+00:00
- Post Title: Blood Bowl II - cef models

> Reply from Karpati
>
> xelanizul wrote:Karpati, 3D Object Converter don*t understend CPK files from Blood Bowl 2 

It is normally, because it supports the .CEF format!

CEF files open, but its static pose of 3d model.... can anybody tell me how i can save NIF files in obj or oher formats for 3dmax or Zbrush?
