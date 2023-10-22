## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-11-30T21:46:22+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

A tool for previewing/exporting animations from Mortal Kombat X and 11. Seems to work with a good amount of combat and voice-over animations. There is still some non-working stuff.

Johnny Nutpunch



Kitana X-Ray



Mortal Kombat X

How to use

Better watch the tutorial video to understand it. It requires the usage of multiple tools. 

Video: [https://youtu.be/QeljMCkRF1k](https://youtu.be/QeljMCkRF1k)

1 ) Move python scripts to Noesis plugins folder
2 ) Export the model you want with umodel (gltf)
3 ) Convert it to NUX using Noesis
4 ) Unpack animations using daemon1's MKX tools
5 ) Copy names.txt file into the unp folder
6 ) Load the NUX model in MKXAnim
7 ) Load the animation from the unp folder
8 ) Export the animated model as NUX
9 ) Preview/convert using Noesis
10) Profit!

Tool and scripts download: [http://www.mediafire.com/file/xgu5fus48 ... m.rar/file](http://www.mediafire.com/file/xgu5fus48fivpw2/MKXAnim.rar/file)

daemon1's MKX tools: [https://zenhax.com/viewtopic.php?t=851](https://zenhax.com/viewtopic.php?t=851)

Mortal Kombat 11

How to use
Mostly the same as the MKX tool. Umodel is replaced with daemon's tool.

1) Move python scripts to Noesis plugins folder
2) Extract models with daemon's tool. Important models are mostly in "GEAR_" files
3) Convert models to NUX using Noesis
4) Unpack the XXX file containing the animations. Mostly "_ScriptAssets" files
4.1) Dragging and dropping the XXX file on daemon's tool will unpack it and produce unp files
5) Drag and drop the unp file on MK11AnimUnpack. This will extract the animations
6 ) Load the NUX model in MK11Anim
7 ) Load the animation from the anim folder
8 ) Export the animated model as NUX
9 ) Preview/convert using Noesis

