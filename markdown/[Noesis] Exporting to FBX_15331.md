## Post #1
- Username: dirtypantsdan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 03, 2012 3:33 am
- Post datetime: 2016-10-05T06:34:34+00:00
- Post Title: [Noesis] Exporting to FBX

Hi there!

Not sure if this is the right forum to post Noesis related issues, however. recently I've been trying to import a model into Super Smash Bros for Wii U. I did so successfully, however my UVs showed up pretty messed up. I've gotten plenty of comments and advice on how to fix this and apparently it was suggested to import the model as a DAE format into Noesis, and export it as an FBX with the "flip UVs" option ticked.

Now, when I get the model back into 3DS Max, I get double the Verts in 3DS Max. Meaning I must re-rig the model. Before re-rigging I'm curious if there is a advanced parameter that disables this increase of verts into my model, or is this absolutely necessary? Anyone with some knowledge on how or why Noesis does this, would be great. 

Thanks again~
## Post #2
- Username: dirtypantsdan
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-10-05T06:59:26+00:00
- Post Title: [Noesis] Exporting to FBX

DAE->FBX doesn't double up verts, so I'd guess something else in the workflow (export to DAE or import from FBX perhaps) is causing this.

That's ridiculous advice, though. Just pull up the UV editor in Max and flip the UV's there, no export/import necessary.
## Post #3
- Username: dirtypantsdan
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Aug 03, 2012 3:33 am
- Post datetime: 2016-10-05T07:11:00+00:00
- Post Title: [Noesis] Exporting to FBX

Exactly what I thought as well! But apparently this works for some strange reason.. I have also thought of just flipping the UVs myself like that, but I have yet to try it. I think I'll try flipping the UVs on Max first before trying that conversion you suggested. Thanks for your quick response though, I feel more encouraged to try it in Max first now.

Here's where the advice came from btw if you're curious, it's at the very end of the tutorial....

[http://gamebanana.com/tuts/12128](http://gamebanana.com/tuts/12128)

Edit: Also if I may add, how does Noesis flip the UVs anyway? Vertically, or horizontally?
