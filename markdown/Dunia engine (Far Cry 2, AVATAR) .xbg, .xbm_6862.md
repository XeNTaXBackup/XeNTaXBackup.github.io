## Post #1
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-06-27T22:54:28+00:00
- Post Title: Dunia engine (Far Cry 2, AVATAR): *.xbg, *.xbm

[This format has previously been discussed](http://forum.xentax.com/viewtopic.php?f=16&t=4310).

*.xbg = geometry, *.xbm = material

They share the same format ('Geometry Resource File'), with different block types.

I've written code that can successfully read in the entire format, though much of it is unknown.

[http://svn.gib.me/public/dunia/trunk/Gi ... rceFile.cs](http://svn.gib.me/public/dunia/trunk/Gibbed.Dunia.FileFormats/GeometryResourceFile.cs)
[http://svn.gib.me/public/dunia/trunk/Gi ... /Geometry/](http://svn.gib.me/public/dunia/trunk/Gibbed.Dunia.FileFormats/Geometry/)

Here's what I know about the vertex buffer formats so far: [http://svn.gib.me/public/dunia/trunk/doc/vertex buffer formats.txt](http://svn.gib.me/public/dunia/trunk/doc/vertex%20buffer%20formats.txt)

Understanding the entirety of the format would be nice. 
[xbg_samples.zip](https://xentaxbackup.github.io/file/4390_xbg_samples.zip)
