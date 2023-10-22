## Post #1
- Username: BenXX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 16, 2019 10:32 pm
- Post datetime: 2020-02-24T23:06:50+00:00
- Post Title: Possible to merge models while preserving animations in Noesis (or other program)?

Hey everyone, I'm creating some Dragon Quest Builders 2 stuff and for that I need a fully functioning model.
Unfortunately the models are split into 3 parts - body, face & hair.

Is there a way to combine/merge those 3 elements into 1 model in Noesis or any other program?

Here are a few screens:
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-02-25T01:53:58+00:00
- Post Title: Possible to merge models while preserving animations in Noesis (or other program)?

Weight transfer is required when transferring a mesh that does not fit in one rig to another rig.
It can be done with 3D software, but it may not be easy.

By the way, this uses Joshua's fmt_g1m isn't?
He is very kind. There should have been an option in the plugin to combine(merge) the rigs.

There is a "Model merging" Note on his github page. See that.
## Post #3
- Username: BenXX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Dec 16, 2019 10:32 pm
- Post datetime: 2020-02-25T15:03:47+00:00
- Post Title: Possible to merge models while preserving animations in Noesis (or other program)?

Ahh found it! Thank you 

Model merging

If you want to combine models, follow these steps :

    put all the desired models in the same folder. If the skeleton g1m is in a separate file, put it in another folder.
    make sure to put bAutoLoadG1MS to False and bLoadG1MS to True.
    right click on the first g1m and choose model merge. Noesis will then load all the models of the same format located next to the one selected. They will be loaded one after another, choose the texture file, skeleton and animations for each one of them (most of the time you'll have to choose the same skeleton and animations for all of them)

The model merger can also be used to extract textures from several g1t files at the same time.

If you only want the t-posed combined model, put the MERGE_BONES option to 1 at the top of the merge script, it will combine the skeletons. As of now it doesn't work for animations so keep it to 0 if you want combined meshes animated, it will have some duplicated bones. Textures will be duplicated too if the same g1t was use for all the models, I will correct it in the future
