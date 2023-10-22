## Post #1
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2022-06-28T06:14:34+00:00
- Post Title: Unreal 2 Proper Map Extraction?

Hey all. Been spending a long amount of time attempting to get properly exported maps from Unreal II: The Awakening.

The maps are in .un2 format, but other than that, everything else seems to be in the typical unreal engine formats. (besides the golem formats for character and weapon models and animations.)

I've used a couple of methods, these including: Ninja Ripper, which works well with exporting separate meshes with their texture and (for the most part) proper UV Data, but puts all meshes into the origin, and doesn't contain the location data, making it kinda inconvenient. Also tried 3D Ripper DX, which I knew would churn some pretty awful results. Over 10 attempts later and, yeah, pretty awful results from that lol. And finally, after much fiddling and tooling with the Unreal Ed 2 paired with the game, and it indeed can export the static meshes, along with the brushes as one whole mesh, but what sucks about this, is it exports it all as one mesh, and contains absolutely No UV Data at all, which kinda brings me back to my initial point.

Am I missing something? Does UnrealEd2 have the option to export with textures that I don't know about? Using the asset browser to try and export 1 by 1 doesn't work at all, at least not for Unreal 2, and exporting the map as one whole mesh is nice, considering everything keeps their place without any kind of distortion, but needing to split everything by loose parts in blender (splitting by material doesn't work, probably because it doesn't have the data on hand in the model.) and re-mapping Every single piece manually. Any help or suggestions, or even any points in the right direction would be appreciated, thanks!
~Blaze.
## Post #2
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-06-28T14:14:49+00:00
- Post Title: Unreal 2 Proper Map Extraction?

There was a few of them long time ago like UShock (or something like this), but if you want to port it to a different version of UE, just use cmd like batchexport. It works for everything - even Level can be extracted to *.t3d (text version), which you can load to any UE version.
## Post #3
- Username: Blaze Modz
- Rank: advanced
- Number of posts: 42
- Joined date: Mon Dec 28, 2015 8:00 am
- Post datetime: 2022-06-28T16:28:10+00:00
- Post Title: Unreal 2 Proper Map Extraction?

> Reply from VendorX ↑Tue Jun 28, 2022 10:14 pm at Tue Jun 28, 2022 10:14 pm
>
> 
There was a few of them long time ago like UShock (or something like this), but if you want to port it to a different version of UE, just use cmd like batchexport. It works for everything - even Level can be extracted to *.t3d (text version), which you can load to any UE version.

I tried out UShock, and it's great! It views the map pretty nicely, but I don't know if there's anyway to extract the map using this program? It's very nice and could come in handy later regardless.

I don't want to port them to another version of Unreal, my goal is to just get them in Blender, as I want to make some Unreal 2 themed animations using them (Already have character and weapons models and the like ready) I just need a few maps for scenes in my animation. That whole .t3d thing makes me curious, though. I'm wondering if I can use that information to port the map info to another more compatible version of Unreal, preferably one that has a method for what I'm looking for.. Hmm..
Also woah! I thought I recognized your name for a second there haha! I doubt you remember me, but I asked about your .gem script Years and years ago when I was a kid, that's crazy to me to see you here now haha!
## Post #4
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-06-29T10:55:17+00:00
- Post Title: Unreal 2 Proper Map Extraction?

Nice to see U2.

Anyway:
- use batchexport to export content (Tex, SM, Brush), exported map to *.t3d will help you to know which package need to be processed.
- write a python script to import *.t3d file and all exported content to Blender - it should be very easy, because every Actor derived class contain link to the content used, its loc. rot. and sc.
Way back, I wrote a script which will allow you to import Terrain - texturing it will be a small problem, but all info is in TerrainInfo class. In the same post you can find other useful Blender import scripts.

Good luck.
