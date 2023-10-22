## Post #1
- Username: TheLacy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 29, 2020 3:39 am
- Post datetime: 2020-10-20T17:11:06+00:00
- Post Title: Sunset Overdrive (.model) Models

Hello, I just extracted some models from Sunset Overdrive with UnArch Tool([viewtopic.php?f=33&t=22779](https://forum.xentax.com/viewtopic.php?f=33&t=22779)), and since I am not too good with reading 3D model formats I can't manage to open it. Can someone help me with it? 
Sample files:[http://www.mediafire.com/file/vozje1u3c ... s.rar/file](http://www.mediafire.com/file/vozje1u3ctfh2if/models.rar/file)
## Post #2
- Username: homelesskodai
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 11, 2020 5:33 am
- Post datetime: 2021-04-12T21:13:19+00:00
- Post Title: Sunset Overdrive (.model) Models

do you still have the files, and also what UnArch tool did you use?
## Post #3
- Username: homelesskodai
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 11, 2020 5:33 am
- Post datetime: 2021-04-13T00:08:10+00:00
- Post Title: Sunset Overdrive (.model) Models

bruh
## Post #4
- Username: wiredpeach
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 16, 2021 4:14 am
- Post datetime: 2021-05-30T21:23:39+00:00
- Post Title: Sunset Overdrive (.model) Models

> Reply from homelesskodai ↑Tue Apr 13, 2021 8:08 am at Tue Apr 13, 2021 8:08 am
>
> bruh

hello,

i'm also trying to convert a SOPC .model file to .obj. i managed to decompress the file archive using a tool for ratchet and clank ps4, it's been a while so i don't remember exactly which script i used to extract the files using the layout.csv, but i do remember that the .model to .obj script on the github not working ([https://github.com/doesthisusername/ig-tools](https://github.com/doesthisusername/ig-tools))

i have all the .model files, here are a few examples: [https://mega.nz/folder/DgQV3AgB#oVq1UI-2RbcQra1F3iJS2A](https://mega.nz/folder/DgQV3AgB#oVq1UI-2RbcQra1F3iJS2A)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-30T22:51:37+00:00
- Post Title: Sunset Overdrive (.model) Models

> Reply from wiredpeach ↑Mon May 31, 2021 5:23 am at Mon May 31, 2021 5:23 am
>
> 
but i do remember that the .model to .obj script on the github not working (https://github.com/doesthisusername/ig-tools)Hello,
who said it's a .model to .obj converter? Looks like a decompressor:

```
spine
spine_B
chest
LF_clavicle
RT_clavicle
LF_uparm
RT_uparm
LF_loarm
RT_loarm
LF_loarmTwist_B
LF_loarmTwist_A
LF_loarmTwist
LF_wrist
RT_loarmTwist_B
RT_loarmTwist_A
RT_loarmTwist
RT_wrist
LF_wrist_scale
RT_wrist_scale
LF_finger_D_A
LF_finger_C_A
LF_finger_B_A
LF_finger_A_A
LF_thumb_A
RT_finger_D_A
RT_finger_C_A
RT_finger_B_A
RT_finger_A_A
RT_thumb_A
LF_finger_D_B
LF_finger_C_B
LF_finger_B_B
LF_finger_A_B
LF_thumb_B
RT_finger_D_B
RT_finger_C_B
RT_finger_B_B
RT_finger_A_B
RT_thumb_B
LF_finger_D_C
LF_finger_C_C
LF_finger_B_C
LF_finger_A_C
LF_thumb_C
RT_finger_D_C
RT_finger_C_C
RT_finger_B_C
RT_finger_A_C
RT_thumb_C
LF_finger_D_D
LF_finger_C_D
LF_finger_B_D
LF_finger_A_D
RT_finger_D_D
RT_finger_C_D
RT_finger_B_D
RT_finger_A_D
```

Uncompressed data seems to contain hkx data: 57E0E057 10C0C01000 ...
Version: hk_2013.2.0-r1

hktcnv test.hkx test.smd
HKX2SMD Converter v1.00 - Init


Read bytes:76856
sig is: 0x57E0E057
Version:hk_2013.2.0-r1
section:__classnames__
section:ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿ__types__
section:ÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿ__data__
Class ÿÿÿÿÿÿÿÿÿÿÿ?#Ô3   hkClass signature: 0xFFFFFFFF
Class hkClassMember signature: 0xB0EFA719
Class hkClassEnum signature: 0x8A3609CF
Class hkClassEnumItem signature: 0xCE6F8A6C
Class hkRootLevelContainer signature: 0x2772C11E

Unhandled Exception: System.OverflowException: Arithmetic operation resulted in
an overflow.

(Maybe hktcnv expects another file, dunno, it's too long ago that I cared for hkx...)
## Post #6
- Username: wiredpeach
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 16, 2021 4:14 am
- Post datetime: 2021-05-30T23:38:57+00:00
- Post Title: Sunset Overdrive (.model) Models

> Reply from shakotay2 ↑Mon May 31, 2021 6:51 am at Mon May 31, 2021 6:51 am
>
> 
Hello,
who said it's a .model to .obj converter? Looks like a decompressor:

oh god! sorry, i'm very new to the world of reverse engineering and thought the ig_model2obj.py was a converter   
thank you for taking a look at the files, i'll read up on the .hkx format.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-31T07:29:22+00:00
- Post Title: Sunset Overdrive (.model) Models

> Reply from wiredpeach ↑Mon May 31, 2021 7:38 am at Mon May 31, 2021 7:38 am
>
> and thought the ig_model2obj.py was a converter   
thank you for taking a look at the files, i'll read up on the .hkx format.All's fine, as the name tells ig_model2obj.py seems to be a model convertor.   (I was talking about itg.c and dec.c.)

I assume you have to use ig_model2obj.py on the decompressed file.

Well, see README.md in general folder:

> #### ig_model2obj.py
>
> Attempts to create a `.obj` file from a decompressed `.model`. Rarely works properly, but some files are compatible.

Seems the python part is not too handy, you need to rebuild igdat1.py before using ig_model2obj.py:

> # This is a generated file! Please edit source .ksy file and use kaitai-struct-compiler to rebuild
## Post #8
- Username: wiredpeach
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 16, 2021 4:14 am
- Post datetime: 2021-06-01T19:02:40+00:00
- Post Title: Sunset Overdrive (.model) Models

> Reply from shakotay2 ↑Mon May 31, 2021 3:29 pm at Mon May 31, 2021 3:29 pm
>
> 
wiredpeach wrote: ↑Mon May 31, 2021 7:38 amand thought the ig_model2obj.py was a converter   
thank you for taking a look at the files, i'll read up on the .hkx format.All's fine, as the name tells ig_model2obj.py seems to be a model convertor.   (I was talking about itg.c and dec.c.)

I assume you have to use ig_model2obj.py on the decompressed file.

Well, see README.md in general folder:
#### ig_model2obj.py
Attempts to create a `.obj` file from a decompressed `.model`. Rarely works properly, but some files are compatible.

Seems the python part is not too handy, you need to rebuild igdat1.py before using ig_model2obj.py:
# This is a generated file! Please edit source .ksy file and use kaitai-struct-compiler to rebuild

i now have a decompressed .model file ([https://mega.nz/file/vsA0GD5I#LQU2nu_6O ... -iiUbDY8Hk](https://mega.nz/file/vsA0GD5I#LQU2nu_6OnjlS08O6jZXY9nFAFc-NvFkU-iiUbDY8Hk)) and i think i may be able to use the ig_model2obj script to convert it to an .obj, i'm completely new to python so i'll have to read up on rebuilding .py and .ksy files. thank you again for your time
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-01T20:15:53+00:00
- Post Title: Sunset Overdrive (.model) Models

> Reply from wiredpeach ↑Wed Jun 02, 2021 3:02 am at Wed Jun 02, 2021 3:02 am
>
> i now have a decompressed .model file (https://mega.nz/file/vsA0GD5I#LQU2nu_6O ... -iiUbDY8Hk) and i think i may be able to use the ig_model2obj script to convert it to an .objJust in case that doesn't work (correctly) another approach would be with .hkx, in that .model file delete the bytes before offset 0x6D0 and save as hfh_hed_pale_02_dec.hkx. Having the suiting havok tools for version hk_2013.2.0-r1 this might be the more "elegant" way.

(But as you may have noticed, hkx is a weird format because of its variety, similar to nif. Game developers add some "user defined" sections and all tools/scripts we have go bogus.  )

What usually helps is hex2obj (or similar tools):
.



hfh_hed_pale_02_dec_point_cloud.png (117.72 KiB) Viewed 244 times


(Face indices are a little bit harder to track. Part of eyeballs only.)
## Post #10
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-06-01T23:55:54+00:00
- Post Title: Sunset Overdrive (.model) Models

Faces are triangles and start at 0x9C0.
UVs are Half-Float



hfh_hed_pale_02_dec.model.png (28.99 KiB) Viewed 232 times
## Post #11
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-06-02T00:31:22+00:00
- Post Title: Sunset Overdrive (.model) Models

The table at 0x8c0 gives you the offsets for the vertices and faces for each sub-mesh.  Each entry is 0x40 bytes, geometry info is at offset 0x10 in each entry:

Start Vertex (UInt)
Start Face (UInt)
Face Count (UInt)
Vertex Count (UShort)

Seems to work ok for that file, but that's the only file I have, so it may not work for others if developers keep messing with the format.

So you get this for the 4 sub-meshes in that file:
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-02T08:09:12+00:00
- Post Title: Sunset Overdrive (.model) Models

> Reply from reh ↑Wed Jun 02, 2021 7:55 am at Wed Jun 02, 2021 7:55 am
>
> 
Faces are triangles and start at 0x9C0.yeah! Thanks, seems I'm always a little bit "off track".  
.



eyeballs.png (66.4 KiB) Viewed 214 times
## Post #13
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2021-06-04T04:27:18+00:00
- Post Title: Sunset Overdrive (.model) Models

There is a maxscript for 3dsMax written by sleepyzay for the Ratchet and Clank PS4 game, apparently it works with these files:



hfh_hed_pale_02.model.png (76.28 KiB) Viewed 185 times


The script can be found on the xentax discord server.
