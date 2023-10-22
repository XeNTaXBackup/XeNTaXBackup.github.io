## Post #1
- Username: EratoTiaTuatha
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 18, 2018 7:33 am
- Post datetime: 2020-01-27T15:17:19+00:00
- Post Title: Final Fantasy XV WindowsEdition model files (gmdl, gpubin, gmtl, amdl, lik)

Hello~!
Modding FFXV has been at a standstill for a good while now because of the lackluster mod tools delivered by SE (and the fact they never delivered most of them at all) and there is now an effort to create community mod tools that will allow the game to be properly modded.

As a quick info, the issues with the Mod Organizer from SE include but are not limited to: 
all conversion is done online, meaning when SE takes down the servers, modding goes down with them
only select models can be replaced with it (for example we cannot replace props)
adding new models is only possible for very select model types (outfits and weapons) and those are handled by the game with a single temp id meaning using more than one mod weapon at a time breaks them
limited to a default shader that basically treats everything as basic cloth. You want your modded outfit to show the character's hands? Too bad.
Can only utilize the base armature unless tricks are employed and even then rigging is extremely limited

Now there are a few parts to getting custom modding tools off the ground, and those are:
Archive unpacking and repacking (EARC and ffxvbinmod) - done, there are working tools for it
Texture conversion in and out - also possible with existing tools
Scripting/logic/AI/event editing - formats are understood and there are tools for them in the works
Model export into the game's formats - this is the one thing we lack

Noesis reads the models near perfectly (there's some small issues with armature sets but they're fixed easily) but it does not support the reverse process and as the functionality is part of the program rather than a plugin, the code isn't accessible. There are some unfinished, somewhat functional plugins for Blender and Maya that import meshes and sort-of import armatures, that are up on github.

What we know is that the model data is kept in multiple files, so it would be necessary to write those.
gmdl is the main file that references the others
gpubin contains mesh data
amdl is armature
gmtl is materials

So, tl;dr, we're looking for any help with this, whether you're willing to tackle creating the model exporter whole or simply have some advice or know something that could help.

Once we have a full modding suite it will open the door to adding content to the game such as map and quest expansions, hopefully adding the Niflheim map etc for exploration and perhaps remaking some of the cut content. We have the concepts, we have the modders, and we have most of the tools, we're just missing the model format stuff.
