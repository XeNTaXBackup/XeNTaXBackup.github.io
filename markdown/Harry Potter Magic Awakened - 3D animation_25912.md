## Post #1
- Username: Maechen
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Dec 22, 2019 11:37 pm
- Post datetime: 2022-10-16T21:08:07+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

Hi guys ! I managed to export the 3D animation of the game Harry Potter Magic Awakened.
Here is an archive of Luna's model : [https://cdn.discordapp.com/attachments/ ... a_HPMA.zip](https://cdn.discordapp.com/attachments/543593726149394434/1030974330366087318/luna_HPMA.zip)
Inside, you could find 5 file types :
- OBJ (mesh)
- DDS (texture)
- XML (some text data, one is the list of the animations)
- SKE (skelton ?)
- RAW (animation ?)

The SKE and RAW files architecture respect those 3 parts : HEAD, DATA and NAME
The NAME part is very helpfull to know which animation (?) or skeleton (?) is.

In order to reach my goal, I would like to know if the SKE and RAW files are indeed respectively skeleton and animation.
What do you think about this ?

Does anyone have knowledges about those formats ?
How can I use them (SKE and RAW) in order to get the animations on this model ?

Thanks in advance for your help!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-17T20:08:59+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

SKE: should be doable, 40 bytes blocks, maybe position/translation, quaternion/rot and 1.0 1.0 1.0 (but my skeleton looks like an earthworm  )

Got the first 64 bone names but the parenting seems buggy: upperarms should be connected to clavicles, toe0 should have foot as parent and so on.
Forearm should have upperarm as a parent. So I guess I used the wrong DWORDs table.

```
1 "biped" 0
2 "bip001" 1
3 "lower" 2
4 "bip001 l calf" 3
5 "bip001 l foot" 4
6 "bip001 l thigh" 5
7 "bip001 l toe0" 6
8 "bip001 prop3" 7
9 "bip001 r calf" 8
10 "bip001 r foot" 9
11 "bip001 r thigh" 10
12 "bip001 r toe0" 11
13 "upper" 12
14 "bip001 head" 13
15 "bip001 l clavicle" 14
16 "bip001 l finger0" 15
17 "bip001 l finger01" 16
18 "bip001 l finger1" 17
19 "bip001 l finger11" 18
20 "bip001 l finger2" 19
21 "bip001 l finger21" 20
22 "bip001 l finger3" 21
23 "bip001 l finger31" 22
24 "bip001 l finger4" 23
25 "bip001 l finger41" 24
26 "bip001 l forearm" 25
27 "bip001 l hand" 26
28 "bip001 l upperarm" 27 ? 15
29 "bip001 neck" 28
30 "bip001 r clavicle" 29
31 "bip001 r finger0" 30
32 "bip001 r finger01" 31
33 "bip001 r finger1" 32
34 "bip001 r finger11" 33
35 "bip001 r finger2" 34
36 "bip001 r finger21" 35
37 "bip001 r finger3" 36
38 "bip001 r finger31" 37
39 "bip001 r finger4" 38
40 "bip001 r finger41" 39
41 "bip001 r forearm" 40
42 "bip001 r hand" 41
43 "bip001 r upperarm" 42   ? 30
44 "bip001 spine" 43
45 "bip001 spine1" 44
46 "bip001_l_upperarm_fr001" 45
47 "bip001_r_upperarm_fr001" 46
48 "bip001_spine1_bl001" 47
49 "bip001_spine1_bl001_1" 48
50 "bip001_spine1_bl001_2" 49
51 "bip001_spine1_bl001_3" 50
52 "bip001_spine1_bl002" 51
53 "bip001_spine1_bl002_1" 52
54 "bip001_spine1_bl002_2" 53
55 "bip001_spine1_br001" 54
56 "bip001_spine1_br001_1" 55
57 "bip001_spine1_br001_2" 56
58 "bip001_spine1_br001_3" 57
59 "bip001_spine1_fl001" 58
60 "bip001_spine1_fl002" 59
61 "bip001_spine1_fl002_1" 60
62 "bip001_spine1_fm001" 61
63 "bip001_spine1_fm001_1" 62

```
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-17T23:18:18+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

