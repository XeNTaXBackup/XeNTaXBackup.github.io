## Post #1
- Username: Okapi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 07, 2015 12:00 am
- Post datetime: 2015-10-19T16:21:10+00:00
- Post Title: Atlantica Online (yet again?)

Hello,

I've seen several posts about importing Atlantica Online .nif files and [how to convert the .dds files](http://forum.xentax.com/viewtopic.php?f=18&t=3263&start=0) (done). I'm modding a game where I would need 8 directional isometric .gif files in order to import them (how to turn .nif to .gif can be a problem too, but it is possible to conver the .nif to an isometric 8 directional file seen [here](http://forums.civfanatics.com/downloads.php?do=file&id=14657) (this unit is too small)).

One of the units I would like to import is the beastmaster unit; importing beastmaster1.nif will give me [this](http://i.share.pho.to/3821c6d3_o.png) error. (beastmaster3.nif will give me an error too but the only problem there is "uknown object type etc.")

I'm using Autodesk 3Ds Max 2010 with Niftools Maxplugin 3.7.1, NifSkope, Python 3.0 and Python 2.6.

Other Nif files will be imported correctly (e.g. Ajai).

I also tried importing the .nif into Blender. I installed Python 2.6.6, Blender 2.49B, PyFFi 2.1.11 and Blender Nif Scripts 2.5.9. After that I tested importing beastermaster1, 2 or 3 but I receive this error:

```
pyffi.nif.data:ERROR:Block size check failed: corrupt nif file or bad nif.xml?
pyffi.nif.data:ERROR:Skipping 4 bytes in NiControllerManager
pyffi.nif.data:ERROR:Block size check failed: corrupt nif file or bad nif.xml?
pyffi.nif.data:ERROR:Skipping 376 bytes in NiSkinningLODController
Traceback (most recent call last):
  File "C:\Program Files (x86)\Blender Foundation\Blender\.blender\scripts\bpymo
dules\nif_common.py", line 1235, in gui_button_event
    self.gui_exit()
  File "C:\Program Files (x86)\Blender Foundation\Blender\.blender\scripts\bpymo
dules\nif_common.py", line 1598, in gui_exit
    self.callback(**self.config)
  File "C:\Program Files (x86)\Blender Foundation\Blender\.blender\scripts\impor
t\import_nif.py", line 3771, in config_callback
    importer = NifImport(**config)
  File "C:\Program Files (x86)\Blender Foundation\Blender\.blender\scripts\impor
t\import_nif.py", line 176, in __init__
    data.read(niffile)
  File "C:\Python26\lib\site-packages\pyffi\formats\nif\__init__.py", line 1382,
 in read
    "Unknown block type '%s'." % block_type)
ValueError: Unknown block type 'NiPoseBinding'.

```


Today I saw [this](https://github.com/figment/max_nif_plugin/releases) page so I tried importing the .nif files with 3DS Max 2016 but the same error occured.

If someone has any solution please let me know.

Cheers,

~Okapi
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-19T20:15:28+00:00
- Post Title: Atlantica Online (yet again?)

did you try Noesis? (plugin fmt_gamebryo_nif.py)
## Post #3
- Username: Okapi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 07, 2015 12:00 am
- Post datetime: 2015-10-20T11:04:46+00:00
- Post Title: Atlantica Online (yet again?)

Hello Shakotay2,

Thanks for your reply. Tried Noesis and there is a [start](http://i.share.pho.to/c3af2423_o.png).

Noesis won't load the tiger's .dds files; do you happen to know if there is a way to load those?

I saw there are quite a few export file types I could use; what file type would you recommend? (what is the best type to get isometric 8/16 directional .gif files?)

Cheers,

~Okapi
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-20T22:01:45+00:00
- Post Title: Atlantica Online (yet again?)

> Reply from Okapi
>
> Noesis won't load the tiger's .dds files; do you happen to know if there is a way to load those?Hello Okapi,
don't have the tiger - from the ancientgiantf1.nif I know that you can choose the 'Additional texture output' on export to get the embedded textures as dds or png files for example.

edit: well, to be honest, i didn't look at the pic you uploaded. Is this one nif: the tiger plus the girl?
Then it might be that the py plugin didn't "expect" such and needs some tweaking for this "special case".

> (what is the best type to get isometric 8/16 directional .gif files?)don't have a clue about those isometric gifs
## Post #5
- Username: Okapi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 07, 2015 12:00 am
- Post datetime: 2017-11-07T21:02:16+00:00
- Post Title: Atlantica Online (yet again?)

> Reply from shakotay2
>
> Okapi wrote:Noesis won't load the tiger's .dds files; do you happen to know if there is a way to load those?Hello Okapi,
don't have the tiger - from the ancientgiantf1.nif I know that you can choose the 'Additional texture output' on export to get the embedded textures as dds or png files for example.

edit: well, to be honest, i didn't look at the pic you uploaded. Is this one nif: the tiger plus the girl?
Then it might be that the py plugin didn't "expect" such and needs some tweaking for this "special case".

Took some time, but I'm back, whom could I contact for this tweaking you're mentioning?

Also, bump.

Best,

~Okapi
