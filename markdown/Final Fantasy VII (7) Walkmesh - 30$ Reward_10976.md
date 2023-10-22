## Post #1
- Username: MiLO83
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 21, 2013 6:23 am
- Post datetime: 2013-11-21T00:45:16+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

Hi,
I have $15 EDIT!: $30 ready to send via PayPal.
I have loaded the vertices, but there is no poly data.
I need to build a poly between every 3 verts this maxscript loads.
Here is the maxscript.

```
types:"FF7 Field File (*.dec)|*.dec|"
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
fn readBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)
fn readBEshort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 1 2
return short
) 
Face_array=#()
Vert_array=#()
vert_count = 0
if fPKG != undefined then (
   
   f = fopen fPKG "rb"
	fseek f 22 #seek_set -- Pointer to mesh data offset. 
	entryPoint =readshort f  -- Read that pointer
	print entryPoint as string
fseek f entryPoint #seek_set -- Go to pointer offset.

count=900--random number that works, gets extra data overhead. 
fseek f 16 #seek_cur -- Pointer for count is in this 16 byte chunk somewhere.

for x = 1 to count do(

vx=readshort  f as integer
--	Print ("vx = "+ vx as string)
vy=readshort  f as integer
--	Print ("vy = "+ vy as string)
vz=readshort  f as integer
--	Print ("vz = "+ vz as string)
res=readshort  f
--	Print ("Res = "+ res as string)
append Vert_array [vx+1, vy+1, vz+1]
		--Print (vx as string + " , " + vy as string + " , " + vz as string)
append Face_array [vert_count+1,vert_count+3,vert_count+2]
)	

msh = mesh vertices:Vert_array faces:Face_array
--meshop.createPolygon msh Vert_array smGroup:0 matID:1
--setNumCPVVerts msh msh.numverts
msh.name="WalkMesh"

Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
	
gc()
fclose f
   
) else (
   clearlistener()
   messageBox "No file was selected." title:"FF7 Walkmesh Importer"
)
```


