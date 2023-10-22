## Post #1
- Username: Kotcrab
- Rank: beginner
- Number of posts: 31
- Joined date: Fri Jul 28, 2017 5:36 pm
- Post datetime: 2020-04-28T20:06:22+00:00
- Post Title: Fate/Extra and Fate/Extra CCC animations

Fate/Extra and Fate/Extra CCC store animations in .mob files. Inside those are .Imm files. Each .Imm file is a single animation. I made a script for Blender that can import those animations.

Download latest fate-tools:
[https://github.com/kotcrab/fate-tools/releases](https://github.com/kotcrab/fate-tools/releases)
Script is under blender/import_mob.py

How to use:
- Export the model from Noesis and import it into Blender
- Save the Blender file somewhere
- Copy .mob files for the model next to the Blender file
- Open the import_mob.py  script in Blender and edit the config at the top
- Mainly you will want to change mobPath and animationToBeLoadedIdx
- Run the script

For CCC you might need to set the bonePrefix. If nothing changes after running script look at the system console. Script will
list missing bones. For example if armature has bone named "model" and the script can't find bone "as_ego4_model" then set prefix to "as_ego4_".

Samples:
[https://imgur.com/v3ujuol](https://imgur.com/v3ujuol)
[https://imgur.com/el4vOmF](https://imgur.com/el4vOmF)
[https://imgur.com/SbLmRVK](https://imgur.com/SbLmRVK)
