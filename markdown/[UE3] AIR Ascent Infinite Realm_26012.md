## Post #1
- Username: supersteeeeeeeve
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Dec 17, 2018 3:19 pm
- Post datetime: 2022-11-21T10:29:55+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

This is the predecessor to Elyon, 
The client is from 2019
Thailand OBT
Playpark Client

I'm looking to extract some airships out of it.

Full Client:
[https://drive.google.com/file/d/1WTqyau ... share_link](https://drive.google.com/file/d/1WTqyaukweuFLS07DZwtWETDDly8ca2Zo/view?usp=share_link)
Here's a sample with the game executeable.
[https://www.mediafire.com/file/hboz5faa ... IR.7z/file](https://www.mediafire.com/file/hboz5faaas7mbtk/AIR.7z/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-21T16:01:57+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

Seems to have some sub meshes; will check them later:
.



Airship_rock.jpg (74.32 KiB) Viewed 209 times
## Post #3
- Username: supersteeeeeeeve
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Dec 17, 2018 3:19 pm
- Post datetime: 2022-11-21T16:50:35+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

I guess that is just a cut from the whole mesh.

The ship is split into 5 parts.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-22T03:26:20+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

Maybe it's all rocks?
.



Airship_E_Rock04-wpk.jpg (91.5 KiB) Viewed 180 times
## Post #5
- Username: supersteeeeeeeve
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Dec 17, 2018 3:19 pm
- Post datetime: 2022-11-22T10:03:10+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

Your are right, it seems its only one rock.
The whole ship is uploaded [https://www.mediafire.com/file/uj0vzv7o ... _E.7z/file](https://www.mediafire.com/file/uj0vzv7ojqho2ad/AIR_Ship_E.7z/file) if needed.
I wonder where the textures are located, because only UI content is packed in .wpk packages.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-22T13:31:11+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

I'm not the "texture man"  , here's some yacht part (to give you the idea of parameters):
.



Airship_E_Yacht01.jpg (170.47 KiB) Viewed 156 times

Some checking required, obviously.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-23T16:03:32+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

done:
.



Airship_E_Yacht01_v22472.jpg (147.37 KiB) Viewed 136 times
## Post #8
- Username: supersteeeeeeeve
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Dec 17, 2018 3:19 pm
- Post datetime: 2022-11-23T17:26:21+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

awesome!
Full client uploaded to gdrive: [https://drive.google.com/file/d/1WTqyau ... share_link](https://drive.google.com/file/d/1WTqyaukweuFLS07DZwtWETDDly8ca2Zo/view?usp=share_link)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-24T22:19:22+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

well, I won't download 21 GB just for fun  , sorry. (Maybe you could select some 20..30 MB .wpk and upload them separately?)

Sadly rules are different for Airship_E_Yacht02:
.



Yacht02.jpg (52.36 KiB) Viewed 102 times



(btw, got hull of Yacht01 as point cloud only. That's why it's missing in the pic of my previous post.)
## Post #10
- Username: supersteeeeeeeve
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Dec 17, 2018 3:19 pm
- Post datetime: 2022-11-25T00:56:16+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

Sure i can.
Here's a mix ranging from a ship with 25MB to a whopping 80MB
[https://www.mediafire.com/file/hu496ij8 ... ps.7z/file](https://www.mediafire.com/file/hu496ij85e5g2ul/AIR_MixedShips.7z/file)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-25T13:47:15+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

tried the biggest one, Vulpin01:
.



Vulpius01.jpg (179.64 KiB) Viewed 83 times

(Guess, the sails are missing. No time to search for them.)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-25T14:00:36+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

How to get the thing (required H2O files see appended zip file):

```
to create obj files from all contained submeshes.

After hex2obj processed the H2O files there should exist the same amount of obj files 
in the model's folder named from *_0.obj to *_xx.obj.

When executing the py script below in a blender Text Editor window with alt-p
make sure to have set "path_to_obj_dir" in the *.py to YOUR model/H2O directory.

Also be sure that there are no obj files in a maybe contained subdirectory.
(they would be loaded, too)

Best choice would be to have a separate folder for each *.wpk and its obj files.

Keep in mind that ?3.obj is NOT created from ?3.H2O! 
First line in an obj reveals its H2O-source.
```


blender import (if you don't want to import the sub meshes  one by one).
Be sure to adjust the path 'D:\\', 'test\\wpk' to the one on your pc before executing the script.

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie C:\objects
#path_to_obj_dir = os.path.join('C:\\', 'objects')
path_to_obj_dir = os.path.join('D:\\', 'test\\wpk')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```



 Airship_D_Vulpin01.wpk_H2O.zip
(4.59 KiB) Downloaded 14 times


btw: didn't separate the lods, sorry. You'll need to do that manually.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-25T19:59:56+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

Airship_D_BlackPirate03:
.



Airship_D_BlackPirate03.jpg (104.56 KiB) Viewed 67 times
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-26T05:25:40+00:00
- Post Title: [UE3] A:IR Ascent Infinite Realm

Hull of Yacht01:
.



Yacht01_hull.jpg (108.03 KiB) Viewed 56 times
