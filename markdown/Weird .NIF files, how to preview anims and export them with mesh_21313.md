## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-30T04:16:01+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

Hello, Xentax! I've been revisiting some old formats I've messed with a couple years back but I completely forgot how to work with. I posted a thread years back on NifSkope forums, and it taught me how to preview animations within the NifSkope model viewer.

First off, I have no way of exporting the .NIF files, Noesis doesn't want to preview nor export the format. Secondly, I have no clue how to preview or extract any of the animations from the .KF files. Each .KF file contains a set of animations, so they are basically archives of animation data, similar to .psa files on Unreal Engine.

I tried Noesis, it doesn't open the files, the Nifskope model viewer works, but I can't get the animations to work like before, nor can I export anything in any other format than .OBJ, I don't know what to do.. I will upload some samples containing both meshes and animations, I will leave a link to the old thread still available on the Oddworld Forums, however as I mentioned before, the detailed thread on NifSkope Forums is gone ever since they swapped domains.



However, I forgot the process... now if you attempt to attach an animation to the skeletal mesh you would get the following error:



Here is the link to the old thread:

> http://www.oddworldforums.net/showthread.php?t=22096

Here is the link to the sample files:
https://mega.nz/#!UEQQXASa!lv6PYJa13RHg ... P_c_6JqYvw

Thank you for your time!
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-10-30T15:10:50+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

Converted Nif with some tricks. It may have been damaged because it referred to old information.
I wish I could load it correctly, but I get the error message "couldn't find the animation's root node ()".

