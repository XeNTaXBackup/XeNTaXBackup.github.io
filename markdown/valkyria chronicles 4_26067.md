## Post #1
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-12-08T14:53:30+00:00
- Post Title: valkyria chronicles 4

I'm  keep getting this error while trying to import  vla112f.mlx  in blender can you help me with  this  or send me the model. Here the file [https://www.mediafire.com/folder/ffmzcjbkocwqq/Nik](https://www.mediafire.com/folder/ffmzcjbkocwqq/Nik)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-08T17:49:41+00:00
- Post Title: valkyria chronicles 4

Is it only this one model that fails to import?

The data is "doable":
.



vla112F-head.jpg (76.11 KiB) Viewed 156 times
## Post #3
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-12-08T21:58:40+00:00
- Post Title: valkyria chronicles 4

Yes  the only one when I try to import it. It say this. Traceback (most recent call last):
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\__init__.py", line 914, in execute
    self.import_file(self.filepath)
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\__init__.py", line 903, in import_file
    self.valk_scene.read_data()
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\__init__.py", line 849, in read_data
    self.source_file.read_data()
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\__init__.py", line 164, in read_data
    shape_key_set.read_data()
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\__init__.py", line 430, in read_data
    self.F.read_data()
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\valkyria\files.py", line 255, in read_data
    kfsh.read_data()
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\valkyria\files.py", line 266, in read_data
    kfss.read_data()
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\valkyria\files.py", line 402, in read_data
    self.read_vertex_formats()
  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\valkyria\files.py", line 353, in read_vertex_formats
    assert vertfmt['bytes_per_vertex'] in [0x0, 0x8, 0xc, 0x14, 0x18, 0x1c]
AssertionError
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-08T23:09:43+00:00
- Post Title: valkyria chronicles 4

> Reply from blacknight411 ↑Fri Dec 09, 2022 5:58 am at Fri Dec 09, 2022 5:58 am
>
> 
Yes  the only one when I try to import it. It say this. Traceback (most recent call last):
...  File "C:\Users\Admin\AppData\Roaming\Blender Foundation\Blender\2.79\scripts\addons\import_valkyria\valkyria\files.py", line 353, in read_vertex_formats
    assert vertfmt['bytes_per_vertex'] in [0x0, 0x8, 0xc, 0x14, 0x18, 0x1c]
AssertionErrorThat's funny, because the error message I get using the script of angavrilov is different:
"...\import_valkyria\valkyria\files.py", line 1610, in valk_factory
    raise NotImplementedError("File type {} not recognized.".format(ftype))
NotImplementedError: File type POF1 not recognized."

Whom is the script  from you're using?
.

> Reply from AlexNG ↑Thu Jan 28, 2021 10:29 pm at Thu Jan 28, 2021 10:29 pm
>
> 
edit: well, the init reads: "author": "Chrrox, Gomtuu", "version": (0, 8 ),
and it's for PS3 files

edit 2: after I read this:

> Reply from hatehatehate ↑Mon Feb 08, 2021 9:37 am at Mon Feb 08, 2021 9:37 am
>
> I managed to import vla112F into latest blender (very strange...)
.



vla112F.jpg (119.32 KiB) Viewed 131 times
## Post #5
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-12-09T05:18:07+00:00
- Post Title: valkyria chronicles 4

This is what  I use  [https://github.com/gomtuu/import_valkyria](https://github.com/gomtuu/import_valkyria)
can I have  the one you use.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-09T09:51:50+00:00
- Post Title: valkyria chronicles 4

Find the link in the post of AlexNG, which I posted above. Replace "2.8" in the name by "2_8" otherwise blender can't install correctly.
## Post #7
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-12-09T11:56:36+00:00
- Post Title: valkyria chronicles 4

I  Replace "2.8" in the name by "2_8 in thin push import but keep getting this bpy.context.area.ui_type = 'PREFERENCES'
bpy.data.window_managers["WinMan"].addon_search = "ml"
Traceback (most recent call last):
  File "C:\Users\User\Pictures\PROGRAM\blender-2.83.0-windows64\2.83\scripts\modules\addon_utils.py", line 351, in enable
    mod = __import__(module_name)
ModuleNotFoundError: No module named 'import_valkyria-blender-2'
what blender did you use.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-09T14:40:51+00:00
- Post Title: valkyria chronicles 4

Latest should do - try any of the 3.x series.
## Post #9
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-12-09T16:07:19+00:00
- Post Title: valkyria chronicles 4

try it  keep getting  this  bpy.context.area.ui_type = 'PREFERENCES'
bpy.data.window_managers["WinMan"].addon_search = "ml"
Traceback (most recent call last):
File "C:\Users\User\Pictures\PROGRAM\blender-2.83.0-windows64\2.83\scripts\modules\addon_utils.py", line 351, in enable
mod = __import__(module_name)
ModuleNotFoundError: No module named 'import_valkyria-blender-2'
Do I need put this import_valkyria-blender-2_8 some where else. or it do not matter. oh I use blender-3.1.2.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-09T16:40:03+00:00
- Post Title: valkyria chronicles 4

> Reply from blacknight411 ↑Sat Dec 10, 2022 12:07 am at Sat Dec 10, 2022 12:07 am
>
> Do I need put this import_valkyria-blender-2_8 some where else. or it do not matter. oh I use blender-3.1.2.Usually blender 3.x installs scripts to users\<your_account>\AppData\Roaming\Blender Foundation\Blender\3.x\scripts\addons

btw: dunno how you installed the script. If via the zip then you need to unzip before, rename the folder and zip it again. Just in case.
## Post #11
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-12-09T19:27:06+00:00
- Post Title: valkyria chronicles 4

Try it but the same problem  is this error mod = __import__(module_name)
ModuleNotFoundError: No module named 'import_valkyria-blender-2'
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-09T22:29:48+00:00
- Post Title: valkyria chronicles 4

I'm pretty sure this is because you still have that annoying point between 2 and 8, so "2.8" instead of "2_8".

So blender misses "import_valkyria-blender-2" because it stops reading the module path after the "2". That's some kind of bug but it's possible to circumvent it.

That's why I wrote in my previous post:
btw: dunno how you installed the script. If via the zip then you need to unzip before, rename the folder and zip it again. Just in case.
but you didn't seem to read it.
## Post #13
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-12-09T23:56:43+00:00
- Post Title: valkyria chronicles 4

step by step import_valkyria-blender-2.8 unblock right
