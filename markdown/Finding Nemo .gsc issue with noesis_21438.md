## Post #1
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-11-27T11:24:36+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

hi, i'm having a issue. by trying to write a file format for *.gsc with the filesize. when i type in bs.writeInt (0x00000008+=1) it gets me a error in noesis. and the plus and equal doesn't exist in noesis for some reason. i want it to do it automatically so it will say that. i can't write a filesize in until noesis lets me put += so it will add up to 1 only, but it doesn't exist for some reason.
here the incompleted bms script that i got from *.3ds website, i want to convert it to noesis for *.gsc

```
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE4 0 0 ;
log MEMORY_FILE5 0 0 ;
log MEMORY_FILE6 0 0 ;
log MEMORY_FILE7 0 0 ;
GoTo 0 0 ;
Math count = 0 ;
Math gt = 0 ;
Math Qprime = 0 ;
Math werevulpine = 0 ;
Math red = 0 ;
Math gin = 0 ;
SavePos found 0 ;
Get QT ASIZE 0 ;


For T = 0 < QT ;
GoTo found 0 ;
findloc OFFSET string "\x03\x01\x00\x01\x03\x80" 0 0 ;
If OFFSET = 0 ;
Math t = QT ;
Math twotest = 1 ;
EndIF ;
If OFFSET != 0 ;
GoTo OFFSET 0 ;
GoTo 6 0 SEEK_CUR ;
Get onetest Byte 0 ;
Get twotest Byte 0 ;
SavePos found 0 ;
EndIF ;
If twotest = 108 ;
Put count Long MEMORY_FILE1 ;
Math count += onetest ;
Math foxcount = count ;
Math foxcount -= 1 ;
Put foxcount Long MEMORY_FILE1 ;
Put onetest Long MEMORY_FILE1 ;
Put found Long MEMORY_FILE1 ;
Put found Long MEMORY_FILE4 ;
EndIF ;
Next T ;




Get mqa ASIZE MEMORY_FILE1 ;
If mqa = 0 ;
CleanExit ;
EndIF ;
Math mqa /= 16 ;




Math logic = mqa ;
Math logic -= 1 ;
Put 1 Long MEMORY_FILE5 ;
For qjk = 1 To logic ;
GoTo gin MEMORY_FILE4 ;
Get zlow long MEMORY_FILE4 ;
SavePos gin MEMORY_FILE4 ;
Get zhigh long MEMORY_FILE4 ;
Math ztest = zhigh ;
Math ztest -= zlow ;
If ztest > 0x500 ;
Put qjk Long MEMORY_FILE5 ;
EndIF ;
Next qjk ;
Math logic += 1 ;
Put logic Long MEMORY_FILE5 ;

Get fivfiv ASIZE MEMORY_FILE5 ;
Math fivfiv -= 4 ;
Math fivfiv /= 4 ;







Math acera = 0 ;
For hs = 1 To fivfiv ;
GoTo acera MEMORY_FILE5 ;
Get zeblow long MEMORY_FILE5 ;
SavePos acera MEMORY_FILE5 ;
Get zebhigh long MEMORY_FILE5 ;
Math zeblow -= 1 ;
Math numberlow = zeblow ;
Math zeblow *= 16 ;
Math zebhigh -= 1 ;
Math numberhigh = zebhigh ;
Math zebhigh *= 16 ;
GoTo zeblow MEMORY_FILE1 ;
Get adjadj long MEMORY_FILE1 ;



GoTo zeblow MEMORY_FILE1 ;
Get minfox long MEMORY_FILE1 ;
Math minfox -= adjadj ;


GoTo zebhigh MEMORY_FILE1 ;
Get maxfox long MEMORY_FILE1 ;
Math maxfox -= adjadj ;

GoTo zeblow MEMORY_FILE1 ;
SavePos gt MEMORY_FILE1 ;
log MEMORY_FILE6 0 0 ;
For jjj = numberlow To numberhigh ;
GoTo gt MEMORY_FILE1 ;
Get min long MEMORY_FILE1 ;
Math min -= adjadj ;
Get max long MEMORY_FILE1 ;
Math max -= adjadj ;
Get nuv long MEMORY_FILE1 ;
Get loc long MEMORY_FILE1 ;
SavePos gt MEMORY_FILE1 ;
GoTo loc 0 ;
SavePos werefox 0 ;
For cvb = 1 To nuv ;
GoTo werefox 0 ;
Get Type1 Long 0 ;
Get Type2 Long 0 ;
Get Type3 Long 0 ;
Get null Byte 0 ;
Get Type4 Byte 0 ;
Get null Byte 0 ;
Get null Byte 0 ;
SavePos werefox 0 ;
GoTo Qprime MEMORY_FILE2 ;
Put Type1 Long MEMORY_FILE2 ;
Put Type2 Long MEMORY_FILE2 ;
Put Type3 Long MEMORY_FILE2 ;
SavePos Qprime MEMORY_FILE2 ;
GoTo werevulpine MEMORY_FILE7 ;
Put Type4 Byte MEMORY_FILE7 ;
SavePos werevulpine MEMORY_FILE7 ;

Next cvb ;
Math max -= 2 ;

For fff = min To max ;

Math fafter = fff ;
Math fafter += 1 ;
Math fafterafter = fff ;
Math fafterafter += 2 ;


GoTo fafterafter MEMORY_FILE7 ;
Get testfox Byte MEMORY_FILE7 ;
If testfox != 128 ;

GoTo red MEMORY_FILE3 ;
Put fff Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;

Put fff Short MEMORY_FILE3 ;
Put fafterafter Short MEMORY_FILE3 ;
Put fafter Short MEMORY_FILE3 ;
Put 0 Short MEMORY_FILE3 ;
SavePos red MEMORY_FILE3 ;
EndIF ;
Next fff ;
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
Math meshmesh = Sum ;
Math meshmesh += 60 ;
Math QQQ = 60 ;
Math QQQ += Snake ;
Math QQ = 52 ;
Math qaz = 0 ;
Math wsx = 0 ;
log MEMORY_FILE6 0 meshmesh ;
For Vertex = 0 < Zw2 ;
GoTo qaz MEMORY_FILE2 ;
Get D byte MEMORY_FILE2 ;
SavePos qaz MEMORY_FILE2 ;
GoTo QQ MEMORY_FILE6 ;
Put D Byte MEMORY_FILE6 ;
SavePos QQ MEMORY_FILE6 ;
Next Vertex ;
For Face = 0 < Zw3 ;
GoTo wsx MEMORY_FILE3 ;
Get D byte MEMORY_FILE3 ;
SavePos wsx MEMORY_FILE3 ;
GoTo QQQ MEMORY_FILE6 ;
Put D Byte MEMORY_FILE6 ;
SavePos QQQ MEMORY_FILE6 ;
Next Face ;
GoTo 0 MEMORY_FILE6 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x4D ;
Put M Byte MEMORY_FILE6 ;
Math M = Sum ;
Math M += 60 ;
Put M Long MEMORY_FILE6 ;
set M Byte 0x02 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x0A ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x03 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x3D ;
Put M Byte MEMORY_FILE6 ;
Math M = Sum 
Math M += 44 ;
Put M Long MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x40 ;
Put M Byte MEMORY_FILE6 ;
Math M = Sum 
Math M += 38 ;
Put M Long MEMORY_FILE6 ;
set M Byte 0x64 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x72 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x67 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x6F ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x6A ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x61 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x6E ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x00 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE6 ;
Math M = Sum 
Math M += 22 ;
Put M Long MEMORY_FILE6 ;
Set M Byte 0x10 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE6 ;
Math M = Snake ;
Math M += 8 ;
Put M Long MEMORY_FILE6 ;
Math M = VertexNumber ;
Put M Short MEMORY_FILE6 ;
Math JumpJump = Snake ;
Math JumpJump += 52 ;
GoTo JumpJump MEMORY_FILE6 ;
set M Byte 0x20 ;
Put M Byte MEMORY_FILE6 ;
set M Byte 0x41 ;
Put M Byte MEMORY_FILE6 ;
Math M = FaceNumber ;
Math M *= 8 ;
Math M += 8 ;
Put M Long MEMORY_FILE6 ;
Math M = FaceNumber ;
Put M Short MEMORY_FILE6 ;
Get size6 ASIZE MEMORY_FILE6 ;
Get name FILENAME 0 ;
string name += . ;
string name += hs ;
string name += .3ds ;
Log name 0 size6 MEMORY_FILE6 ;
log MEMORY_FILE2 0 0 ;
log MEMORY_FILE3 0 0 ;
log MEMORY_FILE7 0 0 ;
Math count = 0 ;
Math gt = 0 ;
Math Qprime = 0 ;
Math werevulpine = 0 ;
Math red = 0 ;
Math gin = 0 ;
Next hs ;
```


