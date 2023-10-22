## Post #1
- Username: anhhungmeo1234
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Aug 15, 2010 4:48 pm
- Post datetime: 2011-04-05T04:39:23+00:00
- Post Title: Heroes of Newerth game model

hey. I extracted recouse.s2z. In folder there are many hero's folder.Model file is .model and animation is .clip
Who can import it into 3dsmax 2011.
## Post #2
- Username: VILE
- Rank: advanced
- Number of posts: 46
- Joined date: Wed Mar 02, 2011 4:28 pm
- Post datetime: 2011-04-05T10:04:21+00:00
- Post Title: Heroes of Newerth game model

I have extracted these models before, from what I remember it was fairly easy. All the info was pretty easy to find, just google it.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-05T12:06:03+00:00
- Post Title: Heroes of Newerth game model

there are already blender scripts for import and export of this format.
## Post #4
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-04-06T20:30:39+00:00
- Post Title: Heroes of Newerth game model

> Reply from anhhungmeo1234
>
> hey. I extracted recouse.s2z. In folder there are many hero's folder.Model file is .model and animation is .clip
Who can import it into 3dsmax 2011.
if i remember correctly, there is oficial import plugin on HoN forums
## Post #5
- Username: anhhungmeo1234
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Aug 15, 2010 4:48 pm
- Post datetime: 2011-04-07T13:49:48+00:00
- Post Title: Heroes of Newerth game model

Hey chroxx, can you convert .blend to .max. I want to import model HoN to Starcraft II but  i can't import model HoN by 3Ds Max.Can you write scripts import .clip for 3ds max
## Post #6
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-04-07T15:29:44+00:00
- Post Title: Heroes of Newerth game model

If you can import to blender you can probably save it as a fbx or something and open up in max with bones, animations etc.

There shouldnt be needed with a script for this
## Post #7
- Username: anhhungmeo1234
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Aug 15, 2010 4:48 pm
- Post datetime: 2011-04-09T03:38:53+00:00
- Post Title: Heroes of Newerth game model

I tried export .FBX and import into 3ds max, but only the bone, no mesh, no animation
## Post #8
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2011-04-09T12:41:46+00:00
- Post Title: Heroes of Newerth game model

> Reply from anhhungmeo1234
>
> I tried export .FBX and import into 3ds max, but only the bone, no mesh, no animation

FBX and DAE export plugins in blender are really buggy, but i think that in your situation, you did something wrong in FBX export preferences. As i remeber, default settings of blender FBX plugin, are to export "Selected Objects", so you must select all the objects that you want to export or set the option "Scene Objects" instead.
There are also some tricks in Max FBX importer - you can "convert skeleton to dummy" or "Leave as bones"..so try to play with some options, but as i say it's still buggy and sometimes happens that some things imports wrong...for example weights or some animation keys.

Sorry for my english.
## Post #9
- Username: anhhungmeo1234
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Aug 15, 2010 4:48 pm
- Post datetime: 2011-04-10T08:09:59+00:00
- Post Title: Heroes of Newerth game model

How to use k2 scrips of blender to import all animation ?
## Post #10
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-03-27T20:58:25+00:00
- Post Title: Heroes of Newerth game model

Hello,

I know this is an verry old topic but I would like to ask some questions in the hope someone could answer them.

There is an import script for importing models/animations from the HoN game into the newest version of Blender and it works for most of the models but there are quite a lot that have some weighting problems (mesh deformation) i guess when importing an animation after I imported the mesh. I was hoping if there is someone who is able to take a look at the import script in the hope he/she could find some buggy code or something.

