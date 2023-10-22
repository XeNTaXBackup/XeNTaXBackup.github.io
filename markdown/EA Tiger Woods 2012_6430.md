## Post #1
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-14T17:45:31+00:00
- Post Title: EA Tiger Woods 2012

I am trying to extract some data from this game.  Progress so far.  I have extracted a series of XEN and TOC files from the ISO.  Reading through the XEN files they had a number of references to 78 DA indicating a zlib compression routine using max compression.  Using a zlib extractor I extracted a number of files some of which appear to be RSF files.  These appear to contain the model data I am after.  I am not sure whether anyone has done any work on RSF files in the past or whether they are a standard or proprietary format to EA. 

Here is the top of the file...


Looking at this information it appears that the header section contains the following 
RSF HEader 
        No Data  
INFO header
    Long 0
    Long 80 (Appears to be overall length of INFO section)
    Long 16 (Length of header data?)
    Long 58 (Length of following filename)
    Data Filename
BILD
    Long 80 (Appears to be overall length of BILD section)
    Long 16 (Length of header data?)
    Long 7 (Length of Author)
    Data Name
    Long 25 (Length of time stamp)
    Data Time Stamp
    Long 11 (Length of date stamp)
    Data Date Stamp
    Padding
GEOM ( At this point I am a little lost as to what the following data is.
VFMT
VFMT
VFMT

This is followed by what appears to be three large sections of data 
STRM
STRM
STRM

Finally towards the bottom of the file is some sort of index perhaps...
Firstly of mesh and texture lists



and finally of boundings


 

I have uploaded the whole file here is someone can help.  [Download Here](http://www.apcd2003.com/img/rsffile.zip)

Any advice or pointers greatly appreciated.
## Post #2
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-16T20:06:12+00:00
- Post Title: EA Tiger Woods 2012

Well I successfully wrote a c# application to extract all the textures but am still a little lost on the 3D model stuff.   Anyone have any idea?
## Post #3
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-17T20:05:05+00:00
- Post Title: EA Tiger Woods 2012

Ok Brief Update.  I have figured out the structure of the RSF file.

Basically it consists of a bunch of files as follows.

Magic
Unknown
Long Length of section
Long Length of Header
Long Length of Data
Long Number of Elements

Parsing this yields the following files
OFNI (Info)
DLIB
MOEG (Geometry)
TEXT (Textures)
RDHS (Shader)
LTAM (Materials)
SGRF (Some sort of Node based bounding)

Now that I have extracted all this stuff does anyone know what I do with them.  Again any advice guidance or pointers will be appreciated.

Andrew
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-17T20:10:31+00:00
- Post Title: EA Tiger Woods 2012

look at the code for Granado Espada or Valkyria Chronicles they are very close to your format and should give you some ideas on what to do.
## Post #5
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-21T01:49:31+00:00
- Post Title: EA Tiger Woods 2012

Thanks for this.  I have written a max script using yours as a base. Using the debugger I have validated that the data appears to be loading correctly.

The script runs without error and then ends.  Am I missing something or should a model load in the screen.

The file I am running this on is located here

[http://www.apcd2003.com/img/file4.zip](http://www.apcd2003.com/img/file4.zip)

Again additional pointers greatly appreciated...Cant thank you enough for the progress to date...

Here is my messy script

```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"Open Tiger Woods Model File" \
types:"Tiger Woods Model File(*.rsf)|*.rsf" \
historyCategory:"Tiger Woods Object Presets"
f = fopen fname "rb"


fn floatSwap2 f = 
(
	i = bit.floatAsInt f
	h = bit.intashex i
	while h.count < 8 do h = "0" + h
	s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
	bit.intAsFloat (bit.hexasint s)
)	
fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
)
fn PrintOffset Var =
(
	local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
	Var
)
fn PrintCount Var =
(
	local Var = Var
print ("This is the Count 0x" + (bit.intAsHex Var) as string)
	Var
)

fn ReadBEword fstream = (
return (bit.swapBytes (readshort fstream #unsigned) 1 2)
)

  	fn convertTo32 input16 = (
 		inputAsInt = input16
 		sign = bit.get inputAsInt 16
 		exponent = (bit.shift (bit.and inputAsInt (bit.hexasint "7C00")) -10) as integer - 16
 		fraction = bit.and inputAsInt (bit.hexasint "03FF")
 		if sign==true then sign = 1 else sign = 0
 		exponentF = exponent + 127
 		--Ouput 32 bit integer representing a 32 bit float
 		outputAsFloat = bit.or (bit.or (bit.shift fraction 13) (bit.shift exponentF 23)) (bit.shift sign 31)
 		--Output Check	
 		return bit.intasfloat outputasfloat
 	)

fn ReadBEHalfFloat fstream = (
return convertTo32(ReadBEword fstream)
)
 

fn ReadBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
)


fn ReadFixedString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)


struct Face_Offset_Struct
(
	ID,Face_Offset
)

struct Vert_Info_Struct
(
	u01,u02,u03,VCount,FCount,n01,u04,VPos,FPos,n02,n03
)
magicsize = 16
moegsize = 20
MRTS_Array = #()
XDNI_Array = #()
fseek f 0x18#seek_set
infosize = ReadLong f

fseek f 0x20#seek_set
modelnamesize = Readlong f
modelname = ReadFixedString f modelnamesize

--break()
fseek f (infosize + magicsize + 8)#seek_set
dlibsize = Readlong f
--break()
fseek f (infosize+magicsize+dlibsize+16)#seek_set

nbrTFMV = Readlong f
regionsize=0
--break()
for t = 1 to nbrTFMV do (
  idstring = ReadFixedString f 4
 
  secsize = Readlong f
  regionsize = secsize+regionsize +8	
  fseek f (infosize+magicsize+dlibsize+moegsize+regionsize)#seek_set
  idstring = ReadFixedString f 4
  if idstring !="TMFV" do(
    regionsize = regionsize+1
   )
  fseek f (infosize+magicsize+dlibsize+moegsize+regionsize)#seek_set
 --break()
)

numobjects = Readlong f
Vert_array = #()
Normal_array = #()
UV_array = #()
Face_array = #()
--break()
for i=1 to numobjects do(
	SecStart = (ftell f)
	idstring = ReadFixedString f 4
	print idstring
	SecHeader = 17
	
	fseek f 0x05#seek_cur
	--break()
	NumVerts = Readlong f
	VertLength = Readlong f
	VertType = Readlong f
	SecSize = VertLength * NumVerts
	
	--break()
	for k=1 to NumVerts do (
		if VertLength == 44 Do (
		vx = Readfloat f
		vy = Readfloat f
		vz = Readfloat f
		tu = Readfloat f
		tv = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		)
		if VertLength == 32 Do (
		vx = ReadBEfloat f
		vy = ReadBEfloat f
		vz = ReadBEfloat f
		tu = Readfloat f
		tv = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		
		)
		if VertLength == 52 Do (
		vx = ReadBEfloat f
		vy = ReadBEfloat f
		vz = ReadBEfloat f
		tu = Readfloat f
		tv = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		uk = Readfloat f
		)
		
		--break()
		
		append Vert_array [vx,vy,vz]
		--append Normal_array [nx,ny,nz]
		append UV_array [tu,tv,0]
	)
	--break()
)
--break()
numobjects = Readlong f
print numobjects
--break()
for i=1 to numobjects do(
	SecStart = (ftell f)
	idstring = ReadFixedString f 4
	print idstring
	SecHeader = 17
	fseek f 0x05#seek_cur
	NumFace = Readlong f
	NumFace = NumFace / 3
	SecSize = (NumFace*2)
	--break()
	append XDNI_Array SecStart
	for k = 1 to NumFace do (
		f1= Readshort f +1
		f2 = Readshort f +1
		f3 = Readshort f +1
		append Face_array [(f1),(f3),(f2)]
		
		
		--break()
	)
	fseek f 0x04#seek_cur
	SecEnd= (ftell f)
	
	--break()
)
break()
msh = mesh vertices:Vert_array faces:Face_array
break()
msh.numTVerts = UV_array.count
break()
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
fclose f


```
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-21T02:06:56+00:00
- Post Title: EA Tiger Woods 2012

what you want to do is store all the offsets of the mesh and index locations then after you parse the file create a loop that loops to the first part of each section

fseek vert1 start #seek_set
read first verts
fseek f face1 start#seek_set
read first faces
build mesh here

next loop
if you notice  all the indecies are based on the vert sections so the id's do not constantly increase into one big array like you have them.
At-least if i am reading your script correctly.
## Post #7
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-21T22:37:41+00:00
- Post Title: EA Tiger Woods 2012

Great.... That got it sort of working.  At least I see something inside MAX now.  I am just looking at the first model in the file of 83 models.  However, clearly I have not got the right pieces in the right places.  What is the best way to figure that out.  I have vert sections that range from 28 byte to 52 byte depending on the model.  They dont appear to all be the same so for example while the 44 byte one clearly starts with x,y,z the 28 one does not have verts at the beginning.  I cant figure out how to tell a normal from a texture coord and when I should look for half floats full floats or shorts even.

Any more advice... I am getting there albeit slowly, but as I said this is the first time I tried to do anything like this.

Ta...Andrew
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-22T00:35:47+00:00
- Post Title: EA Tiger Woods 2012

make sure you reset your array after creating each section
so put the 
vert_array = #()
ext
inside your mesh import loop
## Post #9
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-22T00:53:13+00:00
- Post Title: EA Tiger Woods 2012

Yup understood. I had not done that..   But how do you normally go about figuring out which of the floats are normals and which are UVs Is it just a case of trial and error?  OR is there some sort of rule of thumb?  Tomorrow I will post a couple of pieces to explain.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-22T01:12:57+00:00
- Post Title: EA Tiger Woods 2012

you can look at the data values that will tell you what type of data it is. but if you import different parts as verts in max normals will look like a sphere and uv's will look like the uv map if you set the z to 0.
## Post #11
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-22T19:46:05+00:00
- Post Title: EA Tiger Woods 2012

Quick Follow Up.  The meshes are importing but it seems as if the faces are out.  In other words it is connecting the faces incorrectly.  Is there a method to find out in what order the faces should be
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-22T20:01:16+00:00
- Post Title: EA Tiger Woods 2012

you are importing them as tri list they are most likely tri strip.
## Post #13
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-22T20:27:02+00:00
- Post Title: EA Tiger Woods 2012

ok it looks like the model verts and model faces are not stored in order so I guess somewhere is a listing of the model and where the verts are and where the faces are. Guess I will have to hunt it down

On your post unfortunately I have no idea what that means
## Post #14
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-23T00:11:04+00:00
- Post Title: EA Tiger Woods 2012

tri list means the triangles are stored like this
123
234
345
456
ext

in tri strip they give you

123
then they just give you
4
5
6
and what you assume is the last 2 faces you read are the first 2 of the next triangle
so 123 then i read 4 becomes
234
think of a square made of 2 triangles
you draw the first triangle which is 3 points 1 2 3
now you only need 1 more dot to make the other triangle
4 then you reuse the edge of the triangle they would share.
## Post #15
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-23T11:55:18+00:00
- Post Title: EA Tiger Woods 2012

Thanks for that I understand it now.  I think I had it right it is just that unfortunately mesh order stored in file is not same as face order... Go figure.. So I went through each face section identified the highest face value and then searched for a mesh with that number of verts and here is what I got


So my next question is how do I go about bringing in the mappings so when I apply a texture to it it works.  Thanks again for all your help, you have no idea the amount of time you have saved me yet allowing me to somewhat figure it out.

A
## Post #16
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-24T18:24:18+00:00
- Post Title: Re: EA Tiger Woods 2012

I have successfully written a C# program that basically figures out which mesh matches which face materials and exports them all out as OBJ files

eg..



I have extracted a set of tu and tv coordinates which are included along with a texture in the obj / mtl files.  However, when I import the object the mapping has not taken form.  I also notice that I do not have a mapping modifier in 3ds max.  Is this normal or if I added UV should I have this.  Will I have to remap every object?  I am guessing I am doing something wrong in MAX here.  

Additional advice appreciated
## Post #17
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-24T21:33:31+00:00
- Post Title: Re: EA Tiger Woods 2012

ok getting there slowly



I am guessing this is a problem with the way I am mapping faces to tverts.  Alternatively could it be due to differences in the direction of the v value in the tverts.

Any thoughts?
## Post #18
- Username: Mogulbasher
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Oct 24, 2006 4:13 am
- Post datetime: 2011-04-24T21:38:38+00:00
- Post Title: Re: EA Tiger Woods 2012

That was it, guess the v coordinates were specific to DirectX.  After substituting 1-tv I get this... Unbelievable...
## Post #19
- Username: Jacoby1218
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 27, 2016 6:01 am
- Post datetime: 2021-10-12T12:43:48+00:00
- Post Title: Re: EA Tiger Woods 2012

Necroing this old post, specifically because this seems to be a common format among ea sports game. Nascar 08/09 use it ([https://zenhax.com/viewtopic.php?f=5&t= ... 981#p66981](https://zenhax.com/viewtopic.php?f=5&t=11621&p=66981#p66981)), and so do the madden/ncaa games. if we could figure out how to open this, we might be able to mod more games