Old tutorial: [https://youtu.be/KcqxbsRcUqk](https://youtu.be/KcqxbsRcUqk)
Just watch like first half of it to see how to use daemon's tools and how to unpack animations. The rest is obsolete and should be done according to the new tutorial.

New tutorial: [https://youtu.be/NA1c1-poZZs](https://youtu.be/NA1c1-poZZs)
You should follow this for converting from SMD/MESH.ASCII to NUX and for scene building.

Tool and unpacker download: [https://www.mediafire.com/file/86pcyodn ... 1.rar/file](https://www.mediafire.com/file/86pcyodnpwyngtx/MK11Anim_Scene_U1.rar/file)

daemon1's MK11 tools: [viewtopic.php?t=20126](https://forum.xentax.com/viewtopic.php?t=20126)

Injustice 2

Same as MK11. Use this for unpacking IJ2 animations: [viewtopic.php?p=169251#p169251](https://forum.xentax.com/viewtopic.php?p=169251#p169251) Also use SMD, because MESH.ASCII doesn't have bone rotations.
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-01T18:41:02+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

Mortal Kombat 11 Support

Instructions on the first post.
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-12-01T20:22:09+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

If MK11 support is added, that means Injustice 2 is possible since is same as MK11
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-01T22:19:44+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

> Reply from mono24 ↑Wed Dec 02, 2020 4:22 am at Wed Dec 02, 2020 4:22 am
>
> 
If MK11 support is added, that means Injustice 2 is possible since is same as MK11

Indeed. The MK11 tool also works with Injustice 2. Same procedure using daemon's tools. Just use the attached animation unpacker instead. Thanks to mono24 for samples.


[IJ2AnimUnpack.rar](https://xentaxbackup.github.io/file/19114_IJ2AnimUnpack.rar)
## Post #5
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2020-12-02T03:36:36+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

I wonder if support for MK9, and MKvsDC animations will work

[https://drive.google.com/file/d/11faTYz ... sp=sharing](https://drive.google.com/file/d/11faTYze7fis2oRTcE1rTAIOFw8jNHgUv/view?usp=sharing)

[https://drive.google.com/file/d/1DsoNEw ... sp=sharing](https://drive.google.com/file/d/1DsoNEwA0cFZ6EADjRHzcfidvFGMDDB5-/view?usp=sharing)
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-02T09:18:50+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

> Reply from MarioSonicU ↑Wed Dec 02, 2020 11:36 am at Wed Dec 02, 2020 11:36 am
>
> 
I wonder if support for MK9, and MKvsDC animations will work
I think the first samples were MKvsDC. The animation data doesn't seem too complex, but the header and types deviate from MKX/MK11 standard. Needs a bit of research.

Second samples were very close to MKX. Just figuring out the bone mapping should be enough.

I will try to give them a try when I have the time.
## Post #7
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-12-02T18:46:30+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

I'm having problems exporting the animated NUX files of Injustice 2, everything is fine on the program but after the export noesis won't load it properly.
 EX: torso only -> load but has animation problem.
Full model: error "WARNING: Weight contains an out of range bone index. Discarding model."
Although Last error is not a problem, it was simply a comodity to have the full setup model in the viewer.

I Linked a few files if you want/can check. Thank you!

[*][http://www.mediafire.com/file/xyxb7m2jc ... el.7z/file](http://www.mediafire.com/file/xyxb7m2jcearhkb/Inj2Model.7z/file)
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-02T21:38:16+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

> Reply from Allanoon ↑Thu Dec 03, 2020 2:46 am at Thu Dec 03, 2020 2:46 am
>
> 
I'm having problems exporting the animated NUX files of Injustice 2

Thanks for reporting. There seems to be a bug when loading a secondary NUX. The tool will keep the bones of the first one. I will fix it for the next release. For now, just close and reopen the program after working on a NUX.

So torso works fine for me actually. But the hellboy still doesn't. Some bones are not animated. I am not sure if this has to do with unity, noesis, or these particular animations. Does hellboy work with any other animation?

Edit:
Ah shit, stupid mistake on my part. It is a miracle that the tool works as it is  I will release an update.
## Post #9
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2020-12-02T22:16:30+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

This looks very handy! Thanks a bunch for sharing.
## Post #10
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-02T22:31:12+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

Updated the MK11 tool. Should fix a huge bug.

[http://www.mediafire.com/file/p0c10zq2e ... 1.rar/file](http://www.mediafire.com/file/p0c10zq2exivnqz/MK11Anim_U1.rar/file)

> Reply from Straight Edge ↑Thu Dec 03, 2020 6:16 am at Thu Dec 03, 2020 6:16 am
>
> 
This looks very handy! Thanks a bunch for sharing.

No problem.
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-06T14:10:35+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

Prop Support

I am planning to change the tool logic, to support multiple models with different animation files. It should be possible to build a more complete scene. I will add this in the next update, along with some other fixes.



Blend Shape Animation

Also got the blend shape animations working, which are used for facial animations. Of course huge credits to daemon1, for making a tool that exports morphs. 

I am not sure how I will add this to the tool. Need to find a way to export blend shape animation somehow first. Also it will complicate the pipeline even more. So I am just thinking of adding it if people really think its useful.
## Post #12
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2020-12-06T17:56:13+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sun Dec 06, 2020 10:10 pm at Sun Dec 06, 2020 10:10 pm
>
> ...support multiple models with different animation files.
Amazing, that's what i am talking bout 

> Reply from akderebur ↑Sun Dec 06, 2020 10:10 pm at Sun Dec 06, 2020 10:10 pm
>
> So I am just thinking of adding it if people really think its useful.
Yes please, all the way.
## Post #13
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2020-12-06T22:14:44+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sun Dec 06, 2020 10:10 pm at Sun Dec 06, 2020 10:10 pm
>
> 
I am not sure how I will add this to the tool. Need to find a way to export blend shape animation somehow first. Also it will complicate the pipeline even more. So I am just thinking of adding it if people really think its useful.

These look incredible! I hope you add them, they'll be a ton useful for creating animations.
## Post #14
- Username: mk11fan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 18, 2020 6:32 am
- Post datetime: 2020-12-24T02:37:47+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

This is awesome. Great work akderebur.

Any chance to load textures to the animations too? 

Also (a bit off-topic) but do you know how to extract the unreadable data from the MKO files of MK11?
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-24T08:58:57+00:00
- Post Title: Mortal Kombat 11/X Animation Tool

> Reply from mk11fan ↑Thu Dec 24, 2020 10:37 am at Thu Dec 24, 2020 10:37 am
>
> 
Any chance to load textures to the animations too?
Über Winfrey was kind enough to share his MK shader, so I was playing around with textures a bit. Still, it requires some manual color input. Need to find a way to associate it with the color palette automatically. I will try to do some more research when I have the time.

> Reply from mk11fan ↑Thu Dec 24, 2020 10:37 am at Thu Dec 24, 2020 10:37 am
>
> 
how to extract the unreadable data from the MKO files of MK11?
No idea. I haven't checked those files.
## Post #16
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-25T19:44:52+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Multiple Meshes/Scene Support

Edit:
This version is obsolete. Check out this post: [viewtopic.php?p=170016#p170016](https://forum.xentax.com/viewtopic.php?p=170016#p170016)

Jade Fatal Blow
## Post #17
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2020-12-26T07:50:15+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

This looks great! Thanks very much for the update. Will you be adding the face animations as well in the future?
## Post #18
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-26T13:46:30+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Straight Edge ↑Sat Dec 26, 2020 3:50 pm at Sat Dec 26, 2020 3:50 pm
>
> 
Will you be adding the face animations as well in the future?
Some face animations should already work. The ones that use skeletal animation only.

If you mean the morph animations, I am planning to add support for them too. I don't know when though. Need to do a few more tests and find a good way to export/convert to some middle format.
## Post #19
- Username: mk11fan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 18, 2020 6:32 am
- Post datetime: 2020-12-26T22:27:43+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sat Dec 26, 2020 3:44 am at Sat Dec 26, 2020 3:44 am
>
> 
Multiple Meshes/Scene Support

- Switched to mesh.ascii for future morph support. DON'T use SMD.
- You will still convert them to NUX though, before loading into the animation tool
- Use the included "fmt_nxps_0_9_6.py" script for mesh.ascii. I have made a change related to rotations.

The new version requires some more user input for building the scene. Better watch the tutorial video: https://www.youtube.com/watch?v=r98eqdDYfps

Tool Download: https://www.mediafire.com/file/iyfb9jxx ... e.rar/file

Jade Fatal Blow

Many thanks for the updates on this tool.

One remark though. Now we are using the mesh.ascii format and composing our model with several nux-exported-mesh.ascii objects. However, some objects, like Krypt Ermac exist in one single mesh.ascii or smd file.

In the previous version of your tool, using the ERM_01_smd.nux would work properly with the CAS_Supermove.AnimSequence.

With the recent version, using the ERM_01.mesh.nux with the same animation, will produce a skewered animation. 



Any chance to fix that?

Thanks again for your great work! Following with interest.
## Post #20
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-26T23:16:00+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from mk11fan ↑Sun Dec 27, 2020 6:27 am at Sun Dec 27, 2020 6:27 am
>
> 
Any chance to fix that?
I don't seem to have "ERM" in my game files. If you can send the mesh.ascii file I can take a look. However, I was able to use different anims with different chars. Tried "CAS_Supermove" with Erron and it worked fine. Of course, I haven't tested all.

Make sure you use this version of daemon's tool: [viewtopic.php?p=152964#p152964](https://forum.xentax.com/viewtopic.php?p=152964#p152964) And also make sure you are using Noesis scripts included in the rar. If you had previous mesh.ascii scripts for example remove them.

Edit:
I will also bring back SMD support anyway for Injustice 2. It looks like mesh.ascii doesn't have rotations for that game. So if you can't make it work, you can use the SMD again worst case. I will probably release the update tomorrow.
## Post #21
- Username: mk11fan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 18, 2020 6:32 am
- Post datetime: 2020-12-26T23:39:35+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sun Dec 27, 2020 7:16 am at Sun Dec 27, 2020 7:16 am
>
> 
mk11fan wrote: ↑Sun Dec 27, 2020 6:27 am
Any chance to fix that?

(...)
And also make sure you are using Noesis scripts included in the rar. If you had previous mesh.ascii scripts for example remove them.
(...)

You are correct. I was using a nux file that had been generated with the previous scripts. It worked well after generating a NUX model with the new scripts.

Thanks!

Edit: Krypt Ermac files here - [https://www.dropbox.com/s/nhwo7141kggvy ... i.rar?dl=1](https://www.dropbox.com/s/nhwo7141kggvy1i/MK11_Krypt_Ermac_Smd-Mesh-Ascii.rar?dl=1) You can extract them from the BGND_Krypt_ShangTsungIsland.(PSF || XXX) files.
## Post #22
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2020-12-27T10:07:12+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Hello!

Realy nice work! i like to see the ingame animations:)

One big question, now is possible export the 3D modells - in base stand pose, and we can visualise the animation of the 3D modell, but possible somehow export a one state of the 3D modell in one animation phase\step example as 3D modell? or import animation into blender to giving ,,live" to a basic standing pose 3D modell?

Example sub zero victory pose ice clone animation.

thank you
## Post #23
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-27T10:53:20+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Omegared ↑Sun Dec 27, 2020 6:07 pm at Sun Dec 27, 2020 6:07 pm
>
> 
import animation into blender to giving ,,live" to a basic standing pose 3D modell?

Example sub zero victory pose ice clone animation.
You can already import the animations into Blender. After getting them in Noesis, you can export them to any format. For example fbx or dae. Then you can load them in Blender.

I am not sure how well Sub-zero would look though. Most of his animations seem to have ice visual fx. The character motion would be there, but not the ice.
## Post #24
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2020-12-27T11:39:33+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

thank you for the fast answer.

I dont want do any complex work, i will feel myself lucky if i can change the standing pose. 

After extract sub zero file, all suit design have separate 3d modell, like as mask and weapons, and face, eyes. So in blender i can ,,build" from these my unique variant of sub zero.

Final goal will, because the original suit modells having base standing position, change this standing pose into a victory -> one hand down other hand in the air. Texture not important, because i want print this victory pose.



11.jpg (70.11 KiB) Viewed 318 times
## Post #25
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2020-12-27T13:36:58+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

I have followed the tutorial, but animation wont start, or i get glitch on face :/

KITpa_Story.nux + Idle.AnimSequence result:



test.jpg (56.41 KiB) Viewed 309 times



Im not expert in these apps, i dont know how i can export *..AnimSequence animation for blender in noesis:(
## Post #26
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2020-12-27T23:13:10+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sat Dec 26, 2020 9:46 pm at Sat Dec 26, 2020 9:46 pm
>
> 
Straight Edge wrote: ↑Sat Dec 26, 2020 3:50 pm
Will you be adding the face animations as well in the future?

Some face animations should already work. The ones that use skeletal animation only.

If you mean the morph animations, I am planning to add support for them too. I don't know when though. Need to do a few more tests and find a good way to export/convert to some middle format.

Thanks very much! I hope you manage with adding morph animation support. Appreciate all the hard work.
## Post #27
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2020-12-28T03:38:44+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

akderebur, I want to Thank you for the wonderful Animation tools you created here, They are actually a big reason why I decided to go ahead and Purchase MK11 and IJ2 recently

I was wondering if it was possible to add Batch export for the nux noesis script?

I tried to do it through Noesis batch process tool but it defaulted to .obj files and since there are hundreds of morphs in both these games, I think it would be very useful for a Nux batch process 

EDIT: I probably should have stated my goal is to visualize all morphs and animations in Blender, and I was assuming I will need all files in Nux for the animations and morphs to work together and then export from your tool , maybe I'm looking at it the wrong way, please correct me If I'm completely not seeing this

Thanks again for your great work
## Post #28
- Username: RuV9999
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 19, 2019 11:00 pm
- Post datetime: 2020-12-28T07:54:40+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

How can i transfer the animation data into my model bones in blender. it looks really weird after i transfer it. it seems broken.
## Post #29
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-28T12:17:41+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Modman69 ↑Mon Dec 28, 2020 11:38 am at Mon Dec 28, 2020 11:38 am
>
> 
 I was assuming I will need all files in Nux for the animations and morphs to work together
Actually, the idea was to use NUX + mesh.acii for morphs. You load base face mesh in NUX and morphs will be loaded directly from mesh.ascii. Otherwise, it would be too much work like you said.

I was thinking of directly switching to SMD/mesh.ascii for loading and using NUX just for export. This would remove the extra step of converting to NUX at the start, but it also means I need to code 2 more format importers for the tool. So maybe I can convert "tool_nux" into a proper export script and you could then use the batch process in Noesis. I also have some plans to batch load/export anims, but need to think of an easy way to present it.

> Reply from RuV9999 ↑Mon Dec 28, 2020 3:54 pm at Mon Dec 28, 2020 3:54 pm
>
> 
How can i transfer the animation data into my model bones in blender. it looks really weird after i transfer it. it seems broken.
If your existing model isn't exported from my tool then it wouldn't work probably. Daemon's tool seems to stick with the game's original coordinate system. I convert it to Unity's while loading and then to Noesis's at export. So if the model and animations don't agree on the same coordinate system it would look broken.
## Post #30
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2020-12-28T15:16:08+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Mon Dec 28, 2020 8:17 pm at Mon Dec 28, 2020 8:17 pm
>
>  

Actually, the idea was to use NUX + mesh.acii for morphs. You load base face mesh in NUX and morphs will be loaded directly from mesh.ascii. Otherwise, it would be too much work like you said.

I was thinking of directly switching to SMD/mesh.ascii for loading and using NUX just for export. This would remove the extra step of converting to NUX at the start, but it also means I need to code 2 more format importers for the tool. So maybe I can convert "tool_nux" into a proper export script and you could then use the batch process in Noesis. I also have some plans to batch load/export anims, but need to think of an easy way to present it.

Thank you for the reply I look forward to all your tools nowadays, keep up the awesome work please
## Post #31
- Username: mk11fan
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Sep 18, 2020 6:32 am
- Post datetime: 2020-12-28T17:18:22+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Do you know where to find the animations for the brutalities and stage brutalities?

Also, someone using your method found a few krypt animations that are not in the game. [https://www.youtube.com/watch?v=uMNuG5sbk10](https://www.youtube.com/watch?v=uMNuG5sbk10)

Pretty cool.
## Post #32
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2020-12-31T04:39:52+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Wed Dec 02, 2020 6:19 am at Wed Dec 02, 2020 6:19 am
>
> 
mono24 wrote: ↑Wed Dec 02, 2020 4:22 am
If MK11 support is added, that means Injustice 2 is possible since is same as MK11 


Indeed. The MK11 tool also works with Injustice 2. Same procedure using daemon's tools. Just use the attached animation unpacker instead. Thanks to mono24 for samples.

Is there and update for Injustice2 Anim Unpack to be compatible with Multiple Meshes/Scene Support due to the change related to rotations?
## Post #33
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-12-31T23:38:56+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Injustice 2 Support and Improvements

- New NUX script for batch processing in Noesis. Removed the tool script.
- Bulk animation load/export. This will export all the animations in the selected folder.
- Bulk animation will work with a single group of meshes (merged). It might take a long time also.
- Both SMD and MESH.ASCII should work now when converted to NUX. So IJ2 is supported using SMD.

New Tutorial (just used batch processing at start): [https://youtu.be/NA1c1-poZZs](https://youtu.be/NA1c1-poZZs)

Tool Download:  [https://www.mediafire.com/file/86pcyodn ... 1.rar/file](https://www.mediafire.com/file/86pcyodnpwyngtx/MK11Anim_Scene_U1.rar/file)

IJ2 Animation
## Post #34
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2021-01-01T05:47:09+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Fri Jan 01, 2021 7:38 am at Fri Jan 01, 2021 7:38 am
>
> 
Injustice 2 Support and Improvements

- New NUX script for batch processing in Noesis. Removed the tool script.
- Bulk animation load/export. This will export all the animations in the selected folder.
- Bulk animation will work with a single group of meshes (merged). It might take a long time also.
- Both SMD and MESH.ASCII should work now when converted to NUX. So IJ2 is supported using SMD.

New Tutorial (just used batch processing at start): https://youtu.be/NA1c1-poZZs

Tool Download:  https://www.mediafire.com/file/86pcyodn ... 1.rar/file

IJ2 Animation

Thank you so much. I will try at this moment and happy new year!!
## Post #35
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2021-01-01T15:53:21+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

INCEDIBLE JOB! Thank You so much for all you do here
## Post #36
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2021-01-05T02:56:56+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sun Dec 06, 2020 10:10 pm at Sun Dec 06, 2020 10:10 pm
>
> 
Blend Shape Animation

Also got the blend shape animations working, which are used for facial animations. Of course huge credits to daemon1, for making a tool that exports morphs. 

I am not sure how I will add this to the tool. Need to find a way to export blend shape animation somehow first. Also it will complicate the pipeline even more. So I am just thinking of adding it if people really think its useful.

I'm so excited to see how you resolved blend shape animations. This tools are so inspirational to me, thanks a lot.
## Post #37
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2021-01-06T19:22:24+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

I have started several times the new mk11 tutorial but something still not ok. 

I have used for start:

GEARASSETS_CAS_ScriptAssets.XXX and however was not clear and i have missed from tutorial video: CHAR_CAS_ScriptAssets.XXX both with PSF pair.

As beginner for me not was clear what i need include in dir, after i have added all ascii SMD file pair:

CAS_FACE_A.mesh.ascii
CAS_GEAR_A_001_Pistol.mesh.ascii
CAS_HAIR_A.mesh.ascii
CAS_SKIN_A.mesh.ascii

All 4 file converted\exported into nux, loaded without gun (everything looks ok modell visible in base pose) after loading CAS_Supermove.AnimSequence

and....modell looks flipped and playing inverse the animation 

Whats wrong?

From where i know what SMD\ASCIII i need for animation? example for sub zero classic victory pose? 

Still question after i see the animation, how can i export in a pose or this is not possible currently? Export nux looks loading, but i get no dialog window.



notgood.jpg (48.96 KiB) Viewed 281 times



thanks for the help and for the work
## Post #38
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-01-06T21:01:16+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Omegared ↑Thu Jan 07, 2021 3:22 am at Thu Jan 07, 2021 3:22 am
>
> 
I have started several times the new mk11 tutorial but something still not ok.
I can't say for sure what the problem is. First of all make a clean start. Delete all the plugin, tool versions you have. Download and use the ones in this post: [viewtopic.php?p=170016#p170016](https://forum.xentax.com/viewtopic.php?p=170016#p170016) Also, make sure to watch the new tutorial in the same post. If mesh.ascii still doesn't work try smd. It doesn't make any difference atm.

I have tried to explain it as well as I can, but I see that it might be hard to understand, especially if you are not used to this stuff.
## Post #39
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2021-01-06T21:21:53+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

I had issues with rotation also but I think the same as akderebur, reset the noesis plugins and reinstall new ones, export using the noesis options and the use the last animation tools.
## Post #40
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2021-01-06T21:53:36+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

With SMD working face+hair+skin with CAS_Supermove.AnimSequence.

Checking the forum topics looks littlebit chaotic where can find anything:) maybe just one description with tutorial :>

I dont know how can i reset noesis.

Ok, now i see a 3x nux as modell and moving - there is any way use one animation phase\pose and export as 3D modell?

Now i can reproduce im sure in blender same modell with these nux-es, just stay in base pose.

My final goal will be if i can move a modell in a victory pose and ,,freeze" as 3D modell.

thanks for any help



kép_2021-01-06_225749.png (209.62 KiB) Viewed 260 times
## Post #41
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2021-01-06T23:18:47+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Omegared ↑Thu Jan 07, 2021 5:53 am at Thu Jan 07, 2021 5:53 am
>
> 
Ok, now i see a 3x nux as modell and moving - there is any way use one animation phase\pose and export as 3D modell?

Export as NUX and convert in FBX with Noesis then import in Blender
## Post #42
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2021-01-07T07:52:48+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

thank you for the help, before try one question. 

After export to nux (if im godd understand with the anim app), i will receive a new file, or the source files will be ,,updated"?

Modell loaded with animation / moving in a loop. In what position will be exported?
## Post #43
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-01-07T09:41:10+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Omegared ↑Thu Jan 07, 2021 3:52 pm at Thu Jan 07, 2021 3:52 pm
>
> 
In what position will be exported?
It won't be exported in a specific pose, it is an "animation". It is a collection of poses/frames. You can play the animation in Blender and stop at any frame you want, so you have a specific pose.

These are really beyond the scope of the tool and related to 3D software knowledge. I suggest you do some research on Blender animation playback and 3D animation concept in general.
## Post #44
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2021-01-07T10:15:31+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

I have asked these questions, because the current aviable information not giving answer to me what for we can use this app. Simple just play mk11 animations with 3D modell or more? In this case we can say, just play the assembled 3D modell what have skeleton\animation, not more, not less.

Just one question remains inside me, with the export feature of nux what changing?

thank you for the answers
## Post #45
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-01-07T10:34:19+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Omegared ↑Thu Jan 07, 2021 6:15 pm at Thu Jan 07, 2021 6:15 pm
>
> 
what for we can use this app.
It is for extracting animations from the game. What you do with them is up to you. I can't go and tell you how to use the animations. Everyone has different uses. Study them, use them in a fan-made clip, etc.

> Reply from Omegared ↑Thu Jan 07, 2021 6:15 pm at Thu Jan 07, 2021 6:15 pm
>
> 
Simple just play mk11 animations with 3D modell or more? 

Just one question remains inside me, with the export feature of nux what changing?

You are missing the whole point of the tool. Playing the animations in the tool isn't the deal, it is just meant as a preview. The aim is to export them to NUX and convert to a widely used format like FBX or DAE. Then use it in a 3D software.

No offense, but if you don't know what to achieve by using this tool, why are you trying to use it in the first place?
## Post #46
- Username: Omegared
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Dec 27, 2020 6:00 pm
- Post datetime: 2021-01-07T10:57:57+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

In a mksecrets forum pointed somebody here to check with title  ,,How to extract and visualize MK11 animations" 

Sorry if im understand this as is and not understand your ,,expert" level description. 

No offense im not developer, but i will make better desciption to prevent ,,primitive" questions like you if you not like answer.

Sorry to disturb with my idiot questions and tryed out your app...
## Post #47
- Username: nostalgic
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jul 07, 2018 11:24 am
- Post datetime: 2021-01-19T18:50:43+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

something is going wrong when exporting, or in the noesis plugin, or MKX animation,
note that after the retarget all animations work, after i get an extract from the game, so that stick stick in the root.

video: [https://youtu.be/VKUra_p4AKw](https://youtu.be/VKUra_p4AKw)
## Post #48
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2021-02-17T00:04:21+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

I know there are a few taunts in the CHAR_*Character Name* anims but does anybody know where the rest are?
## Post #49
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2021-02-20T01:31:53+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sun Dec 06, 2020 10:10 pm at Sun Dec 06, 2020 10:10 pm
>
> 
Blend Shape Animation

Also got the blend shape animations working, which are used for facial animations. Of course huge credits to daemon1, for making a tool that exports morphs. 

I am not sure how I will add this to the tool. Need to find a way to export blend shape animation somehow first. Also it will complicate the pipeline even more. So I am just thinking of adding it if people really think its useful.

Hey akderebur, any updates on the facial animations incorporated into the tool?
## Post #50
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-02-21T00:06:11+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Straight Edge ↑Sat Feb 20, 2021 9:31 am at Sat Feb 20, 2021 9:31 am
>
> 
Hey akderebur, any updates on the facial animations incorporated into the tool?
It is almost ready: [https://youtu.be/p5Xk2C37lBk](https://youtu.be/p5Xk2C37lBk)

I am doing some final test to make sure it doesn't break keyframe animations. Also I am not sure about the export pipeline, but I will probably export it as vertex animation. Anyway it should be done some time soon.
## Post #51
- Username: Straight Edge
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Oct 06, 2014 12:15 am
- Post datetime: 2021-02-26T11:28:41+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Looks amazing so far! Thanks for continuing to work on it.
## Post #52
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2021-03-13T18:03:46+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Hey akderebur, thanks for your Mortal Kombat 11/X Animation Tool.

I noticed that your tool does not load .AnimSequence files that contain disk.animations.characters.scorpion.expressions at the beginning of the file - all files extracted from GEARASSETS_SCO_ScriptAssets.XXX plus some files extracted from CHAR_SCO_ScriptAssets.XXX (e.g. 
 attack2.AnimSequence). Do you plan to support them?

UPD: Well it looks like these are the facial animation files on which you are currently working.

PS: Does anyone know where I can find Scorpion's run animation?

Kind regards
RedBear
## Post #53
- Username: qbnw
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Feb 27, 2019 7:57 pm
- Post datetime: 2021-03-31T06:53:06+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Is there a way to preview brutality/fatality?
## Post #54
- Username: MisterNatal
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Sep 02, 2014 9:53 am
- Post datetime: 2021-04-14T21:18:39+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Did some research and asking around and found that the other animations and newer files are stored in the PSF files, any chance of getting the tools able to extract the files stored in there?
## Post #55
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-15T10:12:35+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Morph Support

Only one morphed model (face) should exist in the scene and it should be loaded first. You can load any other model (body) you want on top of it. Noesis handles the morph animation, but after it's exported to FBX I found out that 3D software doesn't load it as an animation. I have included a Blender helper script for it. Also shown in the tutorial below.

I did everything from scratch in the morph tutorial. I think the workflow will be clearer after you watch it. I have updated the NUX script, make sure to use the new one. Or better yet, just delete all the old scripts/tools and use the ones that come with this download.

Morph Tutorial : [https://youtu.be/9gsRLEA8hqk](https://youtu.be/9gsRLEA8hqk)

Tool Download:  [https://www.mediafire.com/file/9cktgai8 ... h.rar/file](https://www.mediafire.com/file/9cktgai8iamk9pm/MK11Anim_Morph.rar/file)

Jacqui Face Animation


> Reply from MisterNatal ↑Thu Apr 15, 2021 5:18 am at Thu Apr 15, 2021 5:18 am
>
> 
newer files are stored in the PSF files, any chance of getting the tools able to extract the files stored in there?
Normally the files/data is compressed and I am relying on daemon's tools for getting the unpacked data (unp files). I think you suggest that some animations aren't in these unp files and that's why MK11AnimUnpack can't extract them, right? If that is the case tell me the PSF files that should have the animations and I might take a look. We better discuss this over PM.
## Post #56
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-04-23T19:58:36+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Experimenting with materials/textures. I was able to load the base color variants automatically using the texture masks and palettes. There is certainly more stuff going on, but I don't have the time or knowledge to figure out shader calculations. Seeing the base colors isn't half bad for preview purposes.
## Post #57
- Username: RedBear
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Feb 26, 2017 11:40 am
- Post datetime: 2021-05-03T09:14:18+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Sat Apr 24, 2021 3:58 am at Sat Apr 24, 2021 3:58 am
>
> 
Experimenting with materials/textures. I was able to load the base color variants automatically using the texture masks and palettes. There is certainly more stuff going on, but I don't have the time or knowledge to figure out shader calculations. Seeing the base colors isn't half bad for preview purposes.Hey akderebur!
Do I have a chance to get the same results in Photoshop? How can I do this?
## Post #58
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-05-03T13:18:26+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from RedBear ↑Mon May 03, 2021 5:14 pm at Mon May 03, 2021 5:14 pm
>
> 
Do I have a chance to get the same results in Photoshop? How can I do this?
I am not sure as I don't know photoshop too well. I have done it programmatically, but let me tell the process in general. Maybe you can achieve it some way. The idea is to use the ACID (color id) and CPT (color palette) textures to get the base colors. RGB channels of the ACID are all the same, so it doesn't matter what channel you use. As you know the values go from 0 - 255 for a single channel. From what I see these values are actually indices to the palette texture.

When I select a shirt region from Harley's ACID texture with color picker I see that the value is 88. 



I open the default palette texture and look at the pixel 88. You can see that it is a red color which is actually correct.



When you color the whole texture based on that you get a color texture basically. Then you can probably add it as an overlay layer to diffuse texture.



You can just change the palette and get the alternate colors.



As you can see it gets more or less the correct colors. Even though I believe that this is the core idea, there is more going on. When you make a color texture like this you are using just a couple of colors out of 512 colors in the palette. Also, there is no way to get any pixel above 255 this way. So, there is probably some way to reference other colors or maybe they are used as a gradient/tone of the base color. I don't know atm.
## Post #59
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2021-05-22T22:18:13+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Will this tool be updated to support MK vs. DCU and MK9?
## Post #60
- Username: jojox1000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 09, 2019 9:53 am
- Post datetime: 2021-09-21T22:34:19+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

hello i have a problem when i load an animation for anyone its messes up the model
## Post #61
- Username: Delbozkester
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 17, 2011 9:29 pm
- Post datetime: 2021-09-30T04:52:53+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Thu Apr 15, 2021 6:12 pm at Thu Apr 15, 2021 6:12 pm
>
> 
Morph Support

Only one morphed model (face) should exist in the scene and it should be loaded first. You can load any other model (body) you want on top of it. Noesis handles the morph animation, but after it's exported to FBX I found out that 3D software doesn't load it as an animation. I have included a Blender helper script for it. Also shown in the tutorial below.

I did everything from scratch in the morph tutorial. I think the workflow will be clearer after you watch it. I have updated the NUX script, make sure to use the new one. Or better yet, just delete all the old scripts/tools and use the ones that come with this download.

Morph Tutorial : https://youtu.be/9gsRLEA8hqk

Tool Download:  https://www.mediafire.com/file/9cktgai8 ... h.rar/file

Jacqui Face Animation

MisterNatal wrote: ↑Thu Apr 15, 2021 5:18 am
newer files are stored in the PSF files, any chance of getting the tools able to extract the files stored in there?

Normally the files/data is compressed and I am relying on daemon's tools for getting the unpacked data (unp files). I think you suggest that some animations aren't in these unp files and that's why MK11AnimUnpack can't extract them, right? If that is the case tell me the PSF files that should have the animations and I might take a look. We better discuss this over PM.

Some one was tested this tool on IJ2? because I tried but I didn't have success, but I don't understand my error, even simples anim without morph didn't run
## Post #62
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2021-09-30T08:02:06+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from Delbozkester ↑Thu Sep 30, 2021 12:52 pm at Thu Sep 30, 2021 12:52 pm
>
> 
Some one was tested this tool on IJ2? because I tried but I didn't have success, but I don't understand my error, even simples anim without morph didn't run

Morph tool is for MK11 only. Try this for IJ2: [viewtopic.php?p=170016#p170016](https://forum.xentax.com/viewtopic.php?p=170016#p170016)
## Post #63
- Username: Tekkamanchronos
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Aug 24, 2015 1:50 am
- Post datetime: 2022-01-23T02:23:43+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

I've watched the tutorial and followed along, but when I get to cut.bat part of the tutorial the program crashes, and continues to go down the line crashing and nothing is created.
Can someone help me get over this error? is there a version of MkX I should be using, I used the PC steam version.
The same for MK11.
## Post #64
- Username: AlexDDK
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Apr 12, 2022 7:56 am
- Post datetime: 2022-04-17T01:54:37+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Followed step by step tutorial, but it wont load a nux model in unity with morph option? Any ideas how to fix?
## Post #65
- Username: dan2033
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 27, 2022 6:33 am
- Post datetime: 2022-06-27T00:26:54+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Hi everyone! Can anybody help me? When I try to turn .obj model to .nux , it doesn't work, nothing happens. On the other hand, it's done and I would like to load model to a program but nothing happens
## Post #66
- Username: Augusto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 13, 2022 1:23 am
- Post datetime: 2022-10-12T17:33:20+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

> Reply from akderebur ↑Wed Dec 02, 2020 5:18 pm at Wed Dec 02, 2020 5:18 pm
>
> 
MarioSonicU wrote: ↑Wed Dec 02, 2020 11:36 am
I wonder if support for MK9, and MKvsDC animations will work

I think the first samples were MKvsDC. The animation data doesn't seem too complex, but the header and types deviate from MKX/MK11 standard. Needs a bit of research.

Second samples were very close to MKX. Just figuring out the bone mapping should be enough.

I will try to give them a try when I have the time.

Hey guys,
I am late to the conversation but I'd like to use this feature as well and I am willing to collaborate with the team.
Is the source code available?
If you point me in the right direction I can give it a try and maybe we get MK9 animations working.
## Post #67
- Username: Tanishq
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 14, 2022 8:56 pm
- Post datetime: 2022-10-19T09:22:23+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

as soon as I Import the nux file into the MK11_Anim tool to attach animation, It freezes and then crashes .
Help me
## Post #68
- Username: kayhotic
- Rank: n00b
- Number of posts: 16
- Joined date: Sat May 16, 2020 12:50 pm
- Post datetime: 2023-03-24T02:30:00+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

has anyone found the animations for scorpion's spear model? none of Scorp's animations work on it.
## Post #69
- Username: autolab
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Nov 25, 2018 8:54 am
- Post datetime: 2023-04-23T11:45:00+00:00
- Post Title: Re: Mortal Kombat 11/X Animation Tool

Hi. 

First, thanks to the creator of this great tool.
I know this is an old thread but I will post my question.

I've tried to extract anim form the game and mostly all anims are extracted and works fien. Nevertheless I think there is an issue when multiple names exists in those anims files. When the unp extracts it will only retrieve one of those names but count all the existing entries. For example:

JOHN End of Round Taunts:
1 - After extract .xxx (.export.txt file)
C7	A206C4	B0DE	->19C	EndOfRound_Winner_Taunt_1.AnimSequence
1C8	A2B7A2	13542	->19C	EndOfRound_Winner_Taunt_2.AnimSequence
1C9	A3ECE4	58F6	->19C	EndOfRound_Winner_Taunt_2_JOH_Sunglasses_A.AnimSequence
1CA	A445DA	A19E	->19C	EndOfRound_Winner_Taunt_2_JOH_Sunglasses_A_2ndPair.AnimSequence
1CB	A4E778	7D176	->19C	EndOfRound_Winner_Taunt_3.AnimSequence
1CC	ACB8EE	9272	->19C	EndOfRound_Winner_Taunt_3_JOH_Marker_A.AnimSequence
1CD	AD4B60	13532	->19C	EndOfRound_Winner_Taunt_3_JOH_Picture_A.AnimSequence
1CE	AE8092	80FDA	->19C	EndOfRound_Winner_Taunt_4.AnimSequence
1CF	B6906C	917A	->19C	EndOfRound_Winner_Taunt_4_JOH_Beeper_A.AnimSequence
1D0	B721E6	10C46	->19C	EndOfRound_Winner_Taunt_5.AnimSequence
1D1	B82E2C	70AC2	->19C	EndOfRound_Winner_Walkaway_1.AnimSequence
1D2	BF38EE	AFC4A	->19C	EndOfRound_Winner_Walkaway_2.AnimSequence
1D3	CA3538	17F92	->19C	EndOfRound_Winner_Walkaway_3.AnimSequence
1D4	CBB4CA	13346	->19C	EndOfRound_Winner_Walkaway_4.AnimSequence
1D5	CCE810	AE8A	->19C	EndOfRound_Winner_Walkaway_4_JOH_BoomMic_A.AnimSequence
1D6	CD969A	1187E	->19C	EndOfRound_Winner_Walkaway_5.AnimSequence

2 - The unp extracts:
EndOfRound_Winner_Taunt
EndOfRound_Winner_Taunt
EndOfRound_Winner_Taunt_2_JOH_Sunglasses_A
EndOfRound_Winner_Taunt_2_JOH_Sunglasses_A_2ndPair
EndOfRound_Winner_Taunt
EndOfRound_Winner_Taunt_3_JOH_Marker_A
EndOfRound_Winner_Taunt_3_JOH_Picture_A
EndOfRound_Winner_Taunt
EndOfRound_Winner_Taunt_4_JOH_Beeper_A
EndOfRound_Winner_Taunt
EndOfRound_Winner_Walkaway
EndOfRound_Winner_Walkaway
EndOfRound_Winner_Walkaway
EndOfRound_Winner_Walkaway
EndOfRound_Winner_Walkaway_4_JOH_BoomMic_A
EndOfRound_Winner_Walkaway

It shows all number of the Taunts and Walkaway entries but only one of those is written, the other 4 (4 for Taunt and 4 for Walkway) are discarded.

I am asking if the author could make some changes to the unpack anim executable to handle this. It would be very nice to have those End of the Round anim files.

I'll leave here the link to JOH files (xxx, psf and unp): [https://mega.nz/file/oh1gzDrC#ZTABp_7mx ... _bvfZDppgQ](https://mega.nz/file/oh1gzDrC#ZTABp_7mxRCoEAb3CXF7OkHJl8uAXm8Wx_bvfZDppgQ)

Thanks!
