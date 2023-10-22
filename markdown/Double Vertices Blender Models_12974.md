## Post #1
- Username: WeylandYutani
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 22, 2015 5:02 am
- Post datetime: 2015-06-23T09:55:06+00:00
- Post Title: Double Vertices Blender Models

Hi, the fact that its hard to find a place to find answers in that dircetion i search brought me here and i hope someone please can help me.

I mainly extract models but now i want to port them aswell, i want to use blender and i have cleared everything except one Thing what is
called remove doubles what removes doubled Vertices. But i cant tell if that is nessecary or not, i cant tell if that is good or not, the differences
on the mesh are well visible but im unfamiliar with port and sculpturing.

At the Moment i extract stuff from Far Cry into Maya convert it to FBX to work in Blender and then to Source Filmmaker, a simple Model for like a
Bed has over 7000 removed Vertices and the apperence of the mesh changes drasticaly. Im sure i will find some People what extract and Port Models
here and can tell me more about this remove doubles. I know what the function actually do but i dont know if that is nessecary because i cant tell what
Looks better in the end and my Friend what mainly Port Models for me said that he isnt sure =(.

Thanks

Edit: I tried a few Models from earlier exports specially People and it seems it mostly clean up the Mesh specially when it looks cut but im not sure if
this is still nessecary or the right choice for all Models like simple Objects what maybe look better without it but thats only my view of the things and
im far away from expert.
## Post #2
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2015-07-06T02:39:00+00:00
- Post Title: Double Vertices Blender Models

Removing doubles can cause problems in Blender when working with Cryengine files.  It seems to occasionally screw up the UVs.  At least when I'm working with Noesis and the cryengine plug-in.  

As a general rule I do remove doubles, but on some models it isn't worth it.  

I'm working on an updated Cryengine converter so I can access MWO or Star Citizen files properly.  Got a github at github.com/markemp if you want to take a look (C# programming; don't laugh  ).  The Noesis plug-in works good for older versions of CE games, but seems to have problems with 3.4 and newer.
