## Post #1
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-09-29T18:51:29+00:00
- Post Title: Halo 5: Forge Models

I was wondering if there was anyone who could help extract the model files from Halo 5: Forge, I know that textures are already extracted, but models have not been.
I've included a sample provided by Revolution for Master Chief's model, I believe the mesh and skeleton info is in the .model or .render_model file, but all model resources have been included just in case.

Sample: [https://drive.google.com/open?id=0B7bLa ... URaM3A5TjQ](https://drive.google.com/open?id=0B7bLaOhnfhrRbmhxOURaM3A5TjQ)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-09-29T19:43:41+00:00
- Post Title: Halo 5: Forge Models

ugly result (left lower corner of pic) with hex2obj, v024d:



spartan_mchief-render_model.jpg (158.83 KiB) Viewed 1161 times


Looks like a matter of a missing offset in the x and the other in y direction.

edit: well, shit, there's one single line in my code which spoils the model:
if (position>32767) position -= 65536; 

Where this line worked for dozens of other model formats before, though.

You'll get the correct model (left upper corner, apart from the scaling) with an updated version of hex2obj (sooner or later).
## Post #3
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-10-06T17:25:17+00:00
- Post Title: Halo 5: Forge Models

[https://drive.google.com/file/d/0B7bLaO ... l1NGc/view](https://drive.google.com/file/d/0B7bLaOhnfhrRTmIycHhaZGl1NGc/view) 
Here's the files for Locke, if anyone wants to check the stuff on another model.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-07T00:41:33+00:00
- Post Title: Halo 5: Forge Models

a script would be helpful:



locke.jpg (147.56 KiB) Viewed 1126 times
## Post #5
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-10-07T00:44:53+00:00
- Post Title: Halo 5: Forge Models

> Reply from shakotay2
>
> there's too many submeshes (96?), so a script will be required:
locke.jpg
I think most of the meshes are LODs.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-07T01:28:27+00:00
- Post Title: Halo 5: Forge Models

the funny part:



locke_tongue.jpg (81.41 KiB) Viewed 1120 times
## Post #7
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-10-07T02:00:21+00:00
- Post Title: Halo 5: Forge Models

> Reply from shakotay2
>
> the funny part:
locke_tongue.jpg
Locke's got a head model that's used in cutscenes, wasn't sure if it was actually in the Forge version.
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-10-21T22:27:37+00:00
- Post Title: Halo 5: Forge Models

Hey! I'm interested in this, working on making model-import script. Could anyone send me textures for provided samples? Or provide new ones with textures, in order to confirm UV mapping. Thanks a lot in advance!
## Post #9
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-10-22T13:37:32+00:00
- Post Title: Halo 5: Forge Models

In order to make some teaser and raise motivation to send me more models+textures. I'm posting this pic with Master Chief and Spartan Locke imported from Halo 5 Forge (with all LODs) xD And Locke has nice face mesh under helmet
## Post #10
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-10-24T19:46:34+00:00
- Post Title: Halo 5: Forge Models

did you can upload weapons models?
## Post #11
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2016-10-24T20:31:31+00:00
- Post Title: Halo 5: Forge Models

> Reply from zaramot
>
> In order to make some teaser and raise motivation to send me more models+textures. I'm posting this pic with Master Chief and Spartan Locke imported from Halo 5 Forge (with all LODs) xD And Locke has nice face mesh under helmet
I have the models but not the textures but I'm sure they use the same as the ones from the online character viewer. Btw how did you scale the vertices? I didn't even bother figuring out the uv's because of this.

[https://www.mediafire.com/folder/qzb7t6 ... lo_5_forge](https://www.mediafire.com/folder/qzb7t6612daro/halo_5_forge)
## Post #12
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-10-25T01:34:47+00:00
- Post Title: Halo 5: Forge Models

> Reply from killercracker
>
> zaramot wrote:In order to make some teaser and raise motivation to send me more models+textures. I'm posting this pic with Master Chief and Spartan Locke imported from Halo 5 Forge (with all LODs) xD And Locke has nice face mesh under helmet  

I have the models but not the textures but I'm sure they use the same as the ones from the online character viewer. Btw how did you scale the vertices? I didn't even bother figuring out the uv's because of this.

https://www.mediafire.com/folder/qzb7t6 ... lo_5_forge

Textures are far more higher res than the ones in the online viewer and have chunk files that go along with them.
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-10-25T07:46:18+00:00
- Post Title: Halo 5: Forge Models

Thanks guys, I have all textures now thanks to SpookyMajora and Alexis. So, no need to bother with uploading them! I will post script as soon I figure out weights.

P.S. JakeGreen is right, from what I saw, textures are twice bigger than in model viewer, they are 2048x2048 for armor, in model viewer if I remember right, only tech suit is in such resolution, armor 1024x1024 right?
## Post #14
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-10-26T08:12:33+00:00
- Post Title: Halo 5: Forge Models

Thank you!
## Post #15
- Username: dravid51
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 11, 2015 9:52 pm
- Post datetime: 2016-10-31T05:23:01+00:00
- Post Title: Halo 5: Forge Models

Can anyone upload the models and textures in a format like fbx or obj?
## Post #16
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-10-31T09:18:38+00:00
- Post Title: Re: Halo 5: Forge Models

yes, upload weapons textures, please!
## Post #17
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-01T01:43:28+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> In order to make some teaser and raise motivation to send me more models+textures. I'm posting this pic with Master Chief and Spartan Locke imported from Halo 5 Forge (with all LODs) xD And Locke has nice face mesh under helmet

I think I can help you out there. I pulled all of the raw files from the game and I've been working on compiling the textures into a megapack along with the Waypoint-extracted armour files. However, I've also zipped up all of the models and textures from their raw formats and pushed them to my Mega account for others to use and enjoy. Please take them and make better use of them than I could - I'd love to be able to start processing models out of the game myself and putting together packs for people to use. Since you say you already have the textures I'm focusing on the models.

I'm also going to be pushing the full armour/textures pack as soon as I've done it, hopefully as some sort of incentive/thank-you for those with the technical expertise to process the raw model data - my main resource is time, so I'm happy to sit and spend a few hours trawling through the files and getting them all pulled from the game and sorted for others to use. It's a small matter compared to the work that goes into getting the files out.

You can grab my files here:
[https://mega.nz/#!kps3xKqA!1xn7XOl5jeDS ... Ok5B7WAUpQ](https://mega.nz/#!kps3xKqA!1xn7XOl5jeDSRKatGCXxL8P-_RQ2ijNDYOk5B7WAUpQ)
(WARNING: 700mb+)

Also, please feel free to fire me up on Discord or Skype if you need anything directly that I've forgotten or accidentally omitted - I'll leave links to those if you need them.
## Post #18
- Username: dravid51
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 11, 2015 9:52 pm
- Post datetime: 2016-11-01T03:25:22+00:00
- Post Title: Re: Halo 5: Forge Models

RosaWeyland what tools do you use to convert the raw files?
## Post #19
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-01T04:01:28+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from dravid51
>
> RosaWeyland what tools do you use to convert the raw files?

Uh... that's a bit of a process, actually, and given how involved it is, it's probably easier for me to just post up a link to the raw files to use. I'll grub around and post the tools I use once I can get the links, though.

EDIT: if there's a clearer walkthrough or guide for Hex2Obj, however, I'd be very grateful. I'm doing my best to understand all of this but it's... a little beyond me.

EDIT 2: here's the raw texture data, if people want it.
[https://mega.nz/#!lw0VhRIZ!wP9zOWMagOVO ... wEs9tg3y40](https://mega.nz/#!lw0VhRIZ!wP9zOWMagOVOemh7VbSdN8lkkC288Tw5DwEs9tg3y40)
WARNING: huuuuuge file.
## Post #20
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-01T18:55:55+00:00
- Post Title: Re: Halo 5: Forge Models

Managed to pull this with some help last night. Issues are as follows:
- No UVs. Not sure if that was because the person helping me omitted them, or the tool didn't pull them.
- Tool pulls ALL LoD files - so there's a lot of sorting to be done to get the HD stuff you'll most likely want.
- Model seems to be stretched along one axis. Needs manually fixing for now, unless you can figure out how to offset that in the model pull.
[halo 5 Magnum copy.jpg](https://xentaxbackup.github.io/file/11857_halo 5 Magnum copy.jpg)
## Post #21
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-01T19:45:50+00:00
- Post Title: Re: Halo 5: Forge Models

So, someone working on the tool already? Glad to hear, I'm sure the person which helping you just omitted them, there's no any problem with uv's, scaling should be done with bounding-box and LODs aren't such a big problem since they are just as separate mesh, no problem to delete them (or just not importing them). Main issue with Halo 5 it's rigging, only yesterday I figured it out more or less    It's quite strange system if you ask me!
## Post #22
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-11-01T20:02:43+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> So, someone working on the tool already? Glad to hear, I'm sure the person which helping you just omitted them, there's no any problem with uv's, scaling should be done with bounding-box and LODs aren't such a big problem since they are just as separate mesh, no problem to delete them (or just not importing them). Main issue with Halo 5 it's rigging, only yesterday I figured it out more or less    It's quite strange system if you ask me!

You do such amazing work. I'm definitely looking forward to your script release!
## Post #23
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-01T20:51:50+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> So, someone working on the tool already? Glad to hear, I'm sure the person which helping you just omitted them, there's no any problem with uv's, scaling should be done with bounding-box and LODs aren't such a big problem since they are just as separate mesh, no problem to delete them (or just not importing them). Main issue with Halo 5 it's rigging, only yesterday I figured it out more or less    It's quite strange system if you ask me!

That looks pretty amazing. I'd love to be able to help out, if you need it, though I'll echo what others have said: I look forward to the script release!
## Post #24
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-11-02T07:02:08+00:00
- Post Title: Re: Halo 5: Forge Models

Wow, good job. 
Can you show where is scale's value?
## Post #25
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-04T19:19:54+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Wow, good job. 
Can you show where is scale's value?

Unfortunately, I have no idea where it is (I'm using manual scale values, fine for characters I tried though). It appears it's not in the mesh file, neither in skeleton file too. Again, unfortunatelly each Halo 5 model has a lot of extra files near it, so this could take time to locate scaling values/bounding box. + it's using Havok, so maybe it's something Havok related. If someone knows where it is, share the info, this is the only issue, which preventing me to post model-import script xD
## Post #26
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-11-04T20:03:27+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> erik945 wrote:Wow, good job. 
Can you show where is scale's value?

Unfortunately, I have no idea where it is (I'm using manual scale values, fine for characters I tried though). It appears it's not in the mesh file, neither in skeleton file too. Again, unfortunatelly each Halo 5 model has a lot of extra files near it, so this could take time to locate scaling values/bounding box. + it's using Havok, so maybe it's something Havok related. If someone knows where it is, share the info, this is the only issue, which preventing me to post model-import script xD

Unfortunately, If it's similar to the other Halo games' model formats, the scaling is determined entirely by the bounding box. There are no other stored scale values.
## Post #27
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-04T20:17:18+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> erik945 wrote:Wow, good job. 
Can you show where is scale's value?

Unfortunately, I have no idea where it is (I'm using manual scale values, fine for characters I tried though). It appears it's not in the mesh file, neither in skeleton file too. Again, unfortunatelly each Halo 5 model has a lot of extra files near it, so this could take time to locate scaling values/bounding box. + it's using Havok, so maybe it's something Havok related. If someone knows where it is, share the info, this is the only issue, which preventing me to post model-import script xD

I'm having this problem myself. Between my friend and I we're having problems finding out exactly how the scaling works. Every model seems to come out in a cube (1x1x1) and I've had to re-scale the stuff I'm pulling out manually to fix it. Of course, that means that the files are prone to errors since my scaling might not be absolutely accurate. I'm sending my friend a source copy of Adjutant, so maybe he can use that to figure the issue out. If we can, I'll be sure to let you know.

Are you having success with the multiplayer Spartan models, though? I can't seem to get those pulled at all.
## Post #28
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-04T20:25:54+00:00
- Post Title: Re: Halo 5: Forge Models

Hmm, you mean customization parts? Well, I'm imported all models I have so far, maybe I just missing something. If it will not be hard for you to post few such files here or at least tell me their names, so I can try to locate them amoung mine xD
## Post #29
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-04T20:46:09+00:00
- Post Title: Re: Halo 5: Forge Models

Sure - I'm mainly looking for the Marauder set, since I can't get that model from Halo Waypoint's .js files. The tool I'm using (which is quick, dirty and based off of hex2obj) won't open up the multiplayer armour files.

I'd also like to check - are you able to pull a clean, high-definition file of the Hydra launcher? For some reason I can only pull the medium-LoD file using my tool, and I'm curious as to whether it's an issue on my end or that the file will just be like that.
## Post #30
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-04T21:12:58+00:00
- Post Title: Re: Halo 5: Forge Models

I never played Halo games, have no idea how those models looks. Do you have extracted files from Halo 5: Forge, right? Since, I don't have any files with such names lol
## Post #31
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-04T21:22:47+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> I never played Halo games, have no idea how those models looks. Do you have extracted files from Halo 5: Forge, right? Since, I don't have any files with such names lol

Sure. I posted all of the model files [HERE](https://mega.nz/#!kps3xKqA!1xn7XOl5jeDSRKatGCXxL8P-_RQ2ijNDYOk5B7WAUpQ) a few days ago. The Hydra launcher would be under:

(any)globals-rtx-1\objects\weapons\rifle\mlrs

As for the multiplayer armours, they're all in:

(any)globals-rtx-1\objects\characters\storm_masterchief

I'm not sure of which file the Marauder armour would be under, but certainly I know where the Hydra is. Up until now I've assumed that the model/mesh files are under the mesh_resource! file type. And, I'm not asking this of you as a request to rip me stuff specifically, it's more that I want to make sure that these types of files can be pulled properly.
## Post #32
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-11-04T21:26:31+00:00
- Post Title: Re: Halo 5: Forge Models

deleted
## Post #33
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-11-04T21:32:03+00:00
- Post Title: Re: Halo 5: Forge Models

Yes, models are mesh_resource! and I can import them all, I will check them more detailed though. Also, I understand, that you don't need just models from me   You want to understand format like I do, maybe even better.
## Post #34
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-11-04T21:54:41+00:00
- Post Title: Re: Halo 5: Forge Models

I'm usually looking for round elements, and align the scale on them.
## Post #35
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-04T22:17:29+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> Yes, models are mesh_resource! and I can import them all, I will check them more detailed though. Also, I understand, that you don't need just models from me   You want to understand format like I do, maybe even better.

Pretty much that. If I can help, I will. As Erik said, usually I scale manually from a circle, but if we can crack the bounding box then we can do so much more.

I look forward to seeing the Hydra at the least!
## Post #36
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-11-05T05:49:50+00:00
- Post Title: Re: Halo 5: Forge Models

zaramot then maybe you temporarily upload your tool as it is?
## Post #37
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-05T06:57:57+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> zaramot then maybe you temporarily upload your tool as it is?

I'd prefer to get a finished tool than something that's in beta. Be patient and let Zaramot work on it at his own pace, maybe offer help and solutions instead of just demanding results.

I'm thinking that my tool has issues with reading some LoD information, given that the Hydra won't give me a HD pull. I also can't seem to access a few other files, such as the Halo 2 Beam Rifle and all of the Multiplayer mesh_resource! files, so it's obviously not a simple matter of simply reading vertex/face/UV data and then pulling it out (which is what my tool does). I'll compile a list of all the files I'm having problems with and throw it out there while my contact works on the bounding box issue - I'm not terribly worried about UV and rig data for now, I'd prefer to get the files pulling cleanly before we work on making them look good and move good.
## Post #38
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-11-06T15:06:44+00:00
- Post Title: Re: Halo 5: Forge Models

What techniques and tools do you use to analyze hex data?
## Post #39
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-11-22T23:37:36+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from zaramot
>
> erik945 wrote:Wow, good job. 
Can you show where is scale's value?

Unfortunately, I have no idea where it is (I'm using manual scale values, fine for characters I tried though). It appears it's not in the mesh file, neither in skeleton file too. Again, unfortunatelly each Halo 5 model has a lot of extra files near it, so this could take time to locate scaling values/bounding box. + it's using Havok, so maybe it's something Havok related. If someone knows where it is, share the info, this is the only issue, which preventing me to post model-import script xD
Did you try checking the .Physics_Model or .Collision_Model file for that information?
## Post #40
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2016-11-23T18:15:36+00:00
- Post Title: Re: Halo 5: Forge Models

I do not know if this is the place to ask, but I'd be interested in a Halo 2 anniversaly model that would be this:

I just wondered if it was possible using the Halo 5 instruments. unfortunately I do not know how to get the game where there is the model in question :/
## Post #41
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-24T02:19:54+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from dibe91
>
> I do not know if this is the place to ask, but I'd be interested in a Halo 2 anniversaly model that would be this:

I just wondered if it was possible using the Halo 5 instruments. unfortunately I do not know how to get the game where there is the model in question :/

Doubtful. We don't have the raw files for H2A (I believe), much less any way to get anything meaningful from them.

Going to check the collision and physics models when I get back, I have a strong feeling that the collision box will have the bounding box data in it.
## Post #42
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-11-24T05:52:22+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> dibe91 wrote:I do not know if this is the place to ask, but I'd be interested in a Halo 2 anniversaly model that would be this:

I just wondered if it was possible using the Halo 5 instruments. unfortunately I do not know how to get the game where there is the model in question :/

Doubtful. We don't have the raw files for H2A (I believe), much less any way to get anything meaningful from them.

Going to check the collision and physics models when I get back, I have a strong feeling that the collision box will have the bounding box data in it.

If it's similar to previous Halo games, the bounding info has typically been found in the .render_model tag and/or the .model tags as it's generated when 343/Bungie process the model with their tools - As in within the tag data itself, not the resource chunks. 

The current .module extractor is pretty crude, so it just dumps everything, destroying the structure of the tags that store pre-processed assets (Bitmaps, models). 

TL;DR
Check the .render_model tag associated with the resource chunks of the model you're trying to extract.

Here's the actual tag structures from H5. Both tags have specific references to bounding offsets. I'm not sure how helpful it'll be... but here  they are anyway.
[Tag Structures.zip](https://xentaxbackup.github.io/file/11951_Tag Structures.zip)
## Post #43
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-24T23:14:10+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Alexis
>
> Check the .render_model tag associated with the resource chunks of the model you're trying to extract.
.render_model is the model file itself - that's where I've been pulling the mesh data from. Neither I nor my helping friend have found any reference to bounding boxes in there so far - that's not to mean it's not in there, we just might not know where to look. It might be worth rebuilding the module extractor to try and get a clean tag structure before we proceed further, though, probably easier to work with better tools from the offset than to try rebuilding everything from a raw dump.

I'll take a look again, however, there may be something I've missed.
## Post #44
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-11-25T06:02:40+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Alexis wrote:Check the .render_model tag associated with the resource chunks of the model you're trying to extract.
.render_model is the model file itself - that's where I've been pulling the mesh data from. Neither I nor my helping friend have found any reference to bounding boxes in there so far - that's not to mean it's not in there, we just might not know where to look. It might be worth rebuilding the module extractor to try and get a clean tag structure before we proceed further, though, probably easier to work with better tools from the offset than to try rebuilding everything from a raw dump.

I'll take a look again, however, there may be something I've missed.

As I understand it; The plain xxx.render_model should be the the tag structure sans pre-processed data. The xxx.render_model.mesh_resource!  Is the raw mesh data stripped from the xxx.render_model data by the module extractor... Is that not correct? The bounding info should be in the .render_model in a block all by itself. 

Halos have typically stored the bounding box in the tag data rather than the mesh. When the model is compiled, the scale info is written to a specific block in the tag, not the mesh data... if that makes sense. Halo will scale the mesh based on the values in the tag... but I guess that it could have changed with H5
## Post #45
- Username: Renegaderobbie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 04, 2016 5:11 am
- Post datetime: 2016-11-27T18:48:37+00:00
- Post Title: Re: Halo 5: Forge Models

How do you convert .model files / .rended files?
## Post #46
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-27T21:32:22+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Renegaderobbie
>
> How do you convert .model files / .rended files?

With a tool that hasn't been released yet. Stop asking, you already caused enough drama on FacePunch.
## Post #47
- Username: Renegaderobbie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 04, 2016 5:11 am
- Post datetime: 2016-11-29T00:26:32+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Alexis
>
> RosaWeyland wrote:dibe91 wrote:I do not know if this is the place to ask, but I'd be interested in a Halo 2 anniversaly model that would be this:

I just wondered if it was possible using the Halo 5 instruments. unfortunately I do not know how to get the game where there is the model in question :/

Doubtful. We don't have the raw files for H2A (I believe), much less any way to get anything meaningful from them.

Going to check the collision and physics models when I get back, I have a strong feeling that the collision box will have the bounding box data in it.

If it's similar to previous Halo games, the bounding info has typically been found in the .render_model tag and/or the .model tags as it's generated when 343/Bungie process the model with their tools - As in within the tag data itself, not the resource chunks. 

The current .module extractor is pretty crude, so it just dumps everything, destroying the structure of the tags that store pre-processed assets (Bitmaps, models). 

TL;DR
Check the .render_model tag associated with the resource chunks of the model you're trying to extract.

Here's the actual tag structures from H5. Both tags have specific references to bounding offsets. I'm not sure how helpful it'll be... but here  they are anyway.

So super quick question, what program can the tag structures be used in? I've tried using that to convert the .model file to an obj file  with little success
## Post #48
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-30T02:31:56+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Renegaderobbie
>
> So super quick question, what program can the tag structures be used in? I've tried using that to convert the .model file to an obj file  with little success

None. The only real way to get data out is by using the hex data as shown in this thread already - at least, until a better tool to read the module formats is made. You'd know this if you did some research and stopped simply asking for handouts.

Oh, and by the way - if you're asking such basic questions as this, I'd be interested to know why you're telling me over on Facepunch that you have access to the UV and bounding box data.
## Post #49
- Username: Renegaderobbie
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Nov 04, 2016 5:11 am
- Post datetime: 2016-11-30T04:07:07+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Renegaderobbie wrote:So super quick question, what program can the tag structures be used in? I've tried using that to convert the .model file to an obj file  with little success

None. The only real way to get data out is by using the hex data as shown in this thread already - at least, until a better tool to read the module formats is made. You'd know this if you did some research and stopped simply asking for handouts.

Oh, and by the way - if you're asking such basic questions as this, I'd be interested to know why you're telling me over on Facepunch that you have access to the UV and bounding box data.

I wasn't asking for hand outs  just a way to do that. And I private messaged you on facepunch a while ago. I have the hex2obj program. Just having trouble reading the data
## Post #50
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-30T05:12:47+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Renegaderobbie
>
> I wasn't asking for hand outs  just a way to do that. And I private messaged you on facepunch a while ago. I have the hex2obj program. Just having trouble reading the data

Constantly asking for tools I made quite clear you wouldn't be getting is asking for a handout. And, if you want to figure out how to read the data would suggest reading the hex2obj thread a little more closely. I've read your PMs and your posts, and the answer is pretty simple:

No. I'm not giving you the tools I have, because they're not ready to be published. At all. You obviously don't have any idea of what you're doing, you don't have the UV and bounding box information, and the only way I'd even halfway believe you is if you sent over that supposed Warden Eternal file for me to look at. Since I'm expecting you not to be able to do that, I think it's pretty clear what the answer in return is going to be.

Stop being impatient, wait for the tools to be finished, and for the love of god please stop telling people that you're working with me or helping me.
## Post #51
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-11-30T07:49:01+00:00
- Post Title: Re: Halo 5: Forge Models

And what is there a problem with the UV? It normally read as a 2 value type short. Or you're talking about the scale?
## Post #52
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-11-30T16:58:15+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> And what is there a problem with the UV? It normally read as a 2 value type short. Or you're talking about the scale?

Both, honestly. Haven't found the data for either, though if I at least could integrate UV data into my tool then I could publish the assets I have managed to extract with the texture data intact for others to use. Bounding box info could come after, probably.
## Post #53
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-01T12:29:13+00:00
- Post Title: Re: Halo 5: Forge Models

fragment of my maxscript, read vertex data. You need values u_f and w_f

```
y = readshort f__mesh #unsigned
z = readshort f__mesh #unsigned		
fseek f__mesh 0x2 #seek_cur		
u = readshort f__mesh #unsigned
w = readshort f__mesh #unsigned	
u_f = (1.0 * u)/65536
w_f = -(1.0 * w)/65536

```


...and full script. Hasn't skin, scale and names but work for most weapons and vehicle models 
[](http://hostingkartinok.com/show-image.php?id=b4f3bf71b20461d59e6b13dcb5bcd5de)



[render_mesh3.7z](https://xentaxbackup.github.io/file/11974_render_mesh3.7z)
## Post #54
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-01T16:42:03+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> fragment of my maxscript, read vertex data. You need values u_f and w_f
Code: Select allx = readshort f__mesh #unsigned
y = readshort f__mesh #unsigned
z = readshort f__mesh #unsigned		
fseek f__mesh 0x2 #seek_cur		
u = readshort f__mesh #unsigned
w = readshort f__mesh #unsigned	
u_f = (1.0 * u)/65536
w_f = (1.0 * w)/65536


...and full script. Hasn't skin, scale and names but work for most weapons and vehicle models

Nice work. 

One thing I've noticed is that your UVs seem to be flipped vertically. Is that something you can correct in your script?
## Post #55
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-01T17:21:30+00:00
- Post Title: Re: Halo 5: Forge Models

Ok, no problem 
If you get a model which does not work - reported.
[render_mesh3.7z](https://xentaxbackup.github.io/file/11973_render_mesh3.7z)
## Post #56
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-02T00:03:25+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Ok, no problem 
If you get a model which does not work - reported.

Awesome, thanks for correcting the UVs!

So, I am getting a couple errors here and there with specific models. For example, spartan_vale's model gives me an error when creating "Mesh 60" and "Mesh 61". Judging by the face count, "Mesh 61 appears to be the highest LOD for Vales head model.

It also appears that the UVs for this model are also scaled incorrectly. They are scaled too small, and centered to the left of the UV space.

Here's Max's listener output for Vale.
[vale error.zip](https://xentaxbackup.github.io/file/11977_vale error.zip)
## Post #57
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-12-04T01:58:02+00:00
- Post Title: Re: Halo 5: Forge Models

Having issues with the Hydra as well - had the same issues with the model when I was pulling the file using my own tools as well, so I suspect it's something to do with a difference in the file. Seems I can only get the lowest LoD and one of the sub-HD LoDs, and a few decal patches.

Script uploaded below.
[Hydra MaxScript Listener File.zip](https://xentaxbackup.github.io/file/11979_Hydra MaxScript Listener File.zip)
## Post #58
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2016-12-04T21:33:26+00:00
- Post Title: Re: Halo 5: Forge Models

I think I've figured out a pattern for scaling the character models more or less, looks like they need to be scaled down to 75 on the Y-axis, and 30 on the X-axis. I've tried it out on a few characters and it seems to work fine. 



Now weapons are a whole different thing, I checked out the Assault Rifle and the Magnum last night and they seem to both be scaled differently.
## Post #59
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-04T23:49:51+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from SpookyMajora
>
> I think I've figured out a pattern for scaling the character models more or less, looks like they need to be scaled down to 75 on the Y-axis, and 30 on the X-axis. I've tried it out on a few characters and it seems to work fine. 



Now weapons are a whole different thing, I checked out the Assault Rifle and the Magnum last night and they seem to both be scaled differently.

According to my math, assuming the box at the bottom is supposed to be a perfect cube, it should be 75.368331922% on the Y-Axis and 25.208156329 on the X-Axis.

So, you're not too far off. (Unless my math is off!)
## Post #60
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-12-05T05:46:12+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Alexis
>
> According to my math, assuming the box at the bottom is supposed to be a perfect cube, it should be 75.368331922% on the Y-Axis and 25.208156329 on the X-Axis.

So, you're not too far off. (Unless my math is off!)

I think it might be. I used your values on the Helljumper helmet when compared against the Halo Waypoint model rip, and there's a large amount of compression along the Y axis, as well as a difference in the X axis. I used the Z scale (height) to compare and contrast.

What I've ended up doing is exporting the model from Max with that weird cube on the bottom, and then scaling it against a spawned cube mesh in Blender. It's not ideal, but until bounding box data is implemented I can make do with manual scaling. I'd show my maths but... I'm going to be the first one to admit that working out ratios and whatnot is not my area of expertise. Basic maths I can do, anything more is a whole bunch of 'nope'. I can post my numbers tomorrow and let you guys work it out if you like?
## Post #61
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-05T14:14:46+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Alexis wrote:According to my math, assuming the box at the bottom is supposed to be a perfect cube, it should be 75.368331922% on the Y-Axis and 25.208156329 on the X-Axis.

So, you're not too far off. (Unless my math is off!)

I think it might be. I used your values on the Helljumper helmet when compared against the Halo Waypoint model rip, and there's a large amount of compression along the Y axis, as well as a difference in the X axis. I used the Z scale (height) to compare and contrast.

What I've ended up doing is exporting the model from Max with that weird cube on the bottom, and then scaling it against a spawned cube mesh in Blender. It's not ideal, but until bounding box data is implemented I can make do with manual scaling. I'd show my maths but... I'm going to be the first one to admit that working out ratios and whatnot is not my area of expertise. Basic maths I can do, anything more is a whole bunch of 'nope'. I can post my numbers tomorrow and let you guys work it out if you like?

Maybe it's a difference between Blender and Max scaling, or maybe some biped's scaling is different? With my numbers, the box becomes a mathematically perfect cube on the models I've tested. I also tested against my own Waypoint rips and they seem to be exact so far... I'll look into what could be causing the discrepancy tonight.
## Post #62
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-05T18:00:14+00:00
- Post Title: Re: Halo 5: Forge Models

Fixed.
Alexis - UV has coding like vertex.  I use the preliminary scale values. You may need correct its manually.
I think that these values ​​must be a multiple of 1 (1,2,3 ... etc)
[render_mesh4.7z](https://xentaxbackup.github.io/file/11983_render_mesh4.7z)
## Post #63
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-12-06T04:27:10+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Alexis
>
> Maybe it's a difference between Blender and Max scaling, or maybe some biped's scaling is different? With my numbers, the box becomes a mathematically perfect cube on the models I've tested. I also tested against my own Waypoint rips and they seem to be exact so far... I'll look into what could be causing the discrepancy tonight.

I scaled in Max and then exported to Blender, and the file was still squashed. So I've fixed manually in Blender by eye, since it's easier for me to do that than screw around in a program I can't use.
## Post #64
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-06T05:45:13+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Alexis wrote:Maybe it's a difference between Blender and Max scaling, or maybe some biped's scaling is different? With my numbers, the box becomes a mathematically perfect cube on the models I've tested. I also tested against my own Waypoint rips and they seem to be exact so far... I'll look into what could be causing the discrepancy tonight.

I scaled in Max and then exported to Blender, and the file was still squashed. So I've fixed manually in Blender by eye, since it's easier for me to do that than screw around in a program I can't use.

I just checked some other models, and it seems that the scaling is different even between bipeds. What I have done is create a perfect cube with all sides equal to the Z of the model's frame box for reference. Link the main model's pieces to it's own frame box - snap the scale of the frame box to the verts of the perfect cube I created. This scales the model perfectly every time.

You could also get the dimensions of the Z axis of the frame box, and figure out the exact percentage at which each axis is scaled.

It's ranged from 25-30% on one axis, and 75-80% on the other.
## Post #65
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-11T14:35:31+00:00
- Post Title: Re: Halo 5: Forge Models

Script update:
Now you need select *.render_model (don't *.render_model[0_mesh resource!_])
Fix model scale
Fix UV scale and position.

Thank Alexis for hint.
[render_mesh5.7z](https://xentaxbackup.github.io/file/12021_render_mesh5.7z)
## Post #66
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-12-11T18:38:25+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Script update:
Now you need select *.render_model (don't *.render_model[0_mesh resource!_])
Fix model scale
Fix UV scale and position.

Thank Alexis for hint.

Great work as always, but the tool doesn't seem to work on the multiplayer Spartan files. The old method was able to pull the resources from the mesh resource files well enough, but this tool doesn't seem to be able to do that.
## Post #67
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-11T19:14:20+00:00
- Post Title: Re: Halo 5: Forge Models

what filename?
## Post #68
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-11T20:54:30+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Script update:
Now you need select *.render_model (don't *.render_model[0_mesh resource!_])
Fix model scale
Fix UV scale and position.

Thank Alexis for hint.

Ah, so my theory was correct! So, the scale seems to be perfect. The only issue I am seeing besides Rosaweyland's is that the Character model UVs seem to be offset a bit to the left, but are scaled properly. I can provide you some models as an example of what I mean if you'd like.

Also, if you are looking for any of the skin weights... I believe they should also be in the ".render_model"
## Post #69
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-12T12:03:35+00:00
- Post Title: Re: Halo 5: Forge Models

Yes,  upload  examples. I'll see.
Regarding skin probably better to turn to zaramot
He wrote that had already done so.
## Post #70
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2016-12-12T17:05:20+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Yes,  upload  examples. I'll see.

They're the multiplayer armour/body files found in objects > characters > storm_masterchief. The render_model file is roughly 7Mb and the mesh resources are the smaller ones.
## Post #71
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-13T00:36:23+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Yes,  upload  examples. I'll see.
Regarding skin probably better to turn to zaramot
He wrote that had already done so.

I've sent you a PM regarding this!
## Post #72
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-19T20:13:57+00:00
- Post Title: Re: Halo 5: Forge Models

Small update. May be fix UV offset.
Test it please.
[render_mesh5.2.7z](https://xentaxbackup.github.io/file/12084_render_mesh5.2.7z)
## Post #73
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-19T22:26:44+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Small update. May be fix UV offset.
Test it please.

Just tested it on a few models. This seems to have definitely corrected the UV offset! I'll continue digging for any that may still be offset.

Now the only remaining issue I can find is the script still can't open "objects/characters/storm_masterchief/storm_masterchief.render_model". It looks like your script doesn't anticipate multiple resource chunks for a model. This causes the script to end abruptly without an error message.

Great work, nonetheless! Keep it up!
## Post #74
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-25T14:03:09+00:00
- Post Title: Re: Halo 5: Forge Models

New update.
Added support storm_masterchief  

[](http://hostingkartinok.com/show-image.php?id=3a0b0a28c4fb5c759366e602df7d8730)

[render_mesh5.5.7z](https://xentaxbackup.github.io/file/12122_render_mesh5.5.7z)
## Post #75
- Username: Alexis
- Rank: beginner
- Number of posts: 35
- Joined date: Wed May 26, 2010 10:56 am
- Post datetime: 2016-12-26T19:23:08+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> New update.
Added support storm_masterchief

Very nice!

This seems to do the trick. Is the script written in such a way that when they add new armors, they should also load correctly, or will the script need to be updated? 

As always - Keep up the good work!
## Post #76
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2016-12-27T08:29:09+00:00
- Post Title: Re: Halo 5: Forge Models

In some ways, it really is the trick.
As for armor fragments - everything is fair. Previously, I used only one file 0_mesh resource  and worked with him

```
f_header = fopen fname "rb" - the title of the model. Hence taken scaling and offset
f__mesh = fopen (fname + "[0_mesh resource _!]") "rb" - file body, hence take everything buffer.

```


Now I select all files on mask and processed  each of them

```
for i = 1 to file_array.count do (
f__mesh = fopen (file_array[i])  "rb" 

```


If the new  mesh resource throw to folder   - they are also processed.

But an array of coefficient scaling and offset for storm_masterchief is not where typically. I was too lazy to calculate the correct algorithm for a single model, and I found it manually and simply set it's address offset only for this file

```
fseek f_header 0x06d39ca #seek_set

```
## Post #77
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2017-01-02T23:11:34+00:00
- Post Title: Re: Halo 5: Forge Models

Did Zaramot ever make anymore progress on his script?

I know we've already got a script, but his has the weights and such and would be a bit more useful.
## Post #78
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2017-01-07T19:22:05+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> 
If the new  mesh resource throw to folder   - they are also processed.

Since I was able to get the new files from Revo, I went ahead and checked if the new armors would import properly, the scale and UVs are messed up as they were originally, and this is using the newest script.

[https://drive.google.com/file/d/0B7bLaO ... 5MdGM/view](https://drive.google.com/file/d/0B7bLaOhnfhrRM2poc0VMOE5MdGM/view)

Here's the newest "storm_masterchief" folder.
## Post #79
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-09T09:57:00+00:00
- Post Title: Re: Halo 5: Forge Models

Heh, I wonder. I have to write an honest parser.

Where you found it?
You can upload all that there (models and textures)? 
I was primarily interested in the company's characters and aliens of Covenant (elite, jackals, etc.)
## Post #80
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2017-01-09T20:07:02+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from erik945
>
> Heh, I wonder. I have to write an honest parser.

Where you found it?
You can upload all that there (models and textures)? 
I was primarily interested in the company's characters and aliens of Covenant (elite, jackals, etc.)
Seeing as this is from the PC Forge version, the Covenant can't be ripped, with the exception of the Grunt I think (it appears in the main menu iirc).

[https://drive.google.com/file/d/0B7bLaO ... =drive_web](https://drive.google.com/file/d/0B7bLaOhnfhrRVGFqUHNuWW1ZUFk/view?usp=drive_web)

Here's the textures for the new helmets and armor (again thanks to Revo), you'll have to convert them with Zedd's bitmap tool.
## Post #81
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-01-10T07:12:53+00:00
- Post Title: Re: Halo 5: Forge Models

I know that we are have access only  for PC Forge resources.
I just thought that if the new models began to appear - perhaps Forge updated and added new models.
## Post #82
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2017-01-11T04:31:43+00:00
- Post Title: Re: Halo 5: Forge Models

I am very clearly doing something wrong.
Hilariously wrong, perhaps.



EDIT: Thanks peeps for all your hard work. This is going to be awesome for the prop community.
## Post #83
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-01-11T20:43:13+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Spartan019
>
> I am very clearly doing something wrong.
Hilariously wrong, perhaps.
EDIT: Thanks peeps for all your hard work. This is going to be awesome for the prop community.

You're wasting your time with the Forerunner weapons from Halo 5. They're straight ports from Halo 4, you could use cleaner rips from Halo 4 and then apply the Halo 5 textures.
## Post #84
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2017-01-13T03:34:43+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Spartan019 wrote:I am very clearly doing something wrong.
Hilariously wrong, perhaps.
EDIT: Thanks peeps for all your hard work. This is going to be awesome for the prop community.

You're wasting your time with the Forerunner weapons from Halo 5. They're straight ports from Halo 4, you could use cleaner rips from Halo 4 and then apply the Halo 5 textures.

They're certainly very very close to the 4 models(I spent a lot of time with them a few years ago making them printable).
So yeah, easier to just copy the differing bits over to the 4 files.
## Post #85
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2017-02-14T03:48:16+00:00
- Post Title: Re: Halo 5: Forge Models

Has any sort of recent progress been made? I've been wondering if the UV and scaling issue with the recent update has been fixed.
## Post #86
- Username: AgentJersey117
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 11, 2017 8:50 pm
- Post datetime: 2017-03-11T12:52:48+00:00
- Post Title: Re: Halo 5: Forge Models

How can I open these .model files? I tried to open them in 3DSMax but it did not opened? What can I do?
## Post #87
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-03-12T02:24:07+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from AgentJersey117
>
> How can I open these .model files? I tried to open them in 3DSMax but it did not opened? What can I do?

Tools are all conveniently linked within this thread. Please familiarise yourself with them before asking questions. Howeer, in long and short:

Download the most recent copy of the render_mesh tool (5.5 is the most recent version I could find). Drag-drop it into 3DS Max. It'll open up a box allowing you to navigate to the file you want - you'll want to use the render_mesh file as opposed to the .model file. Select your desired file and it should open up in 3DS Max for you to play with.
## Post #88
- Username: dracosfire83
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 13, 2015 7:48 am
- Post datetime: 2017-03-16T19:37:33+00:00
- Post Title: Re: Halo 5: Forge Models

Wanted to thank you Rosa for all your work and the simplified how to but I was wondering if you still had or know where I could find the texture files the link you posted on page 2 is dead.
## Post #89
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-03-17T01:36:16+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from dracosfire83
>
> Wanted to thank you Rosa for all your work and the simplified how to but I was wondering if you still had or know where I could find the texture files the link you posted on page 2 is dead.

Wow. You've come a long way from shitting on me over on the 405th - I thought you were supposed to be some sort of model-extracting god, with terabytes of assets stored on your computer. Surely you're proficient enough to be able to get them yourself, right? After everything that happened on the 405th and the way you guys pretty much dumped me out like cold bathwater, you can understand why I'm now taking a policy of 'I'll release assets privately to those that want them - otherwise, get them yourselves'. I'm no longer putting myself out and doing the amount of work that was required of me to get the assets into a fit state for you guys over on the 405th - your ingratitude and the way you guys treated me after I stepped down showed me why it's just not worth my time helping you guys. Either figure it out for yourself or can it. The tools and instructions are available for you if you look for them.
## Post #90
- Username: dracosfire83
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 13, 2015 7:48 am
- Post datetime: 2017-03-17T03:28:13+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> dracosfire83 wrote:Wanted to thank you Rosa for all your work and the simplified how to but I was wondering if you still had or know where I could find the texture files the link you posted on page 2 is dead.

Wow. You've come a long way from shitting on me over on the 405th - I thought you were supposed to be some sort of model-extracting god, with terabytes of assets stored on your computer. Surely you're proficient enough to be able to get them yourself, right? After everything that happened on the 405th and the way you guys pretty much dumped me out like cold bathwater, you can understand why I'm now taking a policy of 'I'll release assets privately to those that want them - otherwise, get them yourselves'. I'm no longer putting myself out and doing the amount of work that was required of me to get the assets into a fit state for you guys over on the 405th - your ingratitude and the way you guys treated me after I stepped down showed me why it's just not worth my time helping you guys. Either figure it out for yourself or can it. The tools and instructions are available for you if you look for them.

I was just hoping to avoid the hassle of installing a 40gig game I won't play on a hard drive that's over 90% full. But if that's what I got to do I will no problem.
## Post #91
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-03-17T03:48:02+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from dracosfire83
>
> I was just hoping to avoid the hassle of installing a 40gig game I won't play on a hard drive that's over 90% full. But if that's what I got to do I will no problem.

Sounds like a you problem, bud. Have fun.
## Post #92
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-03-20T05:38:29+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> dracosfire83 wrote:I was just hoping to avoid the hassle of installing a 40gig game I won't play on a hard drive that's over 90% full. But if that's what I got to do I will no problem.

Sounds like a you problem, bud. Have fun.

Hm the worst thing about people is the fact that their ego gets in the way and they can't get over themselves and see beyond their own arrogance, that is a huge problem when it's come to extracting Halo models in the past from like Halo 3,Reach,4......ect and the really really nice thing about it this time is we didn't need  the guys behind Adjustant's help with this game and for them to horde their work until they felt like releasing it.

My point being here is this guy asked you just to repair the link to the textures and you had to then return with a rude reply, i don't care what he did on another site but not repairing the link cause you're salty at him isn't right to others, i bet other people would like to have the textures that maybe haven't downloaded them yet (cause i know i would) or doesn't want to either install windows 10 or install the game itself and take the time to dump it to just get out textures.
## Post #93
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-03-20T16:33:51+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from JakeGreen
>
> My point being here is this guy asked you just to repair the link to the textures and you had to then return with a rude reply, i don't care what he did on another site but not repairing the link cause you're salty at him isn't right to others

You're assuming a lot about how much I care, buddy. Not just about that guy, but about people in general.

> i bet other people would like to have the textures that maybe haven't downloaded them yet (cause i know i would) or doesn't want to either install windows 10 or install the game itself and take the time to dump it to just get out textures.

Again, making a lot of assumptions there, buddy. It's very easy for you, on your side of the fence, to say 'Hey! Be nice, provide the files!' - when you've spent as much time as I have doing exactly that, and ended up with nothing but a kick in the teeth for it, you might start to see why I can't be bothered with doing it any more. If people want the files so badly, they can work for them. I'm not here just to provide for you guys any more - stop being lazy.
## Post #94
- Username: dracosfire83
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 13, 2015 7:48 am
- Post datetime: 2017-03-20T17:41:01+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from JakeGreen
>
> RosaWeyland wrote:dracosfire83 wrote:I was just hoping to avoid the hassle of installing a 40gig game I won't play on a hard drive that's over 90% full. But if that's what I got to do I will no problem.

Sounds like a you problem, bud. Have fun.

Hm the worst thing about people is the fact that their ego gets in the way and they can't get over themselves and see beyond their own arrogance, that is a huge problem when it's come to extracting Halo models in the past from like Halo 3,Reach,4......ect and the really really nice thing about it this time is we didn't need  the guys behind Adjustant's help with this game and for them to horde their work until they felt like releasing it.

My point being here is this guy asked you just to repair the link to the textures and you had to then return with a rude reply, i don't care what he did on another site but not repairing the link cause you're salty at him isn't right to others, i bet other people would like to have the textures that maybe haven't downloaded them yet (cause i know i would) or doesn't want to either install windows 10 or install the game itself and take the time to dump it to just get out textures.

While I appreciate and thank you for your support but when Rosa (cherry on the 405th) gets like this it's best just to drop it it's not worth the hassle. She wont stop till you give up or she gets banned. I was told if you look the files are still available if you feel like digging threw the facepunch forums you should find them if not message me I replaced one of my HDD's and did the work myself and I can set up a download link for you.
## Post #95
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-03-20T18:15:33+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from dracosfire83
>
> I was told if you look the files are still available if you feel like digging threw the facepunch forums you should find them if not message me

Information can go out of date pretty quickly. I took my links down because they were out of date, featured content that wasn't really fit for the intended purpose, and needed to be fixed before being re-uploaded - you know, doing my bit for the community and providing high-quality assets designed not only for the costuming groups, but for everyone else. Unfortunately, the way things were handled on the 405th (by you personally, as well as others) meant that I lost the desire to contribute to the community in general. Something about a smartass saying that he could manage my job pretty easily and bragging about the volume of assets he had might have had something to do with that.

I had planned to provide armour, vehicle and weapons models along with their corresponding lossless .DDS textures via Mega.nz since that seems to be the only viable route for getting the community high-quality assets. I have the majority of the files ready to go - but, again, I'm left providing only to certain people who I feel I can trust to not act like entitled brats. Why should I spend my free time on pulling these assets when I rarely get any gratitude for it?

I'm taking a look into audio extraction down the line. Maybe I'll share if I get something figured out, maybe I won't.
## Post #96
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-03-30T20:59:47+00:00
- Post Title: Re: Halo 5: Forge Models

It's sad when people only do this stuff for notoriety and don't give a damn otherwise, i've been on Facepunch for over 7 years and in those years i think i've released thousands of games assets in total from Halo,Call of Duty and mainly Star Wars games so other people don't have to do it and i have never once ever not refused a request or done this for notoriety.

I've spent hours and hours even sometimes days extracting assets from games like Star Wars Battlefront that require you to extract the entire game over and over again just to get out 1 or 2 new assets that was added in each update or DLC that other people have wanted that i myself didn't even care to want.

I guess my problem here is since i do stuff like this on a daily bases i guess i expect in my mind others to be just as nice and generous as i am but i guess not everyone is that nice.

But really when it comes down to it everyone in the Halo asset community is a hording person and out for notoriety when it comes to being one of the first to extract content from the newest Halo game, cause i seen it in the past with Halo 3,Reach and 4 people had access to the assets for weeks and weeks but would never release them to the community but would always show off that they had them but when asked to release them they'd always say no.
## Post #97
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-03-31T00:23:40+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from JakeGreen
>
> It's sad when people only do this stuff for notoriety and don't give a damn otherwise, i've been on Facepunch for over 7 years and in those years i think i've released thousands of games assets in total from Halo,Call of Duty and mainly Star Wars games so other people don't have to do it and i have never once ever not refused a request or done this for notoriety.

You'd be surprised at how much work I put into the Halo community. I don't work for the glamour or the recognition, admittedly nice as they are.

> I've spent hours and hours even sometimes days extracting assets from games like Star Wars Battlefront that require you to extract the entire game over and over again just to get out 1 or 2 new assets that was added in each update or DLC that other people have wanted that i myself didn't even care to want.

Yep.

> I guess my problem here is since i do stuff like this on a daily bases i guess i expect in my mind others to be just as nice and generous as i am but i guess not everyone is that nice.

It's not about generosity - it's about me providing a service and being kicked in the teeth for it. I'd love to still be able to share on a general basis but after pouring my heart and soul into this sort of thing and being treated the way I was, I don't exactly see why I should spend a massive amount of time and resources on creating huge packs for people. If people need certain things, then fine - I'll help out. But if people are expecting fully-processed texture and model packs, they need to look elsewhere.
## Post #98
- Username: AgentJersey117
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 11, 2017 8:50 pm
- Post datetime: 2017-04-11T14:50:18+00:00
- Post Title: Re: Halo 5: Forge Models

So I imported .render_model to 3dsmax with script but I can't see anything right now?
## Post #99
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-04-11T17:07:21+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from AgentJersey117
>
> So I imported .render_model to 3dsmax with script but I can't see anything right now?

Depends on the model. Some just flat-out don't work right now, check the Listener report and it should give you an idea of whether or not the import was successful. Which model were you trying to get?
## Post #100
- Username: AgentJersey117
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 11, 2017 8:50 pm
- Post datetime: 2017-04-11T21:37:51+00:00
- Post Title: Re: Halo 5: Forge Models

I first tried to open storm_masterchief (which is multiplayer spartans I think) with render_mesh tool 5.5, then I saw only 5.7(or later) version of the script can open storm_masterchief. When I open them first it lags about half our then there are objects seen in a menu but there are not any objects in scene. I know maybe I can't tell but I tried my best, sorry
## Post #101
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-04-12T03:14:00+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from AgentJersey117
>
> I first tried to open storm_masterchief (which is multiplayer spartans I think) with render_mesh tool 5.5, then I saw only 5.7(or later) version of the script can open storm_masterchief. When I open them first it lags about half our then there are objects seen in a menu but there are not any objects in scene. I know maybe I can't tell but I tried my best, sorry

The latest version is 5.5, and works absolutely fine for me. Make sure, as I said, that you check the Listener to see if there are any errors within the report, otherwise just zoom out a bit.
## Post #102
- Username: Zelorous
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 07, 2017 4:32 am
- Post datetime: 2017-06-07T18:48:36+00:00
- Post Title: Re: Halo 5: Forge Models

I have a quick question, can somebody help me get the models and textures for the player models in halo 5... I'm going to rig them to use in sfm by using a pre-existing rig... My only problem is that I don't know how to get the .model or .model_render files into blender... I also don't know how to get the textures into blender... I understand if nobody wants to help me do this cause I'm sure it's an annoying task but if anyone decides to must let me know... My Skype is "Zelorous", my Twitter is "RealZelorous", and my email is [Zelorous@outlook.com](mailto:Zelorous@outlook.com)... Thanks in advance
## Post #103
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-06-07T21:36:08+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Zelorous
>
> I have a quick question, can somebody help me get the models and textures for the player models in halo 5... I'm going to rig them to use in sfm by using a pre-existing rig... My only problem is that I don't know how to get the .model or .model_render files into blender... I also don't know how to get the textures into blender... I understand if nobody wants to help me do this cause I'm sure it's an annoying task but if anyone decides to must let me know... My Skype is "Zelorous", my Twitter is "RealZelorous", and my email is Zelorous@outlook.com... Thanks in advance

Read the thread. The answers are all here.
## Post #104
- Username: Zelorous
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 07, 2017 4:32 am
- Post datetime: 2017-06-07T22:40:55+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Zelorous wrote:I have a quick question, can somebody help me get the models and textures for the player models in halo 5... I'm going to rig them to use in sfm by using a pre-existing rig... My only problem is that I don't know how to get the .model or .model_render files into blender... I also don't know how to get the textures into blender... I understand if nobody wants to help me do this cause I'm sure it's an annoying task but if anyone decides to must let me know... My Skype is "Zelorous", my Twitter is "RealZelorous", and my email is Zelorous@outlook.com... Thanks in advance 

Read the thread. The answers are all here.

I have read the thread multiple times... I still don't understand how to get the models and textures converted into a format that blender can read... I don't have any other 3d software... I also don't know how to code... That's why I need help understanding it... I've never converted anything other than sfm models... But thank you for replying
## Post #105
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-06-07T22:53:19+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Zelorous
>
> I have read the thread multiple times... I still don't understand how to get the models and textures converted into a format that blender can read... I don't have any other 3d software... I also don't know how to code... That's why I need help understanding it... I've never converted anything other than sfm models... But thank you for replying

Use the scripts. Like I said - the answers are all there. You'll need a copy of 3DS Max.
## Post #106
- Username: Zelorous
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 07, 2017 4:32 am
- Post datetime: 2017-06-07T22:59:13+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Zelorous wrote:I have read the thread multiple times... I still don't understand how to get the models and textures converted into a format that blender can read... I don't have any other 3d software... I also don't know how to code... That's why I need help understanding it... I've never converted anything other than sfm models... But thank you for replying 

Use the scripts. Like I said - the answers are all there. You'll need a copy of 3DS Max.

Thank you for suggesting that, I was hoping I didn't have to install 3ds max, because I knew thats what the others were using... I will just wait for someone to release the models and texture files... Thank you for the help though, I always appreciate it
## Post #107
- Username: The501stJournal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jun 17, 2017 2:13 pm
- Post datetime: 2017-06-17T06:34:15+00:00
- Post Title: Re: Halo 5: Forge Models

Hey rosa did someone touch a nerve? If you had the spine you would see that your being a immature faggotron about you having tools to export textures and how you play victim and act as if you did nothing wrong when someone asks for them when in reality you were being a dickhead. Acting like your better then everybody makes you look like more of a piece of shit then you already. STOP being a dick and actually be a community member along with getting off your high horse, 'Or one of these days someones gonna release them and your gonna be a nobody.'

Pull your head out of your ass.
## Post #108
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-06-23T16:19:35+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from The501stJournal
>
> STOP being a dick and actually be a community member along with getting off your high horse
I did. As I said, all of the tools are available in the thread, or accessible via a quick Google search. If somebody can't be bothered to do five minutes of reading in their own time to find them, then I can't be bothered to help. If it were a case of 'hey, these tools aren't working as expected, what am I doing wrong?' then sure, I'm happy to help, but if it's a case of 'I can't be bothered to read two or three pages back to find the tools I need' then sorry, you're looking at the wrong person.

> 'Or one of these days someones gonna release them and your gonna be a nobody.'

Glossing completely over the fact that anybody with half a brain and some time on their hands can pull these assets for themselves, sure. Only difference here is that I'm the only person who's been willing to compile asset packs for people to download and use without having to go through the hassle of getting the tools working in the first place - literally anybody else can do what I've done. Of course, nobody has, because nobody can be bothered to.
## Post #109
- Username: savinpvtmike
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Aug 11, 2015 5:07 pm
- Post datetime: 2017-07-01T01:25:05+00:00
- Post Title: Re: Halo 5: Forge Models

hey is there a updated script for the mesh importer?
## Post #110
- Username: Zelorous
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 07, 2017 4:32 am
- Post datetime: 2017-07-01T08:16:27+00:00
- Post Title: Re: Halo 5: Forge Models

Not everything... There's no explanation of the .material file and how to make it a bit map file... No help as to how the hell the armors and visors are labeled... And there's is'nt any help as to how the textures are labelled so weirdly... And the armor files for the "Global.rtx" don't seem to have all of the armors and helmets... And some of the ones it does have (toward the bottom of the list) are corrupted it seems. And yes, I have done my research and spent more than five minutes and have more than half a brain... So yeah
## Post #111
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-07-03T02:33:18+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Zelorous
>
> Not everything... There's no explanation of the .material file and how to make it a bit map file...

Open up, here comes the airplane, zoom zoom, time to spoonfeed.

1. [Grab this file.](https://mega.nz/#!0w9DQBRB!AWru_LieXWWb10mv6Iprc8GMf-o6P77jJ1zRged_96Y)
2. Use the easy-peasy lemon-squeezy instructions bundled with said file to obtain working textures.
3. Use the Intel Texture Works plugin for Photoshop to convert the files from .dds into a usable format
4. Free space. Go nuts.
5. Enjoy having the ability to extract your own textures.

> No help as to how the hell the armors and visors are labeled...
Probably because most people are focused more on the far easier process of extracting the armour files from Halo Waypoint over the actual game files. The high-quality Waypoint files are equal to their game counterparts, and since I'm currently unaware of any rigging support for models, save yourself some trouble and grab the files from Waypoint.

> And there's is'nt any help as to how the textures are labelled so weirdly
That's an issue with every Halo title ever - files use internal development tags for referencing. It's generally pretty easy to figure out what a texture is by the tag, and if not, a quick extract and look will generally tell you.

> And the armor files for the "Global.rtx" don't seem to have all of the armors and helmets...
Probably because others are kept within patch files. 

> And some of the ones it does have (toward the bottom of the list) are corrupted it seems.
This is why we use the Waypoint files.

> And yes, I have done my research and spent more than five minutes and have more than half a brain... So yeah
First point, maybe. Second point, debatable. Either way, this stuff should all be pretty common sense and easy to figure out if you'd actually done some reading, it's all pretty well-documented over on Facepunch, and if you ask nicely I might just do a write-up for you here.
## Post #112
- Username: Zelorous
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 07, 2017 4:32 am
- Post datetime: 2017-07-03T03:51:43+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Zelorous wrote:Not everything... There's no explanation of the .material file and how to make it a bit map file...

Open up, here comes the airplane, zoom zoom, time to spoonfeed.

1. Grab this file.
2. Use the easy-peasy lemon-squeezy instructions bundled with said file to obtain working textures.
3. Use the Intel Texture Works plugin for Photoshop to convert the files from .dds into a usable format
4. Free space. Go nuts.
5. Enjoy having the ability to extract your own textures.
No help as to how the hell the armors and visors are labeled...
Probably because most people are focused more on the far easier process of extracting the armour files from Halo Waypoint over the actual game files. The high-quality Waypoint files are equal to their game counterparts, and since I'm currently unaware of any rigging support for models, save yourself some trouble and grab the files from Waypoint.
And there's is'nt any help as to how the textures are labelled so weirdly
That's an issue with every Halo title ever - files use internal development tags for referencing. It's generally pretty easy to figure out what a texture is by the tag, and if not, a quick extract and look will generally tell you.
And the armor files for the "Global.rtx" don't seem to have all of the armors and helmets...
Probably because others are kept within patch files. 
And some of the ones it does have (toward the bottom of the list) are corrupted it seems.
This is why we use the Waypoint files.
And yes, I have done my research and spent more than five minutes and have more than half a brain... So yeah
First point, maybe. Second point, debatable. Either way, this stuff should all be pretty common sense and easy to figure out if you'd actually done some reading, it's all pretty well-documented over on Facepunch, and if you ask nicely I might just do a write-up for you here.[/quote

Wow... you legit stated stuff I already know... I'm like 20 steps ahead of you, yet 2 steps behind at the same freaking time... My problem isn't the dang bitmap conversion, its the extraction of the (pc) module file... (you only uploaded the [any] files and not the [pc] files so basically there is no way to get the textures from those files, because I asked Soul_ and he said there wasn't any way to change the .material into a .bitmap)... You also removed the link to the raw texture data... And the "simple" extraction tool doesn't even open the global files to be read... Also cut the sarcasm, its not like I'm some god of technology that should know how to do everything... SO before you go and assume that I haven't done anything, I've been working at this since I asked you about the render_mesh issues I was having... So if your going to do nothing constructive in my situation, then please stop messaging me with all the sarcasm... I'm not whoever it was that pissed you off and made you quit porting so stop treating me that way
## Post #113
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-07-03T04:37:25+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Zelorous
>
> -SNIP!-

Soul_ is right - you're doing it wrong. Which is the hilarious thing - all of the tools are self-explanatory, and the documentation is out there if you'd do more than five minutes of Googling. It's getting embarrassing at this point, however, SO. I'm figuring that you just haven't decrypted your files.

To prep the game files for extraction:
1. If your H5F files aren't accessible via Admin privileges, set that up. I won't bother walking you through that.
2. Download the [UWP Dumper tool](https://github.com/Wunkolo/UWPDumper) to decrypt and dump the game files into a new folder. Documentation is included in the tool, I won't bother walking you through that.
3. Once you've done that, use the latest version of Module Extractor to extract the files out of your desired module file
- (any)globals-rtx-1 contains models
- globals-rtx-1 contains textures
- mainmenu-rtx-1 contains the main menu files
4. Drag/drop your desired module file onto the Module Extractor tool. It will automatically unpack the module file for you and spit out a new folder containing the unpacked files.
5. The content will be contained within the _chore folder (for example globals-rtx-1 > _chore > pc_ > objects)
6. Enjoy.

From there:

For bitmaps:
1. Download the aforementioned bitmap tool
2. Locate the file you'd like to convert
3. Each texture will have a BITMAP file, a generic file, and a number of CHUNK files. Drag/drop the BITMAP file onto the bitmap tool and it will dump out a DDS file for you.
4. Import the dumped DDS file into the latest version of Photoshop. Make sure you have the Intel Texture Works plugin installed as well.
5. Enjoy.

For models:
1. Ensure you have a relatively up-to-date copy of 3DS MAX.
2. Download the latest version of render_mesh from this thread (v5.5 is the latest version).
3. Drag/drop the render_mesh tool into 3DS Max to open it.
4. From there, locate the model folder you'd like to open.
- Model folders contain several files - you're going to be looking for the RENDER_MODEL file
5. Once you've found that, open it.
6. Enjoy.

Bear in mind that some models, and some textures, do not work. If they don't work, you're shit out of luck, cry some more. If you still can't get files out after this comprehensive walk-through, I invite you to try something novel and inventive, such as flushing your head down a toilet.
## Post #114
- Username: Zelorous
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 07, 2017 4:32 am
- Post datetime: 2017-07-03T05:05:03+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Zelorous wrote:-SNIP!-

Soul_ is right - you're doing it wrong. Which is the hilarious thing - all of the tools are self-explanatory, and the documentation is out there if you'd do more than five minutes of Googling. It's getting embarrassing at this point, however, SO. I'm figuring that you just haven't decrypted your files.

To prep the game files for extraction:
1. If your H5F files aren't accessible via Admin privileges, set that up. I won't bother walking you through that.
2. Download the UWP Dumper tool to decrypt and dump the game files into a new folder. Documentation is included in the tool, I won't bother walking you through that.
3. Once you've done that, use the latest version of Module Extractor to extract the files out of your desired module file
- (any)globals-rtx-1 contains models
- globals-rtx-1 contains textures
- mainmenu-rtx-1 contains the main menu files
4. Drag/drop your desired module file onto the Module Extractor tool. It will automatically unpack the module file for you and spit out a new folder containing the unpacked files.
5. The content will be contained within the _chore folder (for example globals-rtx-1 > _chore > pc_ > objects)
6. Enjoy.

From there:

For bitmaps:
1. Download the aforementioned bitmap tool
2. Locate the file you'd like to convert
3. Each texture will have a BITMAP file, a generic file, and a number of CHUNK files. Drag/drop the BITMAP file onto the bitmap tool and it will dump out a DDS file for you.
4. Import the dumped DDS file into the latest version of Photoshop. Make sure you have the Intel Texture Works plugin installed as well.
5. Enjoy.

For models:
1. Ensure you have a relatively up-to-date copy of 3DS MAX.
2. Download the latest version of render_mesh from this thread (v5.5 is the latest version).
3. Drag/drop the render_mesh tool into 3DS Max to open it.
4. From there, locate the model folder you'd like to open.
- Model folders contain several files - you're going to be looking for the RENDER_MODEL file
5. Once you've found that, open it.
6. Enjoy.

Bear in mind that some models, and some textures, do not work. If they don't work, you're shit out of luck, cry some more. If you still can't get files out after this comprehensive walk-through, I invite you to try something novel and inventive, such as flushing your head down a toilet.



I'm am about to sound most likely the dumbest I ever have... but what is the process id for the tool... I fear that since I moved the deploy file to my desktop, then accidentally moved the module file out the deploy folder onto my desktop, that I royaly screwed myself

Edit: I think I know now, which means that I have to redownload halo 5 forge again in order to get the files back to there original destination
## Post #115
- Username: RosaWeyland
- Rank: beginner
- Number of posts: 37
- Joined date: Sun Dec 15, 2013 5:20 am
- Post datetime: 2017-07-03T05:11:11+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from Zelorous
>
> I'm am about to sound most likely the dumbest I ever have... but what is the process id for the tool... I fear that since I moved the deploy file to my desktop, then accidentally moved the module file out the deploy folder onto my desktop, that I royaly screwed myself

Just delete everything you've already done to the game. Refresh everything, download a fresh installation, start from scratch. Follow my instructions and you should be fine.
## Post #116
- Username: Zelorous
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 07, 2017 4:32 am
- Post datetime: 2017-07-03T05:46:09+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland
>
> Zelorous wrote:I'm am about to sound most likely the dumbest I ever have... but what is the process id for the tool... I fear that since I moved the deploy file to my desktop, then accidentally moved the module file out the deploy folder onto my desktop, that I royaly screwed myself

Just delete everything you've already done to the game. Refresh everything, download a fresh installation, start from scratch. Follow my instructions and you should be fine.

Thanks again Rosa... Now I can occupy my stupidity and obliviousness for a few weeks
## Post #117
- Username: urium86
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 29, 2016 11:33 pm
- Post datetime: 2017-07-09T19:38:55+00:00
- Post Title: Re: Halo 5: Forge Models

Hi take a look for this video 
[https://youtu.be/JD3gIXwYBcg](https://youtu.be/JD3gIXwYBcg)
## Post #118
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2017-10-22T19:07:03+00:00
- Post Title: Re: Halo 5: Forge Models

Separate script for static models (\.\levels\forge\assets, etc). I have some problem with define offset of scale coefficients.
But you can set this value manualy.

Instruction:
1. Open *.render model with any hex editor.
2. Find at the end of the file a block similar to img1. It  often starts with values 0xBCBC. On img1 offset of this block is 0x160b

-- dead picture duplicated on the next page --

3. Write this offset to first string of script (scale_offset = 0xXXXX) 
4. Use script.
5. Enjoy!  

[](http://savepic.net/10158975.htm)

[render_mesh_static.7z](https://xentaxbackup.github.io/file/13485_render_mesh_static.7z)
## Post #119
- Username: cmpxchg8b
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 30, 2017 8:14 pm
- Post datetime: 2017-11-30T12:29:59+00:00
- Post Title: Re: Halo 5: Forge Models

Heya all.

I've extracted some models from H5F and imported them into 3DS using the render_mesh script. Everything looks great, except the models are too big.

I could fix this quite easily by just scaling everything down to the canon heights, but that would be somewhat imprecise (in so far that the models might not actually be that size in-game).

Is there any way to determine the precise scaling factor required to reduce the models down into real world units? The only thing I've noticed is that each model appears to contain some sort of "marker box" between the feet, and that this somehow has to do with scaling (since it's basically a perfect cube when the model is scaled correctly). Should this box measure a specific size? For example, 1ft^3 (since H5F uses feet for units)? It seems like this brings most Spartans down to within +/- 10% of their canon-specified heights, but it's not exact (for example, if the box measured exactly 1ft^3, then Locke would be about 7.375 feet tall, when canon says he's only 6.83 feet fall).

Cheers,
-CMPX
## Post #120
- Username: frostedtalents
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 23, 2018 10:59 am
- Post datetime: 2018-08-25T01:42:39+00:00
- Post Title: Re: Halo 5: Forge Models

What software do I use to import and play with the models?
## Post #121
- Username: ReclaimerOmega
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 08, 2019 5:19 pm
- Post datetime: 2019-02-21T13:21:44+00:00
- Post Title: Re: Halo 5: Forge Models

Any way to import the H5 Forge model Forge blocks? example: "(any)globals-rtx-1\levels\forge\assets\fo_breakout_accent_2x70x8_c", I used the render_model script, but when I tried to import a render_model doesn't happen nothing.
## Post #122
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2019-03-31T19:17:57+00:00
- Post Title: Re: Halo 5: Forge Models

Repeat image with scale's offset for static meshes:



halo_offset.png (59.81 KiB) Viewed 394 times
## Post #123
- Username: Swagguy47
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 20, 2020 10:24 am
- Post datetime: 2020-10-10T21:53:29+00:00
- Post Title: Re: Halo 5: Forge Models

Not sure if anyone else here has tried this, but if you download the Halo 5: Guardians Local Server app, it also has "rtx" maps inside. Unlike Halo 5: Forge though, this has many campaign assets as well, like warden, jackal, elite, arby, guardians, lasky, roland, etc. They load in the Reclaimer tool and lets you preview the models, but it doesn't support the textures from it or export the weights correctly.

Preview images:
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1u74Vv86e3Q-GsMFqAmkkzfRFz3o1Ejgm?usp=sharing)
## Post #124
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-14T11:03:58+00:00
- Post Title: Re: Halo 5: Forge Models

Has anyone tried repeating this?
How did you unlock WindowsApps encryption?
## Post #125
- Username: Swagguy47
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jul 20, 2020 10:24 am
- Post datetime: 2020-10-25T16:48:48+00:00
- Post Title: Re: Halo 5: Forge Models

(sorry for late reply)
UWPDumper can unpack it all. From the dump it created is where I found the files.
After some talk with the community, some people think these are the Warzone assets, which makes it weird that arby, roland, lasky and all them are in it. But I guess makes sense. Also I found an unused splinter turret model in it too! Tons of fun stuff
## Post #126
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-11-10T01:21:50+00:00
- Post Title: Re: Halo 5: Forge Models

Hello guy i am new to H5 model extraction, i was wondering, how in the world you can overwrite the permissions of the windowsapp, for example halo wars 2 i have located the files for the entire game but the files have a lock in it, when trying to copy them they ask about the permission D game developer, i have read about it but still don't know how it works, if someone could help me out with it, just once, i will be able to extract the files from HW2 and H5F if possible H5G, i will be grateful if you could help me out with this, i been trying on my own but no success yet, thank you in advance for your time!
## Post #127
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2020-11-15T19:07:28+00:00
- Post Title: Re: Halo 5: Forge Models

I have a similar issue. I wanted to rip files from Gears of war 4 but Microsoft Store Encryption is stopping me from doing it, so i tried to use UWP Dumper as you suggested but gears 4 doesn't even show up in the 'UWP Dumper' list of extractable softwares.
Maybe it's due to the fact that my Gears 4 is installed on 'D' drive instead of the main 'System C' drive...
My 'C' drive isn't that big so i'm unable to install Gears 4 on it.
Is there a way to change up UWP Dumper's path so it can detect the game and dump the files in 'D' drive?
Thank you all!
## Post #128
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2020-11-25T19:32:44+00:00
- Post Title: Re: Halo 5: Forge Models

The fastest way to extract files is to download the files from the internet, because you gonna run into programmers staff, find the game you want from torrents or installers, it gonna save you from investing a lot of time for extracting the files.
## Post #129
- Username: oashkoash
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 02, 2016 1:16 am
- Post datetime: 2020-12-01T20:33:21+00:00
- Post Title: Re: Halo 5: Forge Models

CAN CONFIRM this works! Just download the FREE Halo 5 Server tool through the Windows Store, use UWPD and make sure you have the H5 tags available in Assembly. Just be prepared for a massive file dump.
## Post #130
- Username: ChromaCore
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 01, 2020 7:26 am
- Post datetime: 2020-12-16T00:30:05+00:00
- Post Title: Re: Halo 5: Forge Models

Has anyone been able to pull the custom vertex normal data?
## Post #131
- Username: Keltoi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 03, 2021 1:37 am
- Post datetime: 2021-01-02T18:01:09+00:00
- Post Title: Re: Halo 5: Forge Models

> Reply from RosaWeyland ↑Tue Nov 01, 2016 9:43 am at Tue Nov 01, 2016 9:43 am
>
> 
zaramot wrote:In order to make some teaser and raise motivation to send me more models+textures. I'm posting this pic with Master Chief and Spartan Locke imported from Halo 5 Forge (with all LODs) xD And Locke has nice face mesh under helmet  


I think I can help you out there. I pulled all of the raw files from the game and I've been working on compiling the textures into a megapack along with the Waypoint-extracted armour files. However, I've also zipped up all of the models and textures from their raw formats and pushed them to my Mega account for others to use and enjoy. Please take them and make better use of them than I could - I'd love to be able to start processing models out of the game myself and putting together packs for people to use. Since you say you already have the textures I'm focusing on the models.

I'm also going to be pushing the full armour/textures pack as soon as I've done it, hopefully as some sort of incentive/thank-you for those with the technical expertise to process the raw model data - my main resource is time, so I'm happy to sit and spend a few hours trawling through the files and getting them all pulled from the game and sorted for others to use. It's a small matter compared to the work that goes into getting the files out.

You can grab my files here:
https://mega.nz/#!kps3xKqA!1xn7XOl5jeDS ... Ok5B7WAUpQ
(WARNING: 700mb+)

Also, please feel free to fire me up on Discord or Skype if you need anything directly that I've forgotten or accidentally omitted - I'll leave links to those if you need them.

I would love to ask you some questions on discord! I also noticed your links have expired :/ would you have these files still? My discord is Plastered_crab#1070
## Post #132
- Username: Inconnuxdark
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue May 14, 2019 9:12 pm
- Post datetime: 2021-01-29T14:47:40+00:00
- Post Title: Re: Halo 5: Forge Models

Hello everyone
I would have a request to ask you as you can see I am looking for the character Edward Buck from Halo 5 guardians in 3D file and unfortunately I did not manage to find this character, someone here would have found it the 3D model or not at all ?
If you can advise me where in the game files I would be grateful.
## Post #133
- Username: ChristianCRG27
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 10, 2021 8:42 am
- Post datetime: 2021-08-11T02:51:03+00:00
- Post Title: Re: Halo 5: Forge Models

is this stuff still relevant? , want to pay someone to make me and .obj file for the war master armor/and helmet cant find those on the internet or how do you solve the extract files isuue links are expired to... discord me
CRG#3735
## Post #134
- Username: satademon7
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Oct 05, 2017 12:14 pm
- Post datetime: 2021-11-30T19:18:04+00:00
- Post Title: Re: Halo 5: Forge Models

even though this model isnt from halo 5, dont mind, the halo 2 spartan flood is here; by the way is there any possiblility that anybody could upload the halo 5 files, i have try everything, but no success at all, just wanting to know anybody with good soul wanting to share the files?, either way any promethean soldiers out there?
[aerial view.png](https://xentaxbackup.github.io/file/21317_aerial view.png)
