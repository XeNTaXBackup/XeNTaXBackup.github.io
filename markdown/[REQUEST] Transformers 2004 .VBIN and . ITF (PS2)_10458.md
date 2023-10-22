## Post #1
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-05-26T12:08:34+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

OK so from my own knowledge, i have been able to determine the possible options on what each of these file types are, the .VBIN most likely contains mesh and rigging data, as there is a quickbms script (found at [http://ps23dformat.wikispaces.com/How+To+Extract+Models](http://ps23dformat.wikispaces.com/How+To+Extract+Models) ), that allows you to convert the level geometry (GEOMETRY.MESH.VBIN) into several, kind of messed up .3ds files, however the current quickbms script only supports the .mesh.vbin files which only usualy includes the level geometry and not NPC's enemies or others gameplay 3d assets. The .ITF files are most likely texture files, as in the games files, there are a set of these after a .vbin, for example, JETSNIPER.VBIN would then be followed by several .ITF file like JETWING.ITF etc...

I have included two sample files for people to look at, but if more are needed and you own the game, the files TFA.ZIP and TFA2.ZIP can be opened in any archiving software and extracted, these contain all the relevant files for analysis.

Sample Files:
.VBIN: [http://www.mediafire.com/download/ah4ll ... NIPER.VBIN](http://www.mediafire.com/download/ah4ll14pdbzgnrn/JETSNIPER.VBIN)
.ITF: [http://www.mediafire.com/download/f0jb7 ... S_WING.ITF](http://www.mediafire.com/download/f0jb7hc444dd7ac/JETS_WING.ITF)

I do hope someone picks this request up soon as I have done all i can with these files and i really want to see what they contain and if they are useable/convertable to a useable format.
## Post #2
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T16:06:50+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Would someone kindly pick this up soon-ish? these formats have bee driving me mad and ive come no closer to an answer on how to convert/view em
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T17:07:45+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

have you attempted to convert them?
there is plain text labeling the parts of the file.
~PositionArray
this is followed by a series of floats.
then there is also
~IndexArray
followed by what looks to be faces.
would be a good learning experience for you try some of the tutorials in the tutorial section.
## Post #4
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T17:54:47+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

I have tried but my current knowledge of output formats is very limited, so the files i had output would cause errors in 3ds max and be essentially useless.
I need to do some more reading on how this works to better understand the process before I attempt it again, hence my asking on the forums if anyone can have a crack at it.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T17:57:58+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

[viewtopic.php?f=29&t=7760](http://forum.xentax.com/viewtopic.php?f=29&t=7760)
## Post #6
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T18:03:53+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

> Reply from chrrox
>
> viewtopic.php?f=29&t=7760
Thx for the link, im gonna read through that and attempt it again, but gonna leave this open in-case anyone does try.
## Post #7
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T18:43:10+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

OK I'm stuck, Ive got noesis to add the file type to its file listing using that tutorial, but I cant get beyond that it still recognizes it as an unknown file type. I dont know what to put as the header or how I should proceed with the script...
Chrrox if you can help me i would really appreciate it, this is what i have so far:

```

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("Transformers 2004 PS2", ".VBIN")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "464953487E5363656E654E6F64650001"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1
```
## Post #8
- Username: flarespire
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T18:52:03+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

try this

```
import noesis
import rapi

def registerNoesisTypes():
   handle = noesis.register("Transformers 2004 PS2", ".VBIN")
   noesis.setHandlerTypeCheck(handle, t2004CheckType)
   noesis.setHandlerLoadModel(handle, t2004LoadModel) #see also noepyLoadModelRPG
   noesis.logPopup()
   return 1

NOEPY_HEADER = "FISH"

#check if it's this type based on the data
def t2004CheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def t2004LoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1
```
## Post #9
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T18:57:14+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Thanks Chrrox, that got it to recognise, if i get stuck again, ill ask for your assistance again ok?
## Post #10
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T19:09:08+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

How does this look? this is all still pretty new to me, so its gonna take me time to get used to.

```
import noesis
import rapi

def registerNoesisTypes():
   handle = noesis.register("Transformers 2004 PS2", ".VBIN")
   noesis.setHandlerTypeCheck(handle, t2004CheckType)
   noesis.setHandlerLoadModel(handle, t2004LoadModel) #see also noepyLoadModelRPG
   noesis.logPopup()
   return 1

NOEPY_HEADER = "FISH"

#check if it's this type based on the data
def t2004CheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def t2004LoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1
   
   #load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   bs.seek(0x1C, NOESEEK_ABS) #Seek to header info
   hdrInfo = bs.read("iii")
   print(hdrInfo)
   bs.seek(0x32C, NOESEEK_REL) #Seek past junk
   VCount = bs.read("i")
   bs.seek(0x5AB4C, NOESEEK_REL) #Seek past junk
   FCount = bs.read("i")
   bs.seek(0x5AD44, NOESEEK_ABS) #Seek to File Start
   TexNames = []
   for i in range(0, hdrInfo[0]):
      TexNames.append (bs.readBytes(40).decode("ASCII").rstrip("\0"))
   print(TexNames)
   rapi.rpgClearBufferBinds()   
   return 1
```
## Post #11
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T20:09:47+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Well, im at an impass, im not sure how to set the different addresses for the next part of the script up, as the .VBIN format is a little weird. Chrrox, if you could take a look it would really help me out and i may be able to understand what to do in the future.
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-09T20:17:50+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

need more samples.
## Post #13
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-09T20:30:44+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

> Reply from chrrox
>
> need more samples.
ill send you the .ZIP's from the disc in a pm, the models are under the "ANIMATION" folder (extract both to the same dir)
## Post #14
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-10T15:58:08+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

In-case anyone else wants to take a crack at this, here is the BMS script to extract TFA.ZIP and TFA2.ZIP

```
Math test = 0 ;
GoTo 0x0 0 ;
SavePos base 0 ;
Do ;
GoTo base 0 ;
Get test Long 0 ;
If test = 101010256 ;
CleanExit ;
EndIF ;
GoTo base 0 ;
GoTo 0xA 0 SEEK_CUR ;
Get c Byte 0 ;
GoTo base 0 ;
GoTo 0x1C 0 SEEK_CUR ;
Get namelength Long 0 ;
GoTo base 0 ;
GoTo 0x2A 0 SEEK_CUR ;
Get toffset Long 0 ;
GetDString name namelength 0 ;
SavePos base 0 ;
GoTo toffset 0 ;
GoTo 0x12 0 SEEK_CUR ;
Get zsize Long 0 ;
Get size Long 0 ;
Get nz Short 0 ;
GoTo toffset 0 ;
GoTo 0x1E 0 SEEK_CUR ;
GoTo nz 0 SEEK_CUR ;
SavePos offset 0 ;
If c = 8 ;
CLOG name offset zsize size 0 ;
Else ;
Log name offset size 0 ;
EndIF ;
While test != 101010256 ;





```

If you want to get a hold of TFA.ZIP and TFA2.ZIP pm me OR copy it from the game disc/iso yourselves.
IMPORTANT: be sure to extract both files to the same directory!
## Post #15
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-11T19:21:42+00:00
- Post Title: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Chrrox have you had any luck getting the offsets set up? I've tried numerous time and I haven't made any progress yet...
## Post #16
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-16T20:40:03+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Hmm, each file seems to have slightly different offsets, i wonder if finding a common offset for each part might be worth a try?
## Post #17
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-06-30T16:56:49+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

well after repeated attempts, ive come up short... i know that the different sectors of the file are in roughly the same place, but i cant seem to find a common offset, can someone please tell me if the python script allows for multiple offsets or if theres a way to set it up to use a common offset?
## Post #18
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2013-08-30T23:48:34+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Here is a script that will convert the meshes from the .VBIN, and .BIN files (You can save time by running the script on the entire decompressed zipped file, so that the script converts all the meshes at once)
Here is an example of a character mesh (some type of car):
[img]ps23dformat.wikispaces.com/file/view/TransformersBot.jpg[/img]
New (August 2013) Script for Characters:
[http://ps23dformat.wikispaces.com/file/ ... hTo3ds.bms](http://ps23dformat.wikispaces.com/file/view/TransformersVBINbinMeshTo3ds.bms)

```
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
log MEMORY_FILE7 0 0 ;
log MEMORY_FILE8 0 0 ;
log MEMORY_FILE9 0 0 ;
log MEMORY_FILE10 0 0 ;
Get Q ASIZE 0 ;
Math number = 0 ;
For T = 0 < Q ;
Math number += 1 ;
findloc OFFSET string "\x7E\x50\x6F\x73\x69\x74\x69\x6F\x6E\x41\x72\x72\x61\x79\x00\x00" 0 0 ;
If OFFSET = 0 ;
Math T = Q ;
Math T += 1 ;
Math ttest = 0 ;
ELSE ;
GoTo OFFSET 0 ;
SavePos Start 0 ;
Put Start Long MEMORY_FILE4 ;
GoTo OFFSET 0 ;
GoTo 0x08 0 SEEK_CUR ;
Get size Long 0 ;
SavePos null 0 ;
EndIF ;
Next T ;
Put Q Long MEMORY_FILE4 ;


Get listf ASIZE MEMORY_FILE4 ;
If listf = 0 ;
CleanExit ;
EndIF ;
Math spyrodragon = listf ;
Math spyrodragon /= 4 ;
Math spyrodragon -= 1 ;
Math rubyfox = 0 ;
Math diafox = 0 ;
Math rfv = 0 ;
For Y = 1 To spyrodragon ;
log MEMORY_FILE7 0 0 ;
log MEMORY_FILE8 0 0 ;
log MEMORY_FILE1 0 0 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
GoTo rubyfox MEMORY_FILE4 ;
Get start Long MEMORY_FILE4 ;
SavePos rubyfox MEMORY_FILE4 ;
Get size Long MEMORY_FILE4 ;
Math size -= start ;
Log MEMORY_FILE7 start size 0 ;
GoTo 0 MEMORY_FILE7 ;
Math count = 0 ;
Math gt = 0 ;
Math Qprime = 0 ;
Math red = 0 ;
SavePos found MEMORY_FILE7 ;
GoTo 0 MEMORY_FILE7 ;
GoTo 0x10 MEMORY_FILE7 SEEK_CUR ;
Get gee Long MEMORY_FILE7 ;
SavePos gvertex MEMORY_FILE7 ;
Math gee -= 4 ;
Math gee /= 12 ;
Math deedee = 0 ;
For dv = 1 To gee ;
GoTo gvertex MEMORY_FILE7 ;
Get Type1 Long MEMORY_FILE7 ;
Get Type2 Long MEMORY_FILE7 ;
Get Type3 Long MEMORY_FILE7 ;
SavePos gvertex MEMORY_FILE7 ;
GoTo deedee MEMORY_FILE2 ;
Put Type1 Long MEMORY_FILE2 ;
Put Type2 Long MEMORY_FILE2 ;
Put Type3 Long MEMORY_FILE2 ;
SavePos deedee MEMORY_FILE2 ;
Next dv ;





For T = 0 < size ;
GoTo found MEMORY_FILE7 ;
findloc OFFSETT string "\x7E\x49\x6E\x64\x65\x78\x41\x72\x72\x61\x79\x00\x00" MEMORY_FILE7 0 ;
If OFFSETT = 0 ;
Math T = size ;
Math twotest = 1 ;
EndIF ;
If OFFSETT != 0 ;
GoTo OFFSETT MEMORY_FILE7 ;
GoTo 13 MEMORY_FILE7 SEEK_CUR ;
SavePos found MEMORY_FILE7 ;
Put found Long MEMORY_FILE1 ;
EndIF ;
Next T ;
Get mqa ASIZE MEMORY_FILE1 ;
Math mqa /= 4 ;
Math greenfox = 0 ;
For jjj = 1 To mqa ;
GoTo gt MEMORY_FILE1 ;
Get found long MEMORY_FILE1 ;
SavePos gt MEMORY_FILE1 ;
GoTo found MEMORY_FILE7 ;
Get scope Long MEMORY_FILE7 ;
SavePos baseface MEMORY_FILE7 ;
Math foxskin = found ;
Math foxskin += scope ;
Math dragonfox = scope ;
Math dragonfox -= 4 ;
Math dragonfox /= 2 ;
Math dragonfox -= 2 ;
Do ;
GoTo baseface MEMORY_FILE7 ;
Get facecount Short MEMORY_FILE7 ;
SavePos basedeer MEMORY_FILE7 ;
Math redfox = facecount ;
Math redfox *= 2 ;
Math redfox += basedeer ;
Math baseface = redfox ;
Math rfc = facecount ;
Math rfc -= 2 ;
Math kin = rfc ;
Math gng = facecount ;
Math gng *= 2 ;
Math gng += basedeer ;
Math traptiger = 0 ;
Math nogo = 1 ;
If gng > foxskin ;
Math greenfox = 0 ;
log MEMORY_FILE3 0 0 ;
Math traptiger = 1 ;
Math rfc = 0 ;
Math baseface = foxskin ;
GoTo found MEMORY_FILE7 ;
Get null Long MEMORY_FILE7 ;
SavePos basedeer MEMORY_FILE7 ;



EndIF ;




For grayfox = 1 To traptiger ;
For extra = 1 To dragonfox ;
GoTo basedeer MEMORY_FILE7 ;
Get Type1 Short MEMORY_FILE7 ;
SavePos basedeer MEMORY_FILE7 ;
Get Type3 Short MEMORY_FILE7 ;
Get Type5 Short MEMORY_FILE7 ;

Math dragontest = 0 ;
If Type1 = Type3 ;
Math dragontest += 1 ;
EndIF ;

If Type1 = Type5 ;
Math dragontest += 1 ;
EndIF ;

If Type3 = Type5 ;
Math dragontest += 1 ;
EndIF ;


If dragontest = 0 ;
GoTo greenfox MEMORY_FILE3 ;
Put Type1 Short MEMORY_FILE3 ;
Put Type3 Short MEMORY_FILE3 ;
Put Type5 Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos greenfox MEMORY_FILE3 ;


GoTo greenfox MEMORY_FILE3 ;
Put Type1 Short MEMORY_FILE3 ;
Put Type5 Short MEMORY_FILE3 ;
Put Type3 Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos greenfox MEMORY_FILE3 ;
EndIF ;
Next extra ;
Next grayfox ;














For foxes = 1 To rfc ;
GoTo basedeer MEMORY_FILE7 ;
Get Type1 Short MEMORY_FILE7 ;
SavePos basedeer MEMORY_FILE7 ;
Get Type3 Short MEMORY_FILE7 ;
Get Type5 Short MEMORY_FILE7 ;

Math dragontest = 0 ;
If Type1 = Type3 ;
Math dragontest += 1 ;
EndIF ;

If Type1 = Type5 ;
Math dragontest += 1 ;
EndIF ;

If Type3 = Type5 ;
Math dragontest += 1 ;
EndIF ;


If dragontest = 0 ;
GoTo greenfox MEMORY_FILE3 ;
Put Type1 Short MEMORY_FILE3 ;
Put Type3 Short MEMORY_FILE3 ;
Put Type5 Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos greenfox MEMORY_FILE3 ;


GoTo greenfox MEMORY_FILE3 ;
Put Type1 Short MEMORY_FILE3 ;
Put Type5 Short MEMORY_FILE3 ;
Put Type3 Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos greenfox MEMORY_FILE3 ;
EndIF ;
Next foxes ;
While baseface < foxskin ;




Next jjj ;














Get Zw3 ASIZE MEMORY_FILE3 ;
Math Zf3 = Zw3 ;
Math Zf3 /= 8 ;
Get Zw2 ASIZE MEMORY_FILE2 ;
Math Zf2 = Zw2 ;
Math Zf2 /= 12 ;
Math FaceNumber = Zf3 ;
Math VertexNumber = Zf2 ;
Math Snake = VertexNumber ;
Math Snake *= 12 ;
Math Dragon = FaceNumber ;
Math Dragon *= 8 ;
Math Sum = Dragon ;
Math Sum += Snake ;
Math QQQ = 60 ;
Math QQQ += Snake ;
Math QQ = 52 ;
Math qaz = 0 ;
Math wsx = 0 ;
Math hqw = Sum ;
Math hqw += 60 ;
Math bearit = 0 ;
Log MEMORY_FILE8 0 0 ;
For bear = 1 To hqw ;
GoTo bearit MEMORY_FILE8 ;
Put 0 Byte MEMORY_FILE8 ;
SavePos bearit MEMORY_FILE8 ;
Next bear ;


For Vertex = 0 < Zw2 ;
GoTo qaz MEMORY_FILE2 ;
Get D byte MEMORY_FILE2 ;
SavePos qaz MEMORY_FILE2 ;
GoTo QQ MEMORY_FILE8 ;
Put D Byte MEMORY_FILE8 ;
SavePos QQ MEMORY_FILE8 ;
Next Vertex ;
For Face = 0 < Zw3 ;
GoTo wsx MEMORY_FILE3 ;
Get D byte MEMORY_FILE3 ;
SavePos wsx MEMORY_FILE3 ;
GoTo QQQ MEMORY_FILE8 ;
Put D Byte MEMORY_FILE8 ;
SavePos QQQ MEMORY_FILE8 ;
Next Face ;
GoTo 0 MEMORY_FILE8 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum ;
Math M += 60 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x0A ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 44 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 38 ;
Put M Long MEMORY_FILE8 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x72 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6F ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6A ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = Sum 
Math M += 22 ;
Put M Long MEMORY_FILE8 ;
Set M Byte 0x10 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = Snake ;
Math M += 8 ;
Put M Long MEMORY_FILE8 ;
Math M = VertexNumber ;
Put M Short MEMORY_FILE8 ;
Math JumpJump = Snake ;
Math JumpJump += 52 ;
GoTo JumpJump MEMORY_FILE8 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE8 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE8 ;
Math M = FaceNumber ;
Math M *= 8 ;
Math M += 8 ;
Put M Long MEMORY_FILE8 ;
Math M = FaceNumber ;
Put M Short MEMORY_FILE8 ;
Get purpledragon ASIZE MEMORY_FILE8 ;
Get name FILENAME 0 ;
string name += . ;
string name += Y ;
string name += .3ds ;
Log name 0 purpledragon MEMORY_FILE8 ;
Next Y ;
```
## Post #19
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2013-08-30T23:58:36+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Thx for the new script, the version of this i had only did level geometry, now if only we could convert the ITF files....

I've done some tests and they really need to adjust that script so that it gets the models in t-pose and doesnt split it into seperate .3ds files which all default to pos 0, 0, 0.
## Post #20
- Username: Kiriller12
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Sep 07, 2016 8:57 pm
- Post datetime: 2017-07-01T19:23:32+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Did someone understand how to convert .itf texture file?
## Post #21
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-02-19T18:32:11+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Anyone got the other bms for extract the main bin files. Ty. Also not convert persay but you can get at the textures using Textool fairly easy then apply them to the converted models all the same.
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-25T02:23:44+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

> Reply from flarespire
>
> .ITF: http://www.mediafire.com/download/f0jb7 ... S_WING.ITF



JETS_WING_ITF.png (46.82 KiB) Viewed 258 times
## Post #23
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2018-02-25T15:01:03+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Now, mind providing a mirror to that program? it doesn't seem to be available anywhere
## Post #24
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-25T15:38:03+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

i remember posting this here before but here is link to the link   
[viewtopic.php?p=127912#p127912](http://forum.xentax.com/viewtopic.php?p=127912#p127912)

if you post more samples i might could make a Noesis python script to automate the process.
## Post #25
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-02-26T15:15:58+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Another method is the Texmod way. That way you can select and see exactly what textures go where and it automatically converts them to more flexible format.
## Post #26
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2018-02-27T03:45:23+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

oh nice, I still have the ENTIRE disc extractedif you need ITF samples I can make you a package of em, also, any chance of combining it with whats in the BMS script earlier in the thread to make it so Noesis can view the models with the textures?
## Post #27
- Username: SickAlice
- Rank: advanced
- Number of posts: 52
- Joined date: Mon Jul 23, 2012 9:02 am
- Post datetime: 2018-03-02T05:19:17+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Say it before and will again this is such an awesome community, people behave the way community members should and with equal mindfulness. TY to anyone who has and will help me with requests. Side note someone should try and put together a depot of the lost files from the PS2 site. I dunno about anyone else but it was sudden on my end, I was on the site then went on a vacation trip and came back to the empty stub bookmark. There were way too many useful things there to lose spontaneously.
## Post #28
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2018-03-10T19:20:18+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

ok I have a full file repo .zip for this game set up if anyone wants to take a better look at the formats and maybe write a plugin, ill post the link here, however, if this post does get chopped by the mod axe, please send me a PM for the link: [https://drive.google.com/open?id=124xZq ... 7cLNiv3rrC](https://drive.google.com/open?id=124xZqpcSvcTslpWiFRubD97cLNiv3rrC)
## Post #29
- Username: bullettrain
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 31, 2018 8:35 pm
- Post datetime: 2018-07-31T14:05:26+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Hi guys, new member here, and slight bump to the thread!

Editing my previous post, I've been able to use Console Texture Explorer to recreate a good chunk of the background files from the retail game and a recently uncovered early version, which are stored as ITF Texture files. 

There's a few that I'm stuck on, and it'd be great to get a better understanding of how CTE actually reads the files for reconstruction.

So, using file size as a starting point, I recognise that I can't recreate data outside of the file size limit, instead using the Graphics Offset to make up the limit, as well altering the BPP. All the files so far have fallen under Palette Offset of 60, as noted earlier in the thread. There's two file sets so far that seem to be exceptions to the rule.

The First has a file size of 786492, which using CTE, seems to be outside of workable range to achieve the correct dimensions. Secondly the Palette offset for this and another file are not the standard 60. So, how would I be able to determine the appropriate offset in these case? Would Notepad++ or a Hex Editor help to determine the offset?
[ATARI.bmp](https://xentaxbackup.github.io/file/14822_ATARI.bmp)
## Post #30
- Username: lpriefer01
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Sep 06, 2020 6:40 am
- Post datetime: 2021-03-06T07:18:40+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

> Reply from chrrox ↑Mon Jun 10, 2013 2:52 am at Mon Jun 10, 2013 2:52 am
>
> 
try this
Code: Select allfrom inc_noesis import *
import noesis
import rapi

def registerNoesisTypes():
   handle = noesis.register("Transformers 2004 PS2", ".VBIN")
   noesis.setHandlerTypeCheck(handle, t2004CheckType)
   noesis.setHandlerLoadModel(handle, t2004LoadModel) #see also noepyLoadModelRPG
   noesis.logPopup()
   return 1

NOEPY_HEADER = "FISH"

#check if it's this type based on the data
def t2004CheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def t2004LoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1

so this for me only makes noesis display the files in the in program explorer they wont preview or export
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-06T12:52:41+00:00
- Post Title: Re: [REQUEST] Transformers 2004 .VBIN and . ITF (PS2)

Afaics there is NO ready-to-use Noesis script for .vbin in this thread.

You could use the quickbms script from FurryFan some posts above as of Sat Aug 31, 2013:

> Reply from FurryFan ↑Sat Aug 31, 2013 7:48 am at Sat Aug 31, 2013 7:48 am
>
> 
(creates .3ds files, but without uvs, as mostly)
.



JETSNIPER-VBIN.png (62.6 KiB) Viewed 39 times
