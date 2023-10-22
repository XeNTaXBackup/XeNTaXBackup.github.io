## Post #1
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-04-03T09:14:09+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

Tools for batch unpacking models and textures Assassin Creed Origins (Odyssey)

Supports:
	Geometry
	Multiple UV
	Textures

Do not support:
	Skin
	Animations

Using:

1. Edit the unpacker_forge.py script:
	In line 9, specify the path to the game directory
		path_Directory = 'G:\\SteamLibrary\\steamapps\\common\\Assassins Creed Odyssey' 

	In line 19, specify the path to quickbms_4gb_files.exe
		The string should look like
		str__ = '\"G:\\quickbms\\quickbms_4gb_files.exe\" -K -d '

	In line 20, specify the path to the script AC_O_Odyssey_UPD2a.bms
		The string should look like
		str__ = str__ + '\"G:\\SteamLibrary\\steamapps\\acu\\AC_O_Odyssey_UPD2a.bms\"  '

	Execute the script. It will unpack the forge game archives

2. Edit the unpacker_forge.py script:
	You need strings
	game = "acod" # for AssassinsCreedOrigins - "acor", AssassinsCreedOdyssey "acod". Defines the format of the generated files.
	input_path = 'G:\\SteamLibrary\\steamapps\\common\\sorted_all' # path to folder with raw files
	output_path = 'G:\\AssassinsCreedOdyseyUNP' # - path to folder for unpacked files
	bms_binary_path = 'G:\\quickbms\\quickbms_4gb_files.exe'
	script_path =  'G:\\SteamLibrary\\steamapps\\acu\\assassin_creed_raw.bms'
	export_without_sort = False # If you want to disable file sorting (unzip all), enter True
	export_mesh = True
	export_textures = False
	replase_files = False # (if False - if the names match, the files will be renamed, if True - replaced)

	If export_without_sort = False, you can edit the sort_mesh and sort_tex functions to select the necessary files

After execution, the script will unpack the raw files obtained in the previous step. Also, some files will be joined.
Now you can copy scripts from noesis_plugins to "noesisv\plugins\python" and work with the resulting files.

UPDATE: 
2020.04.15
-    add parametr for additional unpack some files
-    change folder names


Good luck!



Credits:

Aluigi ([http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)) 
	- for QuickBMS and assassin_creed_raw.bms script


Zaramot  ([memberlist.php?mode=viewprofile&u=32230](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=32230))
	- for AC_O_Odyssey_UPD2a.bms script