This is the import script:   [https://ufile.io/7p9hy](https://ufile.io/7p9hy)

And here are some game assets samples. I put everything into on zip file.  [https://ufile.io/dfxis](https://ufile.io/dfxis)
Models are named (.model) file
Anim are named (.clip) file

INstall the python files and please try it out, first import the .model an then import the .clip file while selecting the armature.
HOpefully someone is willing to take a look and maybe provide an update for the script or an solution within Blender itself.

Thanks in advance,

PS: Im willing to pay for an updated import script!
## Post #11
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-04-12T16:14:22+00:00
- Post Title: Heroes of Newerth game model

Is there someone who can help me out?
## Post #12
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-03-21T18:55:34+00:00
- Post Title: Heroes of Newerth game model

Anyone?
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-22T12:08:25+00:00
- Post Title: Heroes of Newerth game model

The links in your post as of Tue Mar 27, 2018 9:58 pm are 404 ("File not found").
## Post #14
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-03-22T21:39:34+00:00
- Post Title: Heroes of Newerth game model

Here is an updated link for the Blender import scripts:
[https://mega.nz/#F!2Js2TQ5C!UJTdKLSy6cEGx7VFza4t5w](https://mega.nz/#F!2Js2TQ5C!UJTdKLSy6cEGx7VFza4t5w)

!DOESN'T WORK!  High poly (.model) file with armature and the idle/walk (.clip) animations.
[https://mega.nz/#F!6YswTSKT!n93sh24GwTM7pQrzyWcTaQ](https://mega.nz/#F!6YswTSKT!n93sh24GwTM7pQrzyWcTaQ)

!WORKS!  High poly (.model file with armature and the idle/walk (.clip) animations.
[https://mega.nz/#F!bVlQ1CYT!HcRigqoDE_m9jnhA-Futwg](https://mega.nz/#F!bVlQ1CYT!HcRigqoDE_m9jnhA-Futwg)

Video showing the deformed mesh after importing the .clip animation file:
[https://1drv.ms/v/s!Aoui6UbDlycfga1PBi2UAGBr9CUynA](https://1drv.ms/v/s!Aoui6UbDlycfga1PBi2UAGBr9CUynA)

Hope you can update the scrips.

Thanks in advance,
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-22T22:57:12+00:00
- Post Title: Heroes of Newerth game model

With Blender 2.75 I get an "IndexError: list index out of range" for all four clip files.

(ok, you need to select the bones before you can import a clip file)

Well, see, Chi's breast is wrapped, very strange. Need to log the weights, but this doesn't seem to be easy to be solved because the rest of the bodiy looks ok.

maybe it's a matter of missing bones:

version: 2
num bones: 130
num frames: 33
Bip02 Footsteps not found in armature
Bone007 not found in armature
Bone016 not found in armature
Bone021 not found in armature
Bone027 not found in armature
Bip01 Footsteps not found in armature
Bone024 not found in armature
Bone003 not found in armature
Bone029 not found in armature
Bone018 not found in armature
## Post #16
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-03-22T23:13:21+00:00
- Post Title: Re: Heroes of Newerth game model

Do you think you can fix it in the end? I really hope you can as i'm stuck with this particular issue for quite some time and I would really appreciate it if you eventually can get it to work proparly.

And yes the issue always occurs in the breast part of the model, I always knew it was a weighting issue but i was unable to fix it myself.

Thanks for taking the time to look at this
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-23T13:33:44+00:00
- Post Title: Re: Heroes of Newerth game model

The skinning from the model file looks ok to me:



Chi Spine1_Spine2.jpg (114.85 KiB) Viewed 81 times


We'd need to understand why the clip files cause troubles around Bip01 Spine 2.

Animation data (motion[10]) is like so:
Translation: MKEY_X, MKEY_Y, MKEY_Z
Rotation: MKEY_PITCH, MKEY_ROLL, MKEY_YAW
MKEY_VISIBILITY
Scale: MKEY_SCALE_X, MKEY_SCALE_Y, MKEY_SCALE_Z

for Chi, spine 2 it looks like so:
```
1: [-0.0058956146240234375], 
2: [0.0009686946868896484, 0.001024007797241211, 0.0010755062103271484, 0.0011289119720458984, 0.0011882781982421875, 0.0012481212615966797, 0.0012981891632080078, 0.0013318061828613281, 0.0013422966003417969, 0.0013284683227539062, 0.001300811767578125, 0.0012612342834472656, 0.00121307373046875, 0.0011601448059082031, 0.00110626220703125, 0.0010538101196289062, 0.001007080078125, 0.0009593963623046875, 0.0009059906005859375, 0.0008497238159179688, 0.0007929801940917969, 0.0007405281066894531, 0.0006947517395019531, 0.0006608963012695312, 0.0006403923034667969, 0.0006434917449951172, 0.0006704330444335938, 0.0007143020629882812, 0.0007660388946533203, 0.0008195638656616211, 0.0008661746978759766, 0.00091552734375, 0.0009686946868896484], 
```
There's 33 floats for MKEY_X (motion[0]) for example (for 33 frames) but only the frame 0 value for MKEY_Y.
Might cause the problem (or tells that y is constant for the following frames?)
## Post #18
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-03-24T11:43:03+00:00
- Post Title: Re: Heroes of Newerth game model

As shown on the picture you are clearly making progress, so it's not a skinning issue but the main problem is in the .clip files importer? Does this mean you have find out the root of the problem? If so... I really hope you could make an updated version of the script, if you have some spare time.

You really got my hopes up,
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-24T13:29:33+00:00
- Post Title: Re: Heroes of Newerth game model

> Reply from WollieWoltaz ↑Sun Mar 24, 2019 7:43 pm at Sun Mar 24, 2019 7:43 pm
>
> I really hope you could make an updated version of the script, if you have some spare time.That would take ages for me but I accidentally found a workaround when trying to get deeper insights what is happening when exporting the K2 mesh to IQM (Inter-Quake model):



Chi moving.png (89.94 KiB) Viewed 64 times



These are the scripts I used: iqm_export.py and iqe_import.py (the latter does import IQM, too)

```
    "author": "Lee Salzman",
    "version": (2019, 2, 3),
    "blender": (2, 74, 0),
```


```
	"description": "Import Inter-Quake Model.",
	"author": "Tor Andersson",
	"version": (2012, 12, 2),
	"blender": (2, 80, 0),
	"location": "File > Import > Inter-Quake Model",
	"wiki_url": "http://github.com/ccxvii/asstools",
	"category": "Import-Export",
```


After installing the above mentioned scripts I
selected Chi's mesh, exported to IQM
deleted the mesh
(re) imported the IQM
selected pose in outliner window

imported K2 clip file
done
## Post #20
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-03-24T13:54:31+00:00
- Post Title: Re: Heroes of Newerth game model

Could you provide a video of the whole process? As I'm not quite sure how to install the scripts and do the steps you provided.

Final request,
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-03-24T14:11:12+00:00
- Post Title: Re: Heroes of Newerth game model

copy the scripts into blenders scripts/addons sub directory then in user preferences window type 'iq' for search.
highlight "community bar" at the left
said script lines should pop up, check the boxes at the right



blender-IQM.png (36.07 KiB) Viewed 54 times



btw: path depends on path_to_script (forgot where to set it), usually:
C:\Users\yourAccount\AppData\Roaming\Blender Foundation\Blender\2.75\scripts\addons
(replace 2.75 by your version of blender)
## Post #22
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2019-03-24T15:09:55+00:00
- Post Title: Re: Heroes of Newerth game model

The scripts don't show up??
