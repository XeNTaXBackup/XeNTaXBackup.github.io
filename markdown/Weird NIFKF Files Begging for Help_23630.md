## Post #1
- Username: blamie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 25, 2021 6:28 am
- Post datetime: 2021-03-24T22:40:00+00:00
- Post Title: Weird NIF/KF Files Begging for Help

I want to remake a game in another engine. I was able to get the animations file.
I have a Nif File , KF File and KFM file.
I tried Noesis and i can see the animations but export is all messed up.
I tried NifSkope and no luck it says "this is not a normal .kf file; there should be only NiControllerSequences as root blocks"
I can see the individuals animation Names and the blocks if i open the kf file alone.
I Also tried nif blender addon it says "pyffi.nif.data :block size check failed corrupt nif file or bad nif.xml"

Losing my mind   

What i want is to get them individually to import them into the engine.
Is it possible?

Screenshots of Noesis and NifSkope: [https://imgur.com/a/5Xs4M4d](https://imgur.com/a/5Xs4M4d)

The files of the animations :[https://www.dropbox.com/s/ag3ze8rj6x2ct ... n.rar?dl=0](https://www.dropbox.com/s/ag3ze8rj6x2ctma/Animation.rar?dl=0)

Thank you for your time   .
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-25T00:03:42+00:00
- Post Title: Weird NIF/KF Files Begging for Help

hmm, on importing kf/nif Noesis says: "unsupported rot key type: 3"

I exported as md5anim (from preview) then re-exported that and exported as fbx.
That fbx is loadable into Noesis (animated skeleton, without mesh, though).

So that binary fbx (33.5 MB) might be loadable into other 3D tools.
.



md5anim_fbx.png (28.62 KiB) Viewed 73 times


(Attaching the mesh now is another problem.)
## Post #3
- Username: blamie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 25, 2021 6:28 am
- Post datetime: 2021-03-25T00:20:14+00:00
- Post Title: Weird NIF/KF Files Begging for Help

I just tried ur approach and if u load the KF and then noesis asks for the nif and u select it. The mesh is with the animations.

If i export it it gives me a HUGE FBX file with all the animations on the time line (20000 frames MY BLENDER is crying).
Ur aproach gives the same result but without mesh. Thank you very much just for trying, Seriously for the bottom of my Heart ty

I just tried -fbxmultitake(	export a take for each anim sequence.) BUT the Noesis Crashes.

Is There way just to export some animations?
Or just see why noesis crashed?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-25T09:51:14+00:00
- Post Title: Weird NIF/KF Files Begging for Help

> Reply from blamie ↑Thu Mar 25, 2021 8:20 am at Thu Mar 25, 2021 8:20 am
>
> Thank you very much just for trying, Seriously for the bottom of my Heart tyYour welcome - glad, if I could help a little bit.  

> I just tried -fbxmultitake(export a take for each anim sequence.) BUT the Noesis Crashes.To be honest, I never understood that parameter.

> Is There way just to export some animations?You exported, didn't you? you mean, import to Blender?
You could do a binary2ASCII conversion on the fbx file (using Autodesk FBX converter for free, iirc).
Then cut a 1000 frames from the converted fbx file (but keep it's structure).

> Or just see why noesis crashed?Check the underlying script (should be fmt_gamebryo_nif.py), put some print lines 
to see where the crash occurs (some rough understanding of the script is required).

(If Noesis doesn't show the Debug Log window add noesis.logPopup() to the script.)

(But the treating of the animation part might be hidden in noesis.dll, iirc.)
