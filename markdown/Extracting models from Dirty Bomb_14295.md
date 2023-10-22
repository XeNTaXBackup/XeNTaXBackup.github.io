## Post #1
- Username: errur
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2016 7:31 am
- Post datetime: 2016-05-01T00:27:01+00:00
- Post Title: Extracting models from Dirty Bomb

So I looked around and stumbled upon [this old thread](http://forum.xentax.com/viewtopic.php?f=16&t=12903). It seemed to have provided a .umap file. I'm however interested in grabbing models from it's .upk files. 
Due to custom encryption umodel is unable to load the meshes, while it loads textures and materials just fine. 
While I've seen [evidence](http://imgur.com/VRh1LnR) of umodel loading the meshes I was never able to replicate that.

That old thread showed usage of hex2obj but I'm unsure how am I supposed to load a model in it if it's inside a .upk. Any help is appreciated.

[Here's a sample .upk file.](http://puu.sh/oBNKm/938207bc8c.upk)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-01T07:14:45+00:00
- Post Title: Extracting models from Dirty Bomb

> Reply from errur
>
> That old thread showed usage of hex2obj but I'm unsure how am I supposed to load a model in it if it's inside a .upkuse of hex2obj requires the "raw" model data (as .umap is). It has no unpack/decompression feature.

gildor spent years to create umodel but it claims: "ERROR: Unknown ItemSize 6"
when trying to unpack the upk file you've provided.

You might ask gildor to have a look at.
[http://www.gildor.org/en/projects/umodel](http://www.gildor.org/en/projects/umodel)
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-01T07:50:05+00:00
- Post Title: Extracting models from Dirty Bomb

I've made maxscript for Dirty Bomb models a long time ago (more than a half-year ago for sure). I'm certain they changed a lot since then, or maybe no, who knows? I'm totally agreed with Shakotay, if you have evidences that someone managed to load Dirty Bomb into umodel, Gildor's forums will be the best place to ask about it
## Post #4
- Username: errur
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2016 7:31 am
- Post datetime: 2016-05-01T20:11:47+00:00
- Post Title: Extracting models from Dirty Bomb

> Reply from zaramot
>
> I've made maxscript for Dirty Bomb models a long time ago (more than a half-year ago for sure). I'm certain they changed a lot since then, or maybe no, who knows? I'm totally agreed with Shakotay, if you have evidences that someone managed to load Dirty Bomb into umodel, Gildor's forums will be the best place to ask about it

The art has certainly changed a lot since then, but I can't say about the files. Gildor mentioned (long ago) that he doesn't want to work with it since the game uses custom compression. Here's some [info](https://www.reddit.com/r/Dirtybomb/comments/4gtz7i/the_phantom_face_whats_under_the_mask/d2obt6v) on what can be done.

It says there UEskeltalMeshViewer is able to load the character models, which works. And the decompress and unpack exes work as well but they output files with the engine class as the the file extension so I'm not sure what to do with them after.

Any ideas?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-01T20:33:16+00:00
- Post Title: Extracting models from Dirty Bomb

I won't bother but where's the UE SkelMesh Viewer from?
Virustotal says:



check.jpg (43.86 KiB) Viewed 306 times


I used it in a VM, which I reinstall all 4..6 weeks, so I'm safe.
(and 'yes', it displays this amazing girl...)
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-01T21:15:29+00:00
- Post Title: Extracting models from Dirty Bomb

Well, that's correct, you can extract files from .upk with some Unreal tools. That's how I did it, extracted package and made script for models (they have .SkeletalMesh extension after extraction, if I remember right). Static meshes have .StaticMesh extension, though for them I didn't actually finish my import part, because I'm mostly interested in skinned meshes. I'm personally also interested in evidence you provided, that Dirty Bomb files can be opened in Umodel. That would be cool, since it could mean we can get animation too?
## Post #7
- Username: errur
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2016 7:31 am
- Post datetime: 2016-05-01T21:25:39+00:00
- Post Title: Extracting models from Dirty Bomb

> Reply from zaramot
>
> Well, that's correct, you can extract files from .upk with some Unreal tools. That's how I did it, extracted package and made script for models (they have .SkeletalMesh extension after extraction, if I remember right). Static meshes have .StaticMesh extension, though for them I didn't actually finish my import part, because I'm mostly interested in skinned meshes. I'm personally also interested in evidence you provided, that Dirty Bomb files can be opened in Umodel. That would be cool, since it could mean we can get animation too?
I was wrong, it wasn't actually Umodel from the out of context screenshot but it was the UESkelMeshViewer above. I just assumed it was Umodel since it had the exact same interface. I don't actually know where it originated from as I got it from the reddit post, and searching around hasn't really provided any sort of clue. 

This is probably as close as I saw anyone get to getting the models from the game.
## Post #8
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-05-01T21:58:42+00:00
- Post Title: Extracting models from Dirty Bomb

.upk from first post, the one you uploaded, is it from latest game client? My script seams to work, not sure how with other files
## Post #9
- Username: errur
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2016 7:31 am
- Post datetime: 2016-05-01T22:06:59+00:00
- Post Title: Extracting models from Dirty Bomb

> Reply from zaramot
>
> .upk from first post, the one you uploaded, is it from latest game client? My script seams to work, not sure how with other files
Yep, it's from the latest client but it's only a single .upk. The reference pose model is old though (still used for founders who played the game in alpha) but the one on the left is up to date and with all the parts that are usually missing on the reference models (like glasses, hair etc).

Are the UV's retained? As you can get the textures and materials with umodel.
I can provide a few more, since the game is f2p and the files are readily available.

Edit:
Here's a [player character](http://puu.sh/oCTCG/202b4614a0.zip), a [weapon](http://puu.sh/oCTG2/f929db249d.zip) and [an animation set](http://puu.sh/oCUpc/d5108a3cac.zip).
## Post #10
- Username: errur
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2016 7:31 am
- Post datetime: 2016-05-18T15:16:40+00:00
- Post Title: Extracting models from Dirty Bomb

> Reply from zaramot
>
> Well, that's correct, you can extract files from .upk with some Unreal tools. That's how I did it, extracted package and made script for models (they have .SkeletalMesh extension after extraction, if I remember right). Static meshes have .StaticMesh extension, though for them I didn't actually finish my import part, because I'm mostly interested in skinned meshes. I'm personally also interested in evidence you provided, that Dirty Bomb files can be opened in Umodel. That would be cool, since it could mean we can get animation too?

It'd be nice if you could share your maxscript sometime... 

Meanwhile there's new info coming from [here](https://www.reddit.com/r/Dirtybomb/comments/4haxuo/i_know_how_to_export_3d_models_from_the_game/d3a16gn). Some version of umodel that you can find in your temp folder when running UEskelmeshViewer.exe can indeed open the packages. I'm not sure about animations but if you look at my previous post you can get a whole character folder which should include a package with animations as well.

> Reply from shakotay2
>
> I won't bother but where's the UE SkelMesh Viewer from?
Virustotal says:

I used it in a VM, which I reinstall all 4..6 weeks, so I'm safe.
(and 'yes', it displays this amazing girl...)

Apparently it's from [here](http://www.gildor.org/smf/index.php?topic=538.0), just for reference.
## Post #11
- Username: gildor
- Rank: n00b
- Number of posts: 19
- Joined date: Tue May 25, 2010 5:15 am
- Post datetime: 2016-06-15T07:51:13+00:00
- Post Title: Extracting models from Dirty Bomb

> Reply from errur
>
> 
shakotay2 wrote:I won't bother but where's the UE SkelMesh Viewer from?
Virustotal says:

I used it in a VM, which I reinstall all 4..6 weeks, so I'm safe.
(and 'yes', it displays this amazing girl...)

Apparently it's from here, just for reference.
Hi guys. This is just a very first attempt to create a kind of GUI for UModel, with an old UModel version bundled into it.
