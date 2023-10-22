## Post #1
- Username: lukamas
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 07, 2015 3:12 am
- Post datetime: 2017-01-13T20:03:34+00:00
- Post Title: Africa Rxm2 models

hi, I need help extracting models from afrika ps3


the model format is rxm2, and I found samples from another thread on here, I was wondering how to extract Afrika ps3 models?

[https://mega.nz/#!yoM21YjD!mh9KrwOq9-Q9 ... ee8DZlxgIc](https://mega.nz/#!yoM21YjD!mh9KrwOq9-Q98dluLnpu6bK-q2_jlnxBTee8DZlxgIc)

thanks in advance
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-01-14T00:50:11+00:00
- Post Title: Africa Rxm2 models

[viewtopic.php?f=10&t=14702](http://forum.xentax.com/viewtopic.php?f=10&t=14702)
## Post #3
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2017-06-04T11:20:26+00:00
- Post Title: Africa Rxm2 models

I have been on that page, but if anyone would like to, I was going to request a noesis script for the mesh importing from AFRIKA's files, it would be all I need because Noesis can extract many different formats.
## Post #4
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2020-03-23T12:41:37+00:00
- Post Title: Africa Rxm2 models

Sorry to ask for help with this, but I tried looking at the rxm2 file in a hex editor but could not figure it out,

If anyone could help me with this or make a bms script that converts the rxm2 to obj, that would be great because I am struggling to find a way to fix this.

The game is called AFRIKA for Playstation 3

here are some samples

[https://drive.google.com/open?id=1uy-SE ... YcGugh_nZD](https://drive.google.com/open?id=1uy-SE9tmh3wCWn1WVAOCaNYcGugh_nZD)

thanks in advance
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-23T15:07:54+00:00
- Post Title: Africa Rxm2 models

Seems you're out of luck with your script request... (which started Jun 04, 2017 12:20 pm, iirc)

Anyways, I polished my Make_obj function for rxm2 files (just missing one submesh, afaics):
.



blackrhino_adult-rxm2.png (167.19 KiB) Viewed 146 times


(There's some trouble with the giraffe, so may last some time.)
## Post #6
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2020-03-23T15:37:17+00:00
- Post Title: Africa Rxm2 models

wow thanks shakotay, no worries at all, keep me updated on how it is going with that, I know I do not need the script, but this function I would like to know about when you get the chance to.
## Post #7
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2020-03-24T12:27:15+00:00
- Post Title: Africa Rxm2 models

Great work on the Giraffe so far! so I have a question

So when you finish the function is it alright if you could upload the file so I can download it?

Just wondering.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-24T16:15:13+00:00
- Post Title: Africa Rxm2 models

well, I finished the tool, more or less. Elephant, rhino and baboon_baby look ok to me.
For the giraffe you have to do some fixing (usually I don't upload files in case you can fix them for yourself  ).
.


 Make_obj_rxm2.zip
(64.27 KiB) Downloaded 25 times


For lycaon.rxm2 use Make_obj_lycaon.exe (and maybe for other rxm2 with too spoiled results)
(updated it to be used with ostrich_f.rxm2 - logged .obj has the model file name now)

After having imported the resulting Makeobj_log.obj into blender you'll have to delete
the first (elephant) or the last three submeshes (giraffe), because they go bogus.

(rhino usually has no problems)

btw: you can use the multimesh feature of hex2obj (view link in my sig) for creating separate submeshes/obj files.
Will work fine for rhino and jackal; but not recommended for giraffe, because hex2obj's optimation will lead to holes.
-- You have been warned. --

### jackal: requires above mentioned feature - gives bogus FIs with the tool, will fix it later ###

How to fix 2 submeshes of giraffe
---------------------------------
Here we go.

Convert girafe_adult.rxm2 using Make_obj_rxm2.exe.
Import created Makeobj_log.obj into blender.

Delete submeshes 33, 34 and 35.
Look for the left spoiled ones: no 16 and no 25.
It's superfluous faces only which need to be deleted. (Vertices should be ok.)

Well, that's tedious doing it manually so there's a workaround using hex2obj.
You may hate it - well, then simply don't use it...

### Be sure to close Make_obj_rxm2.exe before proceeding!
---------------------------------------------------------

You need to load girafe_adult.rxm2 into hex2obj, then an H2O file.

Starting with girafe_adult.rxm2_16.h2o:

```
Vb1
24 12
0x6acb0 737
120200
0x0 255
```


The parameter of importance is the FIcount (face index count): 1401

Pressing the 'go1' button, scrolling down the bottom left listbox it says:
max FI is 737
and, as you can see, it's the vertex count in the lower right editbox.

Decrease 1401, press 'go1', maxFI: 737 (repeat as long as the 'max FI' remains its value)
Try out 700, press 'mesh' button

Looks good, you could even use 550 as FIcount but I'd suggest to choose 750 here.
(You'll have some superfluous faces again but it's better than having holes to be fixed later isn't it?)

Ok then, finishing here:
File\SaveAs mesh

Have a look into the folder where girafe_adult.rxm2 resides:
girafe_adult_0.obj (maybe some other number than '0', just care for the latest file date/time).

---------------------------
Back in blender again.

Select submesh 16, delete it. Then import girafe_adult_0.obj.
Fits like a charm but remember the faces mentioned above. It's 4 or 5 to be deleted now.

(Maybe better to load/repair the 2 submeshes without having the giraffe present. Your decision.)

---------------------------------------------------
Anyways, load girafe_adult.rxm2_25.h2o into hex2obj (with rxm2 model file still loaded):

```
Vb1
24 12
0xa6fd0 731
120200
0x0 255
```


Press 'mesh' button, mesh looks horrible.
Lower FIcount to 768 -> 'max FI' still 731.

Submesh looks ok, some superfluous faces, as intended.

SaveAs, same procedure like above.
Import created girafe_adult_1.obj into blender, delete superfluous faces (there were 3).

Import the whole giraffe (Makeobj_log.obj) into blender (in case it's not present).

Select SM16 and 25, then delete each.

(There maybe situations with other meshes where it's more convenient to use the outliner window
 for selection to reduce the risk of deleting the submeshes you repaired previously.)

Before exporting the whole beast you need to fill a 3-faces-hole at the bottom of its neck.

Fixing holes in blender:
-----------------------
[https://codeyarns.github.io/tech/2013-1 ... ender.html](https://codeyarns.github.io/tech/2013-10-22-how-to-fill-hole-in-mesh-in-blender.html)
but import the obj with "import as groups" <off> in case a hole is at a submesh border.

Have fun
shak-otay
## Post #9
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2020-03-24T20:54:47+00:00
- Post Title: Africa Rxm2 models

Wow thanks, I tried it and most of the models worked, but some of them have huge faces in random bogus positions when I import some of them, 

anyway this can be fixed, or do you plan on fixing this soon?

also when I import the lycaon.rxm2 model, I get these vertices with no faces, when I try to fill the vertices, faces go to random positions.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-24T21:53:56+00:00
- Post Title: Africa Rxm2 models

> Reply from lukamas233 ↑Wed Mar 25, 2020 4:54 am at Wed Mar 25, 2020 4:54 am
>
> 
[...], but some of them have huge faces in random bogus positions when I import some of them,Which ones are you talking about exactly?  Most of them (SM 33, 34 and 35 of the giraffe for example) can be safely deleted. SM 16 and 25 of the giraffe need to be fixed manually, as described.

Also you may take into account to use the H2O files with hex2obj (not for lycaon.rxm2 though - code needs fixing).

```
H2O files should be created.

In hex2obj_0.24e (view link in my sig) load the model *.rxm2 then choose File "SaveAs Mmesh" (multiple mesh)
to create obj files from all contained submeshes.

After hex2obj processed the H2O files there should exist the same amount of obj files 
in the model's folder named from *_0.obj to *_xx.obj.

*.objx may be invalid (especially files >1MB) but normally you can rename them to *.obj.

When executing "load_multi_obj_blender2.69.py" (see next code window) in a blender Text Editor window with alt-p
make sure to have set "path_to_obj_dir" in the *.py to YOUR model directory.

Also be sure that there are no obj files in a maybe contained subdirectory.
(they would be loaded, too)

Best choice would be to have a separate folder for each *.rxm2 and its obj files.

Keep in mind that ?3.obj is NOT created from ?3.H2O! 
First line in an obj reveals its H2O-source.
```


(If you don't know how to use the script you can import the submeshes one by one.)

```
import bpy

# http://blender.stackexchange.com/questions/5064/batch-import-wavefront-obj
# put the location to the folder where the objs are located here in this fashion
path_to_obj_dir = os.path.join('D:\\', 'test\\rxm2')

# get list of all files in directory
file_list = sorted(os.listdir(path_to_obj_dir))

# get a list of files ending in 'obj'
obj_list = [item for item in file_list if item[-3:] == 'obj']

# loop through the strings in obj_list and add the files to the scene
for item in obj_list:
    path_to_file = os.path.join(path_to_obj_dir, item)
    bpy.ops.import_scene.obj(filepath = path_to_file)
```


> anyway this can be fixed, or do you plan on fixing this soon?Not to soon. (That's tedious work left that I usually don't care for...  )

(For lycaon.rxm2 I'll care tomorrow (maybe) - problem looks interesting...)
## Post #11
- Username: lukamas233
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Apr 13, 2017 6:10 pm
- Post datetime: 2020-03-24T22:02:37+00:00
- Post Title: Africa Rxm2 models

Sounds good to me, thanks for the help, I really appreciate it.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-25T08:55:58+00:00
- Post Title: Africa Rxm2 models

Updated the zip here: 
> Reply from shakotay2 ↑Wed Mar 25, 2020 12:15 am at Wed Mar 25, 2020 12:15 am
>
> 
.



lycaon.png (53.84 KiB) Viewed 94 times
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-03-26T11:47:19+00:00
- Post Title: Africa Rxm2 models

Another update to the zipped file (link see post above)
So ostrich_f.rxm2 will be treated better now (named ostrich_f.rxm2.obj instead of Makeobj_log.obj now):
.



ostrich.png (172.55 KiB) Viewed 68 times


You may delete submesh 10 safely (or correct the _10.H2O as described for giraffe some posts above).

Just in case you're using the H2O files:
ostrich_f.rxm2_7.H2O needs an urgent FI address correction:

0x371A0 651
Vb1
26 10
0x34280 459
120200
0x0 255

------------------------

For pelican.rxm2 use the H2Os with the multi mesh feature of hex2obj (File SaveAs Mmesh)
because the pelican.rxm2.obj misses a lot of faces.