yes its pos, quat, scl.



ske.png (44.73 KiB) Viewed 493 times



```

def registerNoesisTypes():
    handle = noesis.register("directx", ".SKE")
    noesis.setHandlerTypeCheck(handle, CheckType)
    noesis.setHandlerLoadModel(handle, LoadModel)
    return 1

def CheckType(data):
    if data[:8] != b'SKELETON':
        return 0
    return 1

def LoadModel(data, mdlList):
    bs = NoeBitStream(data)
    print('magic::',bs.readBytes(8))#SKELETON
    print('fsize:',bs.readInt64())
    print('ver?:',bs.readInt())
    print('stride?:',bs.readInt())
    print('unk:',bs.readBytes(16))
    
    #while...
    #HEAD
    print('chunk_name::',bs.readBytes(4))
    bsize, curPos = bs.readInt(), bs.getOffset()
    print('chunk_size:',bsize)
    print('unk:',bs.readBytes(8))
    print('block_size:',bs.readInt())
    bnum = bs.readInt()
    print('bone_num:',bnum)
    print('unk_name:', bs.readBytes(bs.readInt()).decode())
    print('skel_name:', bs.readBytes(bs.readInt()).decode())
    for x in range(bs.readInt()):
        print(' ', bs.readBytes(bs.readInt()).decode(), ':', bs.readInt(), bs.readInt())
    bs.seek(curPos+bsize)
    
    #DATA
    print('chunk_name::',bs.readBytes(4))#DATA
    bsize, curPos = bs.readInt(), bs.getOffset()
    iname = [bs.readInt() for x in range(bnum)]
    print('name_index:', iname)
    bs.seek(12,1)#zero
    parent = [bs.readShort() for x in range(bnum)]
    print('parent_index:', parent)
    bs.seek(14,1)#zero
    
    matrix = []
    for x in range(bnum):
        pos = NoeVec3.fromBytes(bs.readBytes(12))
        rot = NoeQuat.fromBytes(bs.readBytes(16)).toMat43().transpose()
        scl = NoeVec3.fromBytes(bs.readBytes(12))
        rot[3] = pos
        matrix.append(rot)

    bs.seek(curPos+bsize)
    
    #NAME
    print('chunk_name::',bs.readBytes(4))#NAME
    bsize, curPos = bs.readInt(), bs.getOffset()
    
    names = [bs.readBytes(bs.readInt()).decode() for x in range(bs.readInt())]
    print('names:', names)
    
    #create bones
    bones = []
    for x in range(bnum):
        bones.append(NoeBone(x, names[iname[x]], matrix[x], None, parent[x]))

    bones = rapi.multiplyBones(bones)

    mdl = NoeModel()
    mdl.setBones(bones)
    mdlList.append(mdl)
    return 1

```
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-18T07:53:30+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

Hi, Durik256! Well, seems there's nothing that can stop you.  
(Parent indices at 02F8 in luna.ske. How could I miss that?  I wrongly chose 0xE8 and was wondering about FFFF being at tables end, haha.)

Just as a thought (not a request): did you ever thing about a tool that can get skeletons from hex data? Something like skel2smd or alike.
(I started years ago with it but never finished. Then Bigchillghost came up with his amazing "Approaches of Parsing Bone Representations". Again I gave it a go but still WIP. Main problem is that there's so many different skeleton formats/types. For example, what comes first? Trans or Rot? It's near to impossible to find this out automatically. So you'll need to try it out. A live displaying of the skeleton would be helpful then.)

Stay tuned!
.



skel2smd.jpg (126.28 KiB) Viewed 471 times
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-18T18:18:26+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from shakotay2 ↑Tue Oct 18, 2022 3:53 pm at Tue Oct 18, 2022 3:53 pm
>
> 
Parent indices
anyway they are wrong)

