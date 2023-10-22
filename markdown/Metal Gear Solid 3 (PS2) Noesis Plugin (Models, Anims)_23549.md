## Post #1
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-05T19:48:46+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Firstly I'd like to thank revel8n for helping me with how the face indices are created. I've released a plugin which you can grab from the link below which will allow you to view textured models and animations from the game Metal Gear Solid 3 on the PS2. To view animations you have to select 'Prompt for Motion Archive' in the tool menu. You can get the plugin here;
[https://github.com/Jayveer/MGS-MDL-Noesis/releases](https://github.com/Jayveer/MGS-MDL-Noesis/releases)

Like my other mgs noesis plugins it will automatically map the textures provided the tri files are in the correct directory alongside the model, which it will be if you use the tool below to extract the files from the games SLOT and STAGE dat files.
[https://github.com/Jayveer/Shagohod/releases](https://github.com/Jayveer/Shagohod/releases)

I haven't tried it on every file, so let me know if there are issues, I think there are issues with some textures, I'll look into that eventually.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2021-03-06T05:40:56+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Awesome work Jay!
There a small number of you guys just holding down the MGS fort, awesome stuff.

Does this tool happen to support animations from within cutscenes or is it purely gameplay animations?
## Post #3
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-03-06T14:35:47+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

I''m actually not sure, I think the mtar's for cutscenes are in the demo.dat alongside other stuff used for cutscenes, rather than the stage and slot files. But i've never looked into the demo.dat files.
## Post #4
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-04-23T15:20:57+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Hey, do you know where I can find the player animations .MTAR? Also will there be a fix in the near future for the broken weights/rigging on the models? Great work as always however!
## Post #5
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-23T16:29:49+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

This is very cool! Does this allow us to extract the models with skeletons/weights too? I know it's been done before somewhere...
## Post #6
- Username: OPR23b
- Rank: advanced
- Number of posts: 50
- Joined date: Mon Mar 08, 2021 6:54 am
- Post datetime: 2021-04-23T17:19:57+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

It does, along with animations.
## Post #7
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-24T02:38:36+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

This is awesome! One problem, the weights and rigging is broken, is this going to be fixed in a future update?
## Post #8
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-04-26T10:14:15+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Hi, can you tell if that's happening on a specific model or all models you're trying? Also If you play an animation within noesis does that work ok or is it messed up there as well? Just trying to find out if it happens on export or before. Also which version of Noesis are you using? Thanks.
## Post #9
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-26T13:01:05+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

> Reply from JayK ↑Mon Apr 26, 2021 6:14 pm at Mon Apr 26, 2021 6:14 pm
>
> 
Hi, can you tell if that's happening on a specific model or all models you're trying? Also If you play an animation within noesis does that work ok or is it messed up there as well? Just trying to find out if it happens on export or before. Also which version of Noesis are you using? Thanks.

I'm using Noesis v4442, the latest on RWS's website. I used it to view EVA's Tatiana Disguise outfit, called something like "eve_tac" or something and the rigging was broken I remember. I don't know if this is the case with other models though but it seems like it, as another user a few posts above also reported broken weights/rigging.
## Post #10
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-04-26T13:12:48+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Can you try playing an animation for that model within Noesis by selecting 'Prompt for Mtar' in the menu? For example try 0d8f7b.mtar in S122a
## Post #11
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-26T14:17:22+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Huh okay now it seems to be alright. The only thing that sucks is that the bones aren't named and for some reason the model is split into a thousand different pieces when I export as fbx, and import into Blender. Some of this rigging looks a bit crappy but I guess that's what I get for trying a ps2 model lol.
## Post #12
- Username: JayK
- Rank: mega-veteran
- Number of posts: 172
- Joined date: Fri Jun 01, 2012 5:08 pm
- Post datetime: 2021-04-26T14:30:44+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Well, there are bone names that are being set, it's just that the game uses a 6 byte hash. I could use a dictionary to resolve the real names but I don't know what all of them are. As far as I know when exporting to fbx and loading it in 3ds max these hash names should be retained, dunno about blender. For the meshes being split up I could do something to group meshes in a future release. I'm still curious about this situation in which the rigging is messed up though considering two of you have mentioned it now, it's not a problem I've ever run into and things often don't just fix themselves so I'd like to find out more about that if possible.
## Post #13
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-04-26T15:01:30+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

> Reply from JayK ↑Mon Apr 26, 2021 10:30 pm at Mon Apr 26, 2021 10:30 pm
>
> 
Well, there are bone names that are being set, it's just that the game uses a 6 byte hash. I could use a dictionary to resolve the real names but I don't know what all of them are. As far as I know when exporting to fbx and loading it in 3ds max these hash names should be retained, dunno about blender. For the meshes being split up I could do something to group meshes in a future release. I'm still curious about this situation in which the rigging is messed up though considering two of you have mentioned it now, it's not a problem I've ever run into and things often don't just fix themselves so I'd like to find out more about that if possible.

Sure I'd love to help if I can, I'm not sure if it was my own user error or I was thrown off by the bad shading in Blender because the meshes are split up into all these pieces. They look like this in Max for me:



So I kind of need these to be conjoined together into one mesh, the body anyway but I don't seem to have any way of doing that in Max. I know in Blender it's easy to conjoin meshes without losing skin data/rigging but not in Max so this is a bit...well it's a problem for me lol. I figure if there is a  way to fix this, the meshes will need to be welded with a low threshold anyway.
## Post #14
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2021-04-30T17:04:03+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Okay, rigging works for previews but Noesis crashes instantly upon importing any of Snake's .MTAR anims from the r_sna01, r_sna02, r_sna03 folders..
## Post #15
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2023-03-13T18:32:38+00:00
- Post Title: Metal Gear Solid 3 (PS2) Noesis Plugin (Models, Anims)

Is it possible for an update so ripping snake's animations is possible?   Thank you in advance.
