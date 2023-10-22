## Post #1
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2013-01-29T17:56:52+00:00
- Post Title: DmC animation error?

Hello.
I've tried to open some .upk files of DmC Devil May Cry with the UE Viewer, but it can open just three packages.

When I open other packages of DmC there is this error:

```
ERROR: AnimSequence::Serialize(AnimSequence_0): 5876 unread bytes
LoadObject:AnimSequence'CH19_MundusTraversal.AnimSequence_0', pos=BE4D3, ver=845/4, game=8033 <- UObject::EndLoad <- LoadWholePackage:CH19_MundusTraversal <- Main
```


The numbers are always the same.
It looks like the UE Viewer dosn't find the animatons.

The package with Dante without jacket just works.

Can someone help me?
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-01-29T19:18:03+00:00
- Post Title: DmC animation error?

Wrong place.Post on gildor's forum.
Update Umodel.
## Post #3
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2013-01-29T20:59:07+00:00
- Post Title: DmC animation error?

[http://www.gildor.org/projects/umodel/compat](http://www.gildor.org/projects/umodel/compat)

Yes animations are not supported yet.
And I don't think that will be soon ...

But I just want to export models with textures not animations.
## Post #4
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2013-01-30T14:26:25+00:00
- Post Title: DmC animation error?

Use the -noanim parameter to skip animations. 

It's part of the command line parameters, most of them should be on the website with the program itself.
(I had to use this parameter to load a few of the archives properly due to as mentioned above the animations not being fully supported yet.)
## Post #5
- Username: hotgoblin
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Apr 15, 2012 1:52 am
- Post datetime: 2013-01-30T17:14:48+00:00
- Post Title: DmC animation error?

Thanks ! 

Now I can load all .upk Files.
