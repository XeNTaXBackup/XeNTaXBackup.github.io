## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-02T10:51:13+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

Hey guys, not good at MAX here, and my DAE code now only works with COLLADA importer from MAX so I'm forced now to use software I don't like. I have a ripper that exports models to DAE that only contains XYZ and UV data. Is there a way in MAX to make it compute smoothed vertex normals on import (as what happens with MAX's OBJ import when loading a file that doesn't have vertex normals specified)? I tried messing with the mesh modifiers to edit the normals but it doesn't have the same effect as a typical smooth shade in Maya or Lightwave.
## Post #2
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-02-02T12:50:43+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

I think the best software to preserve smoothed vertex normals is Maya , which ahve more parameters about it, In 3ds max there are some methods as u said ,but they have to be well calibrated, to not effect so much the correct smooth of the mesh.
I don't know any method to smooth the mesh in the import, maybe with some max script on the web like here: [http://www.scriptspot.com](http://www.scriptspot.com) u  may obtain a better result.
I usually use cinema4d for those dae files without normals,( if the mesh is a bit complex)  which have some automatic optimisations for mesh smooth. Anyway can u post a small sample ? i have an idea with max but i need to test it before.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-02T13:39:10+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

Sure, here you go. Use the OpenCollada import.
[http://www.mediafire.com/?2691p1oc5omk0wy](http://www.mediafire.com/?2691p1oc5omk0wy)
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-02T14:22:45+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

Wow, blender 2.61 crashes when trying to load that DAE and blender 2.59 loads it but doesn't load any textures. Man COLLADA support sucks everywhere.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-02T16:38:12+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

COLLADA's that format with a whole bunch of different variations right?
I think they should just stick with a single format, or push out an API so they can change their underlying format however they like...

Or if they already have an API, then maybe people should use it.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-02T17:13:27+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

By variations do you mean variations of crappy, half-ass implementations? Then yes, that's the one lol.
## Post #7
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2012-02-02T18:42:01+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

> Reply from howfie
>
> By variations do you mean variations of crappy, half-ass implementations? Then yes, that's the one lol.

lol ...i agree with u guys, actually collada doesn't let to modyfiy almost nothing in parameter settings, so the great work to
"translate" the imput informations is assigned to the 3d software u use. Some applications works better than others expecially with
the smooth parameters on a 3d mesh..as maya lightwave and rinho...then cinema, max and so on (so this is one of the reasons why it quite difficult to obtain the same smooth effect in max like maya and lightwave).
Anyway if u work with max the faster solution to obtain a smooth mesh like in the obj import plugin is to activate the hsds modifier or
use edgesmooth macroscript (u can find it in the max script site i told u before)instead of work with all other parameters which soluld be applied by case to case. I prefer this second solution but it require a bit of trials before obtain the best result.
Now i hope u will be able to implement the model skin which contain the normal and weight informations if i remeber well.
I compared this model with the previous Oneechanbara one for xbox....this is hotter   ...amazing work man.
Sorry for my bad English.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-02-11T05:44:24+00:00
- Post Title: 3DS Max 2012 Compute Smooth Normals

Another 3D Studio Max question:

I have written an import plugin for 3DS Max 2012. F-ing can do the normal computation in the plugin code lol. It is so much better just writing your own damn plugin rather than fighting with COLLADA and all it's stupid technique_COMMON and technique_NOTSOUNCOMMON crap.

The game here uses identity matrix for rotation part of inverse bind matrix so all bones show as misaligned (I have to go to Bone Tools > Object Properties > Realign to fix). Bone ends still end up being misaligned. In Lightwave, bone orientation matters and is important since IK is done on bone's pitch channel. Does the bone orientation in 3ds max matter? Can I just render all fins as size zero and render the bone as a line and will IK work ok on this type of bone?

Thanks.
