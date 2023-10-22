## Post #1
- Username: JKerman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Feb 06, 2021 7:02 am
- Post datetime: 2023-01-06T19:58:59+00:00
- Post Title: Ace Combat 7 model extraction?

Has anyone figured out how to decrypt the AC7 models yet?
## Post #2
- Username: RythusOmega
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Sep 20, 2014 11:05 pm
- Post datetime: 2023-01-08T07:15:12+00:00
- Post Title: Ace Combat 7 model extraction?

(bit suprising to see a new AC7 article, as i have seen previously others on both forums)
Hi, good news is yes, it has been figured out, you can access the unencrypted PC files using a custom edited build of Umodel made by Spiritovod, originally linked on the umodel forums
[https://drive.google.com/file/d/13LXTDa ... B5bcXJpdcx](https://drive.google.com/file/d/13LXTDa-jAAGx9V5eQUfvaHB5bcXJpdcx)

There's also the separate tool called ACE7Decrypt, but the Umodel build is more straightforward as you can dump the desired files you want at the moment, when the tool mentioned works better if you want to make a general dump of all the files at HDD and unencrypt them

Some protips i can give due i tend to work with dumping(as i'm a modder to a extent), i recommend dumping the models using GLTF instead of PSK by some factors, the format is already supported by Blender, mesh normals looks better, and PSK despite possible to import using the Noesis trick, the same got a very weird issue that high poly based models would export in PSKX instead, which is the format used for static meshes, Gildor(creator of Umodel) mentioned this occurs due Umodel is programmed to treat heavy poly count models as static meshes when exporting, which imo isn't the ideal

The things you'll be losing from the PSK export would be the skeleton armature order, which unlike the GLTF one, you could make a quick and dirty reimport with them by just tweaking the model, despite at the end i would recommend building the whole armature structure when making something from scratch. and secondary UV coordinates used for the emblem customization, which isn't probably your interest if you goal for getting the AC7 models turns to be 3D Printing for example

If you would like to export the model with animations, you could press Ctrl + A after loading a skeletal mesh, it will start loading all the available animations of each mesh, which takes a whole due it'll check the entire game file structure, after that you can press "]" to input the animation group, then export it, which when importing the GLTF, it'll include the animations already on the model data, then you can check some basic tutorials of how to handle animation edits if you want to get a specific frame of it to print
## Post #3
- Username: MichaelBFS
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jan 04, 2021 10:18 pm
- Post datetime: 2023-05-22T23:34:19+00:00
- Post Title: Ace Combat 7 model extraction?

Hi Guys!
I am trying to import a model into blender. But I can't figure out what the procedure is.

I tried to open .uasset and .ubulk files in the Unreal Engine 4.18, but unreal engine  says that it's "unknown extension uasset".

I tried to unpack these files and in Quickbms with unreal_tournament_4.bms  PC version and PS version. But I could not open these files .uasset in the Unreal Engine 4.18 and Unreal Engine 5 to convert later to FBX.

But I found some planes in GTA 5 mods. How can I do this and get 3D models of planes and buildings from the game?