Pineapples721 ([memberlist.php?mode=viewprofile&u=65770](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=65770) ,   [http://t-poses.com/bs/](http://t-poses.com/bs/))
	- for some hints about file formats


Rich Whitehouse ([https://richwhitehouse.com/index.php?co ... ojects.php](https://richwhitehouse.com/index.php?content=inc_projects.php))
	- for Noesis
[ACO_2.7z](https://xentaxbackup.github.io/file/17932_ACO_2.7z)
## Post #2
- Username: ubifan1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 28, 2020 8:19 pm
- Post datetime: 2020-04-11T23:13:34+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

Hi! Could you make video how to use these scripts? I tried with cmd and python.exe but always got: "end of dds creating"
## Post #3
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-04-15T18:33:30+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

You need edit script, watch first post in thread. Use "\\" for separating folders (as in example 'G:\\SteamLibrary\\steamapps\\common\\1'   )
Next in command line:
python.exe  path_to_script.py
## Post #4
- Username: nonamebatbai
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Sep 22, 2019 10:32 am
- Post datetime: 2020-05-01T16:21:23+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

Can you find and edit the font file of the assassin's creed origins game?
## Post #5
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-09T12:39:17+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

Test tool for unpacking Valhalla' s forge  with names support .

1. You must unpack the *.forge using AC_Valhalla_v001t
It will create a bunch of raw files without names.
You can use unpacker_forge.py for batch processing.
Don't forget to edit the paths in the script itself!

2. You must use unpacker_Valhalla_raw.py.
Script create filenames and sort it by magic number (type of file)

Edit
input_path = 'C: \\ my_programs \\ acv \\ DataPC_ACK_Asgard.forgefolder'
output_path = 'C: \\ my_programs \\ acv \\ 3'
bms_binary_path = 'C: \\ my_programs \\ acv \\ quickbms \\ quickbms_4gb_files.exe'
script_path = 'C: \\ my_programs \\ acv \\ assassin_creed_raw.bms'

input_path - unpacked forge's folder with raw files
output_path - folder to save files
bms_binary_path - path to quickbms_4gb_files.exe
script_path - path to assassin_creed_raw.bms

Run it!
Enjoy!
[acv.zip](https://xentaxbackup.github.io/file/18999_acv.zip)
## Post #6
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-09T12:40:35+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

to previous post
[test.jpg](https://xentaxbackup.github.io/file/19000_test.jpg)
## Post #7
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2020-11-09T16:31:38+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

work noesis plugins (fmt_acod2 & fmt_acor8) with the extracted files?
## Post #8
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-09T17:18:23+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

No, format changed.
## Post #9
- Username: Lord Vaako
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Jul 15, 2013 5:28 am
- Post datetime: 2020-11-10T10:53:51+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

Does the attached file contain texture? If so, could someone share information on how to extract it?
[ACD_UI_MENU_ResourceMat_Metal_MapDesc.zip](https://xentaxbackup.github.io/file/19003_ACD_UI_MENU_ResourceMat_Metal_MapDesc.zip)
## Post #10
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-10T11:13:09+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

Now, as far as I know, in no way.
We need to research the format and write plugins.
## Post #11
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-11T13:35:06+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

Trying geometry research  
[123.png](https://xentaxbackup.github.io/file/19016_123.png)
## Post #12
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-11-11T18:17:25+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

I'm trying the extract meshes from .raw files for Oddesy, but the python script just closes immediately without giving an error. Could someone tell me what the problem is? thanks, 


import subprocess

import struct
import os
import shutil
import datetime


array_tex=[]


game = "acod" # for AssassinsCreedOrigins -  "acor", AssassinsCreedOdyssey "acod"
input_path = 'E:\\FakeACOInstall'
output_path = 'E:\\ACODump'
bms_binary_path = 'D:\\QuickBMS\\quickbms_4gb_files.exe'
script_path =  'D:\\ACOUnpacker\\assassin_creed_raw.bms'
export_without_sort = False
export_mesh = 	True
export_textures = False

export_addon = True
addon_dirs = ["1096652136"]


replase_files = False


def sort_mesh(path_and_file):
	path, file = os.path.split(path_and_file)
	if(file.lower().startswith("acd_ch")): return True
	return False
	if(file.find("(") >= 0): return False
	if(file.lower().find("lod0") >= 0): return True
	if(file.lower().find("lod") >= 0): return False
	return True

def sort_tex(path_and_file):
	path, file = os.path.split(path_and_file)
	if(file.find("(") >= 0): return False
	return True



def sort_addon(path_and_file):
	path, file = os.path.split(path_and_file)
	return True
## Post #13
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-12T04:29:21+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

try run cmd or powershell and enter the path to python and the path to the script there.
like here 
C:\Python\Python38\python.exe D:\acv\unpacker_raw.py
## Post #14
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-11-14T21:47:45+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

> Reply from erik945 ↑Thu Nov 12, 2020 12:29 pm at Thu Nov 12, 2020 12:29 pm
>
> 
try run cmd or powershell and enter the path to python and the path to the script there.
like here 
C:\Python\Python38\python.exe D:\acv\unpacker_raw.py

Thanks, I think that worked. The only problem is, when I try to import the Hair mesh of Kassandra, the UV's of the hair strands are messed up.
## Post #15
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2020-11-17T14:23:00+00:00
- Post Title: Assassin Creed (Origins / Odyssey / Valhalla) batch tool

> Reply from erik945 ↑Wed Nov 11, 2020 9:35 pm at Wed Nov 11, 2020 9:35 pm
>
> 
Trying geometry research
Awesome!!!
## Post #16
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-20T05:39:17+00:00
- Post Title: Re: Assassin Creed Origins (Odyssey) batch tool

Test release of the script for Noesis.

You need use acvlh_texture_joiner.py for join parts of textures to one files.
Edit input_path - unpacked "2729961751" folder, output_path - folder for save joined files, and run it.

Works:

-Many models (not all!). Among them are most of the weapons and animals.

-Two UV channels. There is often trash in one of them. Check both.

-Textures



Does not work:

-Some models

-Bones / Skin.

Upsate 23.11.2020
- Add support textures

Upsate 24.11.2020
- Updte support textures



img2.png (59.41 KiB) Viewed 438 times
## Post #17
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-11-20T05:39:43+00:00
- Post Title: Re: Assassin Creed Origins (Odyssey) batch tool

Script
[fmt_acVlh07.7z](https://xentaxbackup.github.io/file/19077_fmt_acVlh07.7z)
## Post #18
- Username: DarthphoeniX
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Nov 06, 2015 11:10 pm
- Post datetime: 2021-03-29T20:27:57+00:00
- Post Title: Re: Assassin Creed Origins (Odyssey) batch tool

thanks for the tool erik945! is there any progress in the script to support all models?
## Post #19
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2021-06-17T22:16:34+00:00
- Post Title: Re: Assassin Creed Origins (Odyssey) batch tool

> Reply from gep55 ↑Sun Nov 15, 2020 5:47 am at Sun Nov 15, 2020 5:47 am
>
> 
erik945 wrote: ↑Thu Nov 12, 2020 12:29 pm
try run cmd or powershell and enter the path to python and the path to the script there.
like here 
C:\Python\Python38\python.exe D:\acv\unpacker_raw.py


Thanks, I think that worked. The only problem is, when I try to import the Hair mesh of Kassandra, the UV's of the hair strands are messed up.

Ok, I still haven't managed to fix the hair UVs, but I think I know what the cause is.

If you extract Kassandra's LOD1 hair model, the UV's are fine. It is only the LOD0 model which has broken UVs. I believe this is because whereas the LOD1 model is all one mesh, the LOD0 model is split into multiple objects/meshes.

Hope this helps
## Post #20
- Username: urao
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Oct 29, 2016 9:14 pm
- Post datetime: 2022-01-19T08:11:14+00:00
- Post Title: Re: Assassin Creed Origins (Odyssey) batch tool

Hi,
I have a lot of .acvlhtex files and ACK_Asgard.acvlh_4223024711 for example.
Can you tell me how i can open the textures and mesh of Valhalla format, pls?
Thanks in advance
## Post #21
- Username: pepapoha
- Rank: n00b
- Number of posts: 16
- Joined date: Wed May 20, 2020 9:49 pm
- Post datetime: 2023-05-28T16:42:36+00:00
- Post Title: Re: Assassin Creed Origins (Odyssey) batch tool

hey guys any have assasin creed origin map models and texture link?
