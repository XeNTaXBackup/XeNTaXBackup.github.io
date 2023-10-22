## Post #1
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-06-12T17:50:27+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

I've run into a strange problem while extracting models from FFXV.  Typically, when I extract a model from FFXV (using FFXVScout tool) Noesis displays it correctly with its entire skeleton.  There is one model, however, that Noesis indicates as having *no* skeleton (specifically the model for Ignis used in chapter 3 of Episode Ignis DLC).  It indicates that the model has no bones at all.  Now I know this can't be given that the model animates in game (and has unique hair, etc that must have required bones).  I thought it might be that the Episode Ignis model exceeded some hidden bone limit of Noesis, but the other models from ep Ignis display properly with bones (the model you start with has 1382 bones).

My question--is there any reason Noesis would choose not to display bones on just this one model?  Any advice would be greatly appreciated!

Relevant info: 

1. the extracted models from FFXV are gmdl.gfxbin

2. the Episode Ignis model in question is nh03_310.gmdl.gfxbin
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-12T18:03:17+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

The skeleton is read from the .amdl file. Make sure you have that.
## Post #3
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-06-12T18:08:51+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

> Reply from akderebur
>
> The skeleton is read from the .amdl file. Make sure you have that.

Thanks for the quick reply!  I'm pretty new to modding, where can I find that file?  When I have extracted FFXV files (.earcs) I haven't seen that file popup.

Edit: Had a look at the model's hex and I did not see a call for the .amdl (saw gmdl and gmtl calls)
## Post #4
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-12T18:16:53+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

> Reply from metapoodle
>
> When I have extracted FFXV files (.earcs) I haven't seen that file popup.
It should get extracted for the models that have skeleton. For example this is for Noctis.



gfxbin is inside the "model_010" folder, and amdl is in the upper directory as you can see. Noesis should be able to load the models with skeleton, if the structure is like this.

So I think you are missing the amdl. I am not sure why it isn't getting exported, but since you said it is a DLC character it is possible that the model uses the amdl file of the standard Ignis. This is just a guess though. I haven't really checked lots of FFXV models, so can't say for sure.
## Post #5
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-06-12T18:18:22+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

> Reply from akderebur
>
> metapoodle wrote:When I have extracted FFXV files (.earcs) I haven't seen that file popup.
It should get extracted for the models that have skeleton. For example this is for Noctis.



gfxbin is inside the "model_010" folder, and amdl is in the upper directory as you can see. Noesis should be able to load the models with skeleton, if the structure is like this.

So I think you are missing the amdl. I am not sure why it isn't getting exported, but since you said it is a DLC character it is possible that the model uses the amdl file of the standard Ignis. This is just a guess though. I haven't really checked lots of FFXV models, so can't say for sure.

Thanks--this helps a lot.  I'll give it a look and see if I can see what's up.  In the meantime, is it possible for there to be a boneless Ignis and yet he is animated because the programming calls for a skeleton from a different model?

Edit: basically what I'm trying to do is extract that cool looking model for Ignis (310) but when I extracted him he was a boneless chicken and it was sad.  So I've either got to find his missing skele or re rig him I guess.
## Post #6
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-06-12T18:25:04+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

> Reply from metapoodle
>
> In the meantime, is it possible for there to be a boneless Ignis and yet he is animated because the programming calls for a skeleton from a different model?
It might be using a shared (common) skeleton, or like I said the skeleton of the standard Ignis. I don't think it will be a shared skeleton, because he is one of the main chars, so standard Ignis is more likely. Just try copying the Ignis amdl to the directory where you extracted the DLC outfit, and see if Noesis loads it properly.

Of course you can also open the gfxbin file in a hex editor, and check what amdl file it references.
## Post #7
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-06-12T18:32:45+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

> Reply from akderebur
>
> metapoodle wrote:In the meantime, is it possible for there to be a boneless Ignis and yet he is animated because the programming calls for a skeleton from a different model?
It might be using a shared (common) skeleton, or like I said the skeleton of the standard Ignis. I don't think it will be a shared skeleton, because he is one of the main chars, so standard Ignis is more likely. Just try copying the Ignis amdl to the directory where you extracted the DLC outfit, and see if Noesis loads it properly.

Of course you can also open the gfxbin file in a hex editor, and check what amdl file it references.

Thanks much--I was able to locate the .amdl in the nh03 archive but it's not showing in Noesis for some reason.  Let me try your suggestion.  Thanks for the help--most progress I've made in a while.
## Post #8
- Username: metapoodle
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Jun 13, 2018 1:28 am
- Post datetime: 2018-06-12T18:51:21+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

> Reply from akderebur
>
> metapoodle wrote:In the meantime, is it possible for there to be a boneless Ignis and yet he is animated because the programming calls for a skeleton from a different model?
It might be using a shared (common) skeleton, or like I said the skeleton of the standard Ignis. I don't think it will be a shared skeleton, because he is one of the main chars, so standard Ignis is more likely. Just try copying the Ignis amdl to the directory where you extracted the DLC outfit, and see if Noesis loads it properly.

Of course you can also open the gfxbin file in a hex editor, and check what amdl file it references.

You are a legend.  It worked!!!  Saved me the total nightmare of re-rigging.
## Post #9
- Username: Arshi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 02, 2023 4:43 pm
- Post datetime: 2023-02-06T08:50:18+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

There is a possibility that not all of the bones in the model are being attempted to be parsed but NotEs are being detected. In order to address this potential issue, please ensure that the bones within the model is attempted to be parsed by NotEs are properly geo-referenced and exported.GBWhatsApp
## Post #10
- Username: neonvega
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Sep 06, 2021 6:58 am
- Post datetime: 2023-02-06T23:14:04+00:00
- Post Title: Noesis not detecting bones from a specific model in FFXV

its none of that Ive extracted and ported from ffxv to blender and xps the main issue is when a model isnt displaying bones all you have to do is simply go to that root folder like xe-and drag the amdl file into the model folder then the bones will show up in noesis that simple
