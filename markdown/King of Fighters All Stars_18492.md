## Post #1
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-07-25T15:59:43+00:00
- Post Title: King of Fighters All Stars

Managed to rip the models of the new KOF game for phones using the usual Unity Studio method.

Because you're allowed to download every files once you open the game, this means you can basically just
run the app once, ask for it to DL all the data and rip it without much trouble, which is nice considering how the big part
of these games actually download one specific file once you get them through the gacha and you need to actually download
everything by hand making it a more tedious thing to do.

The model files include the default HD version and also the LQ one (which I'm assuming is used for long distance shots)
both merged in the same mesh file, so if you don't want the LQ one you can just download that part of the mesh.

One thing that's sad for me is that the models only seem to have face bones for the eyes, which means the face animations
are probably animated by messing with the mesh itself rather than by having a face rig. I don't know how to extract animations
from Unity games, so it would be great if someone who's also interested in this game could help. I'm sharing Geese's mesh, animations
and also something called prefabs (which I don't know what those files are supposed to be or if they're important at all) so you guys
can mess with them and see if you can figure out how to extract the animations and import them into Blender/3DS/whatever.

Download Geese's Files
## Post #2
- Username: BobDope
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 22, 2011 5:56 pm
- Post datetime: 2018-07-28T14:58:51+00:00
- Post Title: King of Fighters All Stars

That's cool (and quick).

I got hold of the files, but can't seem to get the model from the mesh-file, even using Unity Studio 0.5.0.0

Is there somewhere, I can find a run-down of "the usual Unity Studio method"? (I'm a noob, i know).

Thank you.
## Post #3
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-07-28T19:43:53+00:00
- Post Title: King of Fighters All Stars

> Reply from BobDope
>
> That's cool (and quick).

I got hold of the files, but can't seem to get the model from the mesh-file, even using Unity Studio 0.5.0.0

Is there somewhere, I can find a run-down of "the usual Unity Studio method"? (I'm a noob, i know).

Thank you.
Yeah, I've been waiting for this game since there's a lack of KOF models available,
and since I know how to rip Unity models this was the best chance to get some so I didn't waste any time!   

Is simple, you just open Unity Studio, load the Unity3d file (the model one, since iirc the animation files don't work in Unity Studio)
and then you just mark the square of (in this case) Geese's model files and then in 3d model just export all 3d objects (split).
It should export the model's meshes in a .fbx file with the in-game rig (it is pretty basic for the face tho since it seems the facial animations
are stored in the actual animation.unity3d file, and I don't know how to export those to use in blender yet).
Once you have the .fbx file, then its up to you & your fav method you like to use to port the model to whatever software (Blender, Maya, SFM, MMD...) you plan to use it.
That's the basic run-down I do and it works for basically every game I've tried it with. Hopefully it works for you too.
## Post #4
- Username: BobDope
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 22, 2011 5:56 pm
- Post datetime: 2018-07-29T07:41:03+00:00
- Post Title: King of Fighters All Stars

Thanks for the reply

What version of Unity Studio are you using?

I'm using 0.5.0.0 and can't get it to do it.

First off, I can't load the mesh-files in it, unless i rename the file *.assets
I click the check-box, go to export -> All 3D objects (or Selected 3D objects), give the .fbx-file a name and get an error, resulting in a 2kb .fbx-file and nothing more.
## Post #5
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-07-29T20:04:39+00:00
- Post Title: King of Fighters All Stars

> Reply from BobDope
>
> Thanks for the reply

What version of Unity Studio are you using?

I'm using 0.5.0.0 and can't get it to do it.

First off, I can't load the mesh-files in it, unless i rename the file *.assets
I click the check-box, go to export -> All 3D objects (or Selected 3D objects), give the .fbx-file a name and get an error, resulting in a 2kb .fbx-file and nothing more.
I'm using version 0.9.0.22 so maybe that's where you have the problem, since I can load .unity3d files with no problem.
Try again with a newer version and see if it works.
## Post #6
- Username: BobDope
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Dec 22, 2011 5:56 pm
- Post datetime: 2018-07-30T05:20:18+00:00
- Post Title: King of Fighters All Stars

That did the trick - thank you for the help!
## Post #7
- Username: ratonmalo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 23, 2010 10:46 pm
- Post datetime: 2018-08-01T00:12:56+00:00
- Post Title: King of Fighters All Stars

Hi, In what folder are the mesh files? 

In this one?
com.netmarble.kof\files\assetbundles 

thanks
## Post #8
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-08-01T20:32:18+00:00
- Post Title: King of Fighters All Stars

> Reply from ratonmalo
>
> Hi, In what folder are the mesh files? 

In this one?
com.netmarble.kof\files\assetbundles 

thanks
Yeah, if I recall correctly, that's the directory (can't confirm because I don't remember clearly and I can't check it at the moment, but I'm 90% sure that was the folder).

> Reply from BobDope
>
> That did the trick - thank you for the help!
You're welcome!
## Post #9
- Username: lurenx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 13, 2017 9:37 am
- Post datetime: 2018-09-20T01:17:14+00:00
- Post Title: King of Fighters All Stars

for animiation I got it working with AssestStudio
[https://github.com/Perfare/AssetStudio/releases](https://github.com/Perfare/AssetStudio/releases)
the anmiations are saved in a different source file. If you load them together in AssetStudio you will be able to view the model with animation in Noesis.

I found that the exported model only has the normal map. 
I was able to export as FBX, then use the Autodesk FBX tool to convert it to FBX2013, then everything can be loaded into Blender correctly. The diffuse maps need to be updated manually.
Somehow 3dsmax cannot load the files correctly.

The only issue I have is that the facial expression does not seem to import to blender.
I found that they are imported as shape keys but not loaded to the model animation directly.
## Post #10
- Username: iehaiel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 01, 2019 2:42 pm
- Post datetime: 2019-04-20T15:18:27+00:00
- Post Title: King of Fighters All Stars

> Reply from lurenx ↑Thu Sep 20, 2018 9:17 am at Thu Sep 20, 2018 9:17 am
>
> 
for animiation I got it working with AssestStudio
https://github.com/Perfare/AssetStudio/releases
the anmiations are saved in a different source file. If you load them together in AssetStudio you will be able to view the model with animation in Noesis.

I found that the exported model only has the normal map. 
I was able to export as FBX, then use the Autodesk FBX tool to convert it to FBX2013, then everything can be loaded into Blender correctly. The diffuse maps need to be updated manually.
Somehow 3dsmax cannot load the files correctly.

The only issue I have is that the facial expression does not seem to import to blender.
I found that they are imported as shape keys but not loaded to the model animation directly.

Thanks for sharing this tool, it has helped me a lot, I have problems in making animations work, could you explain me better how to do it?
## Post #11
- Username: zhang123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 26, 2018 1:55 pm
- Post datetime: 2019-05-01T03:47:41+00:00
- Post Title: King of Fighters All Stars

> Reply from iehaiel ↑Sat Apr 20, 2019 11:18 pm at Sat Apr 20, 2019 11:18 pm
>
> 
lurenx wrote: ↑Thu Sep 20, 2018 9:17 am
for animiation I got it working with AssestStudio
https://github.com/Perfare/AssetStudio/releases
the anmiations are saved in a different source file. If you load them together in AssetStudio you will be able to view the model with animation in Noesis.

I found that the exported model only has the normal map. 
I was able to export as FBX, then use the Autodesk FBX tool to convert it to FBX2013, then everything can be loaded into Blender correctly. The diffuse maps need to be updated manually.
Somehow 3dsmax cannot load the files correctly.

The only issue I have is that the facial expression does not seem to import to blender.
I found that they are imported as shape keys but not loaded to the model animation directly.


Thanks for sharing this tool, it has helped me a lot, I have problems in making animations work, could you explain me better how to do it?

1,select the model in Scene Hierarchy
2,select an AnimationClip in Asset list
3,use Model/Export selected objects with AnimationClip
## Post #12
- Username: iehaiel
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Apr 01, 2019 2:42 pm
- Post datetime: 2019-05-04T17:36:49+00:00
- Post Title: King of Fighters All Stars

> Reply from zhang123 ↑Wed May 01, 2019 11:47 am at Wed May 01, 2019 11:47 am
>
> 
iehaiel wrote: ↑Sat Apr 20, 2019 11:18 pm
lurenx wrote: ↑Thu Sep 20, 2018 9:17 am
for animiation I got it working with AssestStudio
https://github.com/Perfare/AssetStudio/releases
the anmiations are saved in a different source file. If you load them together in AssetStudio you will be able to view the model with animation in Noesis.

I found that the exported model only has the normal map. 
I was able to export as FBX, then use the Autodesk FBX tool to convert it to FBX2013, then everything can be loaded into Blender correctly. The diffuse maps need to be updated manually.
Somehow 3dsmax cannot load the files correctly.

The only issue I have is that the facial expression does not seem to import to blender.
I found that they are imported as shape keys but not loaded to the model animation directly.


Thanks for sharing this tool, it has helped me a lot, I have problems in making animations work, could you explain me better how to do it?


1,select the model in Scene Hierarchy
2,select an AnimationClip in Asset list
3,use Model/Export selected objects with AnimationClip

thank you very much for the explanation, it helped me a lot
## Post #13
- Username: korea0799
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2016 3:44 pm
- Post datetime: 2019-05-12T09:51:36+00:00
- Post Title: King of Fighters All Stars

Workable  
Just need to reScale
## Post #14
- Username: ratonmalo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Mar 23, 2010 10:46 pm
- Post datetime: 2019-05-19T23:34:51+00:00
- Post Title: King of Fighters All Stars

Hi,
I having problems with the animations.

If I Load the Character (Menu File > Load file // Select file prefabs_character_takuma)
I can extracted and the facials (Blend Shape) works great.

From there If I load the animation file (Menu File > Load file // Select file resourcesdata_animation_character_takuma)
All the animations appear in the Asset List Tab and the Takuma Character Moldes disappear.

If I try to extract the animations selecting the menu Export > All Assets, the extracting progress bar start to move but I get no extracted file in the folder. Getting the next error "Nothing exported. 62 assets skipped (not extractable of files already exist)"

Any help? Thanks
## Post #15
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-05-20T16:50:16+00:00
- Post Title: King of Fighters All Stars

Would anyone be willing to DM me the data files that download when you start up the game? I've been trying to get them via BlueStacks, but I can never seem to wrap my head around how one gets data files that aren't included in the main ipa/apk file.


Hope I'm not being a bit of a nuisance for asking this.
## Post #16
- Username: korea0799
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2016 3:44 pm
- Post datetime: 2019-05-23T08:43:10+00:00
- Post Title: Re: King of Fighters All Stars

> Reply from MisterPrawn ↑Tue May 21, 2019 12:50 am at Tue May 21, 2019 12:50 am
>
> 
Would anyone be willing to DM me the data files that download when you start up the game? I've been trying to get them via BlueStacks, but I can never seem to wrap my head around how one gets data files that aren't included in the main ipa/apk file.


Hope I'm not being a bit of a nuisance for asking this.

NOX workable
## Post #17
- Username: zhanghongming123
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Mar 16, 2019 1:01 pm
- Post datetime: 2019-05-29T10:02:35+00:00
- Post Title: Re: King of Fighters All Stars

> Reply from ratonmalo ↑Mon May 20, 2019 7:34 am at Mon May 20, 2019 7:34 am
>
> 
Hi,
I having problems with the animations.

If I Load the Character (Menu File > Load file // Select file prefabs_character_takuma)
I can extracted and the facials (Blend Shape) works great.

From there If I load the animation file (Menu File > Load file // Select file resourcesdata_animation_character_takuma)
All the animations appear in the Asset List Tab and the Takuma Character Moldes disappear.

If I try to extract the animations selecting the menu Export > All Assets, the extracting progress bar start to move but I get no extracted file in the folder. Getting the next error "Nothing exported. 62 assets skipped (not extractable of files already exist)"

Any help? Thanks
put prefabs_mesh_character_*** and resourcesdata_animation_character_***  in the same folder
Menu File >Load folder
## Post #18
- Username: kskui008
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Apr 04, 2018 11:56 am
- Post datetime: 2019-08-11T12:01:29+00:00
- Post Title: Re: King of Fighters All Stars

Hi, I use ASSestStudio to extract animations, exported FBX files, but only one frame in 3DSMAX, please ask me how to use the assest Studio. To extract this animation's animation and get it in 3dsmax?  Anyone can help me，Thanks
## Post #19
- Username: korea0799
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2016 3:44 pm
- Post datetime: 2019-08-15T14:22:22+00:00
- Post Title: Re: King of Fighters All Stars

> Reply from kskui008 ↑Sun Aug 11, 2019 8:01 pm at Sun Aug 11, 2019 8:01 pm
>
> 
Hi, I use ASSestStudio to extract animations, exported FBX files, but only one frame in 3DSMAX, please ask me how to use the assest Studio. To extract this animation's animation and get it in 3dsmax?  Anyone can help me，Thanks

What result if you read fbx in NOESIS?
## Post #20
- Username: donovan
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 17, 2016 4:58 pm
- Post datetime: 2019-12-05T23:06:02+00:00
- Post Title: Re: King of Fighters All Stars

I don't understand how to export models...
I have the game (only 92mo... it's strange), I have Unity studio, but that's all, I don't know how to do after that.

Anybody could help please ?
## Post #21
- Username: lurenx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 13, 2017 9:37 am
- Post datetime: 2019-12-16T06:42:54+00:00
- Post Title: Re: King of Fighters All Stars

> Reply from MisterPrawn ↑Tue May 21, 2019 12:50 am at Tue May 21, 2019 12:50 am
>
> 
Would anyone be willing to DM me the data files that download when you start up the game? I've been trying to get them via BlueStacks, but I can never seem to wrap my head around how one gets data files that aren't included in the main ipa/apk file.


Hope I'm not being a bit of a nuisance for asking this.
you need to access internal storage. Any type of file manager will work, with emulator or on actual android device.
it is under Android/data/com.netmarble.kof/files/assetbundles
you have to actually play the game to download them. The apk won't include the files.
## Post #22
- Username: YAGAMI97
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 26, 2020 6:51 am
- Post datetime: 2020-02-25T22:56:25+00:00
- Post Title: Re: King of Fighters All Stars

How can I extract the animations of the characters with movement?
## Post #23
- Username: lurenx
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Mar 13, 2017 9:37 am
- Post datetime: 2020-02-26T05:23:12+00:00
- Post Title: Re: King of Fighters All Stars

> Reply from YAGAMI97 ↑Wed Feb 26, 2020 6:56 am at Wed Feb 26, 2020 6:56 am
>
> 
How can I extract the animations of the characters with movement?

use Assetstudio, load both the mesh file and the animation file for the character
select the animations and the animator file, pick the export with animation
## Post #24
- Username: YAGAMI97
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 26, 2020 6:51 am
- Post datetime: 2020-03-02T05:19:53+00:00
- Post Title: Re: King of Fighters All Stars

[https://youtu.be/cfSA-cYL74w](https://youtu.be/cfSA-cYL74w)

I want to get those animations, in what folder and with what program can I extract them?
PLEASE HELP!
## Post #25
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2020-03-19T08:16:03+00:00
- Post Title: Re: King of Fighters All Stars

> Reply from YAGAMI97 ↑Mon Mar 02, 2020 1:19 pm at Mon Mar 02, 2020 1:19 pm
>
> 
https://youtu.be/cfSA-cYL74w

I want to get those animations, in what folder and with what program can I extract them?
PLEASE HELP!

Spine 2d Full version
## Post #26
- Username: azrael
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 03, 2020 6:47 pm
- Post datetime: 2020-09-03T13:31:06+00:00
- Post Title: Re: King of Fighters All Stars

hi, I was able to open files in AssetStudio.v0.15.20 I also can view them,, when exporting it's exported as obj for the mesh and png for textures.
is there a tutorial how to rip the characters as xps with textures and skeleton/armature ?
ps : I work with blender and have the addon to open xps, found a guy ripped some characters as xps but not all, i want to complete his work
