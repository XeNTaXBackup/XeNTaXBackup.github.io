## Post #1
- Username: Vida1996
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 11, 2011 8:04 pm
- Post datetime: 2011-09-18T19:05:06+00:00
- Post Title: Aion Export ERROR !

I export the model 3d , but when i put on 3d studio max , with the texture , the texture are wrong !
Someone help me?
## Post #2
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-18T20:07:34+00:00
- Post Title: Aion Export ERROR !

Could you be more specific?

What exactly is wrong with the textures?
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-09-19T17:59:00+00:00
- Post Title: Aion Export ERROR !

> Reply from Vida1996
>
> I export the model 3d , but when i put on 3d studio max , with the texture , the texture are wrong !
Someone help me?
maybe the problem is when export this object break UNWRAP, so you need fix it.
## Post #4
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-20T18:59:37+00:00
- Post Title: Aion Export ERROR !

If you're importing the AION models from Collada DAE into a program like 3DS Max or especially Maya, that's your problem.

Autodesk has a total crap plugin for DAE import. The Open source one is likewise pretty crap in my experience. If you need to import DAE into one of those programs, use Autodesk FBX Tool to convert it from DAE to FBX, which Maya and Max can open no problem. (Why Autodesk can make a converter but not an import export plugin I have no idea)

Or just use Blender3D. 

It could also be that you applied a "UVW Map" property to your models in Max, that would also ruin your UV's as it overwrites them.

It would be much easier to diagnose your problem if you were more specific.
