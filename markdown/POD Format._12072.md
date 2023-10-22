## Post #1
- Username: w3d
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 09, 2014 12:54 pm
- Post datetime: 2014-10-09T06:13:12+00:00
- Post Title: POD Format.

Hello folks,

I am looking for a .POD converter. I'm not sure if there is one around, so let me talk about it a little.
.POD is a format used on many cocos3d games, they include not only the 3D meshes but bones and animation as well. There are many exporters available (mesh to POD), but no importers (POD to whatever format). 

The format was created by Imagination Tec. and the developers appear to be friendly to people willing to make a converter or such. Using their tools (PowerVR Tools & SDK), I can already see the model and animation just fine, however, there is not an option to export that out to FBX or OBJ. Their tools also make it possible to export POD Formats on 3DS Max, Maya and Blender on any OS.

Perhaps we could use the PVRTModelPOD code in the SDK's PVRTools framework to load a POD file into memory and write it out to another format? I do not know.

Unfortunately, I do not have the knowledge to start this out myself, but I think it would be an interesting addition for everyone exploring these files.

From here, I'll just leave links to interesting [or not] things that could [or not] be useful.

POD File Order

```
LightNodes
CameraNodes
Everything else (bones, helpers etc.)

```

[http://community.imgtec.com/developers/ ... nstallers/](http://community.imgtec.com/developers/powervr/installers/) - PowerVR Tools & SDK Download. [Totally free]

[https://dl.dropboxusercontent.com/u/847 ... 0files.zip](https://dl.dropboxusercontent.com/u/84768322/POD%20files.zip) - POD File samples (static and animated)

I think this is all.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-09T10:46:54+00:00
- Post Title: POD Format.

for the static mesh use hex2obj (view link in my sig):



static_POD.jpg (88.17 KiB) Viewed 109 times
## Post #3
- Username: w3d
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 09, 2014 12:54 pm
- Post datetime: 2014-10-10T03:40:44+00:00
- Post Title: POD Format.

Fantastic!

Thank you very much for this!

Did you have the chance to try out the animated file?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-10T09:55:24+00:00
- Post Title: POD Format.

animated_POD_meshes.jpg (253.97 KiB) Viewed 91 times
## Post #5
- Username: w3d
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Oct 09, 2014 12:54 pm
- Post datetime: 2014-10-12T05:49:45+00:00
- Post Title: POD Format.

Much appreciated!

Getting the bones and animations done would be a headache, wouldn't it?
I mean, using the OBJ format wouldn't work, so this would need an entire new tool, right?

But thank you a lot for your help. It's already letting me explore some meshes.