> Reply from shakotay2 ↑Tue Oct 18, 2022 3:53 pm at Tue Oct 18, 2022 3:53 pm
>
> 
skel2smd
Yes, there are too many options for storing skeletons. probably it is unrealistic to fit all in a few "switches".
can add a textBox in which the user will write a template. 



hex2SMD.png (3.53 KiB) Viewed 441 times
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-10-19T00:03:01+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from shakotay2 ↑Tue Oct 18, 2022 3:53 pm at Tue Oct 18, 2022 3:53 pm
>
> Main problem is that there's so many different skeleton formats/types. For example, what comes first? Trans or Rot? It's near to impossible to find this out automatically.
That's why a text interface is desired for more flexibility and convenience.
Using ASH:



skel.png (43.96 KiB) Viewed 426 times


Note that there's a bug which prevents from using the boneNameIndex to match with corresponding boneName. Setting the start address of the string pool as 0x185F should do the trick for now.
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-20T00:01:07+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from shakotay2 ↑Tue Oct 18, 2022 3:53 pm at Tue Oct 18, 2022 3:53 pm
>
> 
skel2smd or alike.
I started to make a shape, but in the end I decided to make it based on Noesis.  
(Tools/Display Plagin Tools) after (Tools/Skel Finder)
tools has only 7 commands. but this should be enough for most of the skeletons. (this is a prototype, tested on 3 samples)

examples:
luna.ske from this topic:

