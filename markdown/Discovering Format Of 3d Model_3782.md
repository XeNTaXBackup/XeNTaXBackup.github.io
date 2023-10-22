## Post #1
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-14T13:23:08+00:00
- Post Title: Discovering Format Of 3d Model

Where to start, what to read, what soft is available? I'm starving for information!

Fix: I renamed topic, because "Reverse engeneering 3d models" is a process of digitizing a real model.
## Post #2
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-14T20:55:27+00:00
- Post Title: Discovering Format Of 3d Model

Ok...
I've found Milk 3D. Soft has SDK, so it's possible to write your own plugin for it. Looks like it's possible. BUT. The program is shareware and i'm poor pakistan programmer with 7 children (yes, i'm not serious) so there is no way for me to purchuase it. Is there any immortal tool (that lives at least longer than 30 days) around that supports plugins? Or any similar tools at all?

And yes, i'm angrily, frantically request tutorials and other info about reverse engeneering file formats for 3D files.

Also i know that Dragon Unpacker supports plugins and 3d convertion but i can't find any sdk for it. Even though i understand Japanese, English, Russian, American, Russian American English and Chanese (not Chinese) i can't find god damn tutorial on howto create plugins for it at its official pages.

 Moar...   
Seriosly, please, just drop some useful info. Exept this one i mean:
[http://web.archive.org/web/200406081912 ... /graphics/](http://web.archive.org/web/20040608191208/http://etud.epita.fr/~bilalt_j/graphics/)
I suspect it's a little dead.
## Post #3
- Username: Corwin
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-10-14T23:58:23+00:00
- Post Title: Discovering Format Of 3d Model

This is fatducks website [http://gameresearch.5d6d.com/forum-6-1.html](http://gameresearch.5d6d.com/forum-6-1.html)
use guest guest to view the posts on the forum.
He is a very talented programmer and has a lot of tutorials on 3d converting into max.
## Post #4
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-15T02:17:07+00:00
- Post Title: Discovering Format Of 3d Model

Thanks, but seems like i'm not good enough even to log in   . Shame on me... Well "understand Japanese" in my case means "i'm still noob and need dictonary all the time". Feel myself like a dirty liar  

Anyway, i don't believe there is no information about it in english. I've searched in russian internet for a while too and didn't find anything useful. How are you guys doing it? At least tell me what tools you're using. I really don't think that writing my own 3d viewer is a good idea. Or it is?

Added:
Ooops... I somehow missed your great tutorial, shame on me twice. For other dummies like me:
[viewtopic.php?f=29&t=3739](http://forum.xentax.com/viewtopic.php?f=29&t=3739)
Actually i've missed the fact, that this topic is in tutorials section. I thought it's just another game request >_<
## Post #5
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-18T14:29:42+00:00
- Post Title: Discovering Format Of 3d Model

And hello again.  
I was thinking about the way to understand the format of meshes. I tryed to discover it using just a hex editor. It didn't help much. Then i thought about ida again.
When the mesh file is loaded into memory and decompressed i can easily find it in the memory dump and set some breakpoints. When some standart d3d function read some specific part of the mesh i will know what actually this part represents.
But... i'm too lazy just to try it. I would like to know for sure if i'm going in the right direction. Am i? Tell me please what you think about it.
Also any advice would be awsome.
## Post #6
- Username: Corwin
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 29, 2009 2:52 am
- Post datetime: 2009-10-20T07:37:16+00:00
- Post Title: Discovering Format Of 3d Model

I start to love this monologue. hehe. It helps me think. Hope it helps someone else too.   

I discovered the best way to understand what is what in some 3d model file. It's god damn simple.

I locate 3d model file in memory (using IDA) just after it's already decompressed.  Then i open memory with hex editor (HxD), jump to the position where file is, and fill block that i want to check with zerobytes. Then i let game load. If there are no errors, than i've probably found some texture map, vertex, or shader data block. If some part of a model suddenly disappears than it's vertex data. If textures are going wild - it's texture map block. And if model looks crappy than it's some shader data block.
If there is some error than it's probably some part of a skeletal data, because game engine can't work without it.

P.S. WinHex for some reason sucks when work with memory. HxD works better.
