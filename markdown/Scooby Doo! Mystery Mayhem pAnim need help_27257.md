## Post #1
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2023-09-29T14:13:27+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

hi i been trying to work on a scooby doo mystery mayhem animation blender addon an importer and exporter turns like nobody doesn't care helping me and reversing the animations and imported into blender, so i tried looking something up and there no results that somebody making a proper one on github to get it to work here the code i written. 
```
from dataclases import dataclass

@dataclass
class pAnimKeyframe:
    endF : float
    startF : float
    posx : float
    posy : float
    posz : float
    rotx : float
    roty : float
    rotz : float
    scalex : float
    scaley : float
    scalez : float

    @classmethod
    def read(cls, f):
        pass

    def write(self, f):
        pass
        

@dataclass
class pAnim:
    FileSize: int
    size: int
    frameRate: float
    boneCount: int
    type1 : int
    type2 : int
    type3 : int
    unk_size1_on: int # not sure 4096 on or off
    bone_id: int
    keyframe_type: int
    entrysize: int # only starts when 4096 is on not off
    @classmethod
    def read(cls, f):
        FileSize = unpack(">I", f.read(4))[0]
        size = unpack(">I", f.read(4))[0]
        frameRate = unpack(">f", f.read(4))[0]
        boneCount = unpack("B", f.read(1))[0]
        type1 = unpack("B", f.read(1))[0] # 1 or 0
        type2 = unpack("B", f.read(1))[0] # 1 or 0
        type3 = unpack("B", f.read(1))[0] # 1 or 0
        for i in range(entrysize//16):
            unk_size1_on = unpack(">H", f.read(2))[0]
            bone_id = unpack(">H", f.read(2))[0]
            keyframe_type = unpack(">H", f.read(2))[0]
            entrysize = unpack(">H", f.read(2))[0]
        
        return cls(FileSize, size, frameRate, boneCount, type1, type2, type3, unk_size1_on, bone_id, keyframe_type, entrysize)

        
    
def load(cls, filepath):
    with open(filepath, 'rb') as f:
        return cls.read(f)
        
        
    

```
 here the animations that i extracted from the gcr or p2r files [https://drive.google.com/file/d/1POw3cA ... sp=sharing](https://drive.google.com/file/d/1POw3cAuXdpf-f3vBfiMCzhqIfJeTov3h/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-01T11:55:50+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

> Reply from MegaSpeedXtreme ↑Fri Sep 29, 2023 10:13 pm at Fri Sep 29, 2023 10:13 pm
>
> 
hi i been trying to work on a scooby doo mystery mayhem animation blender addon...
 here the code i written.Hi,
is it code that you've written or is it code that you've copied?  

There's a typo in here, so it doesn't even run:

```
from dataclases import dataclass

```


Also I strongly suggest to start with the skeleton(s) otherwise I fear you'll meet a dead end. Just my two cents.
.

> Reply from MegaSpeedXtreme ↑Fri Sep 29, 2023 10:13 pm at Fri Sep 29, 2023 10:13 pm
>
> 
turns like nobody doesn't care helping me and reversing the animations and imported into blender,Once being helped (other 3D format) it turned out you don't really appreciate it:

> Reply from shakotay2 ↑Sun Jul 24, 2022 2:31 am at Sun Jul 24, 2022 2:31 am
>
> Maybe think about it?
## Post #3
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2023-10-01T16:58:27+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

ok, it was a code that i was trying to copy it from someone called psycrow because i was trying to get it to work and i tried looking up some results on github, but there no results of him making a scooby doo mystery mayhem animation blender addon from the community an importer and exporter, because i was trying to get different scripts to make them work like my own scripts and someone else scripts turns like i couldn't get them working but i made a script my own script instead. 
```
import bpy

def pAnim_read(f):
    ob = bpy.context.object
    filesize    = unpack(">I", f.read(4))[0]
    unknown1    = unpack(">H", f.read(2))[0]
    unknown2    = unpack(">H", f.read(2))[0]
    framerate   = unpack(">f", f.read(4))[0]
    bonecount   = unpack("B", f.read(1))[0]
    type1       = unpack("B", f.read(1))[0]
    type2       = unpack("B", f.read(1))[0]
    type3       = unpack("B", f.read(1))[0]
    for pbone in ob.pose.bones:
        
        unk_off = unpack(">H", f.read(2))[0] # 4096 on or off
        if unk_off == 0:
            
            bone_id = unpack(">H", f.read(2))[0] # increment bone count
            keyframe_type = unpack(">H", f.read(2))[0] # not sure
            size_off = unpack(">H", f.read(2))[0]
        elif unk_off == 4096:
            keyframe_id = unpack(">H", f.read(2))[0]
            unk = unpack(">H", f.read(2))[0]
            size_on = unpack(">H", f.read(2))[0]
            if keyframe_id == 0:
                pbone.keyframe_insert(data_path="scale", index=keyframe_id)
            elif keyframe_id == 1:
                pbone.keyframe_insert(data_path="scale", index=keyframe_id)
            elif keyframe_id == 2:
                pbone.keyframe_insert(data_path="scale", index=keyframe_id)
            elif keyframe_id == 6:
                pbone.keyframe_insert(data_path="rotation_euler", index=keyframe_id-6)
            elif keyframe_id == 7:
                pbone.keyframe_insert(data_path="rotation_euler", index=keyframe_id-6)
            elif keyframe_id == 8:
                pbone.keyframe_insert(data_path="rotation_euler", index=keyframe_id-6)
            elif keyframe_id == 3:
                pbone.keyframe_insert(data_path="location", index=keyframe_id-3)
            elif keyframe_id == 4:
                pbone.keyframe_insert(data_path="location", index=keyframe_id-3)
            elif keyframe_id == 5:
                pbone.keyframe_insert(data_path="location", index=keyframe_id-3)
    bpy.context.scene.frame_start = 0
    bpy.context.scene.frame_current = 0
    bpy.context.scene.frame_end = int(framerate*30)

def pAnim_write(f):
    bone_id = 0
    keynum = 0
    ob = bpy.context.object
    fcurves2 = bpy.context.active_object.animation_data.action.fcurves
    f.write(pack(">I", 16+8*len(ob.pose.bones)))
    f.write(pack(">H", 4096))
    f.write(pack(">H", 0))
    f.write(pack(">f", bpy.context.scene.frame_end/30.0))
    f.write(pack("B", len(ob.pose.bones)))
    f.write(pack("B", 0))
    f.write(pack("B", 0))
    f.write(pack("B", 0))
    for pbone in ob.pose.bones:
        f.write(pack(">H", 0))
        f.write(pack(">H", bone_id))
        f.write(pack(">H", 0))
        f.write(pack(">H", 0))
        bone_id +=1
        
def _read_pAnim(filepath):
    with open(filepath, "rb") as f:
        pAnim_read(f)

def _write_pAnim(filepath):
    with open(filepath, "wb") as f:
        pAnim_write(f)

    
        

    
    
    
    
    

```
 i have done some debugging through this stuff and not all them are in floats some of them are in 1000000.0 that you have divide with the same number and some of them are in floats and this only works if you have the renderware model inside the gcr and p2r and xbr with the animations
## Post #4
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2023-10-04T00:14:38+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

the problem is when i import them into blender the positions and the rotations and scales gets completely messed up when i import them into blender and there are different offsets with 0x00010001 and 0x00020001 and even more than that sometimes the maximum can get up to 16 bytes or even 20 or 24 or 28 or 32 or even higher they could get higher than that, there needs to be someone out there that can fix those with some sort of matrix which i don't know how, what your doing is your making it useless by saying think about it and other stuff towards me which i actually i don't need to think about it shakotay2 your just being a bit rude, all i want is some help with the animations to fix the orientation in blender to do with rotations and positions and scales or someone from the community to fix the positions rotations and scales at the same time
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-04T16:42:10+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

How about giving the name of the sample you're talking about, plus a running script (how do you start it?) plus a picture of your current result?

Noone is rude here. Please focus on the problem.

Also I'd like to mention that you seemed to ignore my hint concerning the skeleton:

> Reply from shakotay2 ↑Sun Oct 01, 2023 7:55 pm at Sun Oct 01, 2023 7:55 pm
>
> Also I strongly suggest to start with the skeleton(s) otherwise I fear you'll meet a dead end. Just my two cents.

Do you have the skeleton in blender? Do you have the bone names?

Once you've got the skeleton start with animation positions only. Care for the rotations later.
## Post #6
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2023-10-05T02:09:40+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

still getting rotation problems which i can't fix
[velmaBrokenLIMBS__.png](https://xentaxbackup.github.io/file/24400_velmaBrokenLIMBS__.png)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-05T05:46:11+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

Providing pieces of information doesn't help anyone.
(Nice picture, though.)
## Post #8
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2023-10-05T20:57:24+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

but, what's causing it, it's the right arm is wrong and the right leg is wrong and the left arm is correct and the left leg is correct and the other thumb is wrong if you look into it, the weird thing is, when i looked into that game all the rotations and positions and scales seems to correct in a weird way but when i import it outside of game in blender the rotations seems to be wrong and it didn't get exactly like the exact animations in game but in blender also i did found a workaround to fix those positions is by compressing them and they were fixed by me with the root and pivot bone and getting the index which i didn't show that, like the left arm shoulder is correct than the other limbs except for the right arm should and thumb that is twisted and right leg is still wrong, i did tried some matrix but it didn't seem to work by going mathutils matrix translation and rotation at the same time, there also other offsets that needs to be discovered and this over 20 offsets or more to do with the animations is like a monster, i did it with another different script my own one which i'm not going to show that because it's massive and it's different now, i did tried other ones like the ghosts that gets problem with the rotations as well, still need to find and discover those keyframes that is multiplying that by 30
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T00:59:18+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

> Reply from MegaSpeedXtreme ↑Fri Oct 06, 2023 4:57 am at Fri Oct 06, 2023 4:57 am
>
> 
but, what's causing it, ...Well, I see, you'll need to go your own way. I can't help you in any way, so I'm off for now.

Good luck and all the best!
## Post #10
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2023-10-06T14:12:01+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

do you know what Rotation Matrix they are using to fix the rotations the one in the picture to fix the rotations without getting the wrong rotation to get exactly like the original animations but in blender, because i don't know what it is, i tried matrix basis and it didn't seem to work
## Post #11
- Username: MegaSpeedXtreme
- Rank: beginner
- Number of posts: 35
- Joined date: Thu Jun 14, 2018 7:58 am
- Post datetime: 2023-10-06T15:54:55+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

if you can try and help me with the rotation matrix without getting the wrong rotation but the correct rotation then we could move onto these offsets and keyframes but with these offsets to do with the animation file format

```
0x020001
0x040001
0x040002
0x040003
0x040004
0x040005
0x040006
0x040007
0x040008
0x040009
0x04000A
0x04000B
0x04000C
0x040011
0x040012
0x040013
0x040014
0x040016
0x040017
0x04001A
0x04001C
0x04001D
0x04001E
0x040022
0x040026
0x040028
0x04002C
0x04002D
```
 otherwise this is very incompleted
## Post #12
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-10-06T16:28:28+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

Nobody ever taught you how to write a decent sentence? Learn to use punctuation and show some respect for God's sake.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-10-06T17:56:33+00:00
- Post Title: Scooby Doo! Mystery Mayhem pAnim need help

> Reply from MegaSpeedXtreme ↑Fri Oct 06, 2023 11:54 pm at Fri Oct 06, 2023 11:54 pm
>
> 
if you can try and help me with the rotation matrixHow should anyone do that?

We don't know the file you're talking about.
We don't have the file you're talking about.

Most of your offsets address bytes. That doesn't make sense to me.
If you don't give the file which the offsets are taken from nobody can help you.

> Code: Select all0x010001
>
> 0x020001
>
> 0x040001
>
> 0x040002
>
> 0x040003
>
> 0x040004
>
> 0x040005
>
> 0x040006
>
> 0x040007
>
> 0x040008
>
> 0x040009
>
> 0x04000A
>
> 0x04000B
>
> 0x04000C
>
> 0x040011
>
> 0x040012
>
> 0x040013
>
> 0x040014
>
> 0x040016
>
> 0x040017
>
> 0x04001A
>
> 0x04001C
>
> 0x04001D
>
> 0x04001E
>
> 0x040022
>
> 0x040026
>
> 0x040028
>
> 0x04002C
>
> 0x04002D otherwise this is very incompleted

We can talk until the forum shuts down (at year's end) and we won't move any step further if you don't provide what is required to understand your problem.

I assume you want to keep secret what you've detected so far.
That's ok for me.
But then how should anyone help you?