Here are some random files which all load so far.
[http://www.mylesjohnston.com/field.zip](http://www.mylesjohnston.com/field.zip)

I need the polygons filled automatically.

Here's the File Format Docs.
[http://wiki.qhimm.com/view/FF7/Field#Fi ... t_.28PC.29](http://wiki.qhimm.com/view/FF7/Field#Field_Format_.28PC.29) 

And here's the specific data I'm after's Sub-Doc.
[http://wiki.qhimm.com/view/FF7/Field/Walkmesh](http://wiki.qhimm.com/view/FF7/Field/Walkmesh)

I will reward $7.50 for making the script fill the the polys properly.
I will reward the other $7.50 for creating and aligning the scene camera with THIS data.
[http://wiki.qhimm.com/view/FF7/Field/Camera_Matrix](http://wiki.qhimm.com/view/FF7/Field/Camera_Matrix)

The camera doesnt have to be perfect, just at the correct angle, I can move it closer or further by hand to match the background.
If filling the polys takes more than say 3 hours, or is actually a hassle (Shouldn't) I'll reward the whole $15, but you gotta post in this thread that you're taking the whole $15 cuz thats all the money I have on PayPal for a few days.

Sorry for a request as first post, as I learn I will be working on more model formats.
(Already just donated $7.50, hopefully I can get some help with the rest of this giftcard lol.)

Thanks,
     - Myles

FILES ARE FROM OLD DEMO YET STILL COMPATIBLE.
## Post #2
- Username: MiLO83
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 21, 2013 6:23 am
- Post datetime: 2013-11-23T04:08:11+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

Seriously? It's been 3 days?
Do I need to offer more money?
It should be as easy as a line of code to build a polygon from every 3 loaded verts in order.
Tell me that 1 line, or as many lines as it takes, and i'll send you $15.
If you know why nobody is replying please tell me!
And I forgot to put (Request) in the topic, if a mod could fix that.

   - Myles
## Post #3
- Username: dainazinas
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-23T04:28:29+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

just add this at the end of your script

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
## Post #4
- Username: MiLO83
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 21, 2013 6:23 am
- Post datetime: 2013-11-23T06:16:11+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

Thanks Chrrox, (The Legend!)
but I get this error...

-- Runtime error: buildTVFaces: mesh has no texture vertices - $Editable_Mesh:WalkMesh @ [0.000000,0.000000,0.000000]

Can you please download the sample files and give a working script?
It's $15 man, probably take less than 20 minutes. I know you're 1337!
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-23T06:17:53+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

just append 0's to an array called
0,0
UV_array=#()
that is the same size as the vertex array.
## Post #6
- Username: MiLO83
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 21, 2013 6:23 am
- Post datetime: 2013-11-23T08:06:04+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

Huh?
Can you just modify the script?
Sounds like you know what to do!
I'll send you the $15, just edit the script with your ideas and post the script here.
I have never even coded maxscript before, I was following mariokart64n's video tutorials to get this far...

   - Myles
## Post #7
- Username: Troopermanaic
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-11-23T14:53:01+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

chrrox check this out man, I got these cheeseburgers, they some double cheeseburgers! Man I'll suck yo' dick! Come on man just hook a nigga's UV array up man!
## Post #8
- Username: MiLO83
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 21, 2013 6:23 am
- Post datetime: 2013-11-23T16:43:26+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

Guuud waaaaaaan.
I wood liek to by a ambeg geeerrrrr.
DUR BURRRGGGGER!
Mr.Adults, I tried his suggestions and got runtime errors. I have never written maxscript aside from following mariokart64n's tutorial.
I'm not familiar with its syntax or functions. I will obviously go over chrrox's code and analyze it myself to learn from,
but I've already offered google 2 cheeseburgers and *EhEM!* sucked its d!ck. Google does not seem to me to have much info on reading files to meshes in maxscript.
This model format doesn't have any faces or UV or normals. It is a collision mesh from 1997. I obviously tried myself, and would ask questions without offering money, but I
have a long list of other things i'm working on. Search "Moogle Earth" on Google Play Store for Android. I made that, and it's an old version. I am currently adding new features.

   - Myles

Edit : Here's the current script.

```
types:"FF7 Field File (*.dec)|*.dec|"
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
fn readBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)
fn readBEshort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 1 2
return short
) 
Face_array=#()
Vert_array=#()
Normal_array=#()
UV_array=#()
vert_count = 0
if fPKG != undefined then (
   
   f = fopen fPKG "rb"
	fseek f 22 #seek_set -- Pointer to mesh data offset. 
	entryPoint =readshort f  -- Read that pointer
	print entryPoint as string
fseek f entryPoint #seek_set -- Go to pointer offset.

count=900--random number that works, gets extra data overhead. 
fseek f 16 #seek_cur -- Pointer for count is in this 16 byte chunk somewhere.

for x = 1 to count do(

vx=readshort  f as integer
--	Print ("vx = "+ vx as string)
vy=readshort  f as integer
--	Print ("vy = "+ vy as string)
vz=readshort  f as integer
--	Print ("vz = "+ vz as string)
res=readshort  f
--	Print ("Res = "+ res as string)
append Vert_array [vx+1, vy+1, vz+1]
		--Print (vx as string + " , " + vy as string + " , " + vz as string)
append Face_array [vert_count+1,vert_count+3,vert_count+2]
	append UV_array [0.0,0.0,0.0]
		append Normal_array [0.0,0.0,0.0]
)	


--meshop.createPolygon msh Vert_array smGroup:0 matID:1
--setNumCPVVerts msh msh.numverts

gc()
fclose f
msh = mesh vertices:Vert_array faces:Face_array
setNumCPVVerts msh msh.numverts
msh.name="WalkMesh"
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j] 

)
```
## Post #9
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2013-11-27T04:25:28+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

It appears that some of my script that I wrote nearly a year ago has helped you get a start on FF7 models, no?

[viewtopic.php?f=16&t=9977](http://forum.xentax.com/viewtopic.php?f=16&t=9977)

You're welcome
## Post #10
- Username: MiLO83
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 21, 2013 6:23 am
- Post datetime: 2013-11-27T21:06:53+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

Actually I was following MarioKart64n's Youtube tutorials...
I AM NOW RAISING THE REWARD TO $30 VIA PAYPAL,
OR I CAN BUY YOU A $25 VISA/MASTERCARD GIFTCARD YOU CAN REGISTER AND SPEND ONLINE.
Just in time for the Holidays!

    - Myles
## Post #11
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2013-12-13T02:05:21+00:00
- Post Title: Final Fantasy VII (7) Walkmesh - 30$ Reward

IDK if this helps you but this is how I build mesh for any game

```
	try (
		msh = mesh \
		vertices: Vertex_array[MDL] \
		tverts: TextureVerts_array[MDL] \
		faces: Index_array[MDL] \
		scale: Size_array[MDL] \
		dir: MeshRotation_array[MDL] \
		pos: MeshLocation_array[MDL] \
		name: MeshName_array[MDL]

		buildTVFaces msh

		for UVF = 1 to msh.numfaces do (
			try (
				setTVFace msh UVF (getFace msh UVF)
			)
			catch(
				format "import of UVF % failed\n" UVF
			)
		)
	)
	catch(
		format "import of MDL % failed\n" MDL
	)
)

```

ALSO I think your face loop is wrong, heres mine for example

```
    f1=ReadShort f +1 --Face 1
    f2=ReadShort f +1 --Face 2
    f3=ReadShort f +1 --Face 3
    append Face_array[f3,f2,f1]
)

```


MrAdults I thank you for referencing the funniest line in one of my old favorite 90's movies "Don't be a menace to society while drinking juice in the hood"