and this is the export for noesis
that i want to convert this to a bms script that can convert to noesis
this is not much because i'm stuck on filesize for the sum automatically
if anyone can get this working with the filesize and other stuff it might be really hard
to get textures to work

```

def registerNoesisTypes():

    handle = noesis.register("TTGames Mesh nemo", ".gsc")
    noesis.setHandlerWriteModel(handle, noepyWriteModel)
    return 1

def noepyWriteModel(mdl, bs):
    NU20 = bs.writeInt(0x3032554e)
    ChunkSize = bs.writeInt(0x00000008+=1)
    NumberImage = bs.writeInt(0x00000006)
    unknown = bs.writeInt(0x00000000)
    return 1
```


not much guys. this is the model i want to convert to *.gsc like for example *.fbx, *.dae or *.obj to *.gsc using noesis it's not working i've tried.
[box_example_for_3ds_to_gsc.zip](https://xentaxbackup.github.io/file/17116_box_example_for_3ds_to_gsc.zip)
## Post #2
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-11-27T11:26:16+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

one more.
[error.png](https://xentaxbackup.github.io/file/17117_error.png)
## Post #3
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2019-11-27T11:42:51+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

sorry i forgot to send the *.gsc as well. [https://drive.google.com/open?id=1OdTyh ... hjSAonC_er](https://drive.google.com/open?id=1OdTyhYdN2y1YYiClfQC9ffhjSAonC_er)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-27T13:53:17+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

well, seems you're having several problems here.
First is to understand Noesis python which isn't possible without having basic coding skills.

2nd one is that you deal with a world famous PS2 script using "werevulpine, fivfiv, werefox, fafterafter, Math JumpJump = Snake"
for example.
Their advantage is: they usually work, i.e. create valid *.3ds files

Disadvantages: - it's near to impossible to understand what's exactly happening in the scripts.
- the created 3ds files usually lack of uv data, so are pretty useless. (well, I added uv support some years ago to the WildArms3 script if I remember correctly but I dunno how I did it, a nightmare...  )

And now for the plot stopper: you want to code a "3ds to gsc" convertor script? I don't see how this should work.
You need a full gsc format description for such. Once you have it we could talk again. Just my 2 cents...
.



boat_bsc.png (52.14 KiB) Viewed 191 times

(183 submeshes without correct positions)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-27T21:03:14+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

had another look at this .gsc (because the vertices were simple floats) and then I found the missing uv data:
(ignore the grey rectangled data, just marked identical blocks)
.



boat(91)3ds_gsc-uvs.jpg (237.01 KiB) Viewed 175 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-27T21:37:15+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

as you can see it looks rather nasty because you have to delete dozens of superfluous faces which I get using auto created tri stripped face indices:
.



part_at_0x3816CC.png (48.18 KiB) Viewed 172 times
## Post #7
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-02-20T16:27:28+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

can you guys help?
I need GSC, GHG Files all made from The Game Imported to Source Filmmaker.
## Post #8
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-02-20T16:28:03+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

> Reply from tritterman ↑Mon Feb 21, 2022 12:27 am at Mon Feb 21, 2022 12:27 am
>
> 
can you guys help?
I need GSC, GHG Files all made from The Game Imported to Source Filmmaker.

i'd really appreciate it.
## Post #9
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-02-22T22:27:43+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

I've tried the Lego Games Modding Server but it didn't work out.
## Post #10
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2022-02-26T11:24:21+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

> Reply from tritterman ↑Wed Feb 23, 2022 6:27 am at Wed Feb 23, 2022 6:27 am
>
> 
I've tried the Lego Games Modding Server but it didn't work out.

i did remembered grabbing the noesis importer script but it requires you have to remove HEAD and TREF and modify there script and that does not contain the face data that works on all ttgames, i did try and make a blender importer ages ago and tried using the find command to follow the quickbms but it just got the end of file and couldn't get the correct face data and it's taking me ages to get vertex paints below the uv data, uv and textures to work. i keep getting missing objects.
## Post #11
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2022-02-26T12:08:33+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

i'll just skip noesis, this blender importer and exporter very incompleted which has misleaded object counts.

```
import bpy

bl_info = {
    "name" : "FindingNemoGSC",
    "author" : "Unknown",
    "description" : "Importing and Exporting ttgames",
    "blender" : (2,80,0),
    "location" : "File > Import/Export"
    "category" : "GSCExporterImporter",

def WriteInt(f, v):
    return f.write(struct.pack("<I", v))

def ReadInt(f):
    return struct.unpack("<I", f.read(4))[0]

def ReadHalfFloat(f):
    return struct.unpack("<e", f.read(2))[0]

def ReadFloat(f):
    return struct.unpack("<f", f.read(4))[0]

def ReadByte(f):
    return struct.unpack("B", f.read(1))[0]

def GSCOpener(filename):
    f = open(filename, "rb")
    
    NemoSkip = 1
    
    NU20 = ReadInt(f)
    NegativeSize1 = ReadInt(f)
    CountSix = ReadInt(f)
    Unk01 = ReadInt(f)
    NTBL = ReadInt(f)
    NTBLSize1 = ReadInt(f)
    f.seek(NTBLSize1-8, NemoSkip)
    TST = ReadInt(f)
    TSTSize = ReadInt(f)
    f.seek(TSTSize-8, NemoSkip)
    MS = ReadInt(f)
    MSSize = ReadInt(f)
    MaterialCount = ReadInt(f)
    MaterialUnk = ReadInt(f)
    for i in range(MaterialCount):
        f.seek(324, NemoSkip)
        R = ReadByte(f)
        G = ReadByte(f)
        B = ReadByte(f)
        A = ReadByte(f)
        R2 = ReadByte(f)
        G2 = ReadByte(f)
        B2 = ReadByte(f)
        A2 = ReadByte(f)
        R3 = ReadByte(f)
        G3 = ReadByte(f)
        B3 = ReadByte(f)
        A3 = ReadByte(f)
        f.seek(48, NemoSkip)
        Red = ReadFloat(f)
        Green = ReadFloat(f)
        Blue = ReadFloat(f)
        f.seek(4, NemoSkip)
        f.seek(56, NemoSkip)
        Unk01 = ReadInt(f)
        Unk02 = ReadInt(f)
        OBJHeader = ReadInt(f)
        OBJSize = ReadInt(f)
        MisleadedObjectCounts = ReadInt(f)
        OBJUnk01 = ReadInt(f)
        
        offset1 = b"\x03\x01\x00\x01\x03\x80"
        uvoffset1 = b"\x01\x00\x00\x05\x04\x80"
        VertexPaint = b"\x00\x00\x00\x05\x05\xC0"
        
        offset1.find()
        uvoffset1.find()
        VertexPaint.find()
        
        fa = -1
        fb = 0
        fc = 1
    f.close()
    
def register():

def unregister():
```
## Post #12
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-01T12:37:45+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

i Don't use Blender 2.80. I use the 2.70s Version and i need one for the the GHG / GSC Models from the Finding Nemo Game or for Noesis.
## Post #13
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2022-03-02T13:35:30+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

Sorry About that, ok i got one for the GHG model and GSC level model, the problem is it will only give you eyeballs and other parts since nobody hasn't told me what 03 02 00 01 03 80 XX 6D is and get them into verts, there a nemogscbeta script up the top of the page that you might have to do it from manually and insert XX 6C next to the offset  that gets access all ttgames but there no 2nd part of the script so far since they contain scientific notations, i don't have the proper script, [https://drive.google.com/file/d/1AFDedd ... sp=sharing](https://drive.google.com/file/d/1AFDeddxQgIk5Uv9PiDInXbvwcYF_y3qX/view?usp=sharing)
## Post #14
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2022-03-02T13:41:30+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

> Reply from tritterman ↑Tue Mar 01, 2022 8:37 pm at Tue Mar 01, 2022 8:37 pm
>
> 
i Don't use Blender 2.80. I use the 2.70s Version and i need one for the the GHG / GSC Models from the Finding Nemo Game or for Noesis.

oh ok
## Post #15
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-03T00:32:51+00:00
- Post Title: Finding Nemo: *.gsc issue with noesis

like where in Ttgames.py do i have to put the XX 6C Part in?
## Post #16
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-03-10T20:44:46+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

any updates with Ghg for noesis or Blender or anything to help today?
## Post #17
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-07-22T21:16:25+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

i found out when i run in Blender 2.8, the Script line has Errors. How do i fix the line in import?
## Post #18
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-07-23T11:21:44+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

I have no idea what you guys are trying to achieve exactly but for the audience, here's a picture from the latest uploaded toschool.gsc after using the FindingNemo.bms on it and importing the resulting 44 3ds files (no uvs) into blender:
.



toSchool.jpg (147.8 KiB) Viewed 79 times
## Post #19
- Username: tritterman
- Rank: veteran
- Number of posts: 88
- Joined date: Tue Aug 24, 2021 5:14 am
- Post datetime: 2022-07-23T11:23:52+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

Well Keep trying.
## Post #20
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2022-07-23T14:22:39+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

right, to be honest It's not going to work all you will get is messed up connected triangle strips starting with fa = -1, fb = 0, fc = 1, i tried it before with a filepath and it does not work in blender and it only works in quickbms, there is too much cd padding there no equal the object counts are to less and the material counts are too less and there more submeshes than object and material counts.
## Post #21
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2022-07-23T15:01:42+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

all i did was i used exponent to the object count and i got this completely messed up, now how do i or someone make an addon of this
## Post #22
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2022-07-23T15:07:41+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

here the messed up triangle strip picture with exponents i was doing in blender and it does not work in blender and only works in quickbms

[https://drive.google.com/file/d/14hi0nI ... sp=sharing](https://drive.google.com/file/d/14hi0nIwfJ195s9iGluhtpU_3xft9cGu5/view?usp=sharing)
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-07-23T18:31:13+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

> Reply from MegaSpeedXtreme ↑Sat Jul 23, 2022 11:01 pm at Sat Jul 23, 2022 11:01 pm
>
> or someone make an addon of thisyeah, would be cool. Starting with point clouds (boat.gsc):
.



boat_gsc_point_cloud.jpg (236.66 KiB) Viewed 58 times
## Post #24
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-07-23T20:53:10+00:00
- Post Title: Re: Finding Nemo: *.gsc issue with noesis

(Results without using the bms script, just some Make_obj/H2O approach.)

Well, some oddities, (superfluous faces), rest looks fine to me:
.



boat_gsc_.jpg (178.27 KiB) Viewed 37 times


(except for this harlequine look (whatever), might be the result of wrong face windings, dunno.)
