## Post #1
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2014-06-29T11:30:56+00:00
- Post Title: Seven Knights Android (.nxm)

Can someone make noesis or max script for the new android game by netmarble?they use .nxm format for the models.
i am trying using hex2obj but my knowledge for hex editor too low (sadly)   

a reply will be appreciated!
thank you  
[sample1.zip](https://xentaxbackup.github.io/file/7534_sample1.zip)
## Post #2
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2015-02-26T08:09:10+00:00
- Post Title: Seven Knights Android (.nxm)

the same  problem about exactor the model

the nexus game developer team make the model files   .nxm   the  motion files .nxa
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-26T13:48:56+00:00
- Post Title: Seven Knights Android (.nxm)

you may check what's wrong with the uvs:



SevenKnightsAndroid.JPG (191 KiB) Viewed 854 times


(Guess I took too many face indices/vertices.)

hmm, 0x3E8: 21 05 00 00 -> 1313 (dec.)

(0x3FC: 8C 3D 00 00= 15756 (dec.) = 12x1313, size of vertex data block,
0xEF9D: 02 13 00 00= 4866 (dec.), face indices count
## Post #4
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2015-02-27T04:15:10+00:00
- Post Title: Seven Knights Android (.nxm)

> Reply from shakotay2
>
> you may check what's wrong with the uvs:
SevenKnightsAndroid.JPG
(Guess I took too many face indices/vertices.)

hmm, 0x3E8: 21 05 00 00 -> 1313 (dec.)

(0x3FC: 8C 3D 00 00= 15756 (dec.) = 12x1313, size of vertex data block,
0xEF9D: 02 13 00 00= 4866 (dec.), face indices count

i re  import the  model maybe the uv is right could you try it again？
[http://pan.baidu.com/s/1pJOFi9X](http://pan.baidu.com/s/1pJOFi9X)
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-02-27T11:43:36+00:00
- Post Title: Seven Knights Android (.nxm)

> Reply from shakotay2
>
> you may check what's wrong with the uvs:
-- snip --
(Guess I took too many face indices/vertices.)

I think it's more likely that the model just uses multiple material IDs.
There's clearly another texture referenced inside the mesh file: c_0011_evan_02.png
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-28T08:31:10+00:00
- Post Title: Seven Knights Android (.nxm)

> Reply from barti
>
> I think it's more likely that the model just uses multiple material IDs.yeah, but where to search for them?
There's a table of maybe 1313 words at 0x6ABC but seems creating submeshes is easier than analyzing:



SevenKn_SM.JPG (61.59 KiB) Viewed 805 times
## Post #7
- Username: systemchester
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 02, 2010 9:44 am
- Post datetime: 2015-03-01T08:56:12+00:00
- Post Title: Seven Knights Android (.nxm)

> Reply from shakotay2
>
> barti wrote:I think it's more likely that the model just uses multiple material IDs.yeah, but where to search for them?
There's a table of maybe 1313 words at 0x6ABC but seems creating submeshes is easier than analyzing:
The attachment SevenKn_SM.JPG is no longer available
[c_0011_evan_02.png](https://xentaxbackup.github.io/file/8775_c_0011_evan_02.png)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-01T10:50:17+00:00
- Post Title: Seven Knights Android (.nxm)

building_submeshes.JPG (117.98 KiB) Viewed 780 times

the arrow hinting to the face indices is marking the border of the upper body submesh.
The submesh name is submesh_0.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-18T17:15:15+00:00
- Post Title: Seven Knights Android (.nxm)

Due to a user's request I've checked another model (c_0216):



c_0216.JPG (76.83 KiB) Viewed 724 times



You'll have to find the correct border between submeshes for yourself.
(remember that hex2obj creates submeshes every 500 faces. But the real borders are different, maybe stored in the format.)

It's not too hard for this model. In c_0216_export_0.obj comment out g submesh_ 1 to 5 by a #
and insert no 1 here:
f 2145/2145 2154/2154 2146/2146 
f 2149/2149 2153/2153 2150/2150 
g submesh_1
f 573/573 574/574 575/575 
f 575/575 576/576 573/573
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-11-04T10:17:36+00:00
- Post Title: Seven Knights Android (.nxm)

As I remembered me being a member of most secret "Riders of dead horses"  club   I feel obliged to do another contribution to this thread (though not sure whether h_7308_export.nxm belongs to this game):



KhunAgueroAgnes.png (125.19 KiB) Viewed 408 times


Interesting thing: you can interpret data being sequential, too:

0x14E69 6408
Vb0
0x56B6
0x406 1762
020000
0x0 255

Or, it's 'seq' and all sequential formats can be exported with 'VB' (where a vertex block of 3 floats isn't really a combined vertex block, as I wrote here: [viewtopic.php?f=29&t=10894&p=143658&hil ... ed#p143658](http://forum.xentax.com/viewtopic.php?f=29&t=10894&p=143658&hilit=+combined#p143658))
## Post #11
- Username: kim743
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 17, 2016 1:32 am
- Post datetime: 2019-01-02T06:49:53+00:00
- Post Title: Seven Knights Android (.nxm)

So we can only extract models from this game as .obj? Any method to get bones as well?
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-02T11:14:55+00:00
- Post Title: Seven Knights Android (.nxm)

Always the same as long as there does no script exist:
search for the bone names in nxm (Bip001... here), build the hierarchy, get the matrices (with positions and rotations), create an smd file from it

(It's about 4 and a half years now and noone has done it - so very unlikely that someone will do...)
## Post #13
- Username: kim743
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 17, 2016 1:32 am
- Post datetime: 2019-01-02T11:41:53+00:00
- Post Title: Seven Knights Android (.nxm)

> Reply from shakotay2
>
> 
search for the bone names in nxm (Bip001... here), build the hierarchy, get the matrices (with positions and rotations), create an smd file from it

Can you elaborate that with more details? I would like to give at least a shot. (it's learning, after all)
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-03T11:04:54+00:00
- Post Title: Seven Knights Android (.nxm)

you may read my posts here concerning the creation of an smd file for a skeleton:
[viewtopic.php?f=16&t=19223](http://forum.xentax.com/viewtopic.php?f=16&t=19223)
## Post #15
- Username: kim743
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Sep 17, 2016 1:32 am
- Post datetime: 2019-01-04T07:48:00+00:00
- Post Title: Seven Knights Android (.nxm)

> Reply from shakotay2
>
> you may read my posts here concerning the creation of an smd file for a skeleton:
viewtopic.php?f=16&t=19223

Thank you! I will take a look into it.
## Post #16
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2019-01-04T15:40:23+00:00
- Post Title: Re: Seven Knights Android (.nxm)

Can anyone share the models (.nxm) from this game?
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-01-04T19:35:13+00:00
- Post Title: Re: Seven Knights Android (.nxm)

Apart from the zip in the first post this is what I have:


 SevenKnightsAndroid-sample1a.zip
(228.62 KiB) Downloaded 42 times
## Post #18
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2019-01-05T11:50:50+00:00
- Post Title: Re: Seven Knights Android (.nxm)

Here is a bones importer . Only for Blender version 2.49.
Tested only on 3 models.

[http://www.mediafire.com/view/rt9rzt893 ... models.jpg](http://www.mediafire.com/view/rt9rzt8936e184u/models.jpg)

Updated 2019-01-09:
-import meshes 
-splitt meshes by materials
-weights - still missing bone maps
[Blender249[SevenKnights[mobile][nxm][2019-01-09].zip](https://xentaxbackup.github.io/file/15433_Blender249[SevenKnights[mobile][nxm][2019-01-09].zip)
## Post #19
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2019-01-05T16:21:34+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Szkaradek123
>
> Here is a bones importer . Only for Blender version 2.49.
Tested only on 3 models.

http://www.mediafire.com/view/rt9rzt893 ... models.jpg

not work on .nmx new ver
## Post #20
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2019-01-05T17:00:01+00:00
- Post Title: Re: Seven Knights Android (.nxm)

I don't have this game.
As i wrote : checked only on 3 files.
## Post #21
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2019-01-06T03:36:30+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Szkaradek123
>
> I don't have this game.
As i wrote : checked only on 3 files.

.nxa = aniamtion

all file 2018-2019

here : [https://drive.google.com/open?id=1Nc6yU ... m2_fVq8yb9](https://drive.google.com/open?id=1Nc6yUP83AyaDj_6avp-191m2_fVq8yb9)
## Post #22
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2019-01-13T05:40:34+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Szkaradek123
>
> Here is a bones importer . Only for Blender version 2.49.
Tested only on 3 models.

http://www.mediafire.com/view/rt9rzt893 ... models.jpg

Updated 2019-01-09:
-import meshes 
-splitt meshes by materials
-weights - still missing bone maps

Thx ♥

possible ? animation
## Post #23
- Username: Gooddom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 29, 2019 9:39 pm
- Post datetime: 2020-09-12T15:14:33+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Szkaradek123 ↑Sat Jan 05, 2019 7:50 pm at Sat Jan 05, 2019 7:50 pm
>
> 
Here is a bones importer . Only for Blender version 2.49.
Tested only on 3 models.

http://www.mediafire.com/view/rt9rzt893 ... models.jpg

Updated 2019-01-09:
-import meshes 
-splitt meshes by materials
-weights - still missing bone maps

THX, Possible nxa importer script?
## Post #24
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2021-01-31T10:44:07+00:00
- Post Title: Re: Seven Knights Android (.nxm)

Sorry, but I can't find where the .nxm and .nxa files are located.
There are no such files in Data and Obb folders.
Can someone tell me in detail how I can extract these files?
Thanks.
## Post #25
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2021-03-27T15:21:42+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from RedBear ↑Sun Jan 31, 2021 6:44 pm at Sun Jan 31, 2021 6:44 pm
>
> 
Sorry, but I can't find where the .nxm and .nxa files are located.
There are no such files in Data and Obb folders.
Can someone tell me in detail how I can extract these files?
Thanks.

It might be 0/data/data/com.cjenm.sknight/res/heros
## Post #26
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-04T21:51:28+00:00
- Post Title: Re: Seven Knights Android (.nxm)

Sorry, I'm really late to this, but has anyone figured out how to import the models with textures into Blender? I am in /\data\data\com.netmarble.sknightsgb\files\Resources\res_en\heroes, but I don't know what to do with these .nxm files and I don't have much knowledge regarding data mining, extracting models/meshes, modding or using 3D software, I was mostly just looking to get the models to recreate characters in more detail or at least try to.
If anyone has found a solution and would be willing to share the step-by-step process, detailed or simplified, I would very much appreciate it. 

Edit: Not sure if .nxa files are relevant at all, also it seems the majority of heroes are in \res\heroes, not res_en, my bad.
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-05T09:15:39+00:00
- Post Title: Re: Seven Knights Android (.nxm)

edit: seems there's a problem with this py script under Windows 10/11, so my answer is related to Windows 7 only!

> Reply from Enliof ↑Sat Nov 05, 2022 5:51 am at Sat Nov 05, 2022 5:51 am
>
> If anyone has found a solution and would be willing to share the step-by-step process, detailed or simplified, I would very much appreciate it. :)majority of heroes are in \res\heroes, not res_en, my bad.I have no idea what you're expecting. Use the blender 2.49 script from this thread:
.



blender2.49_nxm.jpg (236.33 KiB) Viewed 107 times

There's dozens if not hundreds of posts where the use of M. Szkaradek's scripts is explained.
For use under Win7 and newer additionally read here:

> Reply from shakotay2 ↑Mon Oct 24, 2022 7:51 pm at Mon Oct 24, 2022 7:51 pm
>
> (yes, other format but the principle is the same)

Don't have a textured models to try it out so you'll need to check for yourslef whether the script supports it.
If not, this is what we have so far:

> Reply from shakotay2 ↑Thu Feb 26, 2015 9:48 pm at Thu Feb 26, 2015 9:48 pm
>
> 

> Reply from shakotay2 ↑Sun Mar 01, 2015 6:50 pm at Sun Mar 01, 2015 6:50 pm
>
>
## Post #28
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-05T11:04:49+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from shakotay2 ↑Sat Nov 05, 2022 5:15 pm at Sat Nov 05, 2022 5:15 pm
>
> 
...

Doesn't seem to work, I just get error in console:

```
  File "starter.py", line 1, in <module>
  File "M:\Old Blender\newGameLib\__init__.py", line 1, in <module>
    import myLibraries
  File "M:\Old Blender\newGameLib\myLibraries\__init__.py", line 1, in <module>
    import myFunction
  File "M:\Old Blender\newGameLib\myLibraries\myFunction.py", line 2, in <module>
    import Blender,os
  File "M:\Old Blender\python26.zip\os.py", line 63, in <module>
  File "M:\Old Blender\python26.zip\ntpath.py", line 11, in <module>
ImportError: No module named genericpath

```


The files are all there and the scripts are unedited. The line 1 is always just import x.

Edit: Ok, it seems just genericpath is missing, not sure where to get that, can't really find anything that seems useful online.
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-05T11:49:38+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Enliof ↑Sat Nov 05, 2022 7:04 pm at Sat Nov 05, 2022 7:04 pm
>
> Edit: Ok, it seems just genericpath is missing, not sure where to get that, can't really find anything that seems useful online.Forget about genericpath. I used dozens of Mariusz' scripts. All of them worked. So you're doing something wrong. (Probably you ignored what I wrote about Windows 7 and newGameLib.)

(The only problematic thing is that newGameLib may be different with different scripts. So in this case under windows 7 it's required to have a renamed individual newGameLib_SKA in the blender2.49 folder, where the blender.exe is in. In starter.py change of "newGameLib" to "newGameLib_SKA" is required, of course.)
## Post #30
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-05T12:43:37+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from shakotay2 ↑Sat Nov 05, 2022 7:49 pm at Sat Nov 05, 2022 7:49 pm
>
> 
Forget about genericpath. I used dozens of Mariusz' scripts. All of them worked. So you're doing something wrong. (Probably you ignored what I wrote about Windows 7 and newGameLib.)

(The only problematic thing is that newGameLib may be different with different scripts. So in this case under windows 7 it's required to have a renamed individual newGameLib_SKA in the blender2.49 folder, where the blender.exe is in. In starter.py change of "newGameLib" to "newGameLib_SKA" is required, of course.)

What you wrote in the linked post was:

> Works like a charm for me.
>
> Really, dunno how many dozens times I've posted it:
>
> 
>
> You'll need to copy the newGameLib directory into the blender_2.49 directory to make the script work under Windows 7 and higher.
>
> (If you need more than one dir for other scripts expand the dir name. You'll have to change the name in the script then, too.)

So I copied the folder over and since I didn't use other scripts, I didn't have to change the directory name according to that. But ok, I changed the name of the folder to newGameLib_SKA now and changed the script to  

```
from newGameLib_SKA import *
import Blender	

```


Same result:

```
  File "starter.py", line 1, in <module>
  File "M:\Old Blender\newGameLib\__init__.py", line 1, in <module>
  File "M:\Old Blender\newGameLib\myLibraries\__init__.py", line 1, in <module>
  File "M:\Old Blender\newGameLib\myLibraries\myFunction.py", line 2, in <module>
  File "M:\Old Blender\python26.zip\os.py", line 63, in <module>
  File "M:\Old Blender\python26.zip\ntpath.py", line 11, in <module>
ImportError: No module named genericpath

```


I'm running on Windows 11 using Blender 2.49. I would use newer versions, but since the scripts seem to specifically for 2.49, I use that.

Not sure why the console shows the folder as "newGameLib" even though the name is "newGameLib_SKA" now, but oh well.
## Post #31
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-05T12:52:36+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Enliof ↑Sat Nov 05, 2022 8:43 pm at Sat Nov 05, 2022 8:43 pm
>
> I'm running on Windows 11 using Blender 2.49. I would use newer versions, but since the scripts seem to specifically for 2.49, I use that.I can't test it with Win 11. Maybe some things changed (as always  ).

If you are familiar with file monitors (such as Process Monitor 3.92, free) you could try to find out what's going wrong with accessing files and folders.
## Post #32
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-05T13:05:35+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from shakotay2 ↑Sat Nov 05, 2022 8:52 pm at Sat Nov 05, 2022 8:52 pm
>
> 

Well, genericpath could be accessed, it just doesn't exist. I just tried editing out any part where the script references genericpath and then I got the next error of another missing module. Instead of going through and deleting everything it can't find, I just changed it back before something gets really messed up.
I sadly don't know how to use Process Monitor, but I can try it, though I think the issue is neither file access nor Windows 11, but I don't know, so maybe.
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-05T13:13:31+00:00
- Post Title: Re: Seven Knights Android (.nxm)

I really appreciate that you're trying. So I copied the whole stuff to Win10.
Got an error, too. But it's  missing module zipfile. Need to check this.

edit: well, that's a hard nut to crack.
Had a solution for Windows 10 here:

> Reply from shakotay2 ↑Sat Nov 05, 2022 9:51 pm at Sat Nov 05, 2022 9:51 pm
>
> 
but doing the same with 7KnightsA failed because module path is missing (os.path). So annoying...
## Post #34
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-05T14:06:52+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from shakotay2 ↑Sat Nov 05, 2022 9:13 pm at Sat Nov 05, 2022 9:13 pm
>
> 

So I think I have some idea of Process Monitor now, I filtered it so it only shows any file access in my Blender 2.49 folder and I got to the point where it tries to find genericpath. I removed the timestamp and the process ID for better readability.

```
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\genericpath								NO SUCH FILE		Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: genericpath
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender										SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender										SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.pyd								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.py								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.pyw								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.pyc								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender										SUCCESS			Desired Access: Read Data/List Directory, Synchronize, Disposition: Open, Options: Directory, Synchronous IO Non-Alert, Attributes: n/a, ShareMode: Read, Write, Delete, AllocationSize: n/a, OpenResult: Opened
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\genericpath								NO SUCH FILE		Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: genericpath
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender										SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender										SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.pyd								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.py								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.pyw								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\genericpath.pyc								NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender									SUCCESS			Desired Access: Read Data/List Directory, Synchronize, Disposition: Open, Options: Directory, Synchronous IO Non-Alert, Attributes: n/a, ShareMode: Read, Write, Delete, AllocationSize: n/a, OpenResult: Opened
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\.blender\scripts								SUCCESS			Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: scripts, 3: scripts
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender\.blender									SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender\.blender									SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender									SUCCESS			Desired Access: Read Data/List Directory, Synchronize, Disposition: Open, Options: Directory, Synchronous IO Non-Alert, Attributes: n/a, ShareMode: Read, Write, Delete, AllocationSize: n/a, OpenResult: Opened
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\.blender\scripts								SUCCESS			Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: scripts, 3: scripts
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender\.blender									SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender\.blender									SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts								SUCCESS			Desired Access: Read Data/List Directory, Synchronize, Disposition: Open, Options: Directory, Synchronous IO Non-Alert, Attributes: n/a, ShareMode: Read, Write, Delete, AllocationSize: n/a, OpenResult: Opened
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\.blender\scripts\genericpath						NO SUCH FILE		Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: genericpath
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender\.blender\scripts								SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender\.blender\scripts								SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\genericpath.pyd						NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\genericpath.py						NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\genericpath.pyw						NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\genericpath.pyc						NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts								SUCCESS			Desired Access: Read Data/List Directory, Synchronize, Disposition: Open, Options: Directory, Synchronous IO Non-Alert, Attributes: n/a, ShareMode: Read, Write, Delete, AllocationSize: n/a, OpenResult: Opened
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\.blender\scripts\bpymodules						SUCCESS			Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: bpymodules, 3: bpymodules
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender\.blender\scripts								SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender\.blender\scripts								SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts								SUCCESS			Desired Access: Read Data/List Directory, Synchronize, Disposition: Open, Options: Directory, Synchronous IO Non-Alert, Attributes: n/a, ShareMode: Read, Write, Delete, AllocationSize: n/a, OpenResult: Opened
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\.blender\scripts\bpymodules						SUCCESS			Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: bpymodules, 3: bpymodules
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender\.blender\scripts								SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender\.blender\scripts								SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\bpymodules						SUCCESS			Desired Access: Read Data/List Directory, Synchronize, Disposition: Open, Options: Directory, Synchronous IO Non-Alert, Attributes: n/a, ShareMode: Read, Write, Delete, AllocationSize: n/a, OpenResult: Opened
blender.exe		IRP_MJ_DIRECTORY_CONTROL		M:\Old Blender\.blender\scripts\bpymodules\genericpath					NO SUCH FILE		Type: QueryDirectory, FileInformationClass: FileBothDirectoryInformation, Filter: genericpath
blender.exe		IRP_MJ_CLEANUP				M:\Old Blender\.blender\scripts\bpymodules						SUCCESS	
blender.exe		IRP_MJ_CLOSE				M:\Old Blender\.blender\scripts\bpymodules						SUCCESS	
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\bpymodules\genericpath.pyd				NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\bpymodules\genericpath.py				NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\bpymodules\genericpath.pyw				NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a
blender.exe		IRP_MJ_CREATE				M:\Old Blender\.blender\scripts\bpymodules\genericpath.pyc				NAME NOT FOUND		Desired Access: Generic Read, Disposition: Open, Options: Synchronous IO Non-Alert, Non-Directory File, Attributes: N, ShareMode: Read, Write, AllocationSize: n/a


```
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-05T14:09:55+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Enliof ↑Sat Nov 05, 2022 10:06 pm at Sat Nov 05, 2022 10:06 pm
>
> So I think I have some idea of Process Monitor now, I filtered it so it only shows any file access in my Blender 2.49 folder and I got to the point where it tries to find genericpath.Cool! It's a py script from Python 2.6(.2). See linked post in my previous (edited) answer a minute before. 

Guess you simply need to install python 2.6.2 on your PC.
## Post #36
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-05T14:34:40+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from shakotay2 ↑Sat Nov 05, 2022 10:09 pm at Sat Nov 05, 2022 10:09 pm
>
> 

Well, that worked, all .py in the lib folder of Python 2.6.2 copied into a folder, zipped into python26.zip and dumped in Blender 2.49 directory. I have no idea how to get the textures in here, I can barely do it in the latest Blender version and 2.49 looks really weird, I don't know what it is, but the perspective of the user camera (not the Blender camera object for use in rendering, but what the user sees) is just awful. But hey, at least it seems to work, I took all the files from Seven Knights, so I have all the models, just have to find the exact version of my character that I need. If you happen to know how to show the textures in here, I don't really, but maybe with the accompanying .png, I will try to figure out how to put it on.
Thanks for your help with this , if you want the model files, I can upload them to Mega and post a link, not sure if that's okay here, but I could.

Edit: The skeleton starts in the model already, seems to be in the right position too, just took it out of the way for better visibility, you could hide it too.
[It works.png](https://xentaxbackup.github.io/file/23006_It works.png)
## Post #37
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-05T15:07:49+00:00
- Post Title: Re: Seven Knights Android (.nxm)

I can't seem to find all characters though, I have the games resources, but I can only seem to find the skin models and textures in here, the base skins/models seem to be somewhere else, I just can't find them for some reason. I might have to check in Nox again if I can find the files, though I can't think of anywhere else they could be.
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-11-05T16:38:51+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Enliof ↑Sat Nov 05, 2022 10:34 pm at Sat Nov 05, 2022 10:34 pm
>
> I have no idea how to get the textures in here, I can barely do it in the latest Blender version and 2.49 looks really weird,Usually you'd use this version for importing only, then export to .dae or .fbx and reimport it to a blender version of your choice to get the textures applied. That's how I'd do it.

(Those python 2.6 scripts are candidates since years for being converted to actual python but they're too cryptical (for me at least) to make it worth the effort because importing works nice once you know the conditions.  )
## Post #39
- Username: Enliof
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Nov 05, 2022 5:45 am
- Post datetime: 2022-11-05T16:43:12+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from shakotay2 ↑Sun Nov 06, 2022 12:38 am at Sun Nov 06, 2022 12:38 am
>
> 

True, I could just do it in the newer version, thanks. I'm trying to get the base character models without cosmetics now and then I can do that. Couldn't find them at all, but they have to be somewhere.

As long as it works, old version is ok too, it's not that important to update it, though I don't think it can import the other filetypes Seven Knights uses, but nxm are the most important anyway.
## Post #40
- Username: Orang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 04, 2023 10:31 pm
- Post datetime: 2023-02-04T14:37:54+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Enliof ↑Sat Nov 05, 2022 10:34 pm at Sat Nov 05, 2022 10:34 pm
>
> 
shakotay2 wrote: ↑Sat Nov 05, 2022 10:09 pm


Well, that worked, all .py in the lib folder of Python 2.6.2 copied into a folder, zipped into python26.zip and dumped in Blender 2.49 directory. I have no idea how to get the textures in here, I can barely do it in the latest Blender version and 2.49 looks really weird, I don't know what it is, but the perspective of the user camera (not the Blender camera object for use in rendering, but what the user sees) is just awful. But hey, at least it seems to work, I took all the files from Seven Knights, so I have all the models, just have to find the exact version of my character that I need. If you happen to know how to show the textures in here, I don't really, but maybe with the accompanying .png, I will try to figure out how to put it on.
Thanks for your help with this , if you want the model files, I can upload them to Mega and post a link, not sure if that's okay here, but I could.

Edit: The skeleton starts in the model already, seems to be in the right position too, just took it out of the way for better visibility, you could hide it too.

I need all the model files! Please share it with us sir! Thankyou!
## Post #41
- Username: Orang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 04, 2023 10:31 pm
- Post datetime: 2023-02-05T05:31:57+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from shakotay2 ↑Sun Nov 06, 2022 12:38 am at Sun Nov 06, 2022 12:38 am
>
> 
Enliof wrote: ↑Sat Nov 05, 2022 10:34 pmI have no idea how to get the textures in here, I can barely do it in the latest Blender version and 2.49 looks really weird,Usually you'd use this version for importing only, then export to .dae or .fbx and reimport it to a blender version of your choice to get the textures applied. That's how I'd do it.

(Those python 2.6 scripts are candidates since years for being converted to actual python but they're too cryptical (for me at least) to make it worth the effort because importing works nice once you know the conditions.  )

Hello!! all the apk file were expire, could you reshare it with us again please?
I download the latest game's apk from apk site, when I extract that apk by zip, I don't found any hero resource file (both model, texture, animation) at all, thankyou!

Truly new here, and still lacking how to start the process lol, thanks!
## Post #42
- Username: Orang
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 04, 2023 10:31 pm
- Post datetime: 2023-02-06T22:44:37+00:00
- Post Title: Re: Seven Knights Android (.nxm)

> Reply from Szkaradek123 ↑Sat Jan 05, 2019 7:50 pm at Sat Jan 05, 2019 7:50 pm
>
> 
Here is a bones importer . Only for Blender version 2.49.
Tested only on 3 models.

http://www.mediafire.com/view/rt9rzt893 ... models.jpg

Updated 2019-01-09:
-import meshes 
-splitt meshes by materials
-weights - still missing bone maps

Hello guys!
Can anyone sharing the game model or atleast just one model with rigs/bone please? I will try rigged it on my own, just need the bone
I'm new to .nxm file, try to open it on Nexus Mod Manager, but cannot open the file you share tho!

I try open your script file on Blender too. The script show up, but I don't know how to extract or receive the model from the script. Extra noob lol

Thankyou! The game will be removed on this 9th Feb, and I still don't know how to rip their model by script at all.

I can do some on Ninjaripper, but the way you guy work on script was better, and seems come up with bone/rig!
