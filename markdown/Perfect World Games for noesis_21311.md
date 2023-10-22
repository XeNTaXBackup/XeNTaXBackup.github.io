## Post #1
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-29T21:53:25+00:00
- Post Title: Perfect World Games for noesis

Since this thread has turned into a Perfect world games thread heres a summery of everything found in here:

1.Saint Seiya Online
Support for .ski, .bon, .stck, .mox, .bmd
skinned mesh + animation + static mesh

2.Perfect World
Support for .ski, .bon, .stck, .mox, .bmd
skinned mesh + animation + static mesh

3.Jade Dynasty
Support for .ski, .bon
skinned mesh

4.Forsaken World
Support .ski, .bon, .mox, .bmd (ski works with Perfect World script )

5.Swordsman Online 
Support for .ski, .bon
skinned mesh

.........................................................................................................................
Hi,

In order to complete my basic noesis study i started working on a noesis script for .stck  animation based of the following topic: 
[viewtopic.php?f=16&t=11776&hilit=animation#p98283](https://forum.xentax.com/viewtopic.php?f=16&t=11776&hilit=animation#p98283)

iv been working on this for the past few days - most of them trying to resolve an issue where my weights were being assigned to the wrong 
bone id, had to ditch the .rapi and learn NoeMesh so i could manipulate the data  - finally got it fixed. but now i am stuck with the animation part and have some issues i cant seem to resolve.

i tried following both shakotay2  and killercracker script. (also credit to zaramot - used his script to try and t/s my issues)
i am able to get the correct quat and translation vector but for some frames they are not equal, for example frame 8 has 93 translation vectors and 97 rotation quats, so what do i do with the missing translation? does it mean translation for quat is 0?

additionally what is "at time((i-1) * timeMult)"? is this a maxscript thing? or something that is relevant for my understanding of animations? 
in shakotay2  script keyframe 200 was used didnt understand what that was for either?
also the line marked in black box - i understand changing numFrames, but what is rotFrames?

thanks in advance 



for xentax1.png (51.32 KiB) Viewed 720 times



my current noesis script (animation not working)

```
from math import *
from inc_noesis import *


def ReadStringKnown(f, size): # read string of known size
    String = []
    k = 0
    for i in range(size): 
        num = int(f.readUByte()) # bug reading 31 as ASCII 0 end existing
        if (num > 64 and num < 91) or(num > 45 and num < 58) or (num > 96 and num < 123) or num == 95 : #num == 95 add _ charecter
            if k == 0:
                k += 1
                Name = chr(num)
            else:
                Name = Name + chr(num)
    return Name



def registerNoesisTypes():
    handle = noesis.register("Perefect World Mesh", ".ski;.bon;.stck")    
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #opens debug consle
    noesis.logPopup()
    return 1


def noepyCheckType(data):
    '''Verify that the format is supported by this plugin. Default yes'''
    #I preform my check while reading mesh data
    return 1


#load skeleton data
def Skeleton(data):
    bones = []
    
    g = NoeBitStream(data, NOE_LITTLEENDIAN)
    g.seek(16,1)
    BoneCount = g.readUInt()
    g.seek(80,1)
    ####
    for i in range(BoneCount):#BoneCount
        boneNameLength = g.readUInt()
        boneName = ReadStringKnown(g, boneNameLength)
        boneID = g.readUInt()
        parentID = g.readInt()
        siblingID = g.readUInt()
        unkcount = g.readUInt()
        tfm2 = NoeMat44.fromBytes( g.readBytes(0x40), NOE_LITTLEENDIAN )
        tfm = NoeMat44.fromBytes( g.readBytes(0x40), NOE_LITTLEENDIAN )
        #boneMat = tfm.toMat43()
        boneMat = tfm.toMat43().inverse()
        #print("boneMat =", boneMat)

        for j in range(unkcount):
            g.seek(4,1)

        bones.append( NoeBone(i, boneName, boneMat, None, parentID) )

    return bones

def animation (data, bones): #def animation (data, bones):
    s = 0
    BoneMat = []
    Rotation_Arr = []
    translation_arr = []
    anims = []
    animFrameMats = []
    animName = "test"
    animFrameRate = 30

    f = NoeBitStream(data, NOE_LITTLEENDIAN)
    Magic = ReadStringKnown(f, 8)
    print("anim magic")
    print(Magic)
    unk = f.readUInt()
    boneCount = f.readUInt()
    f.seek(20,0)
    numFrames = f.readUInt()
    ukw = f.readUInt()

    for i in range (boneCount):
        
        boneID = f.readUInt()
        TransCount = f.readUInt() # number of translation vectors
        f.seek(8,1)

        for k in range(TransCount):
            #Tran = NoeVec3.fromBytes(f.readBytes(12))
            x = (f.readFloat())
            y = (f.readFloat())
            z = (f.readFloat())
            translation_arr.append((x,y,z))

        f.seek(16,1)

        RotCount = f.readUInt() # number of quats
        f.seek(8,1)
        print("TransCount=",TransCount)
        print("RotCount=",RotCount)
        
        for j in range(RotCount):
            x = f.readFloat()
            y = f.readFloat()
            z = f.readFloat()
            w = f.readFloat()
            Rot = NoeQuat((x,y,z,w))
            print("quat - original", Rot)
            #Rot = Rot.normalize()
            #Rotation_Arr.append((x,y,z,w)) #quat(x,y,z,w)
            frameMat = Rot.toMat43(transposed = 1)
            frameMat = frameMat.inverse()
            print("matrix_inverse =",frameMat)           
            #uat = frameMat.toQuat()
            #rint("quat", quat)
            frameMat[3] = translation_arr[s]
            #if TransCount >= RotCount:
            #if   s += 1
            #print(frameMat)
            animFrameMats.append(frameMat)
            
        
        f.seek(16,1)
        #a = f.tell()
    
    #bones must be a list of NoeBone objects, frameMats must be a flat list of NoeMat43 object
    if numFrames < TransCount:
        numFrames = TransCount
    print(numFrames)
    print(len(animFrameMats))
    anim = NoeAnim(animName, bones, 80, animFrameMats, animFrameRate) #numFrames
    anims.append(anim)

    return anims
    
#load mesh data
def Mesh(data, bones):
    
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data, NOE_LITTLEENDIAN)
   
    Magic = noeStrFromBytes(bs.readBytes(8), "ASCII")
    print(Magic)
    if Magic != "MOXBIKSA":
        print("worng file format")
    
    unk2 = bs.readInt()
    meshCount = bs.readInt()

    bs.seek(12,1)  
    
    textureCount = bs.readInt()
    materialCount = bs.readInt()
    mesh_boneCount = bs.readInt()
    null = bs.readInt()
    ukw4 = bs.readInt()
    
    bs.seek(60,1)
    
    boneName_Arr = []
    texName_Arr = []
    
    for l in range(len(bones)):
        print(l)
        print(bones[l].name)
    
    for i in range(mesh_boneCount):
        count = bs.readInt()
        boneName_Arr.append(ReadStringKnown(bs, count)) 

    for i in range(textureCount):
        count = bs.readInt()
        texName_Arr.append(ReadStringKnown(bs, count)) 

    for i in range(materialCount):
        bs.seek(80,1)
    
    for i in range(meshCount):
        nameLength = bs.readInt()
        meshName = ReadStringKnown(bs, nameLength)
    
        matID = bs.readInt()
        ukw2 = bs.readInt()
        vertCount = bs.readInt()
        faceCount = bs.readInt()
    
        Positions = []
        PolygonIndex = []
        Normals = []
        UV =[]
        weightList = []
        meshes = []
    
        for j in range(vertCount): # vert position
            bonesid = []
            weights = []
            vx = bs.readFloat()
            vy = bs.readFloat()
            vz = bs.readFloat()       
            Positions.append(NoeVec3([vx,vy,vz]))
              
            
            weight1 = bs.readFloat() 
            weight2 = bs.readFloat() 
            weight3 = bs.readFloat()
            weight4 = 0.0
                       

            for i in range(4):
                bone = bs.readUByte()
                if bone <= len(boneName_Arr):
                    name = boneName_Arr[bone]
                    for l in range(len(bones)):
                        if bones[l].name == name:
                            index = bones[l].index
                            break
                else:
                    index = 300
                if i == 0:
                   
                   bone1 = index
                if i == 1:
                   bone2 = index
                if i == 2:
                   bone3 = index
                if i == 3:
                   bone4 = index                                     

            
            if weight1 != 0:
                bonesid.append(bone1)
                weights.append(weight1)
            if weight2 != 0:
                bonesid.append(bone2)
                weights.append(weight2)
            if weight3 != 0:
                bonesid.append(bone3)
                weights.append(weight3)
            if weight4 != 0:
                bonesid.append(bone4)
                weights.append(weight4)
            
            weightList.append(NoeVertWeight(bonesid,weights))
            
            #print(j)
            #print(vx,vy,vz)
            #print(bonesid)
            #print(weights)
            
            
            nx = bs.readFloat()
            ny = bs.readFloat()
            nz = bs.readFloat()      
            Normals.append(NoeVec3([nx,ny,nz])) 
            
            tu = bs.readFloat()
            tv = bs.readFloat() * -1
            UV.append(NoeVec3([tu,tv,0.0])) 
            
        for j in range(0, int(faceCount)): # faces / triangles
            PolygonIndex.append(bs.readUShort())

    mesh = NoeMesh(PolygonIndex, Positions, meshName)
    mesh.setWeights(weightList)
    mesh.setNormals(Normals)
    mesh.setUVs(UV)
    meshes.append(mesh)
    
    return meshes
   
def noepyLoadModel(data, mdlList):
        ctx = rapi.rpgCreateContext()
               
        skel_data = rapi.loadPairedFile("skel_file- 1", ".bon")
        mesh_data = rapi.loadPairedFile("mesh_file- 2", ".ski")
        try:
            anim_data = rapi.loadPairedFile("anim_file - 3", ".stck")
        except:
            pass
        
        bones = Skeleton(skel_data) # get skeleton data
        anims = animation(anim_data, bones)    
        #print(anims)
        #print(anims[0].bones)
        #print(anims[0].name)
        #print(anims[0].numFrames)
        #print(anims[0].frameMats)
        #print(len((anims[0].frameMats)))
        
        meshes = Mesh(mesh_data, bones) # need to edit bone id index
        
        mdl = NoeModel(meshes)
        mdl.setBones(bones)           
        mdl.setAnims(anims) 
        
        mdlList.append(mdl)
        rapi.rpgClearBufferBinds()
        
        return 1                     

```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-30T09:22:39+00:00
- Post Title: Perfect World Games for noesis

> Reply from jayn23 ↑Wed Oct 30, 2019 5:53 am at Wed Oct 30, 2019 5:53 am
>
> 
Hi,

In order to complete my basic noesis study i started working on a noesis script for .stck  animationHi,
that's great!  

> i am able to get the correct quat and translation vector but for some frames they are not equal, for example frame 8 has 93 translation vectors and 97 rotation quats, so what do i do with the missing translation?Afair (from my understanding) max interpolates the missing frames but I may be wrong. 

> additionally what is "at time((i-1) * timeMult)"? is this a maxscript thing? or something that is relevant for my understanding of animations?"time" refers to the timeline for the animation (frames, translation/rotation).
timeMult = 2.0, just a variable killercracker introduced

> in shakotay2  script keyframe 200 was used didnt understand what that was for either?timeline thing again
btw: seems there's a bug in my script:

```
	    (
		    rot = RotationAnimation()
		    rot.BoneId = i
		    rot.KeyFrame = i*200-10
		    x = ReadFloat stream
		    y = ReadFloat stream
		    z = ReadFloat stream
		    w = ReadFloat stream
			
		    rot.Quaternion = quat x y z w
	
		    append allRotations rot
	    )
```

I'm pretty sure it should read
rot.KeyFrame = fd*200-10
but I can't check it because I don't have max installed any more. (Dependend on the (max) Frame_cnt "200" might be to big, better use 20 or such.)
## Post #3
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-30T21:48:43+00:00
- Post Title: Perfect World Games for noesis

Thanks again for your help  

 sorry in advance for the lengthy post,

what i wrote here wasnt correct

> i am able to get the correct quat and translation vector but for some frames they are not equal, for example frame 8 has 93 translation vectors and 97 rotation quats, so what do i do with the missing translation?

to be exact, for every bone there is a set of translation vectors and a set of rotation matrix, for bone 8 there were 93 translation vectors and 97 rotation quats, some also have 1 vs 97 or 97 to 31 etc..

what i am assuming based on max code is that every rotation and translation have a specific time calculated by ((i-1) * timeMult) so for say bone 8, i would take the translation and matrix at time 120, and if at time 190 i have only a rotation and no translation i would take the last translation (meaning it didnt move)
is this correct?
is there a way in 3dsmax i can see all of my animation matrix? so i can verify if my data is correct?

i also think i am not using the correct noesis function for this, i found in inc_noesis.py NoeKeyFramedAnim class, i am going to try with this one

One last question - just because i am curious   
on the left code by killercracker i see he just applays the inverse quat and translation
on the right code by you, you first apply b.pos to the rotation matrix from quat then transform it, why not apply allTranslations.Position instead of  b.pos ?



for xentax1.png (44.47 KiB) Viewed 699 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-31T12:44:49+00:00
- Post Title: Perfect World Games for noesis

> Reply from jayn23 ↑Thu Oct 31, 2019 5:48 am at Thu Oct 31, 2019 5:48 am
>
> what i am assuming based on max code is that every rotation and translation have a specific time calculated by ((i-1) * timeMult) so for say bone 8, i would take the translation and matrix at time 120, and if at time 190 i have only a rotation and no translation i would take the last translation (meaning it didnt move)
is this correct?sounds good   (Can't confirm it, because I don't have max installed/used since years...)

> is there a way in 3dsmax i can see all of my animation matrix? so i can verify if my data is correct?depends on. In case you use a script, insert print commands.
In case you use an importer plugin (without source) I don't remember - didn't use max script API, if any.
(in blender you could use for example matrix=Blender.Mathutils.Matrix(bone.matrix['ARMATURESPACE']) for such)


> One last question - just because i am curious   
>
> on the left code by killercracker i see he just applays the inverse quat and translation
>
> on the right code by you, you first apply b.pos to the rotation matrix from quat then transform it, why not apply allTranslations[ i ].Position instead of  b.pos ?good question - that was my first max animation script (and most of the code was "borrowed" from TaylorMouse).
since my script didn't work correctly (while killerscracker's did) it's an academic question, isn't it?

