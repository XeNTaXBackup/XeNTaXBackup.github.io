## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-08T15:52:13+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Asphalt 9: Legends jtex/jmodel convertor for the Android/iOS version game.

Features:
I. Jmodel to FBX convertion: 
- The first released tool using my binary FBX builder which reduces size of the resulting file. 
- Multiple UV channels support: mesh name is followed by UV channel count. Second UV is used with normal maps.
- Vertex colors support: it allows you to export the model with vertex colors if the attribute is available. 
- Option to extracting only the highest LOD: enabled by default.
- Option to quadifying the non-stripped meshes: disabled by default.
- Other small features for the scene properties.
- Batch process options.

II. Jtex to pvr convertion: 
- Converting all *.tga.jtex files to ordinary PVR images.
- Batch process options.

Usage:
Double click the tool and follow the prompt message;
Change the values of corresponding field in the config file to affect program behaviors.

Known Issues:
There're still some parenting issues with most models so you need to adjust/correct them manully, mostly by mirroring or rotating their dummy bone along certain axes.
Edit: issues now fixed in v1.4.6

Potential Issues:
The tool uses a simple/rough method to calculate face counts of grouped submeshes so chances are that it might not work correctly for some models.

A few working examples:
[](https://imgur.com/0LrQiRk)
[](https://imgur.com/umQnfNu)
[](https://imgur.com/ZPvJew7)

(With MeshQuadifier enabled)
[](https://imgur.com/U7EWI3t)
[](https://imgur.com/Epq5opa)
[](https://imgur.com/5IOoZtK)

For those who have no clue about how to unpack Android obb archive, use Haozip.
Or you can try with my Zip64Unpacker for iOS pack files here.
For obb archives containing assets without proper names, you must use this script to unpack them.

You'll need the SQN.db from this post as well. Just place it into the same folder as other components.
[A9Tool.7z](https://xentaxbackup.github.io/file/16372_A9Tool.7z)
## Post #2
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2018-09-11T17:00:53+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I see many issue. When textures convert to .pvr, I saw messege: "This file cannot be open Please..." When I import model to 3DS Max I saw this: [https://mega.nz/#!nl82gQxJ!CxIe1wPPSzYx ... 9sKWtZMYc8](https://mega.nz/#!nl82gQxJ!CxIe1wPPSzYxSfmBXKoSG9Djj8Iyfd0h-9sKWtZMYc8) (this same in 3DSimEd and Blender) and CAR_NAME_fx_overclocked_dyn and CAR_NAME__fx_respawn_dyn.json can't be convert.
And this my files: [https://mega.nz/#!H8tmnaiC!KgkS2jwrpboE ... WIIwnqaNiI](https://mega.nz/#!H8tmnaiC!KgkS2jwrpboEVbRL-SXwQeRiIMD9epEtAWIIwnqaNiI)
Sad news that you don't develop this tool now :/
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-12T00:15:58+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from zimex25
>
> When textures convert to .pvr, I saw messege: "This file cannot be open Please..."
That's not an error message from my code so maybe the file is not accessible.

Edit: Anyway these textures won't be converted correctly coz these formats were out of my consideration.

> Reply from zimex25
>
> When I import model to 3DS Max I saw this: (this same in 3DSimEd and Blender)
That's the issue I described in the first post:

> Reply from Bigchillghost
>
> 
Issues:
Currently there's no way to separate submeshes within the same mesh group, and as a temporary solution they're all represented by an instance of the same mesh group. So you have to clean out the model from a mesh mountain.
...In a word, to get the model you want, you need to work really "hard".
All corresponding meshes are in correct positions so you need to delete the extra parts manully.

> Reply from zimex25
>
> CAR_NAME_fx_overclocked_dyn and CAR_NAME__fx_respawn_dyn.json can't be convert.
Didn't care much for those fx files but it should work too. Might take a look on your files later.

Edit: Your files are using a different compression, are they from the Win32 version?

> Reply from zimex25
>
> Sad news that you don't develop this tool now :/
With that being said I mean currently there's unlikely to be any major updates on the tool. But any running issues causes by the tool are to be considered.
## Post #4
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2018-09-13T10:53:37+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> zimex25 wrote:When textures convert to .pvr, I saw messege: "This file cannot be open Please..." 
That's not an error message from my code so maybe the file is not accessible.

Edit: Anyway these textures won't be converted correctly coz these formats were out of my consideration.
zimex25 wrote:When I import model to 3DS Max I saw this: (this same in 3DSimEd and Blender)
That's the issue I described in the first post:
Bigchillghost wrote:
Issues:
Currently there's no way to separate submeshes within the same mesh group, and as a temporary solution they're all represented by an instance of the same mesh group. So you have to clean out the model from a mesh mountain.
...In a word, to get the model you want, you need to work really "hard".

All corresponding meshes are in correct positions so you need to delete the extra parts manully.
zimex25 wrote:CAR_NAME_fx_overclocked_dyn and CAR_NAME__fx_respawn_dyn.json can't be convert.
Didn't care much for those fx files but it should work too. Might take a look on your files later.

Edit: Your files are using a different compression, are they from the Win32 version?
zimex25 wrote:Sad news that you don't develop this tool now :/
With that being said I mean currently there's unlikely to be any major updates on the tool. But any running issues causes by the tool are to be considered.
I use files from Android game version. (Adreno device)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-13T11:13:12+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from zimex25
>
> 
I use files from Android game version. (Adreno device)
Weird then. The _fx_overclocked_dyn and _fx_respawn_dyn files from your samples are larger in size than both the ones from Android & iOS version I'm using.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-15T13:00:41+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Tool updated.
## Post #7
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-09-15T15:10:17+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I was able to get the Models&Textures from the older version perfectly..though have to delete extra parts.

The PVR file i was getting was easily viewable in PVRTexTool. and Fx_overclocked was also converted but i will have to reorient it to get perfect mesh though...
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-15T15:48:23+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> I was able to get the Models&Textures from the older version perfectly..though have to delete extra parts.
Well the research was based on both the debug and the released versions of the game so the tool is compatible with files from both version.
However files from the released version mostly don't use stripped meshes while the old version did. And the tool will ignore only the lower LODs from the non-stripped mesh group. So it's recommended to use the the latest version of the game.

> Reply from taruncreation
>
> but i will have to reorient it to get perfect mesh though...
Didn't care for the UV mapping earlier, now it should be fine.
## Post #9
- Username: TolikGT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 7:23 am
- Post datetime: 2018-09-16T06:15:35+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

but how unpack obb file ?
## Post #10
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-09-16T06:58:42+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Any solution for getting not rotated model? And any way to get the lowest lods only?

@Tolik- Use HaoZip for extracting obb.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T08:35:38+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> Any solution for getting not rotated model? And any way to get the lowest lods only?
What do you mean by "not rotated model"? And why would you ever need the low LODs?
Unfortunately I'm afraid it's more complicated to get only the lowest LODs, let along it's contrary to my interests. But I can build a separate version to save all LODs if you need it.
## Post #12
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-09-16T11:19:04+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Sorry was unable to explain properly.

The converted models are rotated along x-axis...



Also I'm looking for the lower LODs because not every game runs highpoly models.
## Post #13
- Username: mehrdad995gta
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 19, 2016 10:13 pm
- Post datetime: 2018-09-16T11:20:40+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Thanks for the tool
but I can't just manage to unpack the obb file with WinRAR
is it encrypted?
## Post #14
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-09-16T11:23:15+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from mehrdad995gta
>
> Thanks for the tool
but I can't just manage to unpack the obb file with WinRAR
is it encrypted?

You can open it with HaoZip...

btw @Bigchillghost- Maybe you should state about HaoZip in first post.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T11:45:36+00:00
- Post Title: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> btw @Bigchillghost- Maybe you should state about HaoZip in first post.
Fine. As you wish...
## Post #16
- Username: mehrdad995gta
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 19, 2016 10:13 pm
- Post datetime: 2018-09-16T11:49:38+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> 
You can open it with HaoZip...

Thanks dude,
that worked great.
just tested one of the files, its rotated for me as well but that's not a serious problem,
you can reset the rotation in your 3D editor app (mine is Max) since the pivot axis is aligned correctly along the mesh.
just set (0,0,0) rotation for all meshes
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T12:27:58+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> The converted models are rotated along x-axis...
I suppose you mean the Z axis?
It's that what you're expecting?



pre.jpg (223.39 KiB) Viewed 285 times
## Post #18
- Username: mehrdad995gta
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 19, 2016 10:13 pm
- Post datetime: 2018-09-16T12:55:55+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> 
I suppose you mean the Z axis?

Love the app's logic on defining the axises
In Max it's Z
In Unity its Y and
In Zmodeler X maybe?
## Post #19
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-09-16T13:15:17+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Okay rotating isn't a problem actually   

Offtopic: But can anyone tell me why this happens whenever i try to export .obj files from Blender?ZM only shows the Wireframe but I get the original model after deleting the materials.



So can anything be done about the LODs? Getting only the lower LODs will be good but even if we can get all the LODs in one would also help out
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T13:32:23+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from mehrdad995gta
>
> 
In Max it's Z
In Unity its Y and
In Zmodeler X maybe?
I don't think so. There're only two coordinate systems. Max uses right-hand coordinate system and is Z up, while Unity uses left-hand coordinate system and is Y up.
But we will need to perform a rotation along the upped axis in either coordinate systems don't we?
## Post #21
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T14:38:33+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> So can anything be done about the LODs? Getting only the lower LODs will be good
You sure you need only the LOWEST LODs? Or you might prefer the medium/second LODs if you don't want to lose too much details?



LODs.jpg (255.89 KiB) Viewed 281 times
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T14:59:04+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

But the medium LODs are grouped with other objects which makes it difficult to separate the target LOD.



LODs.jpg (153.11 KiB) Viewed 281 times


So the simplest way would be preserving all LODs.
## Post #23
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-09-16T15:30:51+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> So the simplest way would be preserving all LODs.

Yes, that would be good.

But will we get something like this then?
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T15:38:59+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> But will we get something like this then?
How come? You're still using the debug version?

This would be the actual result:



allLODs.jpg (90.22 KiB) Viewed 275 times
## Post #25
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-16T15:41:53+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Here's a forked version that will preserve all LODs(exe only):

Edit: This version is no longer necessary.

Meshes would be named in the form as [dummy name]#[material name]#LOD[LOD ID].

Also the rotation issue should be fixed in this version.
## Post #26
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-09-16T16:43:46+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Thanks a lot.It's working perfectly.
## Post #27
- Username: rongctor
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Oct 23, 2015 4:01 pm
- Post datetime: 2018-09-17T02:07:20+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

some big scene jmodel file convert to FBX error.
like Him_AllRoads_road.json.jmodel.
[https://drive.google.com/file/d/1wNSLa- ... sp=sharing](https://drive.google.com/file/d/1wNSLa-9K8HVRC8YWS4CM-oyaQ8Xc67Km/view?usp=sharing)

if u have time,thank very much.
## Post #28
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-17T02:23:00+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from rongctor
>
> some big scene jmodel file convert to FBX error.
like Him_AllRoads_road.json.jmodel.
The tool works with files from the car folder only. Files from the environment folder contain other unexpected data chunks so just stop trying to use the tool on files that're not belong to the car folder currently, in case of causing fatal errors.
## Post #29
- Username: rongctor
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Oct 23, 2015 4:01 pm
- Post datetime: 2018-09-17T02:28:07+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> rongctor wrote:some big scene jmodel file convert to FBX error.
like Him_AllRoads_road.json.jmodel.
The tool works with files from the car folder only. Files from the environment folder contain other unexpected data chunks so just stop trying to use the tool on files that're not belong to the car folder currently, in case of causing fatal errors.

ok,thanks again.
## Post #30
- Username: qwzzz
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 13, 2011 1:29 am
- Post datetime: 2018-09-17T19:52:09+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

what program should i used to convert pvr files to png?
## Post #31
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-18T05:04:57+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from qwzzz
>
> what program should i used to convert pvr files to png?
Use PVRTexTool.
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-18T05:07:49+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Tool updated to v1.2.2.

Change log:
1. Added support for environment models;
2. Fixed a wrong parenting issue with the stripped meshes.
## Post #33
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-09-18T07:25:51+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Just wanted to give this a try and forgive my ignorance, but I must be blind, where does it say how one opens the .pack archives?
Just got the game off of iTunes, and I only have few .pack but umm, yeah I only see info about obb android, and that HaoZip will not work for .pack from IPA, so... what am I missing?
## Post #34
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-18T07:41:56+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from mono24
>
> Just wanted to give this a try and forgive my ignorance, but I must be blind, where does it say how one opens the .pack archives?
Just got the game off of iTunes, and I only have few .pack but umm, yeah I only see info about obb android, and that HaoZip will not work for .pack from IPA, so... what am I missing?
Just change their extension to zip before using Haozip. However some files in the pack archive seem to be encrypted. 
You'll have to ignore them when Haozip prompts you for password. Or maybe I can write an unpacker to extract all these files.
## Post #35
- Username: rongctor
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Oct 23, 2015 4:01 pm
- Post datetime: 2018-09-18T09:38:53+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> Tool updated to v1.2.2.

Change log:
1. Added support for environment models;
2. Fixed a wrong parenting issue with the stripped meshes.

amazing job,thanks lot.
## Post #36
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-18T11:31:59+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Here's a BMS unpacker for the iOS pack files. The encrypted files will be dumped into an additional folder.


 Zip64Unpacker.zip
Updated v0.2.1. Improving reading speed. (757 Bytes) Downloaded 173 times


Works with Android obb file too. Just remember to create a new folder as the output location.
## Post #37
- Username: qwzzz
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 13, 2011 1:29 am
- Post datetime: 2018-09-18T13:48:49+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> qwzzz wrote:what program should i used to convert pvr files to png?
Use PVRTexTool.

unable to convert them pvrtextool open the files empty
## Post #38
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-18T14:08:58+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from qwzzz
>
> 
unable to convert them pvrtextool open the files empty
Refer to the second note in this post:
[viewtopic.php?p=137293#p137293](http://forum.xentax.com/viewtopic.php?p=137293#p137293)
## Post #39
- Username: qwzzz
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 13, 2011 1:29 am
- Post datetime: 2018-09-22T03:32:03+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> qwzzz wrote:
unable to convert them pvrtextool open the files empty
Refer to the second note in this post:
viewtopic.php?p=137293#p137293

thanks works now... 

is there a way to convert the windows store version? the textures on mobile are pretty low res
## Post #40
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-22T03:51:25+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from qwzzz
>
> is there a way to convert the windows store version? the textures on mobile are pretty low res
If you can access to the files, maybe. But they are actually the same assets as those used in the Android/iOS version.
## Post #41
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-23T15:59:53+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Tool v1.3.1 updated!

Change log:
1. Added support for multiple UV channels;
2. Added user configuration file support;
3. Fixed a bug when exporting models from files containing both stripped and non-stripped meshes;
4. Now the SaveHighestLodOnly option applys also to stripped meshes.

New Feature:
A simple build-in Mesh Quadifier is Now Available!
[](https://imgur.com/K1Z68Of)
## Post #42
- Username: rongctor
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Oct 23, 2015 4:01 pm
- Post datetime: 2018-09-24T02:50:28+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> Tool v1.3.1 updated!

Change log:
1. Added support for multiple UV channels;
2. Added user configuration file support;
3. Fixed a bug when exporting models from files containing both stripped and non-stripped meshes;
4. Now the SaveHighestLodOnly option applys also to stripped meshes.

New Feature:
A simple build-in Mesh Quadifier is Now Available!

i love u
## Post #43
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-09-27T01:16:58+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> Tool v1.3.1 updated!
New Feature:
A simple build-in Mesh Quadifier is Now Available!
I am impressed with this new feature you added to the latest updated tool, I wish all extraction/dumping tools available to have this as an option which is seriously needed for us 3D artists who need quads in their initial state before devs turned them to tris, thank you very much.
## Post #44
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-27T02:54:16+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Was trying to enhance the functionality of my binary FBX builder by supporting also vertex colors. Here's a simple test on the overclocked model:



Acura_NSX_fx_overclocked_dyn Acura_NSX.jpg (29.72 KiB) Viewed 320 times


Let me know if there is a need for this feature.
## Post #45
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-09-27T08:31:33+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> Was trying to enhance the functionality of my binary FBX builder by supporting also vertex colors. Here's a simple test on the overclocked model:
Acura_NSX.jpg
Let me know if there is a need for this feature.I suppose devs could use vertex coloring for the AO of the car bodies and since cars are high poly so if it's not much of a trouble I would like to see this feature
## Post #46
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-27T11:37:03+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Well, in fact I'm not quite sure if those data are actually vertex color coz except for the cars, I havn't seen one model using these data as vertex color fully makes sense to me. Here's the result of a track model:



Him_AllRoads.jpg (42.6 KiB) Viewed 332 times


Do you think it makes sense to you?
## Post #47
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-09-28T08:00:51+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> Well, in fact I'm not quite sure if those data are actually vertex color coz except for the cars, I havn't seen one model using these data as vertex color fully makes sense to me. Here's the result of a track model:
Him_AllRoads.jpg
Do you think it makes sense to you?devs might use vertex color for ingame effects. it could be used for anything actually
## Post #48
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-09-28T13:21:57+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Alright, I think I'll just leave it like that.

Now, as for your concerns:
Version 1.4.0 updated!
Model will now have vertex colors if the attribute is valid. 
It also comes along with several other options. Just discover it yourself.
## Post #49
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2018-10-20T19:20:58+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

First of all great work guys. Thanks a lot:)

I have a question, is it possible to extract models from Windows 10 version? I see there are many .pack files but no idea how to open them to get models and textures.
## Post #50
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-10-21T16:23:26+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from TomWin
>
> First of all great work guys. Thanks a lot:)

I have a question, is it possible to extract models from Windows 10 version? I see there are many .pack files but no idea how to open them to get models and textures.

Try renaming .pack to .zip and extract using HaoZip...you might get the Models&Textures in corresponding folders.I haven't checked the Win10 version though.
## Post #51
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2018-10-22T16:46:24+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> TomWin wrote:First of all great work guys. Thanks a lot:)

I have a question, is it possible to extract models from Windows 10 version? I see there are many .pack files but no idea how to open them to get models and textures.

Try renaming .pack to .zip and extract using HaoZip...you might get the Models&Textures in corresponding folders.I haven't checked the Win10 version though.

I'm unable to copy these files to other folder.
With A8 no problem at all.
## Post #52
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-10-25T13:32:46+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from TomWin
>
> taruncreation wrote:TomWin wrote:First of all great work guys. Thanks a lot:)

I have a question, is it possible to extract models from Windows 10 version? I see there are many .pack files but no idea how to open them to get models and textures.

Try renaming .pack to .zip and extract using HaoZip...you might get the Models&Textures in corresponding folders.I haven't checked the Win10 version though.

I'm unable to copy these files to other folder.
With A8 no problem at all.

Have seen many people trying to rip from PC version...anything different in PC version than Android one?
## Post #53
- Username: hipatsu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Oct 29, 2018 3:31 am
- Post datetime: 2018-10-28T19:37:33+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Is the source code of this extraction tool available? I would like to port it to C# / Mono so it could be used in macOS as well.
## Post #54
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-21T05:49:05+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from hipatsu
>
> Is the source code of this extraction tool available?
i don't see any source but i made a open source bms script to convert
the Android version jtex to pvr since i was interested in this format.  


 Asphalt9Legends_Android_jtex2pvr.zip
(902 Bytes) Downloaded 94 times


works with all Android version jtex files, its not much but you could use
it as a guideline or something to get started.
## Post #55
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2018-12-22T14:50:17+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Hello everybody
I like to test programs for 3d.
I have followed the instructions and it has emerged an FBX. The FBX file is 50 KB in size.
My conclusion. No 3d program can import this file. I always have a blank screen. I use Win 10 64 bit to test the A9 tool. What am I doing wrong ???

English is not my mother tongue. Translation with Google
## Post #56
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-23T01:00:12+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from oldman
>
> 
I have followed the instructions...What am I doing wrong ???
What am I supposed to tell you with this?
Try running the tool with the following commands:

```
A9Tool.exe file.jmodel
pause

```

Modify the filename to yours and save it to a text file with an extension ''cmd'' aside your jmodel file. 
Run this cmd file and show me the logging message.
## Post #57
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2018-12-23T08:59:41+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Trial performed.

My bat.file
@echo off
D:\a9\gfx3D\cars\models\A9Tool.exe D:\a9\gfx3D\cars\models\testcar.json.jmodel
pause


Result:
Error: missing configuration file! Default settings have been used!
Processing testcar.json.jmodel
Unsupported data type:2

thank you for your effort and patience with me ..
## Post #58
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-23T09:23:20+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Checked the lastest version of the game. They've reduced the quality of the normal vectors down to two bytes and some meshes even have no such attribute.
Here's a quick fix (exe only) where unsupported mesh normals will be ignored. No time to deal with it yet.


 A9Tool_v1.4.1.zip
(34 KiB) Downloaded 93 times
## Post #59
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2018-12-23T11:45:18+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

wow .... it works. You're a hero. 

I am not sure about the version. Maybe 3.01, date 5/2018?
Is on some days a nuisance, version differences. Small change in the game-code, tool does not work.

Now everything is good. It works ... good man
## Post #60
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-12-30T07:24:44+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Hello everyone,
I wanted to have the cars from latest update but looks like the tool is not creating perfect .fbx files.They have done something with the .json fies from latest update.Latest version is (1.2.4a).

Here is a sample:- [https://app.box.com/s/0q4d4mg38nbn05ydo910kum9vdl2yov7](https://app.box.com/s/0q4d4mg38nbn05ydo910kum9vdl2yov7)
## Post #61
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-31T03:35:23+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Works fine.



Genty_Akylone_car.jpg (221.1 KiB) Viewed 575 times


Havn't checked [v1.4.1](http://forum.xentax.com/viewtopic.php?p=146901#p146901)?
## Post #62
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-12-31T05:39:08+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> Works fine.
Genty_Akylone_car.jpg
Havn't checked v1.4.1?

Oh...actually I wanted to but was unable to download it yesterday.It said "You are not authorised to download this".
But one question how did you got the parts at correct positions?I mean in my rip the doors and wing is hanging somewhere else at a different place.
## Post #63
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-31T06:20:30+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation
>
> But one question how did you got the parts at correct positions?I mean in my rip the doors and wing is hanging somewhere else at a different place.
Just rotate the dummy bones of the doors towards the corresponding directions by 220 degrees, or simply set the rotations along y axis to their opposite. Apply similar operations on the rest of them. In Max with angle snap toggled it's a lot easier.
## Post #64
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-02-12T04:49:50+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Hi there,
In the latest update the zip is password protected.Any way to bypass it??
## Post #65
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-12T05:33:09+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I wouldn't know. Tried skipping the password directly?
## Post #66
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-02-12T07:11:08+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

The graphic files are not encrypted. Use the lastest version of the [Zip64Unpacker](http://forum.xentax.com/viewtopic.php?p=144179#p144179).
## Post #67
- Username: TheRealPcGamer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 14, 2019 1:28 pm
- Post datetime: 2019-02-14T05:30:37+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

How to download your tool ?
(I am very new to this community)
## Post #68
- Username: nougat2018
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 05, 2019 4:36 am
- Post datetime: 2019-04-06T18:28:45+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

How can I unzip the Android obb?
## Post #69
- Username: mclarenp20
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 20, 2019 9:53 am
- Post datetime: 2019-04-20T08:07:32+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Hello, Author, which key should I press to smooth these surfaces? It looks like the converted model is terrible. Could you help me ? Thanks.
## Post #70
- Username: mclarenp20
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 20, 2019 9:53 am
- Post datetime: 2019-04-20T09:27:25+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

And errors in PVR files
## Post #71
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-05-03T11:14:42+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

First thing first, tool updated to v1.4.3!

Changes:
1. The normal vectors in later version is now supported, meshes having no normals will still look the same;
2. Added inner batch process options to the config file, which is much faster. Don't turn it on if you need the drag & drop procedure only.

Since I still couldn't figure out the non-linear encoding of this 2-byte normals format, I just came up with another space-consuming but effective solution: generating a normals mapping database from this encoding, to an earlier game version. Therefore, it makes the tool much heavier so I have to split it into 2 parts to overcome the 256KB limitation. Here, it's just for the normals mapping database.

The normals in this database are resampled from the earlier version as signed-8-bit integers. They are mapping to the new format by considering the 2-byte normals as an unsigned-16-bit little-endian index. So for a 2-byte normal vector encoded as 01 00, you should be looking for the second element in this database. If anyone is interested in it and feel like to figure out the encoding, be my guest. I'm just glad that I don't have to worry about it any more. 
[SQN.7z](https://xentaxbackup.github.io/file/16154_SQN.7z)
## Post #72
- Username: mclarenp20
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 20, 2019 9:53 am
- Post datetime: 2019-05-04T06:27:27+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Unfortunately, this configuration of Enable Mesh Quadifier does not work.
## Post #73
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2019-05-04T21:46:51+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

the tool works good...  

the UV channels work too. FBX import and render with 3ds Max 2016. Smoothing in mesh is okay ...   
.
.



porsche_911_gts.jpg (201.24 KiB) Viewed 448 times
## Post #74
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2019-05-11T02:42:53+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

this work in  Asphalt: Street Storm Racing??
## Post #75
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-18T17:23:14+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

A new update of A9 is out but looks like it's using Unity files now...
## Post #76
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-19T07:17:49+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

It would be rediculous for a game to change the engine halfway. It still uses the same engine, just without meaningful asset names.
Use this BMS script to unpack the obb arc with extension filtering.



 Zip64Unpacker_A9_1.6.2.zip
(866 Bytes) Downloaded 294 times



Also the mesh format is a bit different. So remember to update your tool to v1.4.4.
## Post #77
- Username: Agzam
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 18, 2018 6:32 pm
- Post datetime: 2019-06-19T07:35:00+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost ↑Wed Jun 19, 2019 3:17 pm at Wed Jun 19, 2019 3:17 pm
>
> 
It would be rediculous for a game to change the engine halfway. It still uses the same engine, just without meaningful asset names.
Use this BMS script to unpack the obb arc with extension filtering.


Zip64Unpacker_A9_1.6.2.zip


Also the mesh format is a bit different. So remember to update your tool to v1.4.4.

please tell me what to do with this file?
## Post #78
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2019-06-19T09:43:43+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Agzam ↑Wed Jun 19, 2019 3:35 pm at Wed Jun 19, 2019 3:35 pm
>
> 
Bigchillghost wrote: ↑Wed Jun 19, 2019 3:17 pm
It would be rediculous for a game to change the engine halfway. It still uses the same engine, just without meaningful asset names.
Use this BMS script to unpack the obb arc with extension filtering.


Zip64Unpacker_A9_1.6.2.zip


Also the mesh format is a bit different. So remember to update your tool to v1.4.4.


please tell me what to do with this file?

I need Quick BMS to run this script.
## Post #79
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-19T14:14:39+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Use this BMS script to unpack the obb arc with extension filtering.

What Commandline should I use?
## Post #80
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-19T14:53:50+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

No need for commandline. Just run it through the GUI.
## Post #81
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-19T15:00:26+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I used the BMS script you provided but there are same files after extraction.
[64638535_605441909950538_4890486738046156800_n copy.jpg](https://xentaxbackup.github.io/file/16374_64638535_605441909950538_4890486738046156800_n copy.jpg)
## Post #82
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-19T15:05:04+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

No idea. Works fine on my pc.
## Post #83
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-19T16:38:19+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Okay now I got the .jmodel & .jtex files but too hard to locate files of a particular car(11k+ files). Any tool to read those Hexadecimal values quickly?
## Post #84
- Username: Agzam
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 18, 2018 6:32 pm
- Post datetime: 2019-06-19T17:20:05+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost ↑Wed Jun 19, 2019 10:53 pm at Wed Jun 19, 2019 10:53 pm
>
> 
No need for commandline. Just run it through the GUI.

Please give detailed instructions. I'm not good at this stuff. I think this will help many
## Post #85
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-19T17:24:21+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Where do I need to place SQN.db? With the obb?

Edit: I've got the car models after placing the SQN.db with the obb...Still have to find the model of the car I need and also the Textures.
## Post #86
- Username: Agzam
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Dec 18, 2018 6:32 pm
- Post datetime: 2019-06-19T18:04:22+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation ↑Thu Jun 20, 2019 1:24 am at Thu Jun 20, 2019 1:24 am
>
> 
Where do I need to place SQN.db? With the obb?

Edit: I've got the car models after placing the SQN.db with the obb...Still have to find the model of the car I need and also the Textures.

Please make instructions on how you did it. I'm not good at this.
## Post #87
- Username: oldman
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 19, 2017 2:54 am
- Post datetime: 2019-06-19T20:57:09+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

It's a simple way ... test with Game v1.6.2a

Download the A9 Tool, the SQN.db and the Zip64Unpacker_A9_1.6.2.zip

Unzip the Zip64Unpacker_A9_1.6.2.zip, you will get Zip64Unpacker_A9_1.6.2.bms

Use the program Quickbms with the Zip64Unpacker_A9_1.6.2.bms and the big OBB.

You get many files, including car_39xxxxxxxx.json.jmodel

Make a new folder, put in the folder all files for the A9Tool and the SQN.db and the many car_39xxxxxxxx.json.jmodel

Create a9.bat with the editor
content
FOR %%a IN (*.jmodel) DO A9Tool.exe %%a
Put the bat in the folder with the A9Tool etc.
Start this Bat and have a lot of fun with the FBX files  

Same way with the 39xxxxxxxxxxxxx.tga.jtex

To watch for the * .pvr files use the PVRTEXTOOL
## Post #88
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-20T01:50:41+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation ↑Thu Jun 20, 2019 12:38 am at Thu Jun 20, 2019 12:38 am
>
> 
Any tool to read those Hexadecimal values quickly?
Nop. Not saying I know what these sequences are, even if I do, there's no way to reverse the hashing process to track the origianl filenames.

> Reply from taruncreation ↑Thu Jun 20, 2019 1:24 am at Thu Jun 20, 2019 1:24 am
>
> 
Where do I need to place SQN.db? With the obb?

Edit: I've got the car models after placing the SQN.db with the obb...
I would recommend to place it in the A9Tool folder, just as the config file and the dlls, since it's where the tool is started. But if you throw everything into one folder, including the obb and the unpacked assets, it'll work too.

> Reply from taruncreation ↑Thu Jun 20, 2019 1:24 am at Thu Jun 20, 2019 1:24 am
>
> Still have to find the model of the car I need and also the Textures.
Incase you havn't noticed, the script will treate the jmodel files containing standard triangle meshes as car model files, and assign a "car_" prefix to the output name. Its not accurate, but still helps a bit. You can sort the assets by names first, pick out those with the prefix into a new folder, and sort them by size, and remove the small files. Then you can convert all files in the folder with the tool and take a quick glance at the FBXs with Noesis.
As for textures, there's no way to distinguish them. So the only way is to convert them all, and look for the ones you need vis thumbnails.

> Reply from oldman ↑Thu Jun 20, 2019 4:57 am at Thu Jun 20, 2019 4:57 am
>
> 
Make a new folder, put in the folder all files for the A9Tool and the SQN.db and the many car_39xxxxxxxx.json.jmodel

Create a9.bat with the editor
The A9Tool has been capable of build-in batch process since its previous version, so just leave the components where they belong and modify A9Tool.ini to enable batch command and specify the path of your assets files. It'll automatically convert all jmodel and jtex within.
## Post #89
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-20T06:51:14+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Model File Untitled.jpg (250.16 KiB) Viewed 511 times



Alright , I got the model files for cars easily since some files had "car_" as prefix. Finding the ones I need from among 70+files is not hard but finding the required textures from around 3.7k+ files is a big deal. But since it's the only way possible then I'll have to check them all.
Thanks for your efforts on the tool 

EDIT: Is there any way to use batch-operation to convert pvr to other format like png? These PVR files are opening in PVRTexTool only. I tried PS plugin but won't work maybe due to different encoding of these pvr files.
## Post #90
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-21T09:39:22+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation ↑Thu Jun 20, 2019 2:51 pm at Thu Jun 20, 2019 2:51 pm
>
> Is there any way to use batch-operation to convert pvr to other format like png?
Copy and paste the following batch command into a cmd file:

```
for %%f in (*.pvr) do (
YOUR_PATH\PVRTexToolCLI.exe -i "%%f" -d -f r8g8b8a8
)
pause

```

Replace "YOUR_PATH" with the full path of your PVRTexToolCLI.exe then you can run it from any folder.
## Post #91
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-21T11:20:14+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Thanks a lot pal but I'm able to run .pvr files from any place already. I chose .pvr files to always open using PvrTexTool hence I'm able to open .pvr from anywhere by clicking it.
I was thinking about a way to convert all .pvr files together to some other format like .png but it's fine I got the textures after checking all the files.
The car_df textures have size 1.3 mbs each , car_df_nm textures have size 185kbs each. They only needed textures I'm unable to find are the glows textures.
## Post #92
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-06-21T13:10:16+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation ↑Fri Jun 21, 2019 7:20 pm at Fri Jun 21, 2019 7:20 pm
>
> 
Thanks a lot pal but I'm able to run .pvr files from any place already. I chose .pvr files to always open using PvrTexTool hence I'm able to open .pvr from anywhere by clicking it.
That's not what I'm talking about. 

> Reply from taruncreation ↑Fri Jun 21, 2019 7:20 pm at Fri Jun 21, 2019 7:20 pm
>
> I was thinking about a way to convert all .pvr files together to some other format like .png
That's what the batch commands do.
## Post #93
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-06-21T15:24:09+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

My bad. Sorry for that I misunderstood the post. Thanks for this
## Post #94
- Username: Dekill93
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 27, 2019 6:28 pm
- Post datetime: 2019-06-27T10:31:40+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Can anyone help me to unpack obb and edit gameoptions.json ?cz in new version all in encrypt, helm me T.T
## Post #95
- Username: nougat2018
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 05, 2019 4:36 am
- Post datetime: 2019-07-15T13:22:29+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Did you find a way to access the files and see textures?
## Post #96
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-07-19T12:31:30+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from nougat2018 ↑Mon Jul 15, 2019 9:22 pm at Mon Jul 15, 2019 9:22 pm
>
> 
Did you find a way to access the files and see textures?

Yes , we will have to manually check all the files after extraction but it will be a bit easier to find the ones we need if we arrange the files by Size...main car textures are of 1.33mbs.
## Post #97
- Username: mclarenp20
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 20, 2019 9:53 am
- Post datetime: 2019-08-31T09:11:56+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I tried to enter code into cmd, but it didn't work. How can I solve it?
[1.png](https://xentaxbackup.github.io/file/16672_1.png)
## Post #98
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-10T08:18:34+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Thanks for your help
## Post #99
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2019-09-12T11:00:48+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Thank you. I've solved the problem of opening the texture here.
## Post #100
- Username: nougat2018
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Apr 05, 2019 4:36 am
- Post datetime: 2019-11-28T18:17:43+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from taruncreation ↑Fri Jul 19, 2019 8:31 pm at Fri Jul 19, 2019 8:31 pm
>
> 
nougat2018 wrote: ↑Mon Jul 15, 2019 9:22 pm
Did you find a way to access the files and see textures?


Yes , we will have to manually check all the files after extraction but it will be a bit easier to find the ones we need if we arrange the files by Size...main car textures are of 1.33mbs.

And now you can differentiate which are the models and textures?
## Post #101
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-12-09T15:07:49+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> And now you can differentiate which are the models and textures?

Yep. As said above , the car meshes have a prefix "car_" so you can separate them from rest of the files and the textures have .jtex format.
## Post #102
- Username: ErnestHysa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 22, 2019 6:06 pm
- Post datetime: 2019-12-22T12:22:46+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from oldman ↑Thu Jun 20, 2019 4:57 am at Thu Jun 20, 2019 4:57 am
>
> 
It's a simple way ... test with Game v1.6.2a

Download the A9 Tool, the SQN.db and the Zip64Unpacker_A9_1.6.2.zip

Unzip the Zip64Unpacker_A9_1.6.2.zip, you will get Zip64Unpacker_A9_1.6.2.bms

Use the program Quickbms with the Zip64Unpacker_A9_1.6.2.bms and the big OBB.

You get many files, including car_39xxxxxxxx.json.jmodel

Make a new folder, put in the folder all files for the A9Tool and the SQN.db and the many car_39xxxxxxxx.json.jmodel

Create a9.bat with the editor
content
FOR %%a IN (*.jmodel) DO A9Tool.exe %%a
Put the bat in the folder with the A9Tool etc.
Start this Bat and have a lot of fun with the FBX files  

Same way with the 39xxxxxxxxxxxxx.tga.jtex

To watch for the * .pvr files use the PVRTEXTOOL

i am new to all of these but where do I find the sqn.db? i have all the other requirements and thats the only thing missing now
## Post #103
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-12-25T04:16:45+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> i am new to all of these but where do I find the sqn.db? i have all the other requirements and thats the only thing missing now

Here on this post [viewtopic.php?p=151959#p151959](https://forum.xentax.com/viewtopic.php?p=151959#p151959)
## Post #104
- Username: vivaan6s9
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 21, 2019 7:25 pm
- Post datetime: 2019-12-28T19:32:56+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost ↑Wed Jun 19, 2019 3:17 pm at Wed Jun 19, 2019 3:17 pm
>
> 
It would be rediculous for a game to change the engine halfway. It still uses the same engine, just without meaningful asset names.
Use this BMS script to unpack the obb arc with extension filtering.


Zip64Unpacker_A9_1.6.2.zip


Also the mesh format is a bit different. So remember to update your tool to v1.4.4.

where can i get the latest version?
## Post #105
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-12-29T05:20:13+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> where can i get the latest version?

Haven't you checked the first post??
## Post #106
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2020-02-04T23:49:21+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Create a9.bat with the editor
content
FOR %%a IN (*.jmodel) DO A9Tool.exe %%a
Put the bat in the folder with the A9Tool etc.
Start this Bat and have a lot of fun with the FBX files  

 do not understand this part
## Post #107
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2020-02-12T11:48:29+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from JONATHANTKB ↑Wed Feb 05, 2020 7:49 am at Wed Feb 05, 2020 7:49 am
>
> 
Create a9.bat with the editor
content
FOR %%a IN (*.jmodel) DO A9Tool.exe %%a
Put the bat in the folder with the A9Tool etc.
Start this Bat and have a lot of fun with the FBX files  

 do not understand this part

Open a Text Document , write the above command in it and save it as .bat file. Replace .jmodel in it with .jtex to convert the textures.
## Post #108
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2020-02-19T16:13:07+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

can work on Overdrive City??
## Post #109
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2020-03-19T12:42:40+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Okay I back to converting models from A9 but we need rename tool. I can't find texture of Taycan Turbo S, maybe didn't extract. It's too hard to find files now.
## Post #110
- Username: neusi
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jan 31, 2019 9:55 am
- Post datetime: 2020-06-09T23:59:05+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost ↑Fri Jun 21, 2019 5:39 pm at Fri Jun 21, 2019 5:39 pm
>
> 
taruncreation wrote: ↑Thu Jun 20, 2019 2:51 pmIs there any way to use batch-operation to convert pvr to other format like png?

Copy and paste the following batch command into a cmd file:
Code: Select all@echo off
for %%f in (*.pvr) do (
YOUR_PATH\PVRTexToolCLI.exe -i "%%f" -d -f r8g8b8a8
)
pause

Replace "YOUR_PATH" with the full path of your PVRTexToolCLI.exe then you can run it from any folder.

i try to use this command but when i run .bat the PVRTexToolCLI say :
Cannot open file, as it does not exist at specified location.
Has it been renamed, moved or deleted?
## Post #111
- Username: RungeerHA
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 13, 2020 9:55 am
- Post datetime: 2020-08-13T02:26:56+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Hey guys,Thanks for your tool.And I was a noob to 3D Models.But I am dying to get the model of Rezvani Beast X,and i can't find it everywhere...And this post is too difficult for me.I just know how to extract the obb file and get lots of documents without format...what should i do next...i would appreciate it if you can write a tutorials from zero！
## Post #112
- Username: mireg04
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 22, 2020 12:18 pm
- Post datetime: 2020-08-26T01:45:21+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Hello everyone, thanks for the tool, it has been very useful. But I was wondering if it could be possible to share the source code? I am working on a personal project in python and I am interested in this game in particular. I have figured some stuff of the model format, but there is a lot that is still missing. Using your code as reference would be very helpful. Thanks for your effort.
## Post #113
- Username: zingerclick
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Sep 01, 2020 2:32 am
- Post datetime: 2020-09-01T17:37:02+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

hey!!
hello guys!
I'm new here(im dumb and might not understand all the things about the apps and scripts)

but i tried to extract the obb files for the (patch.24321.com.gameloft.android.ANMP.GloftA9HM) file using quickbms app and the (Zip64Unpacker_A9_1.6.2.bms)

it did extract files (.jtex files only tho)

and i used the A9tool.exe to convert it to .pvr files,

when i tried to open it using (PVRTex Tool), it asked for (Chceking that astcnec.exe is in PATH)

sso after 45 minutes of understanding what (ASTC compression encoding is and not knowing why it didn't work even after selecting the PATH in the Environmental variable{but i fixed that sso no problem with it)

it did opened the .pvr file,

(but there is a problem that the texture is corrupted for some reason)(like we can see some things in it)( but its mostly pink)

any ideas why this is happening and how to fix it??

[https://mega.nz/file/1O5TUSAB#_38AC_sIt ... mbi8hp903o](https://mega.nz/file/1O5TUSAB#_38AC_sItyQOIjBUs0_QwLKxT9vzSwYROmbi8hp903o)
## Post #114
- Username: marcus682
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 23, 2020 4:40 am
- Post datetime: 2020-11-22T21:06:56+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

hello,

i got the same issue than zingerclick.

I Extract Switch version of Asphalt 9. astcnec.exe was in Path.

PVRTexTool show me similar image but white background not pink.

Any Idea ?
## Post #115
- Username: TeddySadcat
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 25, 2019 5:44 am
- Post datetime: 2020-12-20T19:04:04+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Yeah I've hit a brick wall with the same problem as the two above me, just this pink vomit when it used to work fine a year back, maybe it's further encrypted now?
## Post #116
- Username: JONATHANTKB
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Nov 24, 2014 12:24 pm
- Post datetime: 2021-04-03T23:28:28+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I honestly do not understand how the tool works, it confuses me a lot if they make a video of how the process is, it would be easier for those who are new to this
## Post #117
- Username: cishy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 19, 2021 8:37 pm
- Post datetime: 2021-06-27T16:20:15+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Help needed... 
I tried to convert .jmodel file from latest android relase and its not working somehow
Does somebody know how to deal with it?
Thanks,
Cishy
[unknown.png](https://xentaxbackup.github.io/file/20370_unknown.png)
## Post #118
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-06-27T17:30:01+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from cishy ↑Mon Jun 28, 2021 12:20 am at Mon Jun 28, 2021 12:20 am
>
> 
Does somebody know how to deal with it?
Did you ever read the first post?

> Reply from Bigchillghost ↑Sat Sep 08, 2018 11:52 pm at Sat Sep 08, 2018 11:52 pm
>
> 
You'll need the SQN.db from this post as well. Just place it into the same folder as other components.
## Post #119
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2021-10-10T12:52:07+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

anyone how to get the latest .obb 
the latest version i got is from 2.9.4a
the newer versions uses a split apk that was unable to open by the scripts
( but u can open it thru renaming it .zip but it just all files no extensions )
( edit: i have found which is which and thanks for the tool )
## Post #120
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-24T13:46:41+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Updated v1.4.5 (exe only): 
Fixed model transformation issue.


 A9Tool_v1.4.5.zip
(34.84 KiB) Downloaded 50 times
## Post #121
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-24T13:47:39+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Now it looks perfect.



Genty_Akylone_car.png (197.87 KiB) Viewed 378 times
## Post #122
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-01-03T15:46:12+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Thank you very much it's much better now  

However there is problem with textures now in new version:



Captureasp9.JPG (107.78 KiB) Viewed 358 times



Any idea what to do?
## Post #123
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-06T14:12:57+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

OK so here's the thing: was attempting to check how textures correspond to the models in previous versions of the game where files still got their proper names. The only versions I managed to find were the China versions. Yet there doesn't seem to be any material files so just another dead end. 

However I did managed to find a manifest file in certain newer versions storing the info to map the hash sequences to their actual names. Checked a few files from different versions (including the Worldwide version) and seems the hash sequence of the same file is constant. So there is a possibility to make use of this manifest file to restore the majority of the filenames (14.5k or so). Let me know if there's still a demand. 

```
7826606840220994454:3344135581749666520:/gfx3D/cars/models/Acura_NSX_fx_overclocked_dyn.json/|/Acura_NSX_fx_overclocked_dyn.json.jmodel:NC:-:NX:-:397F9F0519F5CF1B
10039826136490761637:9772061111109781515:/gfx3D/cars/models/Acura_NSX_fx_respawn_dyn.json/|/Acura_NSX_fx_respawn_dyn.json.jmodel:NC:-:NX:-:397F9F3718A364E7
12076631977921363137:15498437140154039761:/gfx3D/cars/models/Apollo_N_car.json/|/Apollo_N_car.json.jmodel:NC:-:NX:-:397F9F306B8AF862
16576754052122453323:805696109299181830:/gfx3D/cars/models/Apollo_N_fx_overclocked_dyn.json/|/Apollo_N_fx_overclocked_dyn.json.jmodel:NC:-:NX:-:397F9D5E8BBAE900

```
## Post #124
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-01-08T07:12:54+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Yes. Of course. That would be awesome. As now is a real pain to find correct textures.
And even worst probably they Changed texture format in the Newer version so they cannot be converted correctly anymore.
## Post #125
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-01-13T16:32:59+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Yeah , definitely finding textures is a pain atm. I have to sort them by size and check hundreds of textures manually just to get one useful texture.
That would be really helpful
## Post #126
- Username: Vitalik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 07, 2021 5:03 pm
- Post datetime: 2022-01-14T19:25:59+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost ↑Thu Jan 06, 2022 10:12 pm at Thu Jan 06, 2022 10:12 pm
>
> 
OK so here's the thing: was attempting to check how textures correspond to the models in previous versions of the game where files still got their proper names. The only versions I managed to find were the China versions. Yet there doesn't seem to be any material files so just another dead end. 

However I did managed to find a manifest file in certain newer versions storing the info to map the hash sequences to their actual names. Checked a few files from different versions (including the Worldwide version) and seems the hash sequence of the same file is constant. So there is a possibility to make use of this manifest file to restore the majority of the filenames (14.5k or so). Let me know if there's still a demand. 
Code: Select all12230314225805502320:9584570273682123450:/gfx3D/cars/models/Acura_NSX_car.json/|/Acura_NSX_car.json.jmodel:NC:-:NX:-:397F9F334A1DE4D3
7826606840220994454:3344135581749666520:/gfx3D/cars/models/Acura_NSX_fx_overclocked_dyn.json/|/Acura_NSX_fx_overclocked_dyn.json.jmodel:NC:-:NX:-:397F9F0519F5CF1B
10039826136490761637:9772061111109781515:/gfx3D/cars/models/Acura_NSX_fx_respawn_dyn.json/|/Acura_NSX_fx_respawn_dyn.json.jmodel:NC:-:NX:-:397F9F3718A364E7
12076631977921363137:15498437140154039761:/gfx3D/cars/models/Apollo_N_car.json/|/Apollo_N_car.json.jmodel:NC:-:NX:-:397F9F306B8AF862
16576754052122453323:805696109299181830:/gfx3D/cars/models/Apollo_N_fx_overclocked_dyn.json/|/Apollo_N_fx_overclocked_dyn.json.jmodel:NC:-:NX:-:397F9D5E8BBAE900

Hello. I want say thank you for your hard work with this game.

I have a small question for you. I know this is off topic but can you help me.Сan you tell me how to found among all these 14500 filenames GameOptions.json file. I need for change  graphic in game. And maybe how decode his in normal view format for editing.

Thank you for your help.
## Post #127
- Username: shinzef
- Rank: beginner
- Number of posts: 20
- Joined date: Thu Sep 30, 2021 12:03 pm
- Post datetime: 2022-01-16T13:10:34+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost ↑Thu Jan 06, 2022 10:12 pm at Thu Jan 06, 2022 10:12 pm
>
> 
OK so here's the thing: was attempting to check how textures correspond to the models in previous versions of the game where files still got their proper names. The only versions I managed to find were the China versions. Yet there doesn't seem to be any material files so just another dead end. 

However I did managed to find a manifest file in certain newer versions storing the info to map the hash sequences to their actual names. Checked a few files from different versions (including the Worldwide version) and seems the hash sequence of the same file is constant. So there is a possibility to make use of this manifest file to restore the majority of the filenames (14.5k or so). Let me know if there's still a demand. 
Code: Select all12230314225805502320:9584570273682123450:/gfx3D/cars/models/Acura_NSX_car.json/|/Acura_NSX_car.json.jmodel:NC:-:NX:-:397F9F334A1DE4D3
7826606840220994454:3344135581749666520:/gfx3D/cars/models/Acura_NSX_fx_overclocked_dyn.json/|/Acura_NSX_fx_overclocked_dyn.json.jmodel:NC:-:NX:-:397F9F0519F5CF1B
10039826136490761637:9772061111109781515:/gfx3D/cars/models/Acura_NSX_fx_respawn_dyn.json/|/Acura_NSX_fx_respawn_dyn.json.jmodel:NC:-:NX:-:397F9F3718A364E7
12076631977921363137:15498437140154039761:/gfx3D/cars/models/Apollo_N_car.json/|/Apollo_N_car.json.jmodel:NC:-:NX:-:397F9F306B8AF862
16576754052122453323:805696109299181830:/gfx3D/cars/models/Apollo_N_fx_overclocked_dyn.json/|/Apollo_N_fx_overclocked_dyn.json.jmodel:NC:-:NX:-:397F9D5E8BBAE900

Would really like it, but sharing the manifest file alone is great on its own cant find it on mine
## Post #128
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-16T15:22:10+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Vitalik ↑Sat Jan 15, 2022 3:25 am at Sat Jan 15, 2022 3:25 am
>
> 

> Reply from shinzef ↑Sun Jan 16, 2022 9:10 pm at Sun Jan 16, 2022 9:10 pm
>
> 
I'm tired of emphasizing this over and over: do NOT quote at length the entire post in your reply! You're obligated to keep your posts organized & clean and not ruin the mood of those who have been pursuing to do so.  

Now as for your concerns, the unencrypted manifest file existed only in v2.1.0 & v2.2.0 among the China versions (for those I had checked). And I managed to dump the manifest of v2.9.0 through the memory. By removing the duplicate names and comparing the files on the disk, all the hashes match with those in the manifest and there're only 2 files that do not own the corresponding record. And one of the file's size is very close to the manifest file I dumped from the memory, except the data appear to be encrypted. The manifest string fragments can be found in memory even if the game has not been connected to the internet, which means the file must be stored along with the game data. Unfortunately my attempts to dump the manifest of v3.2.2a of the Worldwide version, and to locate the decryption method in the game lib, both failed. The manifest of v2.9.0 (China version) includes 17112 entries and they should cover most of the files of the Worldwide version. That should be sufficient for now.

> Reply from Vitalik ↑Sat Jan 15, 2022 3:25 am at Sat Jan 15, 2022 3:25 am
>
> Сan you tell me how to found among all these 14500 filenames GameOptions.json file.
The file you're looking for should be 397F9F319A55E791. But the data appeared to be encrypted so obviously they don't like someone to mess with their game settings.

> Reply from shinzef ↑Sun Jan 16, 2022 9:10 pm at Sun Jan 16, 2022 9:10 pm
>
> 
Would really like it, but sharing the manifest file alone is great on its own cant find it on mine
Yeah yeah, I know most of you don't have the chance to find it on your own.  I should probably create another topic later, for the renaming tool and maintenance of the converted manifest files.
## Post #129
- Username: Vitalik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 07, 2021 5:03 pm
- Post datetime: 2022-01-17T15:54:05+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Bigchillghost
>
> The file you're looking for should be 397F9F319A55E791. But the data appeared to be encrypted so obviously they don't like someone to mess with their game settings.

Thank for info. I will try decode in normal view for see information in this file.
## Post #130
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-18T02:52:05+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Vitalik ↑Mon Jan 17, 2022 11:54 pm at Mon Jan 17, 2022 11:54 pm
>
> 
You need to edit your previous posts and remove the embed quote and the long context. I'm very serious.  
Read the info in this page if you have no idea how the formatting works.
[app.php/help/bbcode#f2r0](app.php/help/bbcode#f2r0)
## Post #131
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-01-23T16:39:09+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Renaming utility released in this topic:
[viewtopic.php?f=16&t=24982](viewtopic.php?f=16&t=24982)
## Post #132
- Username: Slad
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 29, 2022 1:21 am
- Post datetime: 2022-01-30T21:29:33+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Please, will anyone be kind enought to provide me with a copy of the game files from a ios device, since the latest .obb files on android do not have any logical names, they are some random combinations of letters and numbers. Thanks in advice!

Or if someone can share already renamed files, that would be awesome!
## Post #133
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-01-31T13:43:48+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

you should read previous posts. The renaming tool is already released.

> Reply from Slad ↑Mon Jan 31, 2022 5:29 am at Mon Jan 31, 2022 5:29 am
>
> 
Please, will anyone be kind enought to provide me with a copy of the game files from a ios device, since the latest .obb files on android do not have any logical names, they are some random combinations of letters and numbers. Thanks in advice!

Or if someone can share already renamed files, that would be awesome!
## Post #134
- Username: Slad
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 29, 2022 1:21 am
- Post datetime: 2022-02-02T09:51:26+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from TomWin ↑Mon Jan 31, 2022 9:43 pm at Mon Jan 31, 2022 9:43 pm
>
> 
you should read previous posts. The renaming tool is already released.
Slad wrote: ↑Mon Jan 31, 2022 5:29 am
Please, will anyone be kind enought to provide me with a copy of the game files from a ios device, since the latest .obb files on android do not have any logical names, they are some random combinations of letters and numbers. Thanks in advice!

Or if someone can share already renamed files, that would be awesome!

I did read those, but I'm new to this stuff and i have no clue how to do the renaming thing. Can someone make a more in-depth guide, like for someone who is new to all this. Or someone just upload a copy of the renamed files, or send a copy of the renamed files to my email: [vankotoka1@gmail.com](mailto:vankotoka1@gmail.com)
## Post #135
- Username: TomWin
- Rank: veteran
- Number of posts: 146
- Joined date: Mon Apr 12, 2010 2:46 am
- Post datetime: 2022-02-02T12:13:40+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

> Reply from Slad ↑Wed Feb 02, 2022 5:51 pm at Wed Feb 02, 2022 5:51 pm
>
> 
TomWin wrote: ↑Mon Jan 31, 2022 9:43 pm
you should read previous posts. The renaming tool is already released.
Slad wrote: ↑Mon Jan 31, 2022 5:29 am
Please, will anyone be kind enought to provide me with a copy of the game files from a ios device, since the latest .obb files on android do not have any logical names, they are some random combinations of letters and numbers. Thanks in advice!

Or if someone can share already renamed files, that would be awesome!



I did read those, but I'm new to this stuff and i have no clue how to do the renaming thing. Can someone make a more in-depth guide, like for someone who is new to all this. Or someone just upload a copy of the renamed files, or send a copy of the renamed files to my email: vankotoka1@gmail.com
In simple words

Install newest python
Put all files in one folder (game+tool)
run restoreFileHierarchy.py

That's it


I would like to ask how to convert textures from A9 v3.2.2?
I have following error.


jtex.JPG (14.08 KiB) Viewed 201 times
## Post #136
- Username: Slad
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 29, 2022 1:21 am
- Post datetime: 2022-02-02T16:32:11+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I did read those, but I'm new to this stuff and i have no clue how to do the renaming thing. Can someone make a more in-depth guide, like for someone who is new to all this. Or someone just upload a copy of the renamed files, or send a copy of the renamed files to my email: [vankotoka1@gmail.com](mailto:vankotoka1@gmail.com)
[/quote]
In simple words

Install newest python
Put all files in one folder (game+tool)
run restoreFileHierarchy.py

That's it


I would like to ask how to convert textures from A9 v3.2.2?
I have following error.jtex.JPG
[/quote]

Thank you, i did that. I got a few new folder with the animations, levels etc., but the jtex and jmodel files didn't get renamed. I'm using i believe the 3.2.2 version of the game's .obb. What do i need to do to rename the jtex and jmodel files too?
## Post #137
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-02-05T09:59:15+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Updated v1.4.6 (exe only):
- Better fix for transformation singularity issue;
- Fixed compatibility issue with current jtex format.
[A9Tool_v1.4.6.7z](https://xentaxbackup.github.io/file/21735_A9Tool_v1.4.6.7z)
## Post #138
- Username: Slad
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jan 29, 2022 1:21 am
- Post datetime: 2022-02-06T12:27:20+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

I can't understand how to extract the obb file (v3.2.2) with Haozip. Can someone please make like a step by step tutorial on how to actually unzip this obb file and get the files?
## Post #139
- Username: Cornalito
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 19, 2018 5:52 am
- Post datetime: 2022-03-30T03:54:26+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Seems the tool not working with the 3.3.7a version of game and the models are coming with .jmox extension 

Theres a link with some files:
[https://drive.google.com/file/d/1qvPN4d ... sp=sharing](https://drive.google.com/file/d/1qvPN4dCHLIn5y8DItkiqExcv5CwHNLLj/view?usp=sharing)
## Post #140
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2022-05-20T19:17:34+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

<the content of this message was removed by me because it's offtopic and the problem is solved>
## Post #141
- Username: ZirixStarstrider
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 20, 2022 9:02 pm
- Post datetime: 2022-06-25T19:06:32+00:00
- Post Title: Re: Asphalt 9: Legends Jtex|Jmox Convertor(A9Tool)

Sorry if this is not the place to ask, but where i can find an updated manifest.map? I need the one for the 3.5.2a version of the game. Some cars didn't even appear on the renamed files without it. Thanks in advance
