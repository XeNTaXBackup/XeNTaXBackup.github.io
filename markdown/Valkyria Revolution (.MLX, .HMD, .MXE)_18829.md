## Post #1
- Username: ventuhr
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Jan 06, 2017 10:16 pm
- Post datetime: 2018-09-18T13:49:42+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

Somewhat similiar format like Valkyria Chronicles 1 & 4. 

[https://drive.google.com/open?id=1t7ulp ... 8Gt7ua-Iz0](https://drive.google.com/open?id=1t7ulpGhhSHlxfj9tnkevGe8Gt7ua-Iz0) Weapons only for now, I'll upload more samples if needed.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-20T21:15:38+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

I don't see senseful data in your 7z ipped files.
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-09-20T21:25:39+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

> Reply from shakotay2
>
> I don't see senseful data in your 7z ipped files.
Search for the "KFMG" tag in the largest file. The vertices/indices are below that. Other files don't seem to have any geometry data though.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-20T23:46:55+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

I see - thanx!
Maybe Make_H2O can be patched. From a first glance:

first addrFI[0] at 0x58b260
first addrFI[1] at 0x58ee90
first addrFI[2] at 0x592530
first addrFI[3] at 0x593c50
first addrFI[4] at 0x59a900
first addrFI[5] at 0x5a26e0
first addrFI[6] at 0x5a49a0
first addrFI[7] at 0x5b66f0
first addrFI[8] at 0x5bae00
first addrFI[9] at 0x5bf790
first addrFI[10] at 0x5c6d80
first addrFI[11] at 0x5db9c0
first addrFI[12] at 0x5dddd0
first addrFI[13] at 0x5e0990

first submesh of Weapon WM_Axe_101A:



WM_Axe_101A.jpg (167.9 KiB) Viewed 237 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-21T21:26:54+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

well, I'm not sure if this it is how it should look like:



WM_Axe_101A.MLX.jpg (201.91 KiB) Viewed 227 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-09-22T06:41:22+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

anyways, the H2O files (with 2 corrections for vAddr and FVFSize, 72 instead of 68):


 WM_AXE_101A.MLX_13 submeshes.zip
(2.33 KiB) Downloaded 17 times



btw: you don't load each H2O as a single file; instead you should use the hex2obj, SaveAs Mmesh option!

Then in blender, you need a script like this one to import all .obj in a folder:

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie D:\ValkR\objects
path_to_obj_dir = os.path.join('D:\\', 'ValkR\\objects')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```
## Post #7
- Username: LionRnD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 25, 2020 9:46 pm
- Post datetime: 2020-03-25T14:43:05+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

Hi, there well it anyone explain where can I find the character model/texture filename?
## Post #8
- Username: LionRnD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 25, 2020 9:46 pm
- Post datetime: 2020-11-03T18:24:31+00:00
- Post Title: Valkyria Revolution (.MLX, .HMD, .MXE)

I did found some character texture of Ophelia, Unfortunately, Blender 2.79 w/ MLX tool didn't open.
All I got was Texture.
Still looking for HEX code.

Here the ZIP.


[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1jHeER4KPU60tFBaKxap754KFr9r4d7JW?usp=sharing)
[01.jpg](https://xentaxbackup.github.io/file/18952_01.jpg)
