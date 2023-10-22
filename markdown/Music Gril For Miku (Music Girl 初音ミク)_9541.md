## Post #1
- Username: x=?
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 25, 2012 6:28 pm
- Post datetime: 2012-08-24T08:11:26+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

website [http://mg-miku.com/](http://mg-miku.com/)
There's a game in iphone , it named "Music Gril For Miku"
My friend thought that there were models in it,and he try his best to do it.
Can anybody help us to rip the model?
[http://www.mediafire.com/?k1ugotv1l13di5t](http://www.mediafire.com/?k1ugotv1l13di5t)
This is one of the game file of  "Music Gril For Miku".
------------------------------------------
Sorry for my bad English.
Thanks for every body.
## Post #2
- Username: x=?
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 25, 2012 6:28 pm
- Post datetime: 2012-08-24T08:17:08+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

And we thought the model is the project diva f's model.
[1.jpg](https://xentaxbackup.github.io/file/5709_1.jpg)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-24T18:30:01+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

You need to upload more model samples there are a bunch of offsets, I can see a vertex buffer and index buffer but I don't see any counts.

I have an idea of the basic outline of the format but don't know how to read the specifics.
Also maybe your friend can share some info?



Send an entire model as well (head, body, etc.) along with other random models

I suspect they use "h" for "head", "b" for "body", and others.
## Post #4
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2012-08-24T22:52:35+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

well me and my friend have been looking at these files and the files are seperated into c001.mdl (guessing is the main body) and h001.mdl whilst the physics are in c001.jpx and so far only 2 models in game the rest are just menues and stuff (2 more are planned for future release) we also suspect that the .acv files are textures but are unsure
thats all we got .-.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-24T23:02:11+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

Upload all of them and textures. There should be a file for the materials as well since it does not appear to be stored in the model.
## Post #6
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2012-08-24T23:18:46+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

check your messages and good luck
## Post #7
- Username: x=?
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 25, 2012 6:28 pm
- Post datetime: 2012-08-25T03:03:03+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

> Reply from finale00
>
> You need to upload more model samples there are a bunch of offsets, I can see a vertex buffer and index buffer but I don't see any counts.

I have an idea of the basic outline of the format but don't know how to read the specifics.
Also maybe your friend can share some info?



Send an entire model as well (head, body, etc.) along with other random models

I suspect they use "h" for "head", "b" for "body", and others.
Well.Do you want the whole game file?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-25T06:04:16+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

It was sent to me already.

What is the format of the PVR textures?

EDIT: nvm looks like someone (chrrox?) already wrote one for another game.
## Post #9
- Username: x=?
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 25, 2012 6:28 pm
- Post datetime: 2012-08-25T07:17:36+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

> Reply from finale00
>
> It was sent to me already.

What is the format of the PVR textures?

EDIT: nvm looks like someone (chrrox?) already wrote one for another game.
Sorry , I don't know . I and my friend trying to use some softwave to open the file , but we fail , can you give us a help?
## Post #10
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-08-26T14:29:21+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

Some random guy on deviantArt, gave me a link and said please convert these lol

I was waiting for hm to give me more samples or even the name of the game I was looking at lol.. I think maybe he forgot about me >_<

Anyway everything usually ends up here, and sure enough the sample file here matches the one sent to me on dA.

the IGB format for PSP is insane! and I wouldn't be surprised if this format wasn't just as insane.. the format starts with alot of offsets, which bounce almost randomly through out the entire file.
theres not much for counts, any counts relate to tables that are full of more offsets. 

I couldn't decipher any of it sadly 

I did some fancy foot work though and attempted to calculate the vertex buffer count. this is dependent on locating the correct offset for the facebuffer.. which seems to move around so its hard to know if you read the right one or not.

anyways I give up, so here's was my work on it (maxscript). theres a count after the vertex buffer, which will get you the first object from the face buffer. after that there is no count, so no way to correctly read in the other objects. but even if you keyed in the length manfully, theres only like 20% data left in the entire face buffer.. which won't support all the missing geometry O_O this really boggles my mind.. I looked further down the file and cannot find another face buffer. very confusing.

good news is that there is a specific table for the PVR textures. so if we knew the PVR format, then it would seem to be easy to dump them






```

obj=$*;delete obj

mscale=3.93700787

fsource = GetOpenFileName \
caption:"Music Girl: Hatsune Miku" \
types: "Model Files (*.mdl)|*.mdl|"

-- fsource = "F:\\D-O\\Mikie\\Modle2\\c002.mdl"
-- fsource = "F:\\D-O\\Mikie\\h002.mdl"

if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
-- fpath=getFilenamePath fsource
-- fname=getFilenameFile fsource
-- fsize=getFileSize fsource
f = fopen fsource "rb"

vertArray = #()
normArray = #()
uvwArray = #()
faceArray = #()

mdl = readlong f #unsigned
if mdl == 0x206C646D then(
mdlversion = readlong f
ukn1 = readlong f -- null?
ukn2 = readlong f -- null?
ukn3 = readlong f -- count?

fseek f (0x60) #seek_set -- skips more 0's
for i = 1 to ukn3 do(
getPos = ftell f + 80
ukn3_flag1 = readlong f -- always 1
ukn3_offset1 = readlong f -- offset?
fseek f getPos #seek_set -- skips series of floats
)

ukn4_1a = readlong f -- count
ukn4_1b = readlong f -- offset
ukn4_1c = readlong f --null
ukn4_1d = readlong f -- null

ukn4_2a = readlong f -- count
ukn4_2b = readlong f -- offset
ukn4_2c = readlong f --null
ukn4_2d = readlong f -- null

-- texture offset table
ukn4_3a = readlong f -- count
ukn4_3b = readlong f -- offset
ukn4_3c = readlong f -- ?? flags, float?
ukn4_3d = readlong f -- always 0x00007FFF ?

vertex_offset = readlong f #unsigned


offsetArray=#()
while (ftell f)!=ukn4_3b do(append offsetArray (readlong f #unsigned))
for i = 1 to offsetArray.count do(
fseek f offsetArray[i] #seek_set
check = readlong f #unsigned
if check<=0xFFFF then EXIT
)
fseek f -4 #seek_cur
face_offset = ftell f
vertex_count = (face_offset - vertex_offset)/32


vertArray=#();vertArray[vertex_count]=[0,0,0]
uvwArray=#();uvwArray[vertex_count]=[0,0,0]
normArray=#();normArray[vertex_count]=[0,0,0]

fseek f vertex_offset #seek_set
for i = 1 to vertex_count do(
vx = readfloat f
vy = readfloat f
vz = readfloat f
nx = readfloat f
ny = readfloat f
nz = readfloat f
tu = readfloat f
tv = readfloat f
vertArray[i]=([vx,-vz,vy]*mscale)
normArray[i]=[nx,-nz,ny]
uvwArray[i]=[tu,tv,0]
)


fseek f face_offset #seek_set
face_count = readlong f #unsigned

fa = readshort f #unsigned + 1
fb = readshort f #unsigned + 1
fc = readshort f #unsigned + 1
append faceArray [fa,fb,fc]
for i = 1 to (face_count-3) do (
fa = fb
fb = fc
fc = readshort f #unsigned + 1
if (mod i 2)==1 then(append faceArray [fa,fc,fb])
else(append faceArray [fa,fb,fc]))

try(
msh = mesh vertices:vertArray faces:faceArray
msh.numTVerts = uvwArray.count
buildTVFaces msh
msh.displayByLayer = false
msh.backfacecull = on
msh.wirecolor = random (color 0 0 0) (color 255 255 255)

for j = 1 to uvwArray.count do setTVert msh j uvwArray[j]
for j = 1 to faceArray.count do setTVFace msh j faceArray[j]
-- for j = 1 to normArray.count do setNormal msh j normArray[j]
convertTo msh PolyMeshObject
select msh
modPanel.setCurrentObject msh
subobjectLevel = 1

)catch(Print "Import Failed")
)else(Print "Failed to read MDL header")

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
)else(Print "Aborted.")
fclose f
```



edit updated script to dump texture data. pvr files spit out, which you can open with texture packer.


also to clarify this, Music Girl Miku is a free iSO app
[http://app.moefou.org/app/512849356](http://app.moefou.org/app/512849356)

so its free game ^_^

```

obj=$*;delete obj

mscale=3.93700787

-- fsource = GetOpenFileName \
-- caption:"Music Girl: Hatsune Miku" \
-- types: "Model Files (*.mdl)|*.mdl|"

fsource = "F:\\D-O\\Mikie\\Modle2\\c002.mdl"
-- fsource = "F:\\D-O\\Mikie\\h002.mdl"

if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
fpath=getFilenamePath fsource
fname=getFilenameFile fsource
fsize=getFileSize fsource
f = fopen fsource "rb"

vertArray = #()
normArray = #()
uvwArray = #()
faceArray = #()

mdl = readlong f #unsigned
if mdl == 0x206C646D then(
mdlversion = readlong f
ukn1 = readlong f -- null?
ukn2 = readlong f -- null?
ukn3 = readlong f -- count?

fseek f (0x60) #seek_set -- skips more 0's
for i = 1 to ukn3 do(
getPos = ftell f + 80
ukn3_flag1 = readlong f -- always 1
ukn3_offset1 = readlong f -- offset?
fseek f getPos #seek_set -- skips series of floats
)

ukn4_1a = readlong f -- count
ukn4_1b = readlong f #unsigned -- offset
ukn4_1c = readlong f --null
ukn4_1d = readlong f -- null

ukn4_2a = readlong f -- count
ukn4_2b = readlong f #unsigned -- offset
ukn4_2c = readlong f --null
ukn4_2d = readlong f -- null

-- texture offset table
ukn4_3a = readlong f -- count
ukn4_3b = readlong f #unsigned -- offset
ukn4_3c = readlong f -- ?? flags, float?
ukn4_3d = readlong f -- always 0x00007FFF ?

try_to_read_geometry = true
if try_to_read_geometry==true do(
vertex_offset = readlong f #unsigned


offsetArray=#()
while (ftell f)!=ukn4_3b do(append offsetArray (readlong f #unsigned))
for i = 1 to offsetArray.count do(
fseek f offsetArray[i] #seek_set
check = readlong f #unsigned
if check<=0xFFFF then EXIT
)
fseek f -4 #seek_cur
face_offset = ftell f
vertex_count = (face_offset - vertex_offset)/32


vertArray=#();vertArray[vertex_count]=[0,0,0]
uvwArray=#();uvwArray[vertex_count]=[0,0,0]
normArray=#();normArray[vertex_count]=[0,0,0]

fseek f vertex_offset #seek_set
for i = 1 to vertex_count do(
vx = readfloat f
vy = readfloat f
vz = readfloat f
nx = readfloat f
ny = readfloat f
nz = readfloat f
tu = readfloat f
tv = readfloat f
vertArray[i]=([vx,-vz,vy]*mscale)
normArray[i]=[nx,-nz,ny]
uvwArray[i]=[tu,-tv,0]
)


fseek f face_offset #seek_set
face_count = readlong f #unsigned

fa = readshort f #unsigned + 1
fb = readshort f #unsigned + 1
fc = readshort f #unsigned + 1
append faceArray [fa,fb,fc]
for i = 1 to (face_count-3) do (
fa = fb
fb = fc
fc = readshort f #unsigned + 1
if (mod i 2)==1 then(append faceArray [fa,fc,fb])
else(append faceArray [fa,fb,fc]))





-- fseek f (0x23834) #seek_set
-- count=100
-- fa = readshort f #unsigned + 1
-- fb = readshort f #unsigned + 1
-- fc = readshort f #unsigned + 1
-- append faceArray [fa,fb,fc]
-- for i = 1 to (count-3) do (
-- fa = fb
-- fb = fc
-- fc = readshort f #unsigned + 1
-- if (mod i 2)==1 then(append faceArray [fa,fc,fb])
-- else(append faceArray [fa,fb,fc]))



























try(
msh = mesh vertices:vertArray faces:faceArray
msh.numTVerts = uvwArray.count
buildTVFaces msh
msh.displayByLayer = false
msh.backfacecull = on
msh.wirecolor = random (color 0 0 0) (color 255 255 255)

for j = 1 to uvwArray.count do setTVert msh j uvwArray[j]
for j = 1 to faceArray.count do setTVFace msh j faceArray[j]
-- for j = 1 to normArray.count do setNormal msh j normArray[j]
max tool zoomextents
convertTo msh PolyMeshObject
select msh
-- modPanel.setCurrentObject msh
-- subobjectLevel = 1

)catch(Print "Import Failed")
) -- end try_to_read_geometry


struct texture_entry (offset,size,format,hash)
textureArray = (texture_entry offset:#() size:#() format:#() hash:#())

fseek f ukn4_3b #seek_set
for i = 1 to ukn4_3a do (
append textureArray.offset (readlong f #unsigned) -- offset
append textureArray.size (readlong f #unsigned) -- size
append textureArray.format (readlong f #unsigned) -- format flag? 0x00=PNG | 0x01=PVR
append textureArray.hash (readlong f #unsigned) -- flags?, hash?
)



for i = 1 to textureArray.offset.count do(
fseek f textureArray.offset[i] #seek_set
sext = "."
case of(
(textureArray.format[i]==0): (sext += "png")
(textureArray.format[i]==1): (sext += "pvr")
default:(sext += "dat")
)
s = fopen (fpath+fname+"_"+(textureArray.hash[i] as string)+sext) "wb"
for x = 1 to textureArray.size[i] do (
writebyte s (readbyte f #unsigned) #unsigned
)

fflush s
fclose s
)


)else(Print "Failed to read MDL header")

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
)else(Print "Aborted.")
fclose f
```
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-26T21:25:47+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

Can't get the texture parser for noesis to load the PVR properly by handler.
But, the mesh format is straightforward



mariokart, for the vertex and face offsets, they are stored sequentially.

```
int[numMesh] face offsets
int[numMesh] more offsets?

# tex info after
...

```


So the first vert offset goes with the first face offset, second vert offset with the second face offset, etc.

The fact struct is just

```
   short numIdx
   short matNum # maybe
   short[numIdx] indices
}

```


btw, I can't find miku's normal outfit.
the c001 and h001 files look like something entirely different.
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-08-26T23:58:03+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

I felt pretty stupid after chrrox pointed out the offsets >_< hehe 

yeah I only got what you got there. I'm trying to buy a japanese itunes card so I can buy whatever DLC for this game
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-27T00:03:45+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

Btw do you know how the materials work?

For example, the head model has 6 textures, but there are only 4 meshes. Though I didn't actually look at the textures so they might have been like "alternate colours" or something.
## Post #14
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-08-27T03:08:25+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

yeah just implemented materials in my maxscript

at the start of the file you get mesh count, then a table giving you object count, vertex count, and some matrix info for object positioning

after this is an offset list.. theres actually 2. the first one has 3 entries, containing 4 Longs. the first long is count, second long is offset.
first entry is bones, second entry is materials, and third entry is textures

the bone offset pops over to a list of matrices, chrrox was explaning the bone format. but I havent implmented yet.
the material offset brings you to the mat entriesm each 64bytes in length. the long at 0x20 is the texture index. this relates to the order in which they are defined in the texture info later
the texture offset then brings you to a table with offset and size, and some null info. 

after that its just buffer. now as your parsing each face buffer, you'll have count short, and material id short, then the faces as shorts.

thats about it. I still havent found the bone weights
## Post #15
- Username: Natsuki Okusawa
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-27T09:44:23+00:00
- Post Title: Music Gril For Miku (Music Girl 初音ミク)

The bone format is
Posx    PosY   PosZ    1.0
QuatX QuatY QuatZ   QuatW
ScaleX ScaleY ScaleZ 1.0
1.0      1.0      1.0       1.0
Parent ?         ?           ?

and the weighting goes
for each vertex
read the weight count
then for each of these counts read
bone id long
weight float


also the magic number of the day is

44 90 12 28
## Post #16
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-08-28T02:39:14+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

turns out the main outfit is XOR'd O_O thanks to chrrox for seeing that. 
Earlier if somebody had told me that those files were models, I would have said they were crazy. lol turns out they were XOR'd ... haha never seen anything like that O_o crazy

anyway I wanted to see if I could implement the xor'ing in the maxscript, to see how much tact time it would add to the import.
my read function had to get the alignment by getting the offset, then pass it to maxscripts bitwise function to xor.. I figured it would slug on import.. but its not too bad.
## Post #17
- Username: x=?
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 25, 2012 6:28 pm
- Post datetime: 2012-08-28T03:35:20+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

> Reply from mariokart64n
>
> turns out the main outfit is XOR'd O_O thanks to chrrox for seeing that. 
Earlier if somebody had told me that those files were models, I would have said they were crazy. lol turns out they were XOR'd ... haha never seen anything like that O_o crazy

anyway I wanted to see if I could implement the xor'ing in the maxscript, to see how much tact time it would add to the import.
my read function had to get the alignment by getting the offset, then pass it to maxscripts bitwise function to xor.. I figured it would slug on import.. but its not too bad.
Wow!Good job!How do you get the model?In your script , it can only get the peak.
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-28T03:56:14+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

lol after looking at the file more closely it was pretty obvious it was xor'd...
I wonder if the two models are from the same person, or in fact two different people decided to make their own outfits and then put it together and then one guy was like "hey let's xor this thing" and the other was like "forget it what's the point they're still going to reverse it"

It's a good render though. Better than those MMD models
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-28T10:56:16+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

I have come across a bunch of ios games that devs try to protect the best thing I have seen is a golf game.
the header is
"This is not a zip file I promise"
and then its a normal zip file after that lol.
this is the game
[http://itunes.apple.com/us/app/lets-gol ... 20443?mt=8](http://itunes.apple.com/us/app/lets-golf!-3/id433120443?mt=8)
protecting ios game assets is pointless as anyone who has  a jail broken device can dump the entire apps memory.
## Post #20
- Username: x=?
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 25, 2012 6:28 pm
- Post datetime: 2012-08-29T06:23:34+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

> Reply from mariokart64n
>
> turns out the main outfit is XOR'd O_O thanks to chrrox for seeing that. 
Earlier if somebody had told me that those files were models, I would have said they were crazy. lol turns out they were XOR'd ... haha never seen anything like that O_o crazy

anyway I wanted to see if I could implement the xor'ing in the maxscript, to see how much tact time it would add to the import.
my read function had to get the alignment by getting the offset, then pass it to maxscripts bitwise function to xor.. I figured it would slug on import.. but its not too bad.
Can I have your maxscript?I want to get the mdl model,please help me.
## Post #21
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-30T02:17:02+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

Bone file is in the format i thought.
i can't get it to work in noesis i must be doing something wrong.
but the format is

px, py, pz, null
qx, qy, qz, qw     invert the qw value
sx, sy, sz, null
null null null null
parent, unk , hashed name?, unk

and the matrix is parent relative
[miku bones.png](https://xentaxbackup.github.io/file/5720_miku bones.png)
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-30T02:19:53+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

What do the p/q/s values represent?
## Post #23
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-08-30T02:29:31+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

position
quat
scale

edit i got it now something is weird with the quat values in noesis not sure whats going on but manually setting the transform fixes it.
## Post #24
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-09-03T16:48:07+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

Any news about the script?
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-03T23:08:06+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

Forget it, XOR'ing it in python takes too long lol

```

set key = "0x44 0x90 0x12 0x28"
idstring "wrcp"

get size asize
math size -= 16
goto 16
filexor key
log "" 16 size

```
## Post #26
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-09-06T16:29:50+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

Someone on dA ripped the model [http://xdonotenterx.deviantart.com/#/d5dspx2](http://xdonotenterx.deviantart.com/#/d5dspx2) >.<
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-06T16:48:36+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

He should join xentax and contribute to the 3D ripping efforts
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-06T19:41:40+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

i think he just used your script.
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-06T19:58:45+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

> Reply from chrrox
>
> i think he just used your script.

All it got were the textured meshes.
It looks like he has it skinned as well. Did you release something?

Or maybe he skinned it himself lol
## Post #30
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-06T20:02:41+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

Yeah, oftentimes when someone on DA says "I ripped it," they mean "I went to XeNTax, downloaded and ran some guy's script or program." Happens to me all the time. I stopped minding that a while ago lol. It will happen anytime you rip anything anime and the MMD people find it.
## Post #31
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-06T20:19:16+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

see... he's even got some stuff from my rippers too...

[http://xdonotenterx.deviantart.com/art/ ... erx&qo=204](http://xdonotenterx.deviantart.com/art/As-i-wait-315904881?q=sort%3Atime%20gallery%3Axdonotenterx&qo=204)

Pretty sure those are from MKII. But, nobody other than chris and I have done a neptunia game so you know he comes to xentax lol.

Ha ha ha, I laugh at those MMD people most of the time because they say stuff like this:

[http://melly-kitty.deviantart.com/](http://melly-kitty.deviantart.com/)

```
DO NOT ASK ME HOW TO RIP GAMES I WILL NOT TELL YOU
```


lol recognize these models? and notice they won't tell you where they got them from lol ?

[http://melly-kitty.deviantart.com/galle ... 4#/d597wjz](http://melly-kitty.deviantart.com/gallery/?offset=24#/d597wjz)

In the MMD world, XeNTaX is a trade secret lol!
## Post #32
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-09-07T16:24:53+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

[out]
## Post #33
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2012-09-07T18:24:34+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

> Reply from howfie
>
> see... he's even got some stuff from my rippers too...

http://xdonotenterx.deviantart.com/art/ ... erx&qo=204

Pretty sure those are from MKII. But, nobody other than chris and I have done a neptunia game so you know he comes to xentax lol.

Ha ha ha, I laugh at those MMD people most of the time because they say stuff like this:

http://melly-kitty.deviantart.com/
Code: Select allDO NOT ASK ME HOW TO RIP GAMES I WILL NOT TELL YOU

lol recognize these models? and notice they won't tell you where they got them from lol ?

http://melly-kitty.deviantart.com/galle ... 4#/d597wjz

In the MMD world, XeNTaX is a trade secret lol!

Not really, also you can find some models done with your rippers in face punch and tombraider forums. 

See ya.
## Post #34
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-07T18:33:05+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

> Reply from Wobble
>
> 
- How does one notice that data has been XOR'ed?

When you notice the same set of bytes repeating again and again.
Especially if you suspect there to be large sections of null bytes, like maybe a padded string. Usually dead-giveaway there.

> - And if you have XOR'ed data, how does one figure out the key?

Try using the repeating bytes as your key.
If it doesn't work then try changing the values and see if you get anything useful.

Or I guess you can just take the easy way out and disassemble the exe/dll and look for the procedures.
## Post #35
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-07T19:27:50+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

If the xor key is short you can usually frequency count the bytes in the first 100 bytes or so. The one that has the most zeroes, FFs or 80s may be a full or partial xor key.

Also even if they get the models from face punch or xnalara, those mmd people still won't tell you where or how they got them.
## Post #36
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-07T19:38:45+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

howfie what's the algorithm you use for guessing possible candidate keys? Don't think "frequency count" is a particular class of algorithms..?
## Post #37
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-07T20:01:59+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

yes, counting and permuting are the algorithms. give me a few minutes to find my code and if there's a miku sample i'll show you how to decode the key....

or actually, got any samples with a really complex and long xor key lol?
## Post #38
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-07T20:21:17+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

None that I can think of.
Most of the encryption's I've had to look at are usually 1-byte or 4-byte though. How effective would the algorithms be on arbitrarily long xor keys?
## Post #39
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-07T20:26:03+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

oh ok, i'll whip up a long sample then. but in general, if the key uses a lot of different characters, it's best to look for it in the exe lol.
## Post #40
- Username: manbox74
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Jan 16, 2012 10:54 am
- Post datetime: 2012-09-12T16:03:03+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

How can I rip the textures?I can't find them .
## Post #41
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-12T16:40:37+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

They're stored with the model data.
## Post #42
- Username: foxdemon90210
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Dec 22, 2011 6:12 am
- Post datetime: 2012-12-30T18:58:17+00:00
- Post Title: Re: Music Gril For Miku (Music Girl 初音ミク)

> Reply from howfie
>
> see... he's even got some stuff from my rippers too...

http://xdonotenterx.deviantart.com/art/ ... erx&qo=204

Pretty sure those are from MKII. But, nobody other than chris and I have done a neptunia game so you know he comes to xentax lol.

Ha ha ha, I laugh at those MMD people most of the time because they say stuff like this:

http://melly-kitty.deviantart.com/
Code: Select allDO NOT ASK ME HOW TO RIP GAMES I WILL NOT TELL YOU

lol recognize these models? and notice they won't tell you where they got them from lol ?

http://melly-kitty.deviantart.com/galle ... 4#/d597wjz

In the MMD world, XeNTaX is a trade secret lol!

He does say where he got them and he didn't say he ripped them just rigging them.