Best way to get an answer, imho, is to try the different ways and print out the resulting matrixes - as you intended above.

btw: be carefull with [ i ], without the blanks the browser soft takes it as a command for the font
## Post #5
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-10-31T18:52:00+00:00
- Post Title: Perfect World Games for noesis

> depends on. In case you use a script, insert print commands.
>
> In case you use an importer plugin (without source) I don't remember - didn't use max script API, if any.
>
> (in blender you could use for example matrix=Blender.Mathutils.Matrix(bone.matrix['ARMATURESPACE']) for such)

to be honest before i started learning noesis i tried learning how to script with the blender API and after a week of trying i realized there are many tutorials but each works only for a specific version and not many worked for the 2.8 version... 

> btw: be carefull with [ i ], without the blanks the browser soft takes it as a command for the font
ill make sure i do   

by the way i got it to work   

ill post the code later today just want to clean it up a bit.
now my next ,mission is to start practicing analyzing 3d models, currently i can get verts,faces and uv most of the time but bones and animations iv never even really tried

Thanks again for the help

here is the code:


 fmt_PerfectWorld.rar
(2.85 KiB) Downloaded 100 times
## Post #6
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2019-11-07T09:26:13+00:00
- Post Title: Perfect World Games for noesis

If I understand correctly now, can your Noesis Script load PW animations?
## Post #7
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-07T18:23:29+00:00
- Post Title: Perfect World Games for noesis

Yes it can load animation - iv tested it only on models + animation samples that were provided in the original post, so i cant guarantee it will work for all versions ... i can only hope
## Post #8
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2019-11-08T06:57:11+00:00
- Post Title: Perfect World Games for noesis

Okay no problem i will check 
Maybe u can create a script for .bon Animation because many clients use this "old" animation data.
## Post #9
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2019-11-11T11:17:02+00:00
- Post Title: Perfect World Games for noesis

