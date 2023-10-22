## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2011-12-17T11:00:36+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Hello! 
Somebody can try to read this .gcmesh_pc files?
I only found the xyz vertex...
[](http://imageshack.us/photo/my-images/854/shaundivertex.jpg/)
[](http://imageshack.us/photo/my-images/408/bruteminigunvertex.jpg/)

I made a topic here with some research on the files formats:
[https://www.saintsrowmods.com/forum/ind ... ditor.255/](https://www.saintsrowmods.com/forum/index.php?threads/editing-some-other-files-with-hex-editor.255/)

Some samples files:
[http://www.sendspace.com/file/mnuwbg](http://www.sendspace.com/file/mnuwbg)
Thanks
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-12-17T13:17:29+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

had a quick look at it, the GC file holds the faces, and the vertices, but theres some odd data in there that doesn't line up... so there may be additional data aswell

the CC file is the control file, but I haven't figured out how to parse the damn thing. the face section needs to be seperated, theres LODs and elements combined in the same buffer. 

I wrote up a quick import script for 3dsmax to have a look at the faces, so I could break down the proper face counts

here's a progress update;



```

mscale=39.3700787

fsource = GetOpenFileName \
caption:"Saints Row Turd Importer" \
types: "SRIII CC File (*.ccmesh_pc)|*.ccmesh_pc|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
fpath=getFilenamePath fsource
fname=getFilenameFile fsource
fsize=getFileSize fsource
fsize=          getFileSize fsource
gsource=(fpath+fname+".gcmesh_pc")
if (gsource!=undefined) AND ((doesFileExist gsource)==true) then(
f = fopen fsource "rb"
s = fopen gsource "rb"
gsize=getFileSize gsource
count3=0
count4=0
check=true
while check==true do(
if (ftell f)!=fsize AND check==true then(
if (readbyte f #unsigned)==16 do (
if (ftell f+4)<=fsize AND check==true then(
if (readlong f #unsigned)==0 do (
if (ftell f+4)<=fsize AND check==true then(
if (readlong f #unsigned)==33554432 do (
if (ftell f+71)<=fsize AND check==true then(
check=false
fseek f 63 #seek_cur
count3=readlong f #unsigned
count4=readlong f #unsigned
)else(check=false))
)else(check=false))
)else(check=false))
)else(check=false))

vertArray=#()
uvwArray=#()
normArray=#()
faceArray=#()
count5=(gsize-(count3*32+4))/2
	
StartDirection = -1
f1 = readshort s #unsigned + 1
f2 = readshort s #unsigned + 1
if f1>=count3 do f1=1
if f2>=count3 do f2=1
FaceDirection = StartDirection
IndexCounter = 2
Do (
f3 = readshort s #unsigned

IndexCounter += 1
if f3>=count3 then (
f1 = readshort s #unsigned + 1
f2 = readshort s #unsigned + 1
if f1>=count3 do f1=1
if f2>=count3 do f2=1
FaceDirection = StartDirection
IndexCounter += 2
) else (
f3 += 1
FaceDirection = -FaceDirection
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
if FaceDirection > 0 then append faceArray [f1,f2,f3]
else append faceArray [f1,f3,f2]
)
f1 = f2
f2 = f3
)
)
while IndexCounter !=count5
	
fseek s (gsize-(count3*32+4)) #seek_set

for i = 1 to count3 do(
p1=readfloat s*mscale
p2=readfloat s*mscale
p3=readfloat s*mscale
p4=readfloat s
p5=readfloat s
p6=readfloat s
p7=readfloat s
p8=readfloat s
append vertArray[p1,-p3,p2]
append uvwArray[0,0,0]
append normArray[0,0,0]
)

msh = mesh vertices:vertArray faces:faceArray
msh.numTVerts = vertArray.count
buildTVFaces msh
msh.displayByLayer = false
msh.backfacecull = on

for j = 1 to vertArray.count do setTVert msh j uvwArray[j]
for j = 1 to vertArray.count do setNormal msh j normArray[j]
for j = 1 to faceArray.count do setTVFace msh j faceArray[j]

convertTo msh PolyMeshObject

fclose f
fclose s
)else(messagebox "ERROR!!\nFile Pair Wasn't Found")
)else(Print "Aborted.")
```
## Post #3
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2011-12-17T15:02:13+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Nice
## Post #4
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2011-12-23T11:59:06+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Also animations seem very well made.
## Post #5
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-01-13T15:45:22+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

out of curiosity, in what of the packfiles are the cc and gcmeshes? I've only found cpegs and gpegs for now.
## Post #6
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2012-01-14T11:07:39+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Gibbed tool (unpack VPP) on characters.vpp_pc
Gibbed tool (unpack STR2) on "char".str2_pc
## Post #7
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-01-21T08:56:01+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Hmm that's odd. That precisely doesn't give me the meshes.
## Post #8
- Username: EternaL
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Aug 18, 2010 10:12 pm
- Post datetime: 2012-01-23T18:15:47+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Strange....

An example:

Dragging brianne.str2_pc on gibbed(str2) give me a directory named BRIANNE with 13 files :

1 of those is "brianne.ccmesh_pc"
## Post #9
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-07-20T19:58:26+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

I know this is a bit of a necro, but have been wondering - any updates on this? Has anyone managed to get the UVW parsing into the script?
## Post #10
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-20T21:52:46+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Yes. I have all character models extracted. The level geom which is in the glmesh files, I have yet to finish. Uvs are all half floats. Models are ps2 quality however.
## Post #11
- Username: rexil
- Rank: veteran
- Number of posts: 124
- Joined date: Tue Mar 15, 2011 10:14 pm
- Post datetime: 2012-07-20T23:55:45+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

They don't look that low poly.


Relevant info here [http://www.saintsrowmods.com/forum/inde ... 255/page-4](http://www.saintsrowmods.com/forum/index.php?threads/editing-some-other-files-with-hex-editor.255/page-4)
and
[http://www.saintsrowmods.com/forum/inde ... rmat.1020/](http://www.saintsrowmods.com/forum/index.php?threads/decoding-the-saints-row-3-mesh-format.1020/)

More than a month since the last reply, dunno if they stopped working on it or what.

Maybe it can help you with something. Hope you can finish it SR3 models are pretty nice Imo.
## Post #12
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-21T00:48:18+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Hahaha remember how disappointed with shaundi we were? I finally bought the game and all dlc except the genki cars and there was no hires shaundi to be found. The character models were no problem. Got all 2000 of them or so. But there are 90000+ static models and the control file is more complex for them than they are for the characters and spaceships lol. If anyone wants just a character release...
## Post #13
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-07-21T10:50:23+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

Yeah I noticed the vehicles seem to use a lot of vertex colouring. But a character script would be really really nice. Honestly I'd prefer it over a static mesh one 

So your release would be apreciated.
## Post #14
- Username: Maxunit
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 28, 2010 7:49 am
- Post datetime: 2012-07-21T18:31:30+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

"If anyone wants just a character release..."

Yep, I would love to have the model files from Shaundi  I still had no luck in ripping them from SRTT :/
## Post #15
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-07-21T19:50:14+00:00
- Post Title: Saint Row The Third 3d models [*.gcmesh_pc]

ok i'll release soon. but yeah, in that pic viola doesn't look so bad... but... prepare to be disappointed LOL!
## Post #16
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2012-07-21T20:14:33+00:00
- Post Title: Re: Saint Row The Third 3d models [*.gcmesh_pc]

The mesh definition actually looks fairly decent.
## Post #17
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-10-07T15:21:05+00:00
- Post Title: Re: Saint Row The Third 3d models [*.gcmesh_pc]

...
