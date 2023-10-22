## Post #1
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-02-08T23:04:04+00:00
- Post Title: Need a model viewer/editor for queens blade

ok ive tried every program i possess and none of them are compatible, ive been able to extract the mesh and bone files but they seem to just crash every viewer i attempt to open them with, ive used blender with the plugins noesis as well, udk , GMV and 3dv professional. im at a loss. i know its possible to pull them up since crrox was able to do so. any tips on a program ive not used or if anyone knows what will work?
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-08T23:29:54+00:00
- Post Title: Need a model viewer/editor for queens blade

Well, have you tried Noesis? All noesis plugins are written for Noesis unless someone writes a set of scripts that will allow you to use use noesis plugins in blender.
## Post #3
- Username: s25jin
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 15, 2011 1:11 am
- Post datetime: 2012-02-09T02:47:44+00:00
- Post Title: Need a model viewer/editor for queens blade

put in ..\noesis\plugins\python\fmt_queensBlade_mesh.py  <-

[[url]http://db.tt/mJpqPyRO](%5Burl%5Dhttp%3A//db.tt/mJpqPyRO)[/url]

click Noesis.exe and open  ..QueensBlade\ *.mesh

if u have .dds % mesh in same dir u will so queensmodel 






ps. thx so much finale00
## Post #4
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-02-09T06:32:53+00:00
- Post Title: Need a model viewer/editor for queens blade

ok im not sure how to get the dds file, ive got the mesh files and whatnot but im not sure what you mean by having the dds in the same path as the mesh file. ive for the plugins right for noesis.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-09T07:50:32+00:00
- Post Title: Need a model viewer/editor for queens blade

The textures are stored in the "tex" archive.
After you unpack them you put it in the same folder as the meshes because I don't do any special checks.

It should be fairly easy to tell which goes where, but some of them are not obvious and use the same textures even though the character code is different (eg: many meshes reference SW_...dds textures even when they are not the SW character)

If the debug console is open in noesis, you can just look at which texture failed to load and then just copy that over.
## Post #6
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-02-09T08:23:51+00:00
- Post Title: Need a model viewer/editor for queens blade

figured out the problem, im an idiot!
## Post #7
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-02-09T08:33:51+00:00
- Post Title: Need a model viewer/editor for queens blade

hmm, i did exactly what you all said and its still failing to loed the mesh.
## Post #8
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-02-09T08:59:40+00:00
- Post Title: Need a model viewer/editor for queens blade

got it fixed, i was using the wrong program lol thanks for all the help guys.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-09T20:46:15+00:00
- Post Title: Need a model viewer/editor for queens blade

Maybe you can post what the problem you had was and how you solved it.
The same issue might arise with other games.
## Post #10
- Username: raelizer
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Feb 08, 2012 8:37 pm
- Post datetime: 2012-02-10T02:36:21+00:00
- Post Title: Need a model viewer/editor for queens blade

was a simple fix, i googled noesis and got visilog viewer and it dosnt work with the queens blade plugin, you need to get the actual noesis program not visilog.
