## Post #1
- Username: Reicere
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 24, 2009 2:39 am
- Post datetime: 2009-06-23T19:13:21+00:00
- Post Title: (PS2) R-Type Final

I am trying to figure out this games model format (.IMD)
Currently I can find the vertices, normals, and texure coordinates but can't find anything related to the faces.
Any help in figuring out the rest of the format would be appreciated.
[K01.zip](https://xentaxbackup.github.io/file/2150_K01.zip)
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-08-08T07:48:02+00:00
- Post Title: (PS2) R-Type Final

I am trying to quick answer all these non-popular posts.

Most console game use tri-strip faces since it is faster in calculate rather than load huge list of faces data!
Sometime they don't even have tri-strip indices! Just use the order you read the vertives as tri-strip indices! That why the vertices are record in chunk in the file!

Hope this help!
## Post #3
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2010-03-07T20:26:48+00:00
- Post Title: (PS2) R-Type Final

Way ahead of you buddy 

[http://sourceforge.net/projects/rtfview/](http://sourceforge.net/projects/rtfview/)

Tell ya what though, if you can figure out the rest of the 0x2n blocks(material defs and stuff) or how to split triangle strips between 4 0x00000001 flags(instead of the usual 2) that'd be fantastic. Notes in comments are kind of out of whack for a lot of things, but it does work for most objects. It also fails nicely for animations and lights which are a bit different. Also supports 8 and 32-bit P6T, but not 4-bit(two CLUT, 4-bit swizzled) :/ I found it best to work on the MAP/Knn.IMD series first, these are the ships used in the museum and come with shadows and canopies. Alternatively, in the CHR folder you'll find the in-game ships, canopies are in separate files, the base models are in files labeled KIHON.

[](http://img31.imageshack.us/i/rtfviewfixedalpha.png/)
[](http://img28.imageshack.us/i/rtfviewv3loaderwip8.png/)

Also here's the archive ripper I wrote. Pretty simple stuff.
[http://sourceforge.net/projects/rtyperipper/](http://sourceforge.net/projects/rtyperipper/)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-08T11:49:16+00:00
- Post Title: (PS2) R-Type Final

Nice going!
## Post #5
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2010-12-20T09:45:34+00:00
- Post Title: (PS2) R-Type Final

Long time since I posted. Binaries and current source now available. [http://sourceforge.net/projects/rtftool/](http://sourceforge.net/projects/rtftool/)
It's a steaming hot mess of memory leaks and potential crash material, but.... It exports meshes to OBJ and textures to TGA and it does a pretty fair job of it. Now loading data straight from the disc(FAT/DAT files). [http://i51.tinypic.com/30u9000.jpg](http://i51.tinypic.com/30u9000.jpg) [http://i53.tinypic.com/vnh8jn.png](http://i53.tinypic.com/vnh8jn.png)
I hope someone finds this fun and useful!
