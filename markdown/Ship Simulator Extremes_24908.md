## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-01-02T16:57:56+00:00
- Post Title: Ship Simulator Extremes

Found some data. Maybe it could be parsed by script. I see VTD and VTO strings. Maybe they could be used to parse data correctly in Noesis. 
[](https://ibb.co/nfkBxGG)
[](https://ibb.co/wRKjnLc)
[](https://ibb.co/gdQytMt)
[](https://ibb.co/CHy444f)
[](https://ibb.co/JnMzHHv)

Sample
[https://drive.google.com/file/d/1fDp8aU ... sp=sharing](https://drive.google.com/file/d/1fDp8aUXY5f82aZpUEZ4fq9GR2dEvyH16/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-02T18:20:57+00:00
- Post Title: Ship Simulator Extremes

I'd suggest to search for VPP and POD instead.
.



Sigita.png (104.84 KiB) Viewed 86 times
## Post #3
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-01-02T19:00:00+00:00
- Post Title: Ship Simulator Extremes

Thanks shakotay    i didnt even see POD and VPP in the data. Hopefully someone is as interested as I am for these and could help in making a script for us. Im still learning how to do such magic. Maybe someday. 


So POD..AF in the face data. The AF is the count ? Or is it that data before the POD. 23 6A or the #j ?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-02T21:21:35+00:00
- Post Title: Ship Simulator Extremes

As for 46D40000 (contained once only), it's the size of a "face indices block", divided by 2 gives the  count of face indices for one of the sub meshes.

And well, this mesh format is simple, so here's the 31 H2O files for use with the MultiMesh feature in hex2obj:
.


 Sigita-cgr_H2O.zip
(4.97 KiB) Downloaded 11 times


(uvs not tested, the ones of the big lod0 mesh (or whatever lod it is) look overlapped as hell  )
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-05T05:54:48+00:00
- Post Title: Ship Simulator Extremes

Sigita_ship.png (163.56 KiB) Viewed 42 times


Created using script in a blender text window, then pressing alt-p:

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
# this line will only work on windows ie C:\objects
#path_to_obj_dir = os.path.join('C:\\', 'objects')
path_to_obj_dir = os.path.join('D:\\', 'your\\path\\to\\obj')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```
