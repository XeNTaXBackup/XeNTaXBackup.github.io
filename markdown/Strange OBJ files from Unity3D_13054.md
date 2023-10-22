## Post #1
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-07-11T18:44:43+00:00
- Post Title: Strange OBJ files from Unity3D

So I've tried to use DisUnity to extract the OBJ data from a Unity3D package for the new Star Wars iTunes app, the only problem is the mesh isn't showing up right. I can bring it into Meshlab and it shows all the points of the model data, but the only area with faces are where you see the grey dots. It's like the data is all there it's just not showing the faces. 

Unity3D File
[https://www.mediafire.com/?22xtsu3dcdsoh7m](https://www.mediafire.com/?22xtsu3dcdsoh7m)
Extracted Data (contains the OBJ files)
[https://www.mediafire.com/?22xtsu3dcdsoh7m](https://www.mediafire.com/?22xtsu3dcdsoh7m)
## Post #2
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2015-07-12T01:29:54+00:00
- Post Title: Strange OBJ files from Unity3D

Sorry about the links 
Correct links  
[http://www.mediafire.com/download/md128 ... es.unity3d](http://www.mediafire.com/download/md128jvmbk8hj9c/photobooth_scenes.unity3d)
[http://www.mediafire.com/download/22xts ... r-main.zip](http://www.mediafire.com/download/22xtsu3dcdsoh7m/BuildPlayer-main.zip)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-14T11:33:03+00:00
- Post Title: Strange OBJ files from Unity3D

For NSTGun.obj from BuildPlayer-main.zip
there are 26931 vertices and the maximum face index seems to be 5574 (or something like that).

So a whole bunch of faces is missing. As simple as that.

I see two possibilities: either there's a problem unpacking the assets using disunity
(maybe something's wrong in structdb.dat)
or there's a bug in the conversion chain (to obj) which ends with ObjWriter.java

You could report to the author barracuda.
