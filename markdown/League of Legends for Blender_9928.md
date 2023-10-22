## Post #1
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-12-04T02:21:38+00:00
- Post Title: League of Legends for Blender?

Okay, so I've been googling for quite some time now and I pretty know how lol model files work.

.anm for animation, .skn for mesh, .skl for skeleton.

And I used Blender, there's only two solutions which is to use the Blender for addon, or use an .skn to .obj converter which I also have.

The problem is that the .skn-.obj only gives me the mesh, there are no .skl-.obj's.

So I have to resort to the Blender addon for 2.5, I'm using 2.63 which shouldn't be a problem.

The thing is that I follow the instructions and I download, and install the addon into the blender directory. Some reason it just won't appear in the Blender addons in the import/export.  I even searched in League, .skn,.skl in the search box it just won't appear. Does anyone have a working .skn/.skl addon for blender 2.63 that will work or am I installing the addon wrong? It's in the scripts/addons and I just leave the folder there in the installation directory.
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-12-04T11:32:19+00:00
- Post Title: League of Legends for Blender?

If the plugin was developed for Blender 2.5, why would you expect it to work in Blender 2.63?
The README.txt says:

> This is an addon for the Blender3D 2.5 branch.  It has been tested to work on 2.54

[http://code.google.com/p/lolblender/](http://code.google.com/p/lolblender/)

Couldn't you use Blender 2.54 to convert it to a common exchange format like *.dae or *.fbx then import to Blender 2.63?

The plugin installed and worked fine here:
[http://download.blender.org/release/Blender2.54beta/](http://download.blender.org/release/Blender2.54beta/)
## Post #3
- Username: soulslayerzx
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Aug 14, 2012 9:46 am
- Post datetime: 2012-12-05T01:57:46+00:00
- Post Title: League of Legends for Blender?

> Reply from AceWell
>
> If the plugin was developed for Blender 2.5, why would you expect it to work in Blender 2.63?
The README.txt says:
This is an addon for the Blender3D 2.5 branch.  It has been tested to work on 2.54

http://code.google.com/p/lolblender/

Couldn't you use Blender 2.54 to convert it to a common exchange format like *.dae or *.fbx then import to Blender 2.63?

The plugin installed and worked fine here:
http://download.blender.org/release/Blender2.54beta/

Whoops forgot to edit my post. Anyway, I got the plugin to work in Blender 2.54 beta that's the one I used. It works and I can import a .skn, but the .skl won't work. I want the skeletons but if I try to import the .skl nothing is imported, I tried importing both together but doesn't work.
