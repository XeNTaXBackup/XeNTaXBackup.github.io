## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-24T08:06:41+00:00
- Post Title: Age of Pirates: Caribbean Tales (Корсары 3) - *.gm models

Help me to convert *.gm models into 3ds max with bones and weights.

[sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/korsary-3-pc/dep0.gm)
[other sample 01](http://dl.dropbox.com/u/9919707/blogs/xentax.com/korsary-3-pc/huber_spa5.gm)
[other sample 02](http://dl.dropbox.com/u/9919707/blogs/xentax.com/korsary-3-pc/Blaz2.gm)

I started to researches and wrote script:

```
clearlistener()

fn ReadFixedString bstream fixedLen =
(
   local str = ""
   for i = 1 to fixedLen do
   (
      str0 = ReadByte bstream #unsigned
      if str0!=0xFD AND str0!=0xFC do str+= bit.intAsChar str0
   )
   str
)

Face_array=#()
Vert_array=#()
UV_array=#()

fseek f 0x38BE #seek_set --probably vertexes count start (2172)
vertCount=readshort f #unsigned
print vertCount
skiper=ReadFixedString f 0x7

for x = 1 to vertCount do(

p0=readfloat f
p1=readfloat f
p2=readfloat f
p3=readfloat f
p4=readfloat f
p5=readfloat f
p6=readfloat f
p7=readfloat f
p8=readfloat f -- skiper, looks like "7F 7F 7F FF"
p9=readfloat f
p10=readfloat f
append Vert_array[0,0,0]
append UV_array[0,0,0]
)

fseek f 0x3BC #seek_set --probably polygon count start (2250)

polyCount=readlong f #unsigned
print polyCount
polySkiper=ReadFixedString f 0x40

for x = 1 to polyCount/3 do(
fa=readshort f #unsigned+1
fb=readshort f #unsigned+1
fc=readshort f #unsigned+1
append Face_array[fc,fb,fa]
)

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name="dep"

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
```


As you can see i read count of vertexes in 0x38BE values (i read it in 2 bytes) and get 2171 (actually i now that model have 2172 vertexes). Then skipping 0x7 length values and start reading pattern of vertexes from 0x38C8 until the end.
Count of polygons i reading from 0x3BC (read in 4 bytes and also knows that model have 2250 polygons), then skipping 0x40 length values and start reading polygon pattern from 0x400.

But i can't get a model into max. Someone correct me.

p.s. also i this file don't have weights, or it have?
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-27T10:06:02+00:00
- Post Title: Age of Pirates: Caribbean Tales (Корсары 3) - *.gm models

Hey Tosyk
Mayby this help you to writing script for max.
It is a python script for Blender249.
[import-korsary-2011-03-27.zip](https://xentaxbackup.github.io/file/4118_import-korsary-2011-03-27.zip)
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-03-27T10:19:41+00:00
- Post Title: Age of Pirates: Caribbean Tales (Корсары 3) - *.gm models

> Reply from Szkaradek123
>
> Hey Tosyk
Mayby this help you to writing script for max.
It is a python script for Blender249
Gm files have no bones data.
oh, i'm appreciated Szkaradek123, i will try to understand python script right now, and also i need find bone-files some where
## Post #4
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-27T13:16:50+00:00
- Post Title: Age of Pirates: Caribbean Tales (Корсары 3) - *.gm models

```
   heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"Open KORSARY Model File" \
types:"KORSARY Model File(*.gm)|*.gm" \
historyCategory:"KosaryObjectPresets"
f = fopen fname "rb"

unk01 = readlong f
unk02 = readlong f
unk03 = readlong f
unk04 = readlong f
unk05 = readlong f
unk06 = readlong f
unk07 = readlong f
unk08 = readlong f
unk09 = readlong f
unk010 = readlong f
unk011 = readlong f
fseek f (28) #seek_cur
fseek f (unk03) #seek_cur
fseek f (108+12) #seek_cur
fseek f (5*108) #seek_cur
data = #()
for a=1 to 26 Do(
append data (readlong f)
)
print data

faceslist = #()
for a=1 to data[9] Do(
f1 = (readshort f) + 1 
f2 = (readshort f) + 1
f3 = (readshort f) + 1
--print [f1,f2,f3]
append faceslist [f1,f2,f3]
)
fseek f (8)#seek_cur


vertexes = #()
uvcoord = #()
for a=1 to data[11] Do( 
vx = readfloat f 
vy = readfloat f 
vz = readfloat f
append vertexes [vx,vy,vz]
fseek f (24) #seek_cur
tu = readfloat f
tv = readfloat f * -1
append uvcoord [tu,tv,0]
)

msh = mesh vertices:vertexes faces:faceslist
msh.numTVerts = uvcoord.count
buildTVFaces msh
for j = 1 to uvcoord.count do setTVert msh j uvcoord[j]
for j = 1 to faceslist.count do setTVFace msh j faceslist[j]

fclose f



```
