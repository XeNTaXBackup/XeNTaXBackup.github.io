## Post #1
- Username: jowsss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2012 9:05 pm
- Post datetime: 2012-08-20T13:21:38+00:00
- Post Title: Royal Quest model viewer

Hi, i have unpacked the game files, I would be able to browse models, but most do not have such knowledge, can anyone help?

__
Привет, есть распакованные файлы игры, хотелось бы получить возможность просматривать модельки, но у самого таких познаний нет, может кто поможет?


files:
.ab (animblocks)
.mesh (meshes)
.dds (textures)
[example.rar](https://xentaxbackup.github.io/file/5697_example.rar)
## Post #2
- Username: jowsss
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2012-08-20T15:16:00+00:00
- Post Title: Royal Quest model viewer

Vertices are fairly easy to load.

0x124 = Number Of Vertices
0x128 = Size of singular vert

So (NumVerts * 0x1C) then load it in Noesis. It appears to work but when i try load the faces it comes out wrong unfortunately.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-20T19:10:05+00:00
- Post Title: Royal Quest model viewer

Faces are just a bunch of triangles. Just read int times 3 to get the number of indices and then bind the following buffer.
I wonder how they might be storing the UV's and normals though.

Maybe the just read a short and divide it by 32768


More samples. I can only guess what some of those integers in the header mean.
[royalquest.jpg](https://xentaxbackup.github.io/file/5702_royalquest.jpg)
## Post #4
- Username: jowsss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2012 9:05 pm
- Post datetime: 2012-08-21T02:04:04+00:00
- Post Title: Royal Quest model viewer

[http://rghost.ru/39906342](http://rghost.ru/39906342)
or
[http://depositfiles.com/files/vkv4dkhrc](http://depositfiles.com/files/vkv4dkhrc)
## Post #5
- Username: jowsss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2012 9:05 pm
- Post datetime: 2012-08-24T04:38:53+00:00
- Post Title: Royal Quest model viewer

any good news?
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2012-08-25T13:50:29+00:00
- Post Title: Royal Quest model viewer

> Reply from jowsss
>
> any good news?

Just use the 3D Object Converter v5.0  (unpublished yet):
[http://3dconverter.webege.com/develop](http://3dconverter.webege.com/develop)

The .mesh file has the wrong references for the texture file.
If the .mesh and the .dds files are in same directory, the program will fix it automatically.

I uploaded some converted files:
[http://3dconverter.webege.com/converted](http://3dconverter.webege.com/converted)
## Post #7
- Username: jowsss
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2012 9:05 pm
- Post datetime: 2012-08-27T09:59:36+00:00
- Post Title: Royal Quest model viewer

a great program, but I do something similar, but for the site, so that others can see
