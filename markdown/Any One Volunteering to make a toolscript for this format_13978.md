## Post #1
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-16T06:47:26+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

It has always been my aspiration to learn 3d model reversing.I have zero knowledge about 3D Modes as of now.I've decided to explore the model file of WWF RAW,I've modded RAW For many years before i stepped onto SVR and 2K.I will post any information i know about the format here.
As of now here is what i know,the game has 3 different model files for each wrestler.
C0XXH.FML
C0XXL.FML
C0XXM.FML
These files are located inside the character folder inside FF.XPK File.You'll require XPKGUI.exe to open and extract game files.

Where XX-Stands for the Wrestler/Character ID
H-High Poly Version of the model for inring
L-Low poly version of the model,when the wrestler is viewed far away
M-Medium Poly Model.

The model file has a small header,after the header it has a TOC(Table of Contents) which has the names of objects inside the model which includes the bones.The TOC doesn't contain any offsets to indicate their starting positions.However the data starts with the object name.
The model file contains 9 different head objects for different facial expressions
n_Head-Normal Head
The ones from H_HEAD00->H_HEAD07(Are for different facial expressions,for example for open mouth,closed eyes etc)
Although they have removed blood from the game just before release,the model file does have 5 separate head objects for blood animations.
n_BLOOD
BLOOD00->BLOOD05
When its time for the wrestler to bleed a red flash appears on the screen to indicate that the wrestler starts to bleed,however the wrestler doesn't bleed.What i believe is that they have taken out the U-V Mappings off the blood objects.

After the TOC,The material assignments begin.
just after the material assignments,the list of textures used have been listed.
After the texture listing begins the bones/armature.

n_CTR
o_body
j_chest
o_sako_l
j_u_arm_l
j_f_arm_l
HAND_L
o_sako_r
u_arm_r
j_f_arm_r
HAND_R
j_neck_a
j_neck
n_waist_b
j_thigh_l
j_leg_l
L_FOOT
j_thigh_r
j_leg_r
R_FOOT
Just after the end of bones begins the mesh data which is named after the corresponding body part which begins with
H_SKIN
n_HANDL
H_HANDL00->H_HANDL21
H_HANDR00->H_HANDR21
H_HANDL00
n_BLOOD
BLOOD00->BLOOD05
n_head
H_HEAD00->H_HEAD07