[IndianaJones.msh](https://forum.xentax.com/viewtopic.php?f=16&t=22426&p=187522&hilit=.msh#p165148):

[p1wd.skel](https://forum.xentax.com/viewtopic.php?f=16&t=24928&p=182436#p181218):

Skel Finder for Noesis: 

*(there is also an import/export in *.skelFinder format)
**(for help: write help in template field and click run)
[tool_SkelFinder.zip](https://xentaxbackup.github.io/file/22979_tool_SkelFinder.zip)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-22T19:08:19+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

Hi, having the lastest Noesis (4466?) I get ImportError: No module named noewinext with Skel Finder.
Had to comment out import noewinext to get the Skel Finder launched. 
But when searching for luna.ske I get NameError: global name 'noewinext' is not defined. So noewinext is needed (dialog = noewinext.NoeUserDialog("Choose File")).

What am I doing wrong?
(I know you were the first (here on xentax) to use userEditBox, getControlById and such with Noesis, but I can't seem to find the concerning thread/post.)
Ha, found it:

> Reply from shakotay2 ↑Wed Jan 05, 2022 1:45 am at Wed Jan 05, 2022 1:45 am
>
>
## Post #9
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-22T20:07:51+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

@shakotay2: I suppose it's the same [third-party template](https://github.com/AlexKimov/RSE-file-formats/blob/master/scripts/noesis/noewinext.py), used by some other noesis plugins (or its variation). Should be placed in the same folder with noewin, noesis\plugins\python.
## Post #10
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-22T20:38:21+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from shakotay2 ↑Sun Oct 23, 2022 3:08 am at Sun Oct 23, 2022 3:08 am
>
> 
import noewinext

wow. yes in the new version there is no noewinext. I have it from the old version. 
I fixed everything. noewinext is no longer needed.
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-23T04:13:43+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

i made form. All the same, I want to fit everything into a few "switches".  
can save it in .SkelFinder and open with the plug-in what i published earlier, or as an .obj point cloud. I used yours prog for visualization:

> Reply from shakotay2 ↑Sat Jun 12, 2021 3:05 am at Sat Jun 12, 2021 3:05 am
>
> 
mesh_viewer.exe
(if someone didn't know: key "P" scale points. key "L" on unlit, key "CAPS" swith +/- scale)
before saving or viewing, you must first press "run".
*(big Endian not implemented yet)


i have a problem. how to inverse a 4x3 matrix. because only square matrix can be inverse. and if you just add a column, then there will be the same values ​​​​as 4x4

[mat43.cpp](https://github.com/nathanfaucett/cpp-Odin/blob/6aae957afce1786fe67477758bfdf1619b0c6fce/src/mathf/mat43.cpp#L130) :gives the same result as 4x4
edit: aаа, the attachment didn't add, I don't know why
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-23T09:04:43+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from Durik256 ↑Sun Oct 23, 2022 12:13 pm at Sun Oct 23, 2022 12:13 pm
>
> 
i made form. All the same, I want to fit everything into a few "switches".  
can save it in .SkelFinder and open with the plug-in what i published earlier, or as an .obj point cloud. I used yours prog for visualization:
shakotay2 wrote: ↑Sat Jun 12, 2021 3:05 am
mesh_viewer.exeWell, it's not my program. Original code was made by Szymon Rusinkiewicz, whom I credited in the about box of hex2obj.
---------------------

> i have a problem. how to inverse a 4x3 matrix. because only square matrix can be inverse. and if you just add a column, then there will be the same values ​​​​as 4x4
>
> 
>
> mat43.cpp :gives the same result as 4x4Maybe this helps? [https://www.quora.com/How-do-I-find-the ... 4-3-matrix](https://www.quora.com/How-do-I-find-the-inverse-of-a-4-3-matrix)
## Post #13
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-27T03:52:57+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from shakotay2 ↑Sun Oct 23, 2022 5:04 pm at Sun Oct 23, 2022 5:04 pm
>
> 
whom I credited in the about box of hex2obj.
ah, ok)

> Reply from shakotay2 ↑Sun Oct 23, 2022 5:04 pm at Sun Oct 23, 2022 5:04 pm
>
> 
Maybe this helps?
Maybe, I left it for better times  

this is probably the last my post on this thread.  
no one will use this anyway.
implement 3d view in Windows Form is just fuc**  (3D points convert to 2D, and draw as bmp in pictureBox) 

*(mousedown and move for rotate, scroll mouse wheel for zoom)
**(the archive also has samples, Biped and cube)
***(to load a template from a file: Tools>open temp.txt)

[skelFinder.zip](https://xentaxbackup.github.io/file/22963_skelFinder.zip)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-27T06:03:06+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from Durik256 ↑Thu Oct 27, 2022 11:52 am at Thu Oct 27, 2022 11:52 am
>
> no one will use this anyway.How can you think so?  "And then there were three." At least. You, me and reh. 

> Reply from Durik256 ↑Thu Oct 27, 2022 11:52 am at Thu Oct 27, 2022 11:52 am
>
> this is probably the last my post on this thread.You've done much more than to be expected.  Thanks!

I will continue to find a way to get the parameters (addresses) required to feed both tools, yours and Bigchillghost's ASH.

My (working) skel2smd code contains DWORD addr[3]= {0x2F8, 0x1844, 0x408} ;	// luna, parentIndices, bone names, ref pose matrices

I fear the task of finding those addresses must be left to the users. But with some basic knowledge they're not too hard to find.
(Says then one who chose a wrong address for luna's indices. )
## Post #15
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-28T22:38:27+00:00
- Post Title: Harry Potter Magic Awakened - 3D animation

> Reply from shakotay2 ↑Thu Oct 27, 2022 2:03 pm at Thu Oct 27, 2022 2:03 pm
>
> 
At least. You, me and reh.
ha ha. need to create a new topic.  

> Reply from shakotay2 ↑Thu Oct 27, 2022 2:03 pm at Thu Oct 27, 2022 2:03 pm
>
> 
(Says then one who chose a wrong address for luna's indices. )
don't underestimate your abilities, you ripped models at a time when I didn't yet know how many bytes are in the float.  

> Reply from shakotay2 ↑Thu Oct 27, 2022 2:03 pm at Thu Oct 27, 2022 2:03 pm
>
> 
But with some basic knowledge they're not too hard to find.
those who do not understand at all, can perform a search for keywords like: "root", "bip", "spine", e.t.c to find a block with bones. or search for the zero matrix 4x4, 4x3...
