## Post #1
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-09-03T15:55:07+00:00
- Post Title: Ironsight Animation (*.bea)

Hi, guys! After finishing Ironsight's model file script:[viewtopic.php?f=16&t=24707](https://forum.xentax.com/viewtopic.php?f=16&t=24707), I tried to import animation. But I can't figure out some "20 bytes" information. These bytes should contain position, rotation and scale of animated bones. I am not sure their struct.
Almost finish 010 templates except these "20bytes". Template and samples below, hope someone could give a hand:
[https://drive.google.com/file/d/1KPQb-i ... sp=sharing](https://drive.google.com/file/d/1KPQb-iEzWaNPtU8s6bwlXvNyGlcAJeQB/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-03T21:19:42+00:00
- Post Title: Ironsight Animation (*.bea)

Hi, interpreting those 20 bytes as DWord plus 4 floats looks a liitle bit strange:
ani\social\interact\1st\switch.bea:

 2 f2260000 -16.625000 0.000000 -0.000001 -4.999999 
 3  1130ff3 -81.016815 0.000004 0.000001 0.000002 
 4 f291d922 -5501868544.000000 0.000000 0.000003 -0.000001 
 5 fc390947 -62179.769531 -0.000005 0.000002 -0.000004 

So what applies better (probably) is interpreting 4 bytes each as WORD plus half float (instead of float), with the WORDs not printed:

 0        0 -2.000000 0.000031 0.000031 -0.000031
 1        0 -2.000000 0.000031 0.000031 -0.000031
 2 f2260000 -2.759766 0.221436 -0.343750 -2.310547
 3  1130ff3 -3.316406 0.406006 0.343750 0.374756
 4 f291d922 -30.546875 0.276123 0.387939 -0.358643
 5 fc390947 -7.445312 -0.418213 0.368408 -0.402588
 6 1252ff6e -3.720703 0.392090 0.384277 -0.354980
 7  b77f294 -3.318359 -0.344482 0.414062 -0.294434
 8  2d1fcb4 -2.078125 0.315918 -0.379639 0.441162
 9 f0cef7bc -3.238281 0.379639 0.372070 0.243652
10 efd3f07d -4.054688 -0.386963 -0.400635 0.409180
11 f730f78d -2.589844 -0.381836 0.401367 0.383057
12 f7bafaf7 -2.429688 0.379395 0.369385 0.376465
13 edc1ec10 -6.000000 0.344238 -0.438477 -0.410156
14 f7c3f700 -2.589844 -0.395752 -0.343750 0.401855
15 faeaf798 -2.394531 0.219360 0.260986 -0.406006
16 f7dcf28b -3.019531 -0.404053 -0.383057 0.386963
17 fa13f635 -2.537109 -0.391357 -0.305420 -0.424561
18 fdd5f721 -2.394531 0.383301 0.410400 0.407715
19 fdd5f721 -2.394531 0.388184 0.313232 0.395752
20 fdd5f721 -2.394531 0.405029 0.335449 0.330566
21 e475c64a 0.000031 1.403320 -0.971191 0.830566
22  113ffd7 -2.500000 -0.400391 0.298584 -0.372314
23   a5ffe8 -2.181641 -0.435303 0.400146 0.397949
24 17a71a1e -16.296875 -0.375000 0.343506 -0.056091
25 17f6cde9 -718.000000 0.273682 0.349365 -0.420898
26  af3dddd 0.004642 0.377686 -0.313965 0.406006
27   eefc29 -2.251953 -0.395996 -0.381348 0.302979
28  635077b -2.394531 -0.379883 0.420166 0.427979
29  635077b -2.394531 -0.292480 -0.368164 -0.440674
30 140af6b7 -4.746094 -0.370117 -0.399902 -0.376953
31 13e7eadc -6.976562 0.357666 0.407227 -0.338623
32 1337eb96 -6.480469 -0.294922 -0.329834 0.316895
33  7bbe886 -5.589844 -0.366455 -0.414062 -0.377930
34  1eaf8a0 -2.275391 -0.416992 -0.393799 0.381104
35  1eaf8a0 -2.275391 -0.417480 0.389648 0.351074
36  11d016d -2.279297 -0.411377 -0.402344 -0.406982
37 17c2e9db -9.718750 -0.239746 0.318115 0.340332
38 1128f002 -4.457031 -0.342529 -0.360352 -0.407227
39 135cee4c -6.523438 -0.395264 -0.385010 0.421143
40  65af5d6 -2.589844 -0.386719 -0.399414 0.438232
41  f5ee766 -7.234375 0.381836 0.414062 -0.390381
42  12a00f1 -2.062500 1.822266 -1.770508 2.125000
43  12e002d -2.611328 -0.380615 -0.375977 -0.276855
44  1c20043 -3.369141 -0.375000 -0.365723 0.420410

Unsure thing is why should only 2 rotation values (radians?) in that frame be positive and the others <= -2.0?
## Post #3
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-09-04T06:32:09+00:00
- Post Title: Ironsight Animation (*.bea)

> Reply from shakotay2 ↑Sun Sep 04, 2022 5:19 am at Sun Sep 04, 2022 5:19 am
>
> 
Unsure thing is why should only 2 rotation values (radians?) in that frame be positive and the others <= -2.0?

Thanks for you help. And those rot,scl,pos values are only placeholders.
I will try to write a noesis script later to use those 4 hfloat values as quat as rotation.
here's the template I inspired from you 
[bea.zip](https://xentaxbackup.github.io/file/22753_bea.zip)
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-09-04T08:59:24+00:00
- Post Title: Ironsight Animation (*.bea)

> Reply from shakotay2 ↑Sun Sep 04, 2022 5:19 am at Sun Sep 04, 2022 5:19 am
>
> 
ani\social\interact\1st\switch.bea:
Interpreting the first 8 bytes as 4 normalized shorts (devided by 0x4000):

```
01:     +0.000000       +0.000000       +0.000000       -1.000000       square sum = 1.000000
02:     +0.000000       -0.216431       +0.000000       -0.976257       square sum = 0.999921
03:     +0.249207       +0.016785       +0.134521       -0.958862       square sum = 0.999899
04:     -0.607300       -0.209900       -0.126160       -0.755676       square sum = 0.999834
05:     +0.144958       -0.059021       -0.441101       -0.883667       square sum = 0.999934
06:     -0.008911       +0.286255       +0.150269       -0.946228       square sum = 0.999949
07:     -0.209717       +0.179138       -0.067505       -0.958801       square sum = 0.999928
08:     -0.051514       +0.044006       -0.016541       -0.997559       square sum = 0.999987
09:     -0.129150       -0.237427       -0.053162       -0.961304       square sum = 0.999982
10:     -0.242371       -0.252747       -0.003906       -0.936646       square sum = 0.999944
11:     -0.132019       -0.137695       -0.002136       -0.981567       square sum = 0.999868
12:     -0.078674       -0.129272       -0.060791       -0.986572       square sum = 0.999921
13:     -0.311523       -0.285095       -0.015259       -0.906250       square sum = 0.999848
14:     -0.140625       -0.128723       -0.006897       -0.981567       square sum = 0.999867
15:     -0.131348       -0.079468       -0.029785       -0.987671       square sum = 0.999948
16:     -0.210266       -0.127197       -0.047729       -0.968140       square sum = 0.999963
17:     -0.153015       -0.092590       -0.034729       -0.983215       square sum = 0.999905
18:     -0.138611       -0.033875       -0.064026       -0.987671       square sum = 0.999954
19:     -0.138611       -0.033875       -0.064026       -0.987671       square sum = 0.999954
20:     -0.138611       -0.033875       -0.064026       -0.987671       square sum = 0.999954
21:     -0.901733       -0.430359       -0.039978       +0.000000       square sum = 0.999930
22:     -0.002502       +0.016785       -0.175232       -0.984375       square sum = 0.999988
23:     -0.001465       +0.010071       -0.105408       -0.994324       square sum = 0.999894
24:     +0.408081       +0.369568       -0.196350       -0.811340       square sum = 0.999937
25:     -0.782654       +0.374390       +0.147583       -0.474854       square sum = 0.999981
26:     -0.533386       +0.171082       +0.695862       +0.449280       square sum = 0.999846
27:     -0.059998       +0.014526       -0.108582       -0.992126       square sum = 0.999916
28:     +0.116882       +0.096985       -0.037292       -0.987671       square sum = 0.999952
29:     +0.116882       +0.096985       -0.037292       -0.987671       square sum = 0.999952
30:     -0.145081       +0.313110       +0.153625       -0.925842       square sum = 0.999871
31:     -0.330322       +0.310974       +0.016235       -0.890991       square sum = 0.999947
32:     -0.318970       +0.300232       +0.015686       -0.898743       square sum = 0.999865
33:     -0.366821       +0.120789       +0.133606       -0.912659       square sum = 0.999944
34:     -0.115234       +0.029907       +0.053406       -0.991394       square sum = 0.999888
35:     -0.115234       +0.029907       +0.053406       -0.991394       square sum = 0.999888
36:     +0.022278       +0.017395       +0.128540       -0.991272       square sum = 0.999942
37:     -0.346008       +0.371216       +0.005493       -0.861572       square sum = 0.999860
38:     -0.249878       +0.268066       +0.003967       -0.930359       square sum = 0.999882
39:     -0.276611       +0.302490       +0.159119       -0.898071       square sum = 0.999865
40:     -0.158813       +0.099243       +0.036316       -0.981567       square sum = 0.999864
41:     -0.384399       +0.240112       +0.087952       -0.886963       square sum = 0.999856
42:     +0.014709       +0.018188       -0.057373       -0.998047       square sum = 0.999936
43:     +0.002747       +0.018433       -0.193420       -0.980896       square sum = 0.999916
44:     +0.004089       +0.027466       -0.287842       -0.957214       square sum = 0.999883

```

The rest 12 bytes should be 3 floats for translation:

```
 1:  0.000000  0.000000  0.000000
 2:  0.000000  -0.000001  -4.999999
 3:  0.000004  0.000001  0.000002
 4:  0.000000  0.000003  -0.000001
 5:  -0.000005  0.000002  -0.000004
 6:  0.000003  0.000002  -0.000001
 7:  -0.000001  0.000005  -0.000000
 8:  0.000001  -0.000002  0.000009
 9:  0.000002  0.000002  0.000000
10:  -0.000003  -0.000003  0.000004
11:  -0.000002  0.000004  0.000002
12:  0.000002  0.000002  0.000002
13:  0.000001  -0.000008  -0.000004
14:  -0.000003  -0.000001  0.000004
15:  0.000000  0.000000  -0.000004
16:  -0.000004  -0.000002  0.000003
17:  -0.000003  -0.000000  -0.000006
18:  0.000002  0.000004  0.000004
19:  0.000003  0.000000  0.000003
20:  0.000004  0.000001  0.000001
21:  0.076661  -0.006032  0.001266
22:  -0.000003  0.000000  -0.000002
23:  -0.000007  0.000003  0.000003
24:  -0.000002  0.000001  -0.000000
25:  0.000000  0.000001  -0.000006
26:  0.000002  -0.000001  0.000004
27:  -0.000003  -0.000002  0.000000
28:  -0.000002  0.000006  0.000006
29:  -0.000000  -0.000002  -0.000008
30:  -0.000002  -0.000003  -0.000002
31:  0.000001  0.000004  -0.000001
32:  -0.000000  -0.000001  0.000001
33:  -0.000002  -0.000005  -0.000002
34:  -0.000005  -0.000003  0.000002
35:  -0.000005  0.000003  0.000001
36:  -0.000004  -0.000004  -0.000004
37:  -0.000000  0.000001  0.000001
38:  -0.000001  -0.000001  -0.000004
39:  -0.000003  -0.000003  0.000006
40:  -0.000003  -0.000003  0.000008
41:  0.000002  0.000005  -0.000003
42:  0.791751  -0.585920  3.013351
43:  -0.000002  -0.000002  -0.000000
44:  -0.000002  -0.000002  0.000006

```

As you can tell by those quaternion values the absolute value of the 'w' factor is almost always the largest one and most values of the translations are too small so chance are that "delta" storage has been used.
## Post #5
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-09-04T18:40:18+00:00
- Post Title: Ironsight Animation (*.bea)

> Reply from Bigchillghost ↑Sun Sep 04, 2022 4:59 pm at Sun Sep 04, 2022 4:59 pm
>
> 
As you can tell by those quaternion values the absolute value of the 'w' factor is almost always the largest one and most values of the translations are too small so chance are that "delta" storage has been used.
Just finish writing a Noesis script like BlackDesert. But it doesn't look correct.
Since .bea doesn't have "bonehash" feature, so I guess animation file should only match mesh file which has the same bone count.
Noesis script attached:
[fmt_Ironsight_bea.zip](https://xentaxbackup.github.io/file/22760_fmt_Ironsight_bea.zip)
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-09-05T14:43:50+00:00
- Post Title: Ironsight Animation (*.bea)

> Reply from PeterZ ↑Mon Sep 05, 2022 2:40 am at Mon Sep 05, 2022 2:40 am
>
> 
Just finish writing a Noesis script ...
Guess you didn't pay attention to the last few words?

> Reply from Bigchillghost ↑Sun Sep 04, 2022 4:59 pm at Sun Sep 04, 2022 4:59 pm
>
> 
... so chance are that "delta" storage has been used.
Multiplying the local bone transformation matrix with the corresponding bone key matrix of each frame does seem to reveal something that makes sense:
(ani\social\emotion\love_master.bea)



bea_test.png (52.68 KiB) Viewed 132 times



Noesis code for the test:

```
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("bea anim test", ".msh")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	#noesis.logPopup()
	return 1

#check if it's this type based on the data
def noepyCheckType(data):
	if len(data) < 0x80:
		return 0
	return 1

#load the model
def noepyLoadModel(data, mdlList):
	noesis.logPopup()
	dir = rapi.getDirForFilePath(rapi.getInputName())
	
	skelFile = dir + "/og_01_naf.msh"
	fp = open(skelFile, "rb")
	data = fp.read()
	fp.close()
	bs = NoeBitStream(data)
	
	bs.seek(0x24, NOESEEK_ABS)
	boneCount = bs.readInt()
	bones = []
	boneMats = []
	parents = []
	for i in range(0, boneCount):
		bs.seek(8, NOESEEK_REL)
		parent = bs.readInt()
		tran = NoeVec3.fromBytes(bs.readBytes(12))
		rot = NoeQuat.fromBytes(bs.readBytes(16))
		bs.seek(16, NOESEEK_REL)
		boneMat = rot.toMat43()
		boneMat[3] = tran
		boneMats.append(boneMat)
		parents.append(parent)
		bones.append( NoeBone(i, "bone%d"%i, boneMat, None, parent) )
	
	lclMatrix = []
	for i in range(0, boneCount):
		boneMat = boneMats[i]
		if parents[i] != -1:
			if parents[i] > i:
				print("warning, parent bone behind!")
				return 0
			boneMat = boneMat * boneMats[parents[i]].inverse()
		lclMatrix.append(boneMat)
	
	animFile = dir + "/love_master.bea"
	fp = open(animFile, "rb")
	data = fp.read()
	fp.close()
	bs = NoeBitStream(data)
	bs.seek(4, NOESEEK_ABS)
	version = bs.readInt()
	bs.seek(0xC, NOESEEK_ABS)
	animBoneCount = bs.readInt()
	if animBoneCount != boneCount:
		print("error! wrong anim file")
		return 0
	
	frameCount = bs.readInt()
	bs.seek(4, NOESEEK_REL)
	
	animBoneMats = [0]*(frameCount*boneCount)
	for x in range(0, frameCount):
		frameAnimBoneCount = bs.readInt()
		if version == 0xA:
			frameAnimBoneCount //= 0x14
		if frameAnimBoneCount != boneCount:
			print("error! mismatched bone count in frame %d"%x)
			return 0
		for i in range(0, boneCount):
			quat = [ bs.readShort() / 16384.0 for x in range(4) ]
			rot = NoeQuat( (quat[0],quat[1],quat[2],quat[3]) )
			tran = NoeVec3.fromBytes(bs.readBytes(12))
			boneMat = rot.toMat43()
			boneMat[3] = tran
			boneMat = boneMat * lclMatrix[i]
			animBoneMats[x*boneCount+i] = boneMat
	
	anim = NoeAnim("anim", bones, frameCount, animBoneMats, 20)
	anims = [ anim ]
	mdl = NoeModel()
	mdl.setBones(bones)
	mdl.setAnims(anims)
	mdlList.append(mdl)
	#rapi.setPreviewOption("setAngOfs", "0 -90 90")
	
	return 1

```

Yet as you can see from the right-most screenshot something weird is happing here. Multiplying the following key with its previous key recursively however results in worse outcomes.

Anyway, have spent too much time on this one so I'm off now. Good luck with that.
## Post #7
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-09-10T05:13:25+00:00
- Post Title: Ironsight Animation (*.bea)

> Reply from Bigchillghost ↑Mon Sep 05, 2022 10:43 pm at Mon Sep 05, 2022 10:43 pm
>
> 
Yet as you can see from the right-most screenshot something weird is happing here. Multiplying the following key with its previous key recursively however results in worse outcomes.
Here's my code:

```
#By PeterZ
#Special thanks: Bigchillghost and shakotay2

from inc_noesis import *
import noesis
import rapi
import os
import glob


def registerNoesisTypes():
    handle = noesis.register("Ironsight Animation", ".bea")
    noesis.setHandlerTypeCheck(handle, CheckType)
    # see also noepyLoadModelRPG
    noesis.setHandlerLoadModel(handle, LoadModel)
    noesis.logPopup()
    return 1

def CheckType(data):
    bs = NoeBitStream(data)
    idMagic = bs.readBytes(4)
    if idMagic != b'ANIM':
        return 0
    return 1

def LoadModel(data, mdlList):
    loadedRootBone=-1
    ctx = rapi.rpgCreateContext()
    skelbones=[]
    skelBoneParents=[]
    skelBoneMtxs=[]
    skelBoneLocalMtxs=[]
    kfBoneFrameMtxs=[]#[kfBoneIdx][frameIdx]
    bs = NoeBitStream(data)

    test = rapi.getDirForFilePath(rapi.getInputName())
    os.chdir(test)
    test = glob.glob("*.msh")
    try:
        skelfile = rapi.getDirForFilePath(rapi.getInputName()) + test[0]
    except:
        skelfile = ""
    if not rapi.checkFileExists(skelfile):
        print("require msh file to load skeleton")
        return 0
    #msh file START
    print('Loading skeleton from',skelfile)
    ss = rapi.loadIntoByteArray(skelfile)
    ss = NoeBitStream(ss)
    ss.seek(0x24)
    skelBoneCount=ss.readUInt()
    print('skeleton BoneCount',str(skelBoneCount))
    for skelBoneIndex in range(0,skelBoneCount):
        if(skelBoneIndex):
            skelBoneName='bone'+str(skelBoneIndex)
        else:
            skelBoneName='root'
        ss.seek(8, NOESEEK_REL)
        skelBoneParent=ss.readInt()
        if(skelBoneParent==-1):#attach to first root bone(bone0) to support root motion
            if (loadedRootBone>=0):
                skelBoneParent=loadedRootBone
            else:
                loadedRootBone=skelBoneIndex
        skelBoneTrn=NoeVec3.fromBytes(ss.readBytes(12))
        skelBoneRot = NoeQuat.fromBytes(ss.readBytes(16))
        skelBoneMtx=skelBoneRot.toMat43()
        skelBoneMtx[3]=skelBoneTrn
        skelNewBone = NoeBone(skelBoneIndex, skelBoneName, skelBoneMtx, None, int(skelBoneParent))
        skelbones.append(skelNewBone)
        skelBoneParents.append(skelBoneParent)
        skelBoneMtxs.append(skelBoneMtx)
        ss.seek(16,NOESEEK_REL)
    for i in range(skelBoneCount):#calculate bone localMtx
        boneMtx=skelBoneMtxs[i]
        if(skelBoneParents[i]>=0):
            if(skelBoneParents[i]>i):
                print("warning, parent bone behind!")
                return 0
            boneMtx=boneMtx*skelBoneMtxs[skelBoneParents[i]].inverse()
        skelBoneLocalMtxs.append(boneMtx)

    print('Finish Loading skeleton')  
    #msh file END
    #bea file START
    print("Loading Animation from",rapi.getInputName())

    bs.seek(4,NOESEEK_ABS)#ANIM
    fileVersion=bs.readUInt()
    print("fileVersion",str(fileVersion))
    bs.seek(4,NOESEEK_REL)
    kfTotalBoneCount=bs.readUInt()
    print("kfTotalBoneCount",str(kfTotalBoneCount))
    kfBoneFrameMtxs=[[] for i in range(kfTotalBoneCount)]
    kfTotalFrameCount=bs.readUInt()
    bs.seek(4,NOESEEK_REL)

    if(kfTotalBoneCount!=skelBoneCount):
        print("BoneCount in Anim File",str(kfTotalBoneCount))
        print("BoneCount in Mesh File",str(skelBoneCount))
        print("Mesh file dismatch")
        return 0

    for kframeIdx in range(kfTotalFrameCount):
        kfBoneCount=bs.readUInt()
        if(fileVersion==10):
            kfBoneCount //= 20

        if(kfBoneCount!=kfTotalBoneCount):
            print(print("error! mismatched bone count in frame %d"%kframeIdx))
            return 0
        for kfBoneIdx in range(kfBoneCount):
            quat=[ bs.readShort() / 16384.0 for i in range(4) ]
            rotQuat=NoeQuat((quat[1],quat[0],quat[2],-quat[3]))#for lowerbody
            if(kfBoneIdx==2 or kfBoneIdx>=13):#spine bones
                rotQuat=NoeQuat((-quat[1],quat[0],-quat[2],quat[3]))
            if(kfBoneIdx>=21):#arm bones
                rotQuat=NoeQuat((-quat[1],quat[0],quat[2],quat[3]))
            posVec=NoeVec3.fromBytes(bs.readBytes(12))
            boneMtx=rotQuat.toMat43()
            boneMtx[3]=posVec
            boneMtx *= skelBoneLocalMtxs[kfBoneIdx]
            kfBoneFrameMtxs[kfBoneIdx].append(boneMtx)

    es=noeStrFromBytes(bs.readBytes(bs.readUInt()))
    print("ES",es)
    #bea File END

    kfBoneMtxs = [0]*(kfTotalFrameCount*kfTotalBoneCount)
    for kframeIdx in range(kfTotalFrameCount):
        for kfBoneIdx in range(kfTotalBoneCount):
            kfBoneMtxs[kframeIdx*kfTotalBoneCount+kfBoneIdx]=kfBoneFrameMtxs[kfBoneIdx][kframeIdx]
    anim = NoeAnim(rapi.getExtensionlessName(rapi.getLocalFileName(rapi.getInputName())), skelbones, kfTotalFrameCount, kfBoneMtxs, 1)
    mdl = NoeModel(bones=skelbones,anims=[anim])
    mdlList.append(mdl)
    return 1

```

Just need to edit "rotQuat" to get more normal animation
## Post #8
- Username: ice
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 12, 2019 1:24 am
- Post datetime: 2022-09-11T19:52:07+00:00
- Post Title: Ironsight Animation (*.bea)

I found a problem. The bones of the first -person arm bone and the first -person weapon animation are always different, which makes me unable to preview all the first -person arm animation.


The bone of the first person's arm model is 45



But the bones of the animation are uncertain, and none of them are 45
## Post #9
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2022-09-18T15:38:29+00:00
- Post Title: Ironsight Animation (*.bea)

> Reply from ice ↑Mon Sep 12, 2022 3:52 am at Mon Sep 12, 2022 3:52 am
>
> 
I found a problem. The bones of the first -person arm bone and the first -person weapon animation are always different, which makes me unable to preview all the first -person arm animation.

Currently the script is unfinished, we need more information to generate the bonemap between skeleton and animation, like bonehash.
