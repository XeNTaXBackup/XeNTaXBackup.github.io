## Post #1
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-09-18T16:20:16+00:00
- Post Title: Deathloop model importer

Based on this blender script[viewtopic.php?f=18&t=15518&hilit=dishon ... 60#p176066](https://forum.xentax.com/viewtopic.php?f=18&t=15518&hilit=dishonored&start=60#p176066)
I rewrite it to support Deathloop.Currently *.bmd6model/*.bmodel/*.edgeskl/*.bwm is supported.
Blender 2.9.2 tested 

```
2021.9.21 v3:Add .bwm support
2021.9.21 v4:Fix a bug that fails to import bmd6model StaicMesh
2021.9.27 v5:fix a bug that fails to import *.bwm

```

[io_scene_Deathloop_v5.7z](https://xentaxbackup.github.io/file/20907_io_scene_Deathloop_v5.7z)
## Post #2
- Username: rtrman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 21, 2021 8:07 am
- Post datetime: 2021-09-21T00:31:08+00:00
- Post Title: Deathloop model importer

Hey, great work.
I can't seem to import weapon models, I get a failure message "Error: Could Not Import"
I'm using the files from .\generated\basemodel\models\equipment\weapon\_asset\[class]\[weapon]\mesh\
Thanks

Edit - console log:
Reading C:\Users\user\Documents\Development\Deathloop\generated\basemodel\models\equipment\weapon\_asset\hnd\hamlet\tech\w_hnd_hamlet.bmd6model...
C:\Users\user\Documents\Development\Deathloop\generated\basemodel\models\equipment\weapon\_asset\hnd\hamlet\tech\w_hnd_hamlet.bmd6model:76890: fatal: end of file

Traceback (most recent call last):
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 150, in parse
    self.do_parse()
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\model_files.py", line 39, in do_parse
    self.meshes.append(self.parse_mesh())
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\model_files.py", line 87, in parse_mesh
    mesh.vert_weights = self.read_array('16B', mesh.vertex_count)
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 114, in read_array
    buf = self.read_bytes(size * count)
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 92, in read_bytes
    self.abort('fatal: end of file')
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 80, in abort
    raise Exception('Fatal error: could not parse file')
Exception: Fatal error: could not parse file
## Post #3
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-09-21T07:33:34+00:00
- Post Title: Deathloop model importer

> Reply from rtrman ↑Tue Sep 21, 2021 8:31 am at Tue Sep 21, 2021 8:31 am
>
> 
Hey, great work.
I can't seem to import weapon models, I get a failure message "Error: Could Not Import"
I'm using the files from .\generated\basemodel\models\equipment\weapon\_asset\[class]\[weapon]\mesh\
Thanks

Edit - console log:
Reading C:\Users\user\Documents\Development\Deathloop\generated\basemodel\models\equipment\weapon\_asset\hnd\hamlet\tech\w_hnd_hamlet.bmd6model...
C:\Users\user\Documents\Development\Deathloop\generated\basemodel\models\equipment\weapon\_asset\hnd\hamlet\tech\w_hnd_hamlet.bmd6model:76890: fatal: end of file

Traceback (most recent call last):
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 150, in parse
    self.do_parse()
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\model_files.py", line 39, in do_parse
    self.meshes.append(self.parse_mesh())
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\model_files.py", line 87, in parse_mesh
    mesh.vert_weights = self.read_array('16B', mesh.vertex_count)
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 114, in read_array
    buf = self.read_bytes(size * count)
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 92, in read_bytes
    self.abort('fatal: end of file')
  File "C:\Users\user\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\io_scene_Deathloop\io_utils.py", line 80, in abort
    raise Exception('Fatal error: could not parse file')
Exception: Fatal error: could not parse file
Fix it in V4.
More tests are welcome
## Post #4
- Username: phoondos
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 14, 2020 12:55 pm
- Post datetime: 2021-09-24T01:48:34+00:00
- Post Title: Deathloop model importer

what about textures?
## Post #5
- Username: mariachiscalpi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Sep 20, 2021 3:53 am
- Post datetime: 2021-09-24T10:36:13+00:00
- Post Title: Deathloop model importer

thanks for all the updates! it'd seem there are a few .bwm files which cannot be imported, pasting a few console logs below:


> Reply from console
>
> Reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\upper_antenna\upper_antenna_p\upper_antenna_p.bwm...
C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\upper_antenna\upper_antenna_p\upper_antenna_p.bwm:98f52c4: fatal: end of file

Traceback (most recent call last):
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 168, in parse_lazy
    self.do_parse()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 279, in do_parse
    self.parse_instance_groups()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 435, in parse_instance_groups
    self.instance_groups = [ self.read_array_flat('I', self.read('I')) for i in range(count+1) ]
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 435, in <listcomp>
    self.instance_groups = [ self.read_array_flat('I', self.read('I')) for i in range(count+1) ]
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 118, in read_array_flat
    return list(itertools.chain.from_iterable(self.read_array(spec, count)))
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 114, in read_array
    buf = self.read_bytes(size * count)
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 92, in read_bytes
    self.abort('fatal: end of file')
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 80, in abort
    raise Exception('Fatal error: could not parse file')
Exception: Fatal error: could not parse file
Failed reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\upper_antenna\upper_antenna_p\upper_antenna_p.bwm.

> Reply from console
>
> Reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\tutorial\tutorial_01\tutorial_01_p\tutorial_01_p.bwm...
C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\tutorial\tutorial_01\tutorial_01_p\tutorial_01_p.bwm:fa9e94c: fatal: end of file

Traceback (most recent call last):
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 168, in parse_lazy
    self.do_parse()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 278, in do_parse
    self.parse_unk_indices()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 428, in parse_unk_indices
    self.unk_index_list3 = [
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 429, in <listcomp>
    (self.read('I'), self.read_array_flat('I', self.read('I')))
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 118, in read_array_flat
    return list(itertools.chain.from_iterable(self.read_array(spec, count)))
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 114, in read_array
    buf = self.read_bytes(size * count)
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 92, in read_bytes
    self.abort('fatal: end of file')
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 80, in abort
    raise Exception('Fatal error: could not parse file')
Exception: Fatal error: could not parse file
Failed reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\tutorial\tutorial_01\tutorial_01_p\tutorial_01_p.bwm.
## Post #6
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2021-09-25T00:04:13+00:00
- Post Title: Deathloop model importer

Hey Guys, I was wondering if theres a tool for extracting the models and where I could find it. Can anyone point me in the right direction?
## Post #7
- Username: CAXX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 06, 2019 7:44 pm
- Post datetime: 2021-09-26T22:24:24+00:00
- Post Title: Deathloop model importer

Heya, thanks for writing the script! Here are some issues that I've found:
Hair meshes on complex hair don't import correctly

And another thing that I've found is that imported meshes have basically unnamed vertex groups i.e.:
Here's what the skeleton bone names look like

And here are the vertex group names
## Post #8
- Username: adrenilanegaming
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 7:54 am
- Post datetime: 2021-09-27T00:02:22+00:00
- Post Title: Deathloop model importer

im sorry im sort of a noob when it comes to modding, but i installed the addon and now using the import option its just the default files (cfg, resources, etc) do i have to unpack them and then import using the addon or whatnot? right now im very confused

edit - i actually just figured it out
## Post #9
- Username: adrenilanegaming
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 7:54 am
- Post datetime: 2021-09-27T00:31:58+00:00
- Post Title: Deathloop model importer

> Reply from DV9 x Drillz ↑Sat Sep 25, 2021 8:04 am at Sat Sep 25, 2021 8:04 am
>
> 
Hey Guys, I was wondering if theres a tool for extracting the models and where I could find it. Can anyone point me in the right direction? you use this tool called "quickbms"  [http://aluigi.altervista.org/bms/deathloop.bms](http://aluigi.altervista.org/bms/deathloop.bms) you can find the deathloop script here
## Post #10
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-09-27T10:04:24+00:00
- Post Title: Deathloop model importer

> Reply from mariachiscalpi ↑Fri Sep 24, 2021 6:36 pm at Fri Sep 24, 2021 6:36 pm
>
> 
thanks for all the updates! it'd seem there are a few .bwm files which cannot be imported, pasting a few console logs below:

console wrote:Reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\upper_antenna\upper_antenna_p\upper_antenna_p.bwm...
C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\upper_antenna\upper_antenna_p\upper_antenna_p.bwm:98f52c4: fatal: end of file

Traceback (most recent call last):
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 168, in parse_lazy
    self.do_parse()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 279, in do_parse
    self.parse_instance_groups()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 435, in parse_instance_groups
    self.instance_groups = [ self.read_array_flat('I', self.read('I')) for i in range(count+1) ]
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 435, in <listcomp>
    self.instance_groups = [ self.read_array_flat('I', self.read('I')) for i in range(count+1) ]
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 118, in read_array_flat
    return list(itertools.chain.from_iterable(self.read_array(spec, count)))
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 114, in read_array
    buf = self.read_bytes(size * count)
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 92, in read_bytes
    self.abort('fatal: end of file')
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 80, in abort
    raise Exception('Fatal error: could not parse file')
Exception: Fatal error: could not parse file
Failed reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\upper_antenna\upper_antenna_p\upper_antenna_p.bwm.
console wrote:Reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\tutorial\tutorial_01\tutorial_01_p\tutorial_01_p.bwm...
C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\tutorial\tutorial_01\tutorial_01_p\tutorial_01_p.bwm:fa9e94c: fatal: end of file

Traceback (most recent call last):
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 168, in parse_lazy
    self.do_parse()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 278, in do_parse
    self.parse_unk_indices()
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 428, in parse_unk_indices
    self.unk_index_list3 = [
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\model_files.py", line 429, in <listcomp>
    (self.read('I'), self.read_array_flat('I', self.read('I')))
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 118, in read_array_flat
    return list(itertools.chain.from_iterable(self.read_array(spec, count)))
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 114, in read_array
    buf = self.read_bytes(size * count)
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 92, in read_bytes
    self.abort('fatal: end of file')
  File "C:\Program Files\Blender Foundation\Blender 2.93\2.93\scripts\addons\io_scene_Deathloop\io_utils.py", line 80, in abort
    raise Exception('Fatal error: could not parse file')
Exception: Fatal error: could not parse file
Failed reading C:\Users\user\Desktop\DEATHLOOP\extracts\maps\campaign\tutorial\tutorial_01\tutorial_01_p\tutorial_01_p.bwm.

Fixed in V5.
## Post #11
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-09-27T12:25:06+00:00
- Post Title: Deathloop model importer

> Reply from CAXX ↑Mon Sep 27, 2021 6:24 am at Mon Sep 27, 2021 6:24 am
>
> 
Heya, thanks for writing the script! Here are some issues that I've found:
Hair meshes on complex hair don't import correctly

And another thing that I've found is that imported meshes have basically unnamed vertex groups i.e.:
Here's what the skeleton bone names look like

And here are the vertex group names

I used "\generated\basemodel\models\character\player\juliana\_asset\body_a01\tech\f_juliana_head_a01.bmd6model" and didn't see the issue while vertex groups are unnamed.

Maybe the file you used is low LOD.
Could you please upload the sample files
## Post #12
- Username: CAXX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Aug 06, 2019 7:44 pm
- Post datetime: 2021-09-27T15:07:33+00:00
- Post Title: Deathloop model importer

> I used "\generated\basemodel\models\character\player\juliana\_asset\body_a01\tech\f_juliana_head_a01.bmd6model" and didn't see the issue while vertex groups are unnamed.
Okay, I've probably stumbled onto some sort of recompiled meshes  . Importing from the path you wrote results in complete hair mesh, thanks. 
That leaves vertex groups, I guess I can rename them manually or find a script that could handle it for me.
Do you have any clue on how to convert texture files? There are a bunch of BMS scripts for this format, but they are made for specific games.
Thanks again!
## Post #13
- Username: adrenilanegaming
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 7:54 am
- Post datetime: 2021-09-27T22:32:20+00:00
- Post Title: Deathloop model importer

Im trying to import the maps from map_wharf_04_0.resources but every time i try to import the .bwm it says in blender "Map files must be imported directly from the game files". What do i do

Im exporting the unpacked files into a folder in my downloads, i tried moving the .bwm to the game directory to no avail.
## Post #14
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-09-29T07:03:56+00:00
- Post Title: Deathloop model importer

> Reply from CAXX ↑Mon Sep 27, 2021 11:07 pm at Mon Sep 27, 2021 11:07 pm
>
> 
I used "\generated\basemodel\models\character\player\juliana\_asset\body_a01\tech\f_juliana_head_a01.bmd6model" and didn't see the issue while vertex groups are unnamed.
Okay, I've probably stumbled onto some sort of recompiled meshes  . Importing from the path you wrote results in complete hair mesh, thanks. 
That leaves vertex groups, I guess I can rename them manually or find a script that could handle it for me.
Do you have any clue on how to convert texture files? There are a bunch of BMS scripts for this format, but they are made for specific games.
Thanks again!

If you have imported skeleton before, it will rename vertex groups automatically with the skeleton selected.
I am not familar with texture files, may not be able to process texture files
## Post #15
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-09-29T07:21:16+00:00
- Post Title: Deathloop model importer

> Reply from adrenilanegaming ↑Tue Sep 28, 2021 6:32 am at Tue Sep 28, 2021 6:32 am
>
> 
Im trying to import the maps from map_wharf_04_0.resources but every time i try to import the .bwm it says in blender "Map files must be imported directly from the game files". What do i do

Im exporting the unpacked files into a folder in my downloads, i tried moving the .bwm to the game directory to no avail.

The script will check whether you have the following paths "your_BMS_export_path\generated" and "your_BMS_export_path\generated\decls"
If you have both these paths, it won't show error.
## Post #16
- Username: adrenilanegaming
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Sep 27, 2021 7:54 am
- Post datetime: 2021-09-29T20:41:08+00:00
- Post Title: Re: Deathloop model importer

> Reply from 48464385 ↑Wed Sep 29, 2021 3:21 pm at Wed Sep 29, 2021 3:21 pm
>
> 
adrenilanegaming wrote: ↑Tue Sep 28, 2021 6:32 am
Im trying to import the maps from map_wharf_04_0.resources but every time i try to import the .bwm it says in blender "Map files must be imported directly from the game files". What do i do

Im exporting the unpacked files into a folder in my downloads, i tried moving the .bwm to the game directory to no avail.


The script will check whether you have the following paths "your_BMS_export_path\generated" and "your_BMS_export_path\generated\decls"
If you have both these paths, it won't show error.

Thats why , ive been singling out the map files to export quicker. thanks
## Post #17
- Username: wully
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 30, 2021 7:23 am
- Post datetime: 2021-09-30T18:49:40+00:00
- Post Title: Re: Deathloop model importer

Has there been any progress figuring out how to import with textures? When the bimage files are on the right path I dont get any warnings in blender, but it still doesnt seem to pull out the textures
## Post #18
- Username: kidaXV
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 26, 2019 12:26 pm
- Post datetime: 2021-10-30T23:13:29+00:00
- Post Title: Re: Deathloop model importer

> Reply from wully ↑Fri Oct 01, 2021 2:49 am at Fri Oct 01, 2021 2:49 am
>
> 
Has there been any progress figuring out how to import with textures? When the bimage files are on the right path I dont get any warnings in blender, but it still doesnt seem to pull out the textures

I made a rough [python script here](https://forum.xentax.com/viewtopic.php?f=18&t=24524&p=178929#p178929) that's capable of generating .dds files based on the original .bimage files, although there's a couple of compression types it doesn't work on. I noticed that the bmodel importer script does work pretty well at automatically using the converted .dds textures once they're there, although for character models it doesn't seem to be picking up eyelashes or hair, so that might have to be adjusted manually:



jules.jpg (59.56 KiB) Viewed 341 times
## Post #19
- Username: DV9 x Drillz
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Nov 08, 2020 11:10 pm
- Post datetime: 2021-12-25T02:58:27+00:00
- Post Title: Re: Deathloop model importer

Yo Guys! whats the file/file path need if i want to unpack chracter models and textures (mainly Colt). Usuall I'd just extract and sift through everything but I thought id save myself some time and ask you man

Update: I found out which one it is. For anyone else wondering it's master_resources.index. Quick disclaimer/reminder that this ALWAYS for personal use
## Post #20
- Username: Stut29
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Apr 07, 2017 2:17 pm
- Post datetime: 2022-08-11T08:05:04+00:00
- Post Title: Re: Deathloop model importer

Hi everyone,

I'm running into an error when trying to extract some of the files using QuickBMS, for example "rsc_images_1_1.resources" and "rsc_images_2_0.resources". I run the script on "master_resources.index" and once it hits one of the problem files it says:

> Error: uncompressed data (-1) bigger than allocated buffer (43891)
>
>        It usually means that data is not compressed or uses another algorithm
>
> 
>
> Last script line before the error or that produced the error:
>
>   59  clog NAME OFFSET ZSIZE SIZE 1
>
> 
>
> - OFFSET       0x00000010
>
> - ZSIZE        0x00004394
>
> - SIZE         0x0000ab73
>
>   coverage file 0    18%   11182213   60420162   . offset 00aaa085
>
>   coverage file 1     0%   17312      526116294  . offset 000043a4

So while I can extract and import maps I get very few textures. I know nothing about this stuff so I'm unsure if this was caused by the latest patch or if I'm doing something wrong. Any help would be appreciated.

Thank you.
## Post #21
- Username: georgedevroom
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Nov 07, 2021 9:30 pm
- Post datetime: 2022-11-19T20:16:01+00:00
- Post Title: Re: Deathloop model importer

can anyone help me with getting the models? i used the deathloop.bms script on quickbms and selected master_resources but it doesn't find anything
## Post #22
- Username: ChumpyLump54
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 16, 2022 4:14 pm
- Post datetime: 2022-12-10T06:54:07+00:00
- Post Title: Re: Deathloop model importer

Hello, I've been trying to use QuickBMS to extract files from Deathloop, but I get this error:

"Error: incomplete input file 0: C:\Program Files (x86)\Steam\steamapps\common\DEATHLOOP\base\master_resources.index
       Can't read 1848903863 bytes from offset 0000000003cbf7ec.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec

Last script line before the error or that produced the error:
  25  getDString SHORT_NAME FPSTRLEN
  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec
  coverage file 1     0%   25         30020427   . offset 0000000000000000

Press ENTER or close the window to quit"

And the only thing in the output folder are a few empty folders and a single .decl file
## Post #23
- Username: whynotll83
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jan 19, 2019 4:30 pm
- Post datetime: 2022-12-25T09:58:29+00:00
- Post Title: Re: Deathloop model importer

> Reply from ChumpyLump54 ↑Sat Dec 10, 2022 2:54 pm at Sat Dec 10, 2022 2:54 pm
>
> 
Hello, I've been trying to use QuickBMS to extract files from Deathloop, but I get this error:

"Error: incomplete input file 0: C:\Program Files (x86)\Steam\steamapps\common\DEATHLOOP\base\master_resources.index
       Can't read 1848903863 bytes from offset 0000000003cbf7ec.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec

Last script line before the error or that produced the error:
  25  getDString SHORT_NAME FPSTRLEN
  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec
  coverage file 1     0%   25         30020427   . offset 0000000000000000

Press ENTER or close the window to quit"

And the only thing in the output folder are a few empty folders and a single .decl file

this is the updated code for the deathloop bms file, found it online and now I have the files. [https://zenhax.com/viewtopic.php?f=9&t= ... 640#p73640](https://zenhax.com/viewtopic.php?f=9&t=15808&p=73640#p73640)
## Post #24
- Username: ChumpyLump54
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 16, 2022 4:14 pm
- Post datetime: 2023-01-07T00:43:18+00:00
- Post Title: Re: Deathloop model importer

> Reply from whynotll83 ↑Sun Dec 25, 2022 5:58 pm at Sun Dec 25, 2022 5:58 pm
>
> 
ChumpyLump54 wrote: ↑Sat Dec 10, 2022 2:54 pm
Hello, I've been trying to use QuickBMS to extract files from Deathloop, but I get this error:

"Error: incomplete input file 0: C:\Program Files (x86)\Steam\steamapps\common\DEATHLOOP\base\master_resources.index
       Can't read 1848903863 bytes from offset 0000000003cbf7ec.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec

Last script line before the error or that produced the error:
  25  getDString SHORT_NAME FPSTRLEN
  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec
  coverage file 1     0%   25         30020427   . offset 0000000000000000

Press ENTER or close the window to quit"

And the only thing in the output folder are a few empty folders and a single .decl file


this is the updated code for the deathloop bms file, found it online and now I have the files. https://zenhax.com/viewtopic.php?f=9&t= ... 640#p73640
THANK YOU!!!
## Post #25
- Username: Cintax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 02, 2023 6:24 am
- Post datetime: 2023-07-02T20:29:27+00:00
- Post Title: Re: Deathloop model importer

> Reply from whynotll83 ↑Sun Dec 25, 2022 5:58 pm at Sun Dec 25, 2022 5:58 pm
>
> 
ChumpyLump54 wrote: ↑Sat Dec 10, 2022 2:54 pm
Hello, I've been trying to use QuickBMS to extract files from Deathloop, but I get this error:

"Error: incomplete input file 0: C:\Program Files (x86)\Steam\steamapps\common\DEATHLOOP\base\master_resources.index
       Can't read 1848903863 bytes from offset 0000000003cbf7ec.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec

Last script line before the error or that produced the error:
  25  getDString SHORT_NAME FPSTRLEN
  coverage file 0   100%   63698924   63698924   . offset 0000000003cbf7ec
  coverage file 1     0%   25         30020427   . offset 0000000000000000

Press ENTER or close the window to quit"

And the only thing in the output folder are a few empty folders and a single .decl file


this is the updated code for the deathloop bms file, found it online and now I have the files. https://zenhax.com/viewtopic.php?f=9&t= ... 640#p73640

Sorry to necro this, I'm trying to get the Strelak Verso pistols (models, textures, and hopefully animations too) out of the game and either the deathloop bms script on quickbms' website is incorrect/outdated or I'm doing it wrong.
In the case of the script being outdated, the link you've posted to the updated code is invalid unfortunately.

As for the incorrect methodology, my steps are as follows.
1) Run quickbms
2) Select the deathloop.bms script (from the quickbms site)
3) Select "master_resources.index
4) Select output location.
5) Receive error

```
       Can't read 1848903863 bytes from offset 03cbf7ec.
       Anyway don't worry, it's possible that the BMS script has been written
       to exit in this way if it's reached the end of the archive so check it
       or contact its author or verify that all the files have been extracted.
       Please check the following coverage information to know if it's ok.

  coverage file 0   100%   63698924   63698924   . offset 03cbf7ec

Last script line before the error or that produced the error:
  25  getDString SHORT_NAME FPSTRLEN
  coverage file 0   100%   63698924   63698924   . offset 03cbf7ec
  coverage file 1     0%   25         30020427   . offset 00000000 
```