might be can probably guess that it will be possible to load if you give proper route information, 
but in nifSkope it will be grayed out and cannot be edited. Please let me know if there is a way to fix this problem.
[scrab_basic.zip](https://xentaxbackup.github.io/file/16970_scrab_basic.zip)
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-30T15:33:01+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

> Converted Nif with some tricks. It may have been damaged because it referred to old information.
>
> I wish I could load it correctly, but I get the error message "couldn't find the animation's root node ()".
>
> 
>
> might be can probably guess that it will be possible to load if you give proper route information,
>
> but in nifSkope it will be grayed out and cannot be edited. Please let me know if there is a way to fix this problem

If I remember correctly, the process involved importing the base mesh .NIF file, then attaching the .KF animation file.
Afterwards, you had to mess around with the NiNodes, specifically the Controller section.
I can't really recall what exactly you had to alter its' value with, I think the ID of the next NiNode, so in this case, where we have "NiNode 3" with its base bone being 'scrab', we change its' controller to 4, for 'dButt'.



That's all I can really remember, I've done this a couple years ago and mostly forgot the process. I don't recall if you had to do all the associating controllers before attaching the .KF or afterwards. All I specifically remember is that you ALWAYS put the value of the next NiNode for the Controller value ). I hope this is some help to people!
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-30T22:37:02+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

Okay, I managed to get a plugin working for a very specific version of blender for importing .nif files. Skeletons work, rigging is saved, but animations are another story. 

It all loads up until a certain point and then slaps me in the face with a Python error which I can't see in the console for whatever reason. Seems like the same bad luck that I found myself up against when dealing with Oddworld: Stranger's Wrath files.

I've been told that the best course of action is to work with the Noesis plugin and alter it to support the Munch's Oddysee format for .NIF meshes and .KF animations..




I have attached the Noesis Plugin and Blender Plugins.
[fmt_gamebryo_nif.rar](https://xentaxbackup.github.io/file/16972_fmt_gamebryo_nif.rar)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-31T13:21:50+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

> Reply from Pepsee ↑Thu Oct 31, 2019 6:37 am at Thu Oct 31, 2019 6:37 am
>
> I've been told that the best course of action is to work with the Noesis plugin and alter it to support the Munch's Oddysee format for .NIF meshes and .KF animations..yeah, Noesis is a good choice for handling nifs and kfs (besides the strange fact that you have to load the .kf first. Each time I try it I stumble when loading the nif first...  , ELOA, amalan for example)

But apart from that Nif is the most flexible (translation: most annoying, same as Havok §$%&!)  3D format.
So I don't see how your proceedding should leave to an acceptable result in a timely manner. 

Thing is that your .kf files contain NiSequenceStreamHelper commands. No tools seems to have handled them ever, or correctly.
(the kfs can't be previewed with old Morrowind/Oblivion kf viewers for example)

So it's recommended to just strip out the rotation and translation data from the kf:
(sadly the NifSkope .dae export is empty, more or less, for kf files)
.



Oddworld_SW-kf.png (69.08 KiB) Viewed 356 times
## Post #6
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-10-31T16:38:19+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

Yeah, Nifskope's exports leave much to be desired.. I'm still wondering if Noesis can fully support them as you said, loading the .KF first, .NIF afterwards.
## Post #7
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-11-03T01:28:24+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

*bump* Any idea for previewing/exporting animations and the meshes as well?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-11-03T09:59:53+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

It's a shitload of work to do this for nif version 3.3.0.13 - I don't see a simple method.
(Sources for NifSkope are freely available, btw.)

Since you had a working method you should try to recall it somehow, someday (did you search in wayback archives?).

(Once I have some spare time (not this year, I guess) I could try to get a skeleton at least.)
.



getting frames from kf.png (238.1 KiB) Viewed 303 times
## Post #9
- Username: Ivan04
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 31, 2019 4:05 am
- Post datetime: 2019-11-20T00:03:55+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

Sadly wayback machine won't work.
## Post #10
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-12-07T10:07:35+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

Is there any way to get the contents of the .PAK file from the HD version?
There are very few models on the HD version, sadly, PS3 is the only workaround..

I posted the file here:
[https://mega.nz/#!ocJGmIrK!5gvpASBQX3wq ... BKIrAM4nQ0](https://mega.nz/#!ocJGmIrK!5gvpASBQX3wqNKHXTkG87nN9bm8SZ5TZeBKIrAM4nQ0)
## Post #11
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-13T22:54:15+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

If there's interest I can implement import of these anims for the blender nif plugin. It looks easy enough.
## Post #12
- Username: Ivan04
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 31, 2019 4:05 am
- Post datetime: 2019-12-14T05:54:39+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

> Reply from DMZT2 ↑Sat Dec 14, 2019 6:54 am at Sat Dec 14, 2019 6:54 am
>
> 
If there's interest I can implement import of these anims for the blender nif plugin. It looks easy enough.

Could you maybe ellaborate? the blender plugin so far doesn't import these kind of .kf files, but if the .nif has a sequence attached it works just fine when the .nif is imported.
## Post #13
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-14T09:28:33+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

I help develop the port of the plugin to blender 2.79.
[https://github.com/niftools/blender_nif_plugin](https://github.com/niftools/blender_nif_plugin)

Keyframe Controllers & Data are already supported, it is just the NiSequenceStreamHelper that's missing and that looks quite simple. It just maps bone name to controller with those extra datas.
## Post #14
- Username: Ivan04
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 31, 2019 4:05 am
- Post datetime: 2019-12-14T13:45:07+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?

> Reply from DMZT2 ↑Sat Dec 14, 2019 5:28 pm at Sat Dec 14, 2019 5:28 pm
>
> 
I help develop the port of the plugin to blender 2.79.
https://github.com/niftools/blender_nif_plugin

Keyframe Controllers & Data are already supported, it is just the NiSequenceStreamHelper that's missing and that looks quite simple. It just maps bone name to controller with those extra datas.

Oh it would be awesome if you did that.
## Post #15
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-14T17:18:25+00:00
- Post Title: Weird .NIF files, how to preview anims and export them with mesh?


## Post #16
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-12-14T18:47:55+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

> Reply from DMZT2 ↑Sun Dec 15, 2019 1:18 am at Sun Dec 15, 2019 1:18 am
>
> 

HOLY MOTHER OF ALL THINGS HOLY..
I was not expecting such a lovely surprise. Finally the slow import process can be put to rest.
Where can I find this?
## Post #17
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-14T19:12:35+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

code is here:

[https://github.com/HENDRIX-ZT2/blender_nif_plugin](https://github.com/HENDRIX-ZT2/blender_nif_plugin)

for blender 2.79
needs pyffi 2.2.4.dev3 to be installed in blender's bundled python (see pyffi installation instructions here: [https://github.com/OpenNaja/cobra-blender](https://github.com/OpenNaja/cobra-blender) )

zip up the io_scene_nif folder and install via blender plugin installer
mesh needs to be imported with "Apply Skin Deformation" checked
Anims have no names.
## Post #18
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-12-14T20:41:33+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

> Reply from DMZT2 ↑Sun Dec 15, 2019 3:12 am at Sun Dec 15, 2019 3:12 am
>
> 
code is here:

https://github.com/HENDRIX-ZT2/blender_nif_plugin

for blender 2.79
needs pyffi 2.2.4.dev3 to be installed in blender's bundled python (see pyffi installation instructions here: https://github.com/OpenNaja/cobra-blender )

zip up the io_scene_nif folder and install via blender plugin installer
mesh needs to be imported with "Apply Skin Deformation" checked
Anims have no names.

I'm getting stuck on the pyffi part, it just doesn't seem to install for me at all...
## Post #19
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-14T21:04:15+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

Copy of pyffi:
[https://we.tl/t-CLuGOfMfIr](https://we.tl/t-CLuGOfMfIr)

Put the pyffi folder from inside the zip into C:\Program Files\Blender Foundation\blender-2.79b-windows64\2.79\python\lib\site-packages
or whereever your blender's python lives.
## Post #20
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-12-14T21:28:40+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

> Reply from DMZT2 ↑Sun Dec 15, 2019 5:04 am at Sun Dec 15, 2019 5:04 am
>
> 
Copy of pyffi:
https://we.tl/t-CLuGOfMfIr

Put the pyffi folder from inside the zip into C:\Program Files\Blender Foundation\blender-2.79b-windows64\2.79\python\lib\site-packages
or whereever your blender's python lives.

It's importing properly now, but how do I swap between different animations within a .KF? I get no GUI pop-up, everything imports directly, I don't have any selection of what animation to import.
## Post #21
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-14T21:38:09+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

All anims are imported as blender actions, use the action editor when the armature is selected to switch between them.
## Post #22
- Username: Ivan04
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Oct 31, 2019 4:05 am
- Post datetime: 2019-12-14T22:14:08+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

Thank you so much for this
## Post #23
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-12-15T17:12:19+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

> Reply from DMZT2 ↑Sun Dec 15, 2019 5:38 am at Sun Dec 15, 2019 5:38 am
>
> 
All anims are imported as blender actions, use the action editor when the armature is selected to switch between them.

The plugin did wonders.. I just have to ask why is the Snoozer so buggy? It won't import at all, it even throws up errors when simply imported in NifSkope.. Any clue?
## Post #24
- Username: DMZT2
- Rank: beginner
- Number of posts: 32
- Joined date: Thu Nov 21, 2019 10:48 pm
- Post datetime: 2019-12-15T20:52:35+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

Can't find a snoozer nif in the samples I was sent? Might be corrupted? If nifskope doesn't read it probably has some custom data modification.
## Post #25
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-12-15T21:07:44+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

I managed to get it, PS3 files has a functional version of the OG model. Only problem is textures in .PS3 format:
[https://mega.nz/#!VQQzFKSS!8FrAhV28-mU0 ... 2W_LkaSpJU](https://mega.nz/#!VQQzFKSS!8FrAhV28-mU0KrLj89d7EF4ILhwneaXls2W_LkaSpJU)
I have no idea how to convert them..
## Post #26
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2019-12-16T20:06:22+00:00
- Post Title: Re: Weird .NIF files, how to preview anims and export them with mesh?

I tried converting the textures with everything I had: photoshop, dds to png converters, etc. I've never encountered this format before.
