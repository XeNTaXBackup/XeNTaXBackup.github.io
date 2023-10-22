## Post #1
- Username: Fiorenzone
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Sep 28, 2016 2:42 am
- Post datetime: 2016-10-07T14:07:52+00:00
- Post Title: Importing CryEngine files in 3ds Max PROBLEM

Hi, I'm trying to import a 3d model from ryse son of rome in 3ds max 2017 using the cryimporter script found here on the forum ([viewtopic.php?f=16&t=12085&start=30](http://forum.xentax.com/viewtopic.php?f=16&t=12085&start=30)). The model i'm trying to import is Glott the minotaur chieftain and I figured out on how to import it with bones and textures but the problem is that the bones linked on the body don't work because there aren't skin envelopes.I tried importing other models and it's the same everywhere:some pieces of mesh like armor or helmet works well with bones but the main body doesn't move . I know this is isn't a 3ds max forum so I'm here to ask you if maybe I need to pick any specific file from ryse folder to make the body works like skeleton list or things like that. 

These are the steps I did:

1)Download Cryengine Importer script
2)Extract with Crysis 3 object_charpart0, object_charpart01 and animations.pak
3)Opened 3ds max 2017, runned the script, set directories where ryse, the .ms script and skeletonlist.xml were and finally browsed glott's character definition  from this: GameRyse\Objects\characters\human\large\gltt\gltt.cdf
4)The model is loaded correctly in 3ds max with bones and when i'm start to moving I find that the skin modifier of the body mesh has no envelopes so when I move his foot or his head or his spine or whatever all the body moves well BUT the body that stays still.


P.S: I posted a thread on autodesk forums too,where you can also see some pics of the problem and read a more specific explanation of the problem on the 3ds max side: [http://forums.autodesk.com/t5/3ds-max-a ... -p/6606058](http://forums.autodesk.com/t5/3ds-max-animation-and-rigging/skinning-problem/td-p/6606058)

 I  asked this everywhere and I hope that at least here somebody knows something  



edit:FIXED FIXED FIXEEEEED the problem was simply that I was using an old version ,in the meanwhile the author of the script made another version I dl that and now all wooooorksss
