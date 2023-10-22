## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-17T19:27:24+00:00
- Post Title: [Request] 9Dragons

Ok wirh help of chrrox and finale00, we get unpacker for 9Dragones, so well here I upload some samples for check it.

Web: [9Dragons](http://9dragons.gamescampus.com/)
Client: [Client](http://cdn.pandonetworks.com/pando/9Dragons_20110916_Downloader2.exe)

[9Dragons 2D-3D Samples](http://www.mediafire.com/download.php?um7amd7b4du03ds)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T19:42:28+00:00
- Post Title: [Request] 9Dragons

-vertex and index buffers are obvious.
-The number of textures for a particular mesh does not seem to be determined beforehand. May have to do some rough checks just to deal with those.
-found two different vertex structs. Not obvious how to determine which one to use



EDIT: looks like they use a float to determine the mesh type. You can find this float right after the first integer (idstring maybe)

0.72 is skinned mesh
0.73 is static mesh (buildings and stuff)

That should be how the number of textures is determined.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-17T20:06:15+00:00
- Post Title: [Request] 9Dragons

Ok I've parsed the mesh format and it loads both types of models.

[http://db.tt/8JM9Mnso](http://db.tt/8JM9Mnso)

The section after the index buffer is vertex weights.
The skeleton is located in the .Xbp file.

I may change the script so that you should place all textures in a folder called "texture", just because all of the textures are stored in the same folder.

When you unpack the files, you should consider re-organizing them.
So for example, move all of the textures with the word "object" into a folder for objects only.



Static and skinned meshes all loaded.