many thanks for the great update, well maybe you can take a look into this files, use same format as pw, Saint Seiya Online, grateful if you can help, have a nice day.

[https://www.mediafire.com/file/e2rv2eim ... es.7z/file](https://www.mediafire.com/file/e2rv2eimhasbovl/Saint_Seiya_Online_Samples.7z/file)
## Post #10
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-12T12:46:48+00:00
- Post Title: Perfect World Games for noesis

> well maybe you can take a look into this files, use same format as pw, Saint Seiya Online, grateful if you can help, have a nice day.

Hi,

I took a look at the mesh + skeleton files and the format was almost identical just needed to add one for loop, i also found a bug in my original script that would have prevented loading models made up of multiple meshes. (hope i didnt break anything else when fixing it   )

Saint Seiya Online version supports only mesh and skeleton at the moment, hopefully ill get some time to look at the animation, using search i noticed its had a few members that are far more experienced than me work on it in the past, so i have my doubts that i can...
[fmt_SaintSeyiaOnline.rar](https://xentaxbackup.github.io/file/17050_fmt_SaintSeyiaOnline.rar)
## Post #11
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-12T12:48:03+00:00
- Post Title: Perfect World Games for noesis

This is the perfect world (original) script with bug fix

if i broke anything please let me know, didnt have time to do many tests
[fmt_PerfectWorld.rar](https://xentaxbackup.github.io/file/17051_fmt_PerfectWorld.rar)
## Post #12
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2019-11-12T13:12:23+00:00
- Post Title: Perfect World Games for noesis

Verrry Nice - thanks! :3

Can u also find out how can import Objectfiles (.mox)?
## Post #13
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2019-11-12T13:36:30+00:00
- Post Title: Perfect World Games for noesis

> Reply from jayn23 ↑Tue Nov 12, 2019 8:46 pm at Tue Nov 12, 2019 8:46 pm
>
> 
well maybe you can take a look into this files, use same format as pw, Saint Seiya Online, grateful if you can help, have a nice day.

Hi,

I took a look at the mesh + skeleton files and the format was almost identical just needed to add one for loop, i also found a bug in my original script that would have prevented loading models made up of multiple meshes. (hope i didnt break anything else when fixing it   )

Saint Seiya Online version supports only mesh and skeleton at the moment, hopefully ill get some time to look at the animation, using search i noticed its had a few members that are far more experienced than me work on it in the past, so i have my doubts that i can...well to fast, thanks a lot for support, one thing, edit one line of the script like this:

handle = noesis.register("Perefect World Mesh", ".ski;.bon;.stck")

to

handle = noesis.register("Saint Seiya", ".ski")

so now how we disable bon and stck? because if load ski ask for bon and stck after load all nothing appear in noesis.
## Post #14
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-12T15:26:05+00:00
- Post Title: Perfect World Games for noesis

> handle = noesis.register("Perefect World Mesh", ".ski;.bon;.stck")
>
> 
>
> to
>
> 
>
> handle = noesis.register("Saint Seiya", ".ski")

my bad i forgot to change that   
ill update the original post later today when i have time

It shouldn't be asking you for ,stk since i disabled it in Saint Seiya version.
I noticed that even after changing the handle it still tried to load the files using the perfect world script.
so you cant  have both scripts in you plugin folder at the same time.

.bon file contains the skeleton so if you want skinned meshes i wouldn't disable it.

> Can u also find out how can import Objectfiles (.mox)?
ill see what i can do..
## Post #15
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2019-11-13T03:52:40+00:00
- Post Title: Perfect World Games for noesis

> Reply from jayn23 ↑Tue Nov 12, 2019 11:26 pm at Tue Nov 12, 2019 11:26 pm
>
> 
handle = noesis.register("Perefect World Mesh", ".ski;.bon;.stck")

to

handle = noesis.register("Saint Seiya", ".ski")

my bad i forgot to change that   
ill update the original post later today when i have time

It shouldn't be asking you for ,stk since i disabled it in Saint Seiya version.
I noticed that even after changing the handle it still tried to load the files using the perfect world script.
so you cant  have both scripts in you plugin folder at the same time.

.bon file contains the skeleton so if you want skinned meshes i wouldn't disable it.understand but what I say before, I download a clean copy of noesis and only copy your script into plugin, check.





so now when I select ski to load it ask for .bon ok, after select a .bon it ask again to ski mesh 2, after select same mesh ski don't give error but noesis don't load nothing.

here is the test, and with all files same.
## Post #16
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-13T05:46:45+00:00
- Post Title: Re: Perfect world animation .stck for noesis

ok i dont really know whats the issue same files work for me

link to photo
[https://drive.google.com/open?id=1aAU4J ... TiZ3vEd_FI](https://drive.google.com/open?id=1aAU4JgEAiBaA51IqUUWxSGTiZ3vEd_FI)

edit:
if some models open and the others dont, there might be different versions, let me know which ones and i will add them

lets try again:
[fmt_SaintSeyiaOnline.rar](https://xentaxbackup.github.io/file/17054_fmt_SaintSeyiaOnline.rar)
## Post #17
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2019-11-14T11:25:20+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Wed Nov 13, 2019 1:46 pm at Wed Nov 13, 2019 1:46 pm
>
> 
ok i dont really know whats the issue same files work for me

link to photo
https://drive.google.com/open?id=1aAU4J ... TiZ3vEd_FI

edit:
if some models open and the others dont, there might be different versions, let me know which ones and i will add them

lets try again:thank you very much, now I hooked it, you must first load the bone and then the skeleton, my mistake, now as you will have seen in the files I sent you, if you want to load skeleton characters there are no bone files, then it will be possible to edit your code to just load the skeleton without the bones?
## Post #18
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-14T22:19:27+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Can u also find out how can import Objectfiles (.mox)?ill see what i can do..

well i got it figured out   

script works for Perfect World and Forsaken world versions

> thank you very much, now I hooked it, you must first load the bone and then the skeleton, my mistake, now as you will have seen in the files I sent you, if you want to load skeleton characters there are no bone files, then it will be possible to edit your code to just load the skeleton without the bones?

sure ill make you a version that loads only mesh, ill try  to do it tommorow
[fmt_PerfectWorld-static.rar](https://xentaxbackup.github.io/file/17058_fmt_PerfectWorld-static.rar)
## Post #19
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-16T16:12:48+00:00
- Post Title: Re: Perfect world animation .stck for noesis

here is  to mesh only script for Saint Seiya, PM  me if you have any issues
[fmt_SaintSeyiaOnline - no skin.rar](https://xentaxbackup.github.io/file/17066_fmt_SaintSeyiaOnline - no skin.rar)
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2019-11-16T16:31:54+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Sun Nov 17, 2019 12:12 am at Sun Nov 17, 2019 12:12 am
>
> 
here is  to mesh only script for Saint Seiya, PM  me if you have any issuesthis is great news, for now all I test work fine, another question, is possible add load texture or not possible? because textures located in folder separated of mesh but just ask, thanks for all support.
## Post #21
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-16T16:41:12+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> this is great news, for now all I test work fine great!!

ll take a look if i can but it will have to wait a few days since i am working on something else at the moment
## Post #22
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2019-11-16T16:49:34+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Sun Nov 17, 2019 12:41 am at Sun Nov 17, 2019 12:41 am
>
> 
this is great news, for now all I test work fine great!!

ll take a look if i can but it will have to wait a few days since i am working on something else at the momentok thanks a lot, have a great weekend.
## Post #23
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-11-17T03:18:41+00:00
- Post Title: Re: Perfect world animation .stck for noesis

Hello, can you take a look at this game [Zhuxian world], its character format is also ski, the scene is PXD and CHF, thank you.
[https://mega.nz/#!yuY3RKDZ!Hf20pxOfqE55 ... Izthcc_3iU](https://mega.nz/#!yuY3RKDZ!Hf20pxOfqE55EMIlpBMzeO8MBHdh9IFIQIzthcc_3iU)
## Post #24
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-18T22:12:26+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Hello, can you take a look at this game [Zhuxian world], its character format is also ski, the scene is PXD and CHF, thank you.
>
> https://mega.nz/#!yuY3RKDZ!Hf20pxOfqE55 ... Izthcc_3iU

started looking at the format looks similar to other .ski until it doesn't....  not as easy as i would have hoped but ill do my best
i can get the models pretty easily but finding a pattern that works all the time for the script not so much



xentax.JPG (57.38 KiB) Viewed 220 times



> is possible add load texture or not possible? because textures located in folder separated of mesh but just ask
seems all textures are in Chinese so i need to figure out how to read  Chinese with noesis, if i can than adding support would be easy
## Post #25
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-19T18:36:23+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Hello, can you take a look at this game [Zhuxian world], its character format is also ski, the scene is PXD and CHF, thank you.

Well i got  a working script   
i am using a hack to bypass 1 thing i havent figured out but it seems to work on all provided samples,
supports  bones, mesh and uv.
[fmt_JadeDynasty.rar](https://xentaxbackup.github.io/file/17088_fmt_JadeDynasty.rar)
## Post #26
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-11-20T07:33:03+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Wed Nov 20, 2019 2:36 am at Wed Nov 20, 2019 2:36 am
>
> 
Hello, can you take a look at this game [Zhuxian world], its character format is also ski, the scene is PXD and CHF, thank you.


Well i got  a working script   
i am using a hack to bypass 1 thing i havent figured out but it seems to work on all provided samples,
supports  bones, mesh and uv.

WOW! Great, it's loaded successfully, but each file has to open bon. I wonder if I can only load ski. If you can, take a look at the PXD and CHF format of the scene model. Thank you, man.
## Post #27
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-20T17:30:14+00:00
- Post Title: Re: Perfect world animation .stck for noesis

Here is a only mesh version
[fmt_JadeDynasty-no skin.rar](https://xentaxbackup.github.io/file/17096_fmt_JadeDynasty-no skin.rar)
## Post #28
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-11-27T06:59:18+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Thu Nov 21, 2019 1:30 am at Thu Nov 21, 2019 1:30 am
>
> 
Here is a only mesh version

This script is great. Can its scene PXD and CHF format files be supported?
## Post #29
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2019-11-28T22:26:06+00:00
- Post Title: Re: Perfect world animation .stck for noesis

Sorry i am kind of busy with my own pet project.
i took a look at the files, but at a quick glance i couldn't figure them out.
if some one here can figure out the format, ill write a noesis script for it, but for now i dont have time sorry
## Post #30
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-17T23:02:26+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Fri Nov 29, 2019 6:26 am at Fri Nov 29, 2019 6:26 am
>
> 
Sorry i am kind of busy with my own pet project.
i took a look at the files, but at a quick glance i couldn't figure them out.
if some one here can figure out the format, ill write a noesis script for it, but for now i dont have time sorry

Hi jayn23. 
Swordsman online is another game made by perfect world and use te same format.
Unfortunately your script doesn't work, Could you take a look on this sample? 

[https://www.mediafire.com/file/bkdsmvkm ... n.rar/file](https://www.mediafire.com/file/bkdsmvkmepdi4q8/swordsman.rar/file)
## Post #31
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-19T04:19:04+00:00
- Post Title: Re: Perfect World Games for noesis

> Hi jayn23.
>
> Swordsman online is another game made by perfect world and use te same format.
>
> Unfortunately your script doesn't work, Could you take a look on this sample?

Hi Drawing,

I updated Jade dynasty script to support Swordsman online, works for all provided samples
i attached in folder a script for mesh only and script for mesh + skeleton

enjoy   


 Swordsman online scripts.rar
(4.35 KiB) Downloaded 33 times
## Post #32
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-19T19:20:40+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Sun Apr 19, 2020 12:19 pm at Sun Apr 19, 2020 12:19 pm
>
> 
Hi jayn23.
Swordsman online is another game made by perfect world and use te same format.
Unfortunately your script doesn't work, Could you take a look on this sample?

Hi Drawing,

I updated Jade dynasty script to support Swordsman online, works for all provided samples
i attached in folder a script for mesh only and script for mesh + skeleton

enjoy   

Swordsman online scripts.rar

really thanks man   
p.s.: Do we have any chance in the future to see .stck from jade dynasty and swordsman supported?

Again thanks you jayn23
## Post #33
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-20T00:43:08+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Sun Apr 19, 2020 12:19 pm at Sun Apr 19, 2020 12:19 pm
>
> 

Hi Drawing,

I updated Jade dynasty script to support Swordsman online, works for all provided samples
i attached in folder a script for mesh only and script for mesh + skeleton

enjoy   

Swordsman online scripts.rar

Hi jayn23,
I tried your script ( the mesh + skeleton version) with other samples, it seems to work with a good 70% of models.
Unfortunately some of them doesn't work, I got different error messages in noesis , sometimes noesis just crashed and other times it loaded only skeleton.

I upload 2 sample for each error I got , if you have free time could take them a look? 

[https://www.mediafire.com/file/w67fzlm6 ... g.rar/file](https://www.mediafire.com/file/w67fzlm60kjjzyk/notworking.rar/file)
## Post #34
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-20T08:54:02+00:00
- Post Title: Re: Perfect World Games for noesis

> really thanks man 
>
> p.s.: Do we have any chance in the future to see .stck from jade dynasty and swordsman supported?

ill give it a try, but no promises 

> I tried your script ( the mesh + skeleton version) with other samples, it seems to work with a good 70% of models.
>
> Unfortunately some of them doesn't work, I got different error messages in noesis , sometimes noesis just crashed and other times it loaded only skeleton.
>
> 
>
> I upload 2 sample for each error I got , if you have free time could take them a look?
I expected this, there are different types of material - and each needs a different condition, until we find  and address all of them it wont be 100% , ill take a look at the samples and upload updated version later today
## Post #35
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-20T13:41:14+00:00
- Post Title: Re: Perfect World Games for noesis

Nice   

thanks for the time you are spending on this script
## Post #36
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-20T20:55:21+00:00
- Post Title: Re: Perfect World Games for noesis

OK There were a bit more fixes than i thought   
1. added new material type
2. fixed bug in material i added for swordsman online
3. add fix for occasions when bones are in Chinese and noesis crashes because it cant read the names - now i give these bone a deafult name with their boneID
4. added support for new type of mesh that dosent include weights and bone names in file - for now these will load but mesh and skeleton are not connected because i didnt see any weights just bone index 

iv tested the only mesh script with all of the samples - they all work
as for the script with bones tested only with 2-3 so the rest is up to you  


 Swordsman online scripts.rar
(4.35 KiB) Downloaded 35 times
## Post #37
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-22T18:09:45+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Tue Apr 21, 2020 4:55 am at Tue Apr 21, 2020 4:55 am
>
> 
OK There were a bit more fixes than i thought   
1. added new material type
2. fixed bug in material i added for swordsman online
3. add fix for occasions when bones are in Chinese and noesis crashes because it cant read the names - now i give these bone a deafult name with their boneID
4. added support for new type of mesh that dosent include weights and bone names in file - for now these will load but mesh and skeleton are not connected because i didnt see any weights just bone index 

iv tested the only mesh script with all of the samples - they all work
as for the script with bones tested only with 2-3 so the rest is up to you   
Swordsman online scripts.rar

Hi jayn23,

are you sure you uploaded the updated script and not the old one?
Because I tried it with all the samples I provided , but none of them works and I got the same errors i had before ( error messages, crashing etc..)
I tried both mesh + skeleton and only mesh version but got errors with both.

Screens from noesis with mesh + skele script.
[error.png](https://xentaxbackup.github.io/file/17994_error.png)
## Post #38
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-22T22:53:05+00:00
- Post Title: Re: Perfect World Games for noesis

> are you sure you uploaded the updated script and not the old one?
>
> Because I tried it with all the samples I provided , but none of them works and I got the same errors i had before ( error messages, crashing etc..)
>
> I tried both mesh + skeleton and only mesh version but got errors with both.

you are correct i did upload the old one   

lets try again 


 Swordsman online - updated.rar
(4.5 KiB) Downloaded 37 times
## Post #39
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-04-23T15:58:43+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Thu Apr 23, 2020 6:53 am at Thu Apr 23, 2020 6:53 am
>
> 
are you sure you uploaded the updated script and not the old one?
Because I tried it with all the samples I provided , but none of them works and I got the same errors i had before ( error messages, crashing etc..)
I tried both mesh + skeleton and only mesh version but got errors with both.

you are correct i did upload the old one   

lets try again 
Swordsman online - updated.rar

Thank you for your efforts, but for me the program always crashes when I select ski or bone files
## Post #40
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-23T18:10:58+00:00
- Post Title: Re: Perfect World Games for noesis

> Thank you for your efforts, but for me the program always crashes when I select ski or bone files

Try removing any other .SKI scripts from the noesis plugins folder, if for example you have the saint seiya online script in the same folder it might be trying to load the models with the wrong script.

When you say crash - you mean you get an error from the script or the program actually crashes?
anyone else having issues with the script? 

works fine for me tested it with 5 models from swordsman and 5 from jade dynesty - they all work for me
## Post #41
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-04-24T11:47:15+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Fri Apr 24, 2020 2:10 am at Fri Apr 24, 2020 2:10 am
>
> 
Thank you for your efforts, but for me the program always crashes when I select ski or bone files

Try removing any other .SKI scripts from the noesis plugins folder, if for example you have the saint seiya online script in the same folder it might be trying to load the models with the wrong script.

When you say crash - you mean you get an error from the script or the program actually crashes?
anyone else having issues with the script? 

works fine for me tested it with 5 models from swordsman and 5 from jade dynesty - they all work for me

Actually still had the old one in it, deleted it but the same crash. I have added for u my example:

[https://mega.nz/file/lN8XjLIa#wgCr_8sLg ... J_HvUAo0xI](https://mega.nz/file/lN8XjLIa#wgCr_8sLgdzP6dilr7hnXskQH04zjy6aIJ_HvUAo0xI)

Thank u!
## Post #42
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-24T13:03:07+00:00
- Post Title: Re: Perfect World Games for noesis

> Actually still had the old one in it, deleted it but the same crash. I have added for u my example:

Hi,

files you supplied are a different format and version then what we have in swordsman online and jade dynasty, and is identical to perfect world version + format - what i am saying is it will work with perfect world script   
i dont remember ever doing a perfect world mesh only script so i will add that to my list as well, ill try on Sunday to upload new scripts
which game are these files from?

regardless, i will push a fix so it dosent crash if the format is wrong.
what was happening, because its a different format it reached some random huge number and the loop seemed endless etc..
## Post #43
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-04-24T13:13:49+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Fri Apr 24, 2020 9:03 pm at Fri Apr 24, 2020 9:03 pm
>
> 
Actually still had the old one in it, deleted it but the same crash. I have added for u my example:

Hi,

files you supplied are a different format and version then what we have in swordsman online and jade dynasty, and is identical to perfect world version + format - what i am saying is it will work with perfect world script   
i dont remember ever doing a perfect world mesh only script so i will add that to my list as well, ill try on Sunday to upload new scripts
which game are these files from?

regardless, i will push a fix so it dosent crash if the format is wrong.
what was happening, because its a different format it reached some random huge number and the loop seemed endless etc..

This File is from Jade Dynasty.
Maybe different Client Version?
## Post #44
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-24T14:13:44+00:00
- Post Title: Re: Perfect World Games for noesis

Hi guys,

I tried the sample the guy provided and it doesn't work with swordsman/jade dynasty scripts ( both versions). 
But it WORKS with perfect world script ( when it asks to load a .stck file just skip pressing enter). 
It loads only mesh + skeleton and not animations inside the big .bon file.

As a guy stated in another post, there are different version of models. Some of them cointain skeleton and animation in one big .bon file, differently from other models that got a little .bon file with skeleton and single animations in different .stck files.
Here the quote

> Reply from olli9000 ↑Tue May 08, 2018 9:01 am at Tue May 08, 2018 9:01 am
>
> 
Wow nice! Thank you so much. For me it works only in 2015, but only with .ski who have .stck animation files. There are many models, who dont have animation files (stck).
I was searching for the missing stck files, but nothing and I know why. There are different versions where the animations inside. For the newer version, the animations are in .stck files. For older versions the animations are in the .bon file self!

Here you can see, what i mean (version 6 .smd, then animations are in 1 bon file):


I uploaded a new sample for that. The animations must be in the .bon file inside:
https://www.dropbox.com/sh/zstkr9so5f9v ... T4mna?dl=0

Please help me

Samples I provided you works correctly with the updated script. Thanks for your amazing job. 

> Reply from jayn23 ↑Thu Apr 23, 2020 6:53 am at Thu Apr 23, 2020 6:53 am
>
> 
you are correct i did upload the old one   

lets try again 
Swordsman online - updated.rar

But 
I tried the swordsman updated scripts ( static and ski+ bon) with some weapons. I got errors in noesis and other times noesis crashes. 
The static script works with samples in folder 1 and 2 , not with samples in folder 3 and 4
The ski + bon script doesn't work with all of them. 

Here the samples I'm talking about. 
[https://www.mediafire.com/file/7wjfs8dx ... s.rar/file](https://www.mediafire.com/file/7wjfs8dxcwu8yuq/samples.rar/file)


p.s: any chance to support texture of jade dynasty and swordsman in the future? 
Sorry for thousand of request
## Post #45
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-24T15:14:55+00:00
- Post Title: Re: Perfect World Games for noesis

> Sorry for thousand of request

no problem   
i want my scripts to be a good as possible, iv been working on something for more than 2 months now so this is a nice diversion lol

anyway i wont have time to work on this until Sunday, but i will checkout your samples and update my script
## Post #46
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-24T15:43:55+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Fri Apr 24, 2020 11:14 pm at Fri Apr 24, 2020 11:14 pm
>
> 

Sorry for thousand of request 

no problem   
i want my scripts to be a good as possible, iv been working on something for more than 2 months now so this is a nice diversion lol

anyway i wont have time to work on this until Sunday, but i will checkout your samples and update my script

we waited years to see such a script. Couple of days won't be a problem   .
## Post #47
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-26T20:02:39+00:00
- Post Title: Re: Perfect World Games for noesis

> we waited years to see such a script. Couple of days won't be a problem  .

Ok so iv finished updating the script so it loads all your samples, but i am  guessing there are  many more material types to make this script 
complete so here is a suggestion that i did once for a game that ended having over 20 vertex buffer formats:
search your client directory for all .ski files and copy them to a separate folder, then using the mesh only script and noesis use batch export and any file that dosent work put in a directory than i can take samples from.  

I also added support in the script for lower version so now this script opens jade dynesy from version 9 like kingjules uploaded and perfect world/forsaken world meshes as well.

also added basic texture support per you request  
unfortunately this only works for forsaken world and perfect world samples i have since the names are in Chinese.
the sampeles i have from you for swordsman online dont look like Chinese and i cant figure out how to read them, what language is the client?


attachment has mesh only script, with bone support ill probably add tomorrow


 fmt_JadeDynasy-no skin.rar
(2.29 KiB) Downloaded 39 times
## Post #48
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-04-26T21:58:34+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Mon Apr 27, 2020 4:02 am at Mon Apr 27, 2020 4:02 am
>
> 
we waited years to see such a script. Couple of days won't be a problem  .
the sampeles i have from you for swordsman online dont look like Chinese and i cant figure out how to read them, what language is the client?thanks for the update, the client is chinese, the problem sure don't use correct unpacker to get filenames, so the guy who upload it put like that, I unpack before the game and get with correct file names are in chinese.

Web: [http://xa.wanmei.com/download/](http://xa.wanmei.com/download/)
笑傲江湖OL
## Post #49
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-04-26T23:48:15+00:00
- Post Title: Re: Perfect World Games for noesis

I seem to have found a bug in noesis and wondering if anyone knows how to overcome it or contact rich to report it?

I added all my changes to the mesh + skeleton script and i kept getting these I/O errors when trying to decode the Chinese char which is weird because it works just fine for the mesh only version



so i started playing with it and found that when i comment out paired files it works just fine:


i also added conditions that if its a wrong version or unsupported format, it will just exit with comment  - no more crashing or endless loops
and made it so you double click first .ski file and only need to choose .bon, 1 less click ---- when you debug alot that 1 click get tiresome   
please let me know if everything works.

for now file with skeleton loads everything without textures

> thanks for the update, the client is chinese, the problem sure don't use correct unpacker to get filenames, so the guy who upload it put like that, I unpack before the game and get with correct file names are in chinese.
if you have the names in Chinese the only mesh version should work for you, if you can upload a sample or 2 that have both normal maps and diffuse ill try to get both to load currently i load only diffuse because that what i had
[fmt_JadeDynasty.rar](https://xentaxbackup.github.io/file/18044_fmt_JadeDynasty.rar)
## Post #50
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-04-29T18:17:33+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from CriticalError ↑Mon Apr 27, 2020 5:58 am at Mon Apr 27, 2020 5:58 am
>
> 
jayn23 wrote: ↑Mon Apr 27, 2020 4:02 am
we waited years to see such a script. Couple of days won't be a problem  .
the sampeles i have from you for swordsman online dont look like Chinese and i cant figure out how to read them, what language is the client?
thanks for the update, the client is chinese, the problem sure don't use correct unpacker to get filenames, so the guy who upload it put like that, I unpack before the game and get with correct file names are in chinese.

Web: http://xa.wanmei.com/download/
笑傲江湖OL

Yes i use quickbms scripts from aluigi and filenames are not extracted, the client version is chinese.

I tried an huge amount of unpacker but none of them work.
Could you please share with the community the unpacker you used  for swordsman online and tell us which chinese client version you have?

thanks
## Post #51
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2020-05-01T12:04:59+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from Drawing ↑Fri Apr 24, 2020 10:13 pm at Fri Apr 24, 2020 10:13 pm
>
> 

As a guy stated in another post, there are different version of models. Some of them cointain skeleton and animation in one big .bon file, differently from other models that got a little .bon file with skeleton and single animations in different .stck files.
Here the quote
olli9000 wrote: ↑Tue May 08, 2018 9:01 am
Wow nice! Thank you so much. For me it works only in 2015, but only with .ski who have .stck animation files. There are many models, who dont have animation files (stck).
I was searching for the missing stck files, but nothing and I know why. There are different versions where the animations inside. For the newer version, the animations are in .stck files. For older versions the animations are in the .bon file self!

Here you can see, what i mean (version 6 .smd, then animations are in 1 bon file):


I uploaded a new sample for that. The animations must be in the .bon file inside:
https://www.dropbox.com/sh/zstkr9so5f9v ... T4mna?dl=0

Please help me
Yes, thats me   Iam so happy about this thread, awesome job for the plugin!! With stck animation it works like a charm here. But the .bon files in older versions contain the animation data inside the .bon file, wich i cant open   Iam not sure atm - is that possible/do you solve that?
## Post #52
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-02T06:31:31+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Mon Apr 27, 2020 7:48 am at Mon Apr 27, 2020 7:48 am
>
> 
if you have the names in Chinese the only mesh version should work for you, if you can upload a sample or 2 that have both normal maps and diffuse ill try to get both to load currently i load only diffuse because that what i hadwell I don't have client but the tip to get correct file names is change your system locale.
## Post #53
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-06T20:21:04+00:00
- Post Title: Re: Perfect World Games for noesis

iv been trying to figure out the other .stck formats

I have been successful in figuring out Saint Seiya animation   


the other formats are weird managed to understand the block size so i successfully loop from BoneID 0 to 1 and from 1 to 2 etc.. 
translation part has 12 bytes for x,y,z which is normal but the rotation part has only 6 bytes  - i tried reading them as half floats but most are Nan...

the following code will loop thru structure correctly but i am not reading the data correctly.

```

#version 3
version = struct.unpack("<I",g.read(4))[0] # num of meshes

boneCount = struct.unpack("<I",g.read(4))[0]

g.seek(20,0)

numFrames = struct.unpack("<I",g.read(4))[0]

ukw = struct.unpack("<I",g.read(4))[0]

g.seek(44,0)

for i in range (boneCount):

    boneID = struct.unpack("<I",g.read(4))[0]

    TransCount = struct.unpack("<I",g.read(4))[0]

    g.seek(9,1)

    for k in range(TransCount):
            x = struct.unpack("<f",g.read(4))[0]
            y = struct.unpack("<f",g.read(4))[0]
            z = struct.unpack("<f",g.read(4))[0]
      
    g.seek(16,1)
            
    RotCount = struct.unpack("<I",g.read(4))[0]
    g.seek(9,1)

    #could be packed quaterion or euler angels
    for k in range(RotCount):
            x = struct.unpack("<e",g.read(2))[0]
            y = struct.unpack("<e",g.read(2))[0]
            z = struct.unpack("<e",g.read(2))[0]
                
    g.seek(16,1)
```


ill be posting updated script once i see if i or some one else can help figure this format out
## Post #54
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-05-07T13:52:05+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Thu May 07, 2020 4:21 am at Thu May 07, 2020 4:21 am
>
> 
iv been trying to figure out the other .stck formats

I have been successful in figuring out Saint Seiya animation   


the other formats are wired managed to understand the block size so i successfully loop from BoneID 0 to 1 and from 1 to 2 etc.. 
translation part has 12 bytes for x,y,z which is normal but the rotation part has only 6 bytes  - i tried reading them as half floats but most are Nan...

the following code will loop thru structure correctly but i am not reading the data correctly.
Code: Select allMagic = ReadStringKnown(g, 8)

version = struct.unpack("<I",g.read(4))[0] # num of meshes

boneCount = struct.unpack("<I",g.read(4))[0]

g.seek(20,0)

numFrames = struct.unpack("<I",g.read(4))[0]

ukw = struct.unpack("<I",g.read(4))[0]

g.seek(44,0)

for i in range (boneCount):

    boneID = struct.unpack("<I",g.read(4))[0]

    TransCount = struct.unpack("<I",g.read(4))[0]

    g.seek(9,1)

    for k in range(TransCount):
            x = struct.unpack("<f",g.read(4))[0]
            y = struct.unpack("<f",g.read(4))[0]
            z = struct.unpack("<f",g.read(4))[0]
      
    g.seek(16,1)
            
    RotCount = struct.unpack("<I",g.read(4))[0]
    g.seek(9,1)

    #could be packed quaterion or euler angels
    for k in range(RotCount):
            x = struct.unpack("<e",g.read(2))[0]
            y = struct.unpack("<e",g.read(2))[0]
            z = struct.unpack("<e",g.read(2))[0]
                
    g.seek(16,1)

ill be posting updated script once i see if i or some one else can help figure this format out

You are Create maybe Animation works in future for PW/JD/Swordsmann
## Post #55
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-07T22:18:42+00:00
- Post Title: Re: Perfect World Games for noesis

> You are Create maybe Animation works in future for PW/JD/Swordsmann

As far as i have been able to find there are 4 types of .stck 
version 1 - used in perfect world which my old script supported
version 2 + version 3 - found in swordsman online  and i would assume all the newer games which i dont understand and to be honest without help its not gonna happen.
version 2 unique  -  special format found only in Saint Seiya which i plan to release soon.

So sorry but i dont think you will get more animations than this
## Post #56
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-05-08T07:00:53+00:00
- Post Title: Re: Perfect World Games for noesis

Okay thank u.
But for me no Plugin work for any Model..^^
## Post #57
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-08T15:19:05+00:00
- Post Title: Re: Perfect World Games for noesis

> Okay thank u.
>
> But for me no Plugin work for any Model..^^

this is a unfinished script "all in one" combining all formats in this thread - its a mesh only that can open all games in this thread
PW/FW/Saint Seyia/JD/SO ---  .ski ,bmd, mox

i am posting it just so you can check if it works with you models, if it dosent upload samples.

next week i will post one with .stck and .bon  and better auto texturing.
[fmt_PerfectWorldGames_MO.rar](https://xentaxbackup.github.io/file/18107_fmt_PerfectWorldGames_MO.rar)
## Post #58
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2020-05-09T11:03:52+00:00
- Post Title: Re: Perfect World Games for noesis

With the last Script it works for me perfect!
Thank u very much!

Maybe u can need example for stck Format:
[https://mega.nz/file/wIERhYqS#jYw_UjvM6 ... j849BDufGk](https://mega.nz/file/wIERhYqS#jYw_UjvM6FwGzhZMswxeLgXAnGzRTlJ-Pj849BDufGk)

Best Regards
## Post #59
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-09T20:58:44+00:00
- Post Title: Re: Perfect World Games for noesis

Here is my finale ''all in one" script:

In attachment there are Mesh only script and skinned  + animation script.

Mesh only script - opens all formats mentioned in this thread including ski (form all games)/bmd/mox,  i managed to fix my auto texturing to work 100% correctly. please note that file names must be extracted correctly in Chinese or it wont work - tested on saint seyia and PW.



And another one    


skinned  + animation script - works like Mesh only script + loads .bon (for all games) + .stck animation for Saint Seyia + PW.
sadly i have not been able to figure out version 3 of .stck.
I also have a bug which is a noesis thing i hope rich fixes in the future where i cant load textures in this version so your animation will have to stay untextured.

*If you try to load animation of unsupported version in most cases it will just state unspported and load ski and bon normally.
one  version of animation will cause noesis to crash since it shares a version number with  Saint Seyia (but not the format) so there is no way for me ti distinguish them.

Enjoy the script 
[PerfectWorldGames.rar](https://xentaxbackup.github.io/file/18115_PerfectWorldGames.rar)
## Post #60
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-09T21:28:05+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from jayn23 ↑Sun May 10, 2020 4:58 am at Sun May 10, 2020 4:58 am
>
> 
Here is my finale ''all in one" script:

In attachment there are Mesh only script and skinned  + animation script.

Mesh only script - opens all formats mentioned in this thread including ski (form all games)/bmd/mox,  i managed to fix my auto texturing to work 100% correctly. please note that file names must be extracted correctly in Chinese or it wont work - tested on saint seyia and PW.



And another one    


skinned  + animation script - works like Mesh only script + loads .bon (for all games) + .stck animation for Saint Seyia + PW.
sadly i have not been able to figure out version 3 of .stck.
I also have a bug which is a noesis thing i hope rich fixes in the future where i cant load textures in this version so your animation will have to stay untextured.

*If you try to load animation of unsupported version in most cases it will just state unspported and load ski and bon normally.
one  version of animation will cause noesis to crash since it shares a version number with  Saint Seyia (but not the format) so there is no way for me ti distinguish them.

Enjoy the scriptawesome work, congratulations for your discover and build, keep working hard.
## Post #61
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-10T06:22:51+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from lkw019 ↑Sun Nov 17, 2019 11:18 am at Sun Nov 17, 2019 11:18 am
>
> 
Hello, can you take a look at this game [Zhuxian world], its character format is also ski, the scene is PXD and CHF, thank you.
https://mega.nz/#!yuY3RKDZ!Hf20pxOfqE55 ... Izthcc_3iUthis is not 《诛仙世界》 aka Jade Dinasty 3?
## Post #62
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-10T14:19:45+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Sun May 10, 2020 4:58 am at Sun May 10, 2020 4:58 am
>
> 
Here is my finale ''all in one" script:

In attachment there are Mesh only script and skinned  + animation script.

Mesh only script - opens all formats mentioned in this thread including ski (form all games)/bmd/mox,  i managed to fix my auto texturing to work 100% correctly. please note that file names must be extracted correctly in Chinese or it wont work - tested on saint seyia and PW.

Does the correct files name's matter affect only the auto texturing or the whole script ( importing mesh + skeleton too) ?
## Post #63
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-10T19:29:39+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Does the correct files name's matter affect only the auto texturing or the whole script ( importing mesh + skeleton too) ?

only the auto texturing everything else should work
## Post #64
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-11T22:15:46+00:00
- Post Title: Re: Perfect world animation .stck for noesis

So apparently for skinned version of the script i forgot 1 line of code that prevented static mesh from loading, fixed in script below
Thanks CriticalError for pointing it out.

I also found a workaround the bug that prevented loading textures with skinned version  
1. load any ski and when asked to load .bon file press cancel - it should now load mesh with textures
2. load any ski now if you choose .bon it should load with textures
dont have a clue why this works but who cares   


[fmt_PerfectWorldGames.rar](https://xentaxbackup.github.io/file/18127_fmt_PerfectWorldGames.rar)
## Post #65
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-13T19:37:34+00:00
- Post Title: Re: Perfect world animation .stck for noesis

Did anyone success in exporting skeletal mesh and animation from noesis in a readable format for  3dsmax or blender?
## Post #66
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-13T20:08:45+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from Drawing ↑Thu May 14, 2020 3:37 am at Thu May 14, 2020 3:37 am
>
> 
Did anyone success in exporting skeletal mesh and animation from noesis in a readable format for  3dsmax or blender?yes, you can export to DAE o PSA, it Works in SSO I test.
## Post #67
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-13T21:07:41+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from CriticalError ↑Thu May 14, 2020 4:08 am at Thu May 14, 2020 4:08 am
>
> 
Drawing wrote: ↑Thu May 14, 2020 3:37 am
Did anyone success in exporting skeletal mesh and animation from noesis in a readable format for  3dsmax or blender?
yes, you can export to DAE o PSA, it Works in SSO I test.

Sorry for my ignorance but what SSO stands for ?
## Post #68
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-13T23:02:22+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from Drawing ↑Thu May 14, 2020 5:07 am at Thu May 14, 2020 5:07 am
>
> 
CriticalError wrote: ↑Thu May 14, 2020 4:08 am
Drawing wrote: ↑Thu May 14, 2020 3:37 am
Did anyone success in exporting skeletal mesh and animation from noesis in a readable format for  3dsmax or blender?
yes, you can export to DAE o PSA, it Works in SSO I test.


Sorry for my ignorance but what SSO stands for ?ahahah no problema, is Saint Seiya Online
## Post #69
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2020-05-13T23:23:35+00:00
- Post Title: Re: Perfect world animation .stck for noesis

Ah ok  

I tried with a friend to export models and ani in .fbx but when importing them in 3d studio max nothing is imported, the scene is empty, dunno maybe we made some mistake or maybe .fbx export from noesis is bugged. Anyway thanks for the tips , let s move to collada then
## Post #70
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-21T16:05:24+00:00
- Post Title: Re: Perfect world animation .stck for noesis

@jayn23 is possible check some files won't load in Saint Seiya Online? if you can ofc, thanks for all support.

[https://www.mediafire.com/file/qouat8jf ... ad.7z/file](https://www.mediafire.com/file/qouat8jf9l05g8f/SSO_No_Load.7z/file)
## Post #71
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-05-21T21:02:49+00:00
- Post Title: Re: Perfect world animation .stck for noesis

Hi,

not sure what the issue, is but all of the models worked for me maybe you sent me the wrong samples? or using a older version of script?
i deleted what i had in plugins directory and downloaded from here and it worked - all of them
## Post #72
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2020-05-22T02:01:07+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Fri May 22, 2020 5:02 am at Fri May 22, 2020 5:02 am
>
> 
Hi,

not sure what the issue, is but all of the models worked for me maybe you sent me the wrong samples? or using a older version of script?
i deleted what i had in plugins directory and downloaded from here and it worked - all of themyou right, im not sure about issue, and im %90 I upodate script but well I download again and paste there and voila, it load now ahahah thats crazy, sorry for make you lose time bro, really grateful for all support in the script do, have a nice day.
## Post #73
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2020-12-15T08:42:00+00:00
- Post Title: Re: Perfect world animation .stck for noesis

Hello! 

First of all, thank you for your work and your scripts! I really appriciate it.

I would ask you about new BMD file structure from last patches. I got this error:


Would it be possible to look at it?

Thank you so much!
[BMD samples.rar](https://xentaxbackup.github.io/file/19191_BMD samples.rar)
## Post #74
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-12-17T16:02:19+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from Pinstripe ↑Tue Dec 15, 2020 4:42 pm at Tue Dec 15, 2020 4:42 pm
>
> 
Hello! 

First of all, thank you for your work and your scripts! I really appriciate it.

I would ask you about new BMD file structure from last patches. I got this error:

Would it be possible to look at it?

Thank you so much!

sure ill take a look at it
## Post #75
- Username: Pinstripe
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Dec 15, 2020 4:37 pm
- Post datetime: 2020-12-18T09:21:38+00:00
- Post Title: Re: Perfect world animation .stck for noesis

> Reply from jayn23 ↑Fri Dec 18, 2020 12:02 am at Fri Dec 18, 2020 12:02 am
>
> 
sure ill take a look at it

Thank you! Appriciate it!
## Post #76
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-12-20T18:16:34+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from Pinstripe ↑Fri Dec 18, 2020 5:21 pm at Fri Dec 18, 2020 5:21 pm
>
> 
jayn23 wrote: ↑Fri Dec 18, 2020 12:02 am
sure ill take a look at it


Thank you! Appriciate it!

found some time today to take a look at it.
I already got a script working for both samples, but i am going to need 2-3 more samples with multiple mesh to make sure i got it right.
## Post #77
- Username: cgradilla
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 08, 2017 9:36 am
- Post datetime: 2020-12-20T21:43:16+00:00
- Post Title: Re: Perfect World Games for noesis

Thanks a lot for all the wonderful work done so far, I can get now the models.  

Also I want to comment some Issues I found.

Seems like some name textures in chinese make conflicts with the files. Not sure if this happens because my System , Noesis, or how the .ski file was made it. But this error happens only if I cancel the search for the .bon file. 



e01 noesis_file.png (7.45 KiB) Viewed 334 times



If I open the .bon file and the animation the model opens fine, so Idon't know what is causing this issue so far.
Also if remove the texture files I can open all the models too canceling the search of .bon files 

here a Link with one of the models causing the trouble
[https://drive.google.com/file/d/10GDI8O ... sp=sharing](https://drive.google.com/file/d/10GDI8ODgk6AVNecBWVJk7k6_-FLPei5y/view?usp=sharing)

Thanks again for the script and the hard work
## Post #78
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2020-12-27T21:56:03+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from cgradilla ↑Mon Dec 21, 2020 5:43 am at Mon Dec 21, 2020 5:43 am
>
> 
Thanks a lot for all the wonderful work done so far, I can get now the models.  

Also I want to comment some Issues I found.

Seems like some name textures in chinese make conflicts with the files. Not sure if this happens because my System , Noesis, or how the .ski file was made it. But this error happens only if I cancel the search for the .bon file. 

noesis_file.png

If I open the .bon file and the animation the model opens fine, so Idon't know what is causing this issue so far.
Also if remove the texture files I can open all the models too canceling the search of .bon files 

here a Link with one of the models causing the trouble
https://drive.google.com/file/d/10GDI8O ... sp=sharing

Thanks again for the script and the hard work

sorry i didn't respond sooner, ill take a look and see if i can figure out what's the problem.
when writing the script i did have a texture related bug that was caused by noesis built in python if its something like that then i wont be able to do anything about it.
## Post #79
- Username: cgradilla
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 08, 2017 9:36 am
- Post datetime: 2020-12-28T19:31:02+00:00
- Post Title: Re: Perfect World Games for noesis

no problem

thanks a lot for your hard work
## Post #80
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-14T06:01:54+00:00
- Post Title: Re: Perfect World Games for noesis

> I also found a workaround the bug that prevented loading textures with skinned version  
>
> 1. load any ski and when asked to load .bon file press cancel - it should now load mesh with textures
>
> 2. load any ski now if you choose .bon it should load with textures
>
> dont have a clue why this works but who cares

Thanks for your script Jayn23!Can you please update the script? I'm getting an error with some models of swordsman online, please check it when you have time, thanks!
[https://www.mediafire.com/file/8xeoizwk ... r.zip/file](https://www.mediafire.com/file/8xeoizwkcq826jh/creature-error.zip/file)



swordsman-erro.png (9.18 KiB) Viewed 187 times
## Post #81
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-15T18:27:43+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from moonpaladin ↑Wed Apr 14, 2021 2:01 pm at Wed Apr 14, 2021 2:01 pm
>
> 

Thanks for your script Jayn23!Can you please update the script? I'm getting an error with some models of swordsman online, please check it when you have time, thanks!
https://www.mediafire.com/file/8xeoizwk ... r.zip/file

Hi,

Script Version 1.2 now released:
New mesh type to support this model, and new .bmd support that was requested a long time ago (i never got my samples to finalize it tho...)
New option at the begining of the script:
MESH_ONLY = False  - will load mesh + skeleton + animation
MESH_ONLY = True  - will load only mesh, instaed of having a Mesh Only version for this script.
Made a tiny fix so unsupported mesh types wont give an error anymore, you will just get a "mesh type not supported" message in Debug Log.
[fmt_PerfectWorldGames_V12.rar](https://xentaxbackup.github.io/file/19915_fmt_PerfectWorldGames_V12.rar)
## Post #82
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-16T07:33:00+00:00
- Post Title: Re: Perfect World Games for noesis

> Script Version 1.2 now released:
>
> New mesh type to support this model, and new .bmd support that was requested a long time ago (i never got my samples to finalize it tho...)
>
> New option at the begining of the script:
>
> MESH_ONLY = False  - will load mesh + skeleton + animation
>
> MESH_ONLY = True  - will load only mesh, instaed of having a Mesh Only version for this script.
>
> Made a tiny fix so unsupported mesh types wont give an error anymore, you will just get a "mesh type not supported" message in Debug Log.

Hello Jayn23! that update was fast! Thank you. I found some other models that give different errors, I'm adding them in a folder, hope you can take a look at them! thanks a ton!

[https://www.mediafire.com/file/vzukpxaa ... r2.7z/file](https://www.mediafire.com/file/vzukpxaafjxsakn/creature-error2.7z/file)
## Post #83
- Username: jayn23
- Rank: mega-veteran
- Number of posts: 250
- Joined date: Mon Jul 18, 2011 4:30 am
- Post datetime: 2021-04-16T10:08:00+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from moonpaladin ↑Fri Apr 16, 2021 3:33 pm at Fri Apr 16, 2021 3:33 pm
>
> 

Hello Jayn23! that update was fast! Thank you. I found some other models that give different errors, I'm adding them in a folder, hope you can take a look at them! thanks a ton!

So i took a look at all your sampels,
All the meshes in Error 1 worked without any fixes by me, so not sure what the issue is.
All meshes in mesh type not supported now work   
For the Noesis crashes samples - i got them working but it was weired since they are .SKI Version 9 but are formatted like .SKI Version 10.
to bypass this i added a new option at the start of script:
VERSION9_OVERRIDE = False - while False it will act normaly for all meshes but your samples wont work (Deafult Option)
VERSION9_OVERRIDE = True - will by pass Version 9 formatting and work like Version 10
[fmt_PerfectWorldGames_V121.rar](https://xentaxbackup.github.io/file/19916_fmt_PerfectWorldGames_V121.rar)
## Post #84
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-16T15:55:00+00:00
- Post Title: Re: Perfect World Games for noesis

> So i took a look at all your sampels,
>
> All the meshes in Error 1 worked without any fixes by me, so not sure what the issue is.
>
> All meshes in mesh type not supported now work   
>
> For the Noesis crashes samples - i got them working but it was weired since they are .SKI Version 9 but are formatted like .SKI Version 10.
>
> to bypass this i added a new option at the start of script:
>
> VERSION9_OVERRIDE = False - while False it will act normaly for all meshes but your samples wont work (Deafult Option)
>
> VERSION9_OVERRIDE = True - will by pass Version 9 formatting and work like Version 10
! Thanks!
## Post #85
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-05-18T10:18:06+00:00
- Post Title: Re: Perfect World Games for noesis

Hey,

Do you know where the buildings are included?

Best Regards
## Post #86
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2021-05-18T10:18:26+00:00
- Post Title: Re: Perfect World Games for noesis

> Reply from moonpaladin ↑Fri Apr 16, 2021 11:55 pm at Fri Apr 16, 2021 11:55 pm
>
> 

So i took a look at all your sampels,
All the meshes in Error 1 worked without any fixes by me, so not sure what the issue is.
All meshes in mesh type not supported now work   
For the Noesis crashes samples - i got them working but it was weired since they are .SKI Version 9 but are formatted like .SKI Version 10.
to bypass this i added a new option at the start of script:
VERSION9_OVERRIDE = False - while False it will act normaly for all meshes but your samples wont work (Deafult Option)
VERSION9_OVERRIDE = True - will by pass Version 9 formatting and work like Version 10

! Thanks!
#
Hey,

Do you know where the buildings are included?

Best Regards
## Post #87
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-05-18T15:21:24+00:00
- Post Title: Re: Perfect World Games for noesis

> #
>
> Hey,
>
> 
>
> Do you know where the buildings are included?
>
> 
>
> Best Regards
Hi! I just checked the mount models, hope you find them and them had the same format :'(