Each object contains the mesh data,UV-Data,faces,vertices,face indices and so on.I have attached a sample model file of The Rock below
[https://archive.org/download/TheRock_20 ... e_Rock.rar](https://archive.org/download/TheRock_201602/The_Rock.rar)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-18T20:03:15+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

last submesh (head) in 000H.FML, each submesh is clearly separated in the file


the test previews don't render backfaces but you can unify the normals in Blender after saving the mesh


h2o

```
Vb1
43 28
0xE05EF 576
021000
0x0 255
```
## Post #3
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-19T02:09:18+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from AceWell
>
> last submesh (head) in 000H.FML, each submesh is clearly separated in the file


the test previews don't render backfaces but you can unify the normals in Blender after saving the mesh


h2o
Code: Select all0xE66B1 1568
Vb1
43 28
0xE05EF 576
021000
0x0 255
Could you possibly write a max script/blender script to handle these models.I'm willing to pay an amount if you do.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-02-19T02:50:28+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

Sorry man i'm not a programmer, thats not what i do, and if i could program i sure wouldn't do this for money, everything i do here is for fun and just a hobby.
I posted the H2O example because i saw your post in the tutorial thread and thought i'd take some of the load off shakotay because he is probably a busy guy.
## Post #5
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-20T11:30:22+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

If anyone who knows maxscript or blender scripting and is free,could you please script an import export script for this format.I have posted all the details i know here
[viewtopic.php?f=16&t=13978](http://forum.xentax.com/viewtopic.php?f=16&t=13978)

Sample Model Files
[https://archive.org/download/TheRock_20 ... e_Rock.rar](https://archive.org/download/TheRock_201602/The_Rock.rar)
## Post #6
- Username: eri619
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-20T19:49:56+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

I've been looking at this format for you. I've gotten pretty far except there are some issues with the vertices. Looks like multiple vertex formats however, I cannot see a flag of some sort to distinguish between specific vertex types. Very strange, maybe it's stored in another file, are there any other files?
## Post #7
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-21T04:49:47+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from Gh0stBlade
>
> I've been looking at this format for you. I've gotten pretty far except there are some issues with the vertices. Looks like multiple vertex formats however, I cannot see a flag of some sort to distinguish between specific vertex types. Very strange, maybe it's stored in another file, are there any other files?

Here are all the model files,also could you record a video while analysing the model and writing max/blender scripting so that i could learn tricks of the trade 
If you know blender script,i'd suggest writing it,or if you don't know that then do it over max script.I recommend blender because its the easiest tool to work around with.

[https://app.box.com/s/dsd5zaizx5qlwrqlda23jisa92th63sk](https://app.box.com/s/dsd5zaizx5qlwrqlda23jisa92th63sk)
## Post #8
- Username: eri619
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-21T13:47:09+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

I'm actually writing a Noesis importer script.

Anyhow, the entire format is terribly hacky or I'm mis-understanding this.
If we take a look at the bone hierarchy here: [Clicky - 000H.FML](http://pastebin.com/VPz1Fq4L)
The last "L_SKIN" bone is parented to nothing which makes no sense at all. So this breaks my bone loading code....

I'm going to take a look at loading the vertex buffers again but this format is very weird/hacky.
## Post #9
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-21T13:51:16+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from Gh0stBlade
>
> I'm actually writing a Noesis importer script.

Anyhow, the entire format is terribly hacky or I'm mis-understanding this.
If we take a look at the bone hierarchy here: Clicky - 000H.FML
The last "L_SKIN" bone is parented to nothing which makes no sense at all. So this breaks my bone loading code....

I'm going to take a look at loading the vertex buffers again but this format is very weird/hacky.

Great progress man,my doubt is whether its possible to edit the model and import the edited mesh back into the model,is it possible using noesis?
## Post #10
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-23T16:59:21+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from Gh0stBlade
>
> I've been looking at this format for you. I've gotten pretty far except there are some issues with the vertices. Looks like multiple vertex formats however, I cannot see a flag of some sort to distinguish between specific vertex types. Very strange, maybe it's stored in another file, are there any other files?

@Ghostblade any update buddy?

You can find me here
[http://s15.zetaboards.com/legendsofmodding/index/](http://s15.zetaboards.com/legendsofmodding/index/)
## Post #11
- Username: eri619
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-23T17:37:46+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from eri619
>
> Gh0stBlade wrote:I've been looking at this format for you. I've gotten pretty far except there are some issues with the vertices. Looks like multiple vertex formats however, I cannot see a flag of some sort to distinguish between specific vertex types. Very strange, maybe it's stored in another file, are there any other files?

@Ghostblade any update buddy?

You can find me here
http://s15.zetaboards.com/legendsofmodding/index/

The model format has not been fully solved. There issue with vertex buffers still remains, it seems that there is a weird data alignment in place or the devs hardcoded some things because there's a lot of inconsistencies.

The skeletons can be loaded fine now.

Regards.
## Post #12
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-24T01:11:02+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from Gh0stBlade
>
> eri619 wrote:Gh0stBlade wrote:I've been looking at this format for you. I've gotten pretty far except there are some issues with the vertices. Looks like multiple vertex formats however, I cannot see a flag of some sort to distinguish between specific vertex types. Very strange, maybe it's stored in another file, are there any other files?

@Ghostblade any update buddy?

You can find me here
http://s15.zetaboards.com/legendsofmodding/index/

The model format has not been fully solved. There issue with vertex buffers still remains, it seems that there is a weird data alignment in place or the devs hardcoded some things because there's a lot of inconsistencies.

The skeletons can be loaded fine now.

Regards.

Great Progress you are making 

In noesis is it possible to convert the mesh to obj,make edits and then import the edits back inside the model?
## Post #13
- Username: eri619
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-02-24T01:15:25+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from eri619
>
> 

In noesis is it possible to convert the mesh to obj,make edits and then import the edits back inside the model?
Only exporting is supported. Importing won't be possible.
## Post #14
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-24T02:00:27+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

> Reply from Gh0stBlade
>
> eri619 wrote:

In noesis is it possible to convert the mesh to obj,make edits and then import the edits back inside the model?
Only exporting is supported. Importing won't be possible.

Damn! i really want to make edits to these models and make a renovated game.A help which you can do is make a documentation about this format which will help someone who is willing to make a max script or something.
## Post #15
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-25T01:48:17+00:00
- Post Title: Any One Volunteering to make a tool/script for this format?

Could you please post the previews of what you have achieved so far?
## Post #16
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-26T16:11:03+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

LOL Has the roadblock cleared
## Post #17
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-02-29T23:36:29+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

@GhostBlade-any luck with this man?
## Post #18
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-03-04T01:35:11+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

Could someone please post the obj mesh of these models please
[https://www.sendspace.com/file/gpkk6r](https://www.sendspace.com/file/gpkk6r)
## Post #19
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-04T11:33:36+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

> Reply from eri619
>
> Could someone please post the obj mesh of these models please
https://www.sendspace.com/file/gpkk6r

.obj file format doesn't support bones and weights. Unless you want to rig them yourself (might be better in this case since the original skeleton/rig they used for the game is terrible)

Also, sorry for the delays and no updates. I've been extremely busy with work and studies which have unfortunately clashed.



===

eri619 There was no need to create two threads on the same file format. I have since merged both topics together, please do not do this again.
## Post #20
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-03-04T16:05:01+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

great progress @ghostblade no worries,take your time.

actually the new files i have posted are from RAW 2 for XBOX.Although the extension is the same,the file has a different structure.
## Post #21
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-03-18T23:53:28+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

Any update buddy?
## Post #22
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-20T13:22:16+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

I don't think this is going to be finished up. The code is extremely unstable because again, there's either some weird alignment, hard coded stuff going on. Material structs within those model files have different sizes so that causes a lot of problems.
## Post #23
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-03-21T01:22:55+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

> Reply from Gh0stBlade
>
> I don't think this is going to be finished up. The code is extremely unstable because again, there's either some weird alignment, hard coded stuff going on. Material structs within those model files have different sizes so that causes a lot of problems.

could you please post the beta plugin for me to have a look?

Also with regards to vertex buffers,i'd appreciate it if you could document the offsets and stuff which you have found out from the format so that i could ask my friend who coded script for fifa models to have a look at the vertex buffers.
## Post #24
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-03-28T02:12:10+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

if time permits,could you please describe the format and also post the beta plugin please?
## Post #25
- Username: Acewell
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-03-28T14:15:19+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

Ok, I don't usually do this. But I'll release the plugin as is. I do not have time to continue this anymore, if someone wants to pickup where I left off, feel free to! I have unfortunately been unable to fix some of the issues I mentioned earlier in the thread. This purely boils down to a dodgy file format with inconsistent struct sizes.

I hope it helps!
[fmt_WWF_fml.zip](https://xentaxbackup.github.io/file/10644_fmt_WWF_fml.zip)
## Post #26
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-04-17T08:39:10+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

Its rather disappointing to see no one is picking up this project.
## Post #27
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-08-19T03:16:17+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

anyone?
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-19T21:18:12+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

ugly format, ugly models. Who would waste life and time?
I made some ugly patches to get 000l.fml -
although I read only 14 of 26 (33?) assumed submeshes the model looks to be complete (heads are separate I guess)
after turning face culling on:



000l_fml.png (47.68 KiB) Viewed 75 times
## Post #29
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-08-20T13:05:54+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

> Reply from shakotay2
>
> ugly format, ugly models. Who would waste life and time?
I made some ugly patches to get 000l.fml -
although I read only 14 of 26 (33?) assumed submeshes the model looks to be complete (heads are separate I guess)
after turning face culling on:
000l_fml.png

If its possible to make simple vertex edits and then inject it back to the model file,i'll be really happy.
And yes,the heads are separate,there is a separate head for each facial expression,8 of them to be precise.
## Post #30
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-20T14:17:59+00:00
- Post Title: Re: [Request]Import and Export Script for the model format

> Reply from eri619
>
> If its possible to make simple vertex edits and then inject it back to the model file,i'll be really happy.same problem as before: you'll need to find someone who's willing to code a tool for you.

Also, what does that mean exactly: "simple vertex edits"?
As long as the vertex count doesn't change the skinning shouldn't be affected (hopefully).

But for an armor for example you're always in danger of overlapping mesh parts ingame.

(btw: did you ever do such edits for any other game?)
## Post #31
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-08-20T17:34:51+00:00
- Post Title: Any One Volunteering to make a tool for this format?

> Reply from shakotay2
>
> eri619 wrote:If its possible to make simple vertex edits and then inject it back to the model file,i'll be really happy.same problem as before: you'll need to find someone who's willing to code a tool for you.

Also, what does that mean exactly: "simple vertex edits"?
As long as the vertex count doesn't change the skinning shouldn't be affected (hopefully).

But for an armor for example you're always in danger of overlapping mesh parts ingame.

(btw: did you ever do such edits for any other game?)

What i meant is changing the shape of the model without changing the vertex count.

And yes,i did edit models without changing the vertex count.

Schradek123 made blender script which opens SVR Models in blender,but it doesnt export the edits back.tekken57 a.k.a plodtrew(his name here) coded a function in his tool named x-rey which enables the vertex edits to be injected back into the ps2 model.(U-V edits are not possible).

Thats what i meant,just editing the model shape without making changes to the vertex count.
## Post #32
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-08-20T17:36:32+00:00
- Post Title: Any One Volunteering to make a tool for this format?

> Reply from shakotay2
>
> ugly format, ugly models. Who would waste life and time?
I made some ugly patches to get 000l.fml -
although I read only 14 of 26 (33?) assumed submeshes the model looks to be complete (heads are separate I guess)
after turning face culling on:
000l_fml.png

I know you dont have time to code a tool,but could you possibly mark the offsets within the model file(maybe a hex workshop bookmark file) so that i could provide these information for someone to code a tool?.. it would be really helpful.
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-20T20:00:17+00:00
- Post Title: Any One Volunteering to make a tool for this format?

Someone who can code such tools is able to get such info by a quick glance into the hex editor.

Anyways, here you go, vertices start at 0xC43 in this fml file:



000L_fml-FVF.jpg (194.21 KiB) Viewed 69 times



Keep in mind that the FVF size is odd here: 43 (it might be different for different files, 49 for example).
## Post #34
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-08-21T00:21:25+00:00
- Post Title: Any One Volunteering to make a tool for this format?

> Reply from shakotay2
>
> Someone who can code such tools is able to get such info by a quick glance into the hex editor.

Anyways, here you go, vertices start at 0xC43 in this fml file:
000L_fml-FVF.jpg

Keep in mind that the FVF size is odd here: 43 (it might be different for different files, 49 for example).

Thanks for the info bro,BTW the reason why the model looked ugly to is because you got the mesh out of the Low Poly model.
The wrestler has three models H,L,M you got the mesh out of the L one.This is used when the wrestler runs far away from the ring and the camera looks from the top of the arena.

Sad part of the story is not many people take up old formats,i had to convince the plodtrew guy so much to take up the ps2 format to make a tool for it.

Since i'm on my babysteps on being a model format inspector,this is a total noobish question.

As in the image above you have highlighted the vertices offset.So what should i do to convert the vertex data into wavefront obj data.
I mean is this how it works,convert the vertex data into float data using hex to float tool and then convert the floats into wavefront obj? I'm a total noob,i'm putting my first steps in model inspection.

People like you are such an inspiration for me..You are a pro.
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-08-21T06:56:23+00:00
- Post Title: Any One Volunteering to make a tool for this format?

you could simply use hex2obj - view the wavefront obj data in the test.obj file it creates.
The vertex data is also to be seen in the left lower listbox (go2 button pressed):



000L_fml_.jpg (154.12 KiB) Viewed 57 times

(first submesh only)
## Post #36
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-08-22T14:38:17+00:00
- Post Title: Any One Volunteering to make a tool for this format?

Thanks for your valuable support sir,really appreciate your help.

BTW Any One Volunteering to make a tool for this format?

Features i'm looking for:
1)Since this an old format it would be difficult to make complete modifications,therefore what i'm looking for in the tool/script is for it to allow me to make vertex edits without changing the vertex count and then making it possible to inject the edits back to the model file.

2)Allowing U-V edits if possible.
## Post #37
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-08-30T15:06:38+00:00
- Post Title: Any One Volunteering to make a tool for this format?

Anyone willing?
## Post #38
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2016-09-15T09:54:45+00:00
- Post Title: Any One Volunteering to make a tool for this format?

Where in the blue hell is Szhradek123 when i need him.I only come online somehow when he comes by and leaves once in a while.Each time i miss him.Damn!
