## Post #1
- Username: ghostx2015
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 11, 2015 12:32 am
- Post datetime: 2015-11-05T03:41:19+00:00
- Post Title: Skyforge .bin

Game download link:
[http://sf.my.com/us/download/](http://sf.my.com/us/download/)
sample files: 
[https://mega.nz/#!D0FjiZ7Q!RTxa0vuNjGFk ... hbX4iQeahI](https://mega.nz/#!D0FjiZ7Q!RTxa0vuNjGFkrMV4HmtGWkFFtdzqP1mVZhbX4iQeahI)
## Post #2
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-11-22T11:08:19+00:00
- Post Title: Skyforge .bin

Hi

Files like "Skyforge_Characters\Female\Skins\Armors\Robot\Base.Skin-Geometry.bin" have only mesh data.
No info about submeshes, lods, vertex stride,  only vertexdata size and indicedata size.
Vertex position is as floats from 3 x 2bytes (3 shorts).


Files like "Skyforge_Characters\Female\Skins\Armors\Robot\Base-MaterialLayer.bin" have image data.
[skyforge.jpg](https://xentaxbackup.github.io/file/10050_skyforge.jpg)
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-11-22T11:55:58+00:00
- Post Title: Skyforge .bin

Yes, .bin from character's folder stores only raw mesh/image data inside. There's a big files which stores all information about any object in the game - mesh/textures/skeleton it's about ~270-280mb in size. I have script for model import, but it's in "beta" stage, though it's importing most of player models (maybe vehicles too or weapons)
## Post #4
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2015-11-30T19:14:36+00:00
- Post Title: Skyforge .bin

Zaramot any chance you can share your script? also will it work for Allods online?
## Post #5
- Username: MrMoonKr
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Oct 16, 2009 2:18 pm
- Post datetime: 2015-12-01T07:12:08+00:00
- Post Title: Skyforge .bin

Szkaradek123 , How did you get 3-floats from 3-shorts ?
3-shorts are 3-half ( floats ) ?
## Post #6
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-12-01T09:38:32+00:00
- Post Title: Skyforge .bin

I can, but script is in very early stage  You will get character models (not all of them) and that's all, and no rig! Should finish it, at least with rig support, after I will end with other game I'm working on now
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-01T18:40:20+00:00
- Post Title: Skyforge .bin

Female_Skins_Armors_Robot_Base-Skin-Geom_.jpg (188.8 KiB) Viewed 961 times
## Post #8
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2016-08-22T19:57:31+00:00
- Post Title: Skyforge .bin

> Reply from shakotay2
>
> Female_Skins_Armors_Robot_Base-Skin-Geom_.jpg
thanks for the model shakotay2

not sure if people are still trying to extract assets form Skyforge but i have managed to extract some textures.



Are people still interested in reverse engineering this game? they made one of the most optimized and good looking game engines i've ever seen. their textures are a little bit unusual.

i documented my findings about the textures here [viewtopic.php?f=18&t=12828&p=121865#p121865](http://forum.xentax.com/viewtopic.php?f=18&t=12828&p=121865#p121865) if anyone's intetested
## Post #9
- Username: freakshow
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Jan 20, 2014 2:08 am
- Post datetime: 2017-02-11T17:02:52+00:00
- Post Title: Skyforge .bin

Bump, any progress on the script?
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-12T07:24:45+00:00
- Post Title: Skyforge .bin

here is a Noesis python script to open the Geometry.bin samples  


 fmt_Skyforge_bin.zip
(758 Bytes) Downloaded 178 times


supports geometry and UVs
and it looks like there are overlapping LOD meshes that need separating
## Post #11
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-03-19T01:46:48+00:00
- Post Title: Skyforge .bin

> Reply from AceWell
>
> here is a Noesis python script to open the Geometry.bin samples  
fmt_Skyforge_bin.zip
supports geometry and UVs
and it looks like there are overlapping LOD meshes that need separating

Help, getting the following error...I am trying to extract from the Visual.Characters pak files
File "G:\Program Files\ModTools\Noesisv4206\plugins\python\fmt_Skyforge_bin.py", line 36, in noepyLoadModel
    rapi.rpgCommitTriangles(IBuf, noesis.RPGEODATA_USHORT, FCount, noesis.RPGEO_TRIANGLE, 1) #SHORT for word indices
RuntimeError: Number of indices must be evenly divisible by 3 with RPGEO_TRIANGLE
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-19T09:24:48+00:00
- Post Title: Skyforge .bin

easy fix, looks like it uses triangle strips instead but i would need to see the sample for testing.
## Post #13
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-03-19T16:02:40+00:00
- Post Title: Skyforge .bin

> Reply from AceWell
>
> easy fix, looks like it uses triangle strips instead but i would need to see the sample for testing.
Ace, what info do you need? When you say sample do you want the file that I was trying to open?
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-19T16:31:16+00:00
- Post Title: Skyforge .bin

yeah upload some that don't work so i can test before updating the script.
## Post #15
- Username: parttimegamer15
- Rank: advanced
- Number of posts: 40
- Joined date: Fri Jun 17, 2016 2:00 am
- Post datetime: 2017-03-27T15:34:18+00:00
- Post Title: Skyforge .bin

> Reply from AceWell
>
> yeah upload some that don't work so i can test before updating the script.
Ace, sorry for the delay in replying. I tried again today but I think I am not even getting the basics right...The bin file I am trying to export is under the following folder...Not sure this is the path I should be using (I can't see anything starting with geometry.bin or anything that sounds like mesh file...
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-27T17:04:42+00:00
- Post Title: Re: Skyforge .bin

don't know, i don't have or play the game, but if it isn't "geometry.bin" then it likely won't open with the script
## Post #17
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2017-03-28T10:58:11+00:00
- Post Title: Re: Skyforge .bin

> Reply from parttimegamer15
>
> AceWell wrote:yeah upload some that don't work so i can test before updating the script.
Ace, sorry for the delay in replying. I tried again today but I think I am not even getting the basics right...The bin file I am trying to export is under the following folder...Not sure this is the path I should be using (I can't see anything starting with geometry.bin or anything that sounds like mesh file...
all the materiallayer.bin files are packed textures. as Ace said his plugin for noesis opens geometry.bin files. if you're missing the geometry.bin file then something might have went wrong during the unpacking process. for which armor are you missing the geometry.bin file?
## Post #18
- Username: slawdos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 27, 2016 11:29 pm
- Post datetime: 2017-05-16T00:07:24+00:00
- Post Title: Re: Skyforge .bin

[https://habrahabr.ru/company/mailru/blog/248873/](https://habrahabr.ru/company/mailru/blog/248873/) Here is a description of the device models.
## Post #19
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2017-08-05T03:13:50+00:00
- Post Title: Re: Skyforge .bin

all the materiallayer.bin files are packed textures.

unpack textures  script plz
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-09T06:19:41+00:00
- Post Title: Re: Skyforge .bin

> Reply from lxxxk
>
> all the materiallayer.bin files are packed textures.

unpack textures  script plz
upload some samples for examination please
## Post #21
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2017-08-10T08:15:00+00:00
- Post Title: Re: Skyforge .bin

[http://zheli.org/data/20170810161436.rar](http://zheli.org/data/20170810161436.rar)
## Post #22
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-10T14:19:55+00:00
- Post Title: Re: Skyforge .bin

heres a Noesis python script to open your sample  


 tex_Skyforge_MaterialLayer_bin.zip
(820 Bytes) Downloaded 123 times


supports dxt5 and is set to display all mips   
if some textures appear invisible just press F11 to disable viewport transparency while viewing.
## Post #23
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2017-08-11T02:11:22+00:00
- Post Title: Re: Skyforge .bin

thanks

Model broken， please fixes

heres a model samples

[http://zheli.org/data/20170811101342.rar](http://zheli.org/data/20170811101342.rar)
## Post #24
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-11T03:55:17+00:00
- Post Title: Re: Skyforge .bin

the problem with these model files has always been there is no header, just the total buffer sizes for vertex block and indices are stored.
your sample has face indices that reset to "00 00" five times, could be LODs or accessories, i didn't check.
that reset in the indices is the only indication there may be submeshes, so changing the script to make 
it work for this sample could break it for others because detecting this "reset" may not be reliable.



Geometry_bin.png (47.71 KiB) Viewed 416 times
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-11T14:01:27+00:00
- Post Title: Re: Skyforge .bin

yep, some armor and lod:



Skyforge_geom.jpg (215.05 KiB) Viewed 398 times



H2O file for upper part of pic:

0x16CC36 16035
Vb1
24 8
0x743A8 3928
020400
0x0 255
## Post #26
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2017-08-12T17:03:23+00:00
- Post Title: Re: Skyforge .bin

> Reply from AceWell
>
> heres a Noesis python script to open your sample  
tex_Skyforge_MaterialLayer_bin.zip
supports dxt5 and is set to display all mips   
if some textures appear invisible just press F11 to disable viewport transparency while viewing.
thanks for this but word of warning as not all textures are dxt5, found some r8g8b8a8_unorm in the mix.
## Post #27
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-12T17:15:15+00:00
- Post Title: Re: Skyforge .bin

> Reply from OriginOfWaves
>
> not all textures are dxt5, found some r8g8b8a8_unorm in the mix.
upload some samples and i'll have a look, these files have no header or anything
so there isn't a whole lot one can do with them other than extracting by hand.
## Post #28
- Username: liuxing
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 09, 2014 11:50 am
- Post datetime: 2018-03-04T22:52:20+00:00
- Post Title: Re: Skyforge .bin

> Reply from AceWell
>
> OriginOfWaves wrote:not all textures are dxt5, found some r8g8b8a8_unorm in the mix.
upload some samples and i'll have a look, these files have no header or anything
so there isn't a whole lot one can do with them other than extracting by hand.
[https://drive.google.com/open?id=12e0Z9 ... nm7M3EHHyt](https://drive.google.com/open?id=12e0Z9DPseDcLwzZ3mH-aTynm7M3EHHyt)

all char in this file.please look it and fix python.
## Post #29
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-03-07T07:30:50+00:00
- Post Title: Re: Skyforge .bin

there is no fixing, the files lack a header and there is no way to tell what the format or 
dimensions are, the only factor to work from is the size of each mip which is not reliable.   
unless someone locates files in the game containing the headers there is nothing more i can do, sorry.   
you can always use TextureFinder or Rawtex to get the images in a usable state.
## Post #30
- Username: slawdos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 27, 2016 11:29 pm
- Post datetime: 2018-05-03T02:12:16+00:00
- Post Title: Re: Skyforge .bin

Hi! I use fmt_Skyforge_bin.py, but mesh have many issue:



How fix it?

[https://drive.google.com/open?id=1j3a8C ... 7iAY42uCn4](https://drive.google.com/open?id=1j3a8CeIx-XfSqySwd3zM107iAY42uCn4)
## Post #31
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-03T02:54:05+00:00
- Post Title: Re: Skyforge .bin

the "fix" comes when you guys that have the game find the files that store the header info
for the mesh and texture files so they can be read properly. your sample has submeshes but
can't be read in a single array because the indices run together, i could cobble up something
to attempt locating the indices start of each submesh but that isn't reliable, i'd rather do it right.
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-03T11:24:07+00:00
- Post Title: Re: Skyforge .bin

> Reply from slawdos
>
> How fix it?
If you know 'C' you might fix it in the source of the Make_obj project:
[viewtopic.php?f=29&t=15955&p=140250#p140250](http://forum.xentax.com/viewtopic.php?f=29&t=15955&p=140250#p140250)

edit: well, seems I got it: it's simply up to 3 "lod copies" with the same! vertex count.
Use the 3 H2O files at the bottom with the sample from lxxxk, post as of Fri Aug 11, 2017 3:11 am
to understand what I mean.
- for the bikini girl it's different: two identical meshes here:
0xDD86C 4470
Vb1
24 8
0x1F3E8 1071
020400
0x0 255

0xDD86C 4470
Vb1
24 8
0x5DBA8 1071
020400
0x0 255

-----------------------------

3rd submesh wrong, in hex2obj, too:



Skyforge-3rdSm-errror.jpg (167.66 KiB) Viewed 355 times


As Ace mentioned there's a problem with some submeshes; the pointclouds are ok, the face indices seem to be ok, too
but somehow they don't fit together. (Guess the v addresses have to be changed to higher ones.)

> Reply from zaramot
>
> There's a big files which stores all information about any object in the game - mesh/textures/skeleton it's about ~270-280mb in size.

btw: isn't Skyforge a popular MMO in Russia? I couldn't imagine that there's no perfect modelviewer from some enthusiast russian coder.

And: I'm desperately missing the head of this body 

---------------------------------
same lod with lxxxk' sample:
0x17497C 9030
Vb1
24 8
0xB9468 2546
020400
0x0 255

0x17497C 9030
Vb1
24 8
0xc8318 2546
020400
0x0 255

0x17497C 9030
Vb1
24 8
0xd71c8 2546
020400
0x0 255
## Post #33
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-03T15:05:26+00:00
- Post Title: Re: Skyforge .bin

well, that was kinda a little bit tricky, we have at least (maybe more)
2 copies of body plus LOD2 body, plus bodies at 0x25850, 0x9ef30, FIs?
4 copies of "cloth set"
3 copies of shoes

for the bikini girl. How should anyone have known this? A waste of time and life.  

('copies' means, they are visually identical, the vertices themselves vary a lttle bit)



Bikini-girl.jpg (161.16 KiB) Viewed 352 times



H2O file body, lod 1

0xD1890 24558
Vb1
24 8
0x8 5332
020400
0x0 255
## Post #34
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-05-03T23:05:22+00:00
- Post Title: Re: Skyforge .bin

> There's a big files which stores all information about any object in the game - mesh/textures/skeleton it's about ~270-280mb in size.
i'm still waiting for someone to upload this "big file", it supposedly contains all the secrets.
## Post #35
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-06T16:06:56+00:00
- Post Title: Re: Skyforge .bin

maybe we should ask Zaramot for the name of it; there's many paks, and I couldn't seem to find something promising

anyways, the FVF from this witches' Base.Skin-Geometry has an FVF of 28 instead of 24:



Witch Base_skin-geometry.jpg (211.4 KiB) Viewed 331 times
## Post #36
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2018-05-10T10:08:10+00:00
- Post Title: Re: Skyforge .bin

there are also models with FVF of 16 and 20. usually weapon models. i've extracted most of the models form Skyforge and saved .h2o files for most of them. so let me know if you need a h2o for a particular model.
## Post #37
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T11:23:08+00:00
- Post Title: Re: Skyforge .bin

> Reply from OriginOfWaves
>
> there are also models with FVF of 16 and 20. usually weapon models. i've extracted most of the models form Skyforge and saved .h2o files for most of them. so let me know if you need a h2o for a particular model.Thanks for your offer! But I think we need an overall solution that would require the above mentioned "big (parameter) file".

As for the above model which I called "bikini girl". Did you get the H2O files and if so did you get them one by one (which I found to be very tedious, 4 copies of "cloth set", 3 copies of shoes) or do you have some method which we could transform into code? For me it was a time eating trial 'til I found it were 4 "cloth sets" and 3 pairs of shoes for example.
## Post #38
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-10T14:52:33+00:00
- Post Title: Re: Skyforge .bin

I decided to take a look at the bikini girl and I was able to get the meshes without a problem.



My approach is similar to shakotay's, the only difference being the calculation of the vertex data offset of the following mesh.

It seems like every index block start with "0000 0100 0200". So find the positions of this pattern, read until you find the next occurrence, and for the last one read until the end of the file. This basically gets you the indices of each mesh.

After that I printed out the maximum values of index list to get an idea of the vertex counts. It came up like this :



The vertex data starts almost immediately at offset 0x8, and the integer value before that (at 0x4), is the size of this data. For the bikini girl this value is 858240. We divide that by the total vertex count, and we get 858240 / 11920 = 72.

Still the vertex block size for a single vertex is not 72 bytes, it is 24 bytes as you can see from shakotay's h2o screenshots. Instead for each mesh there are 3 times (24 bytes blocks * vertex count), 2 of them appears to be LODs.

In my code I read 24 * vertex count, but for calculating the vertex data offset of the next mesh, I do 72 * vertex count. It seems right for the bikini girl model. I haven't checked other files, but if every mesh has exactly 3 copies, it would be possible to find the vertex block size with :
vertex data size (at 0x4) / total vertex count / 3.

Here is my code. Some methods are not in the code, but you get the main idea. I commented what the method does.

```
	{
		byte[] fileData = File.ReadAllBytes ("base.bin");
		var pattern  = new byte[] { 0, 0, 1, 0, 2, 0 };
		int[] indPoses = Locate (fileData, pattern); // Find the positions of the pattern 0000 0100 0200

		MemoryStream ms = new MemoryStream (fileData);
		BinaryReader reader = new BinaryReader (ms);

		List<int> vertCounts = new List<int> ();
		List<List<int>> allInds = new List<List<int>> ();

		int len = indPoses.Length;
		for (int i = 0; i < len; i++) {
			int pos = indPoses [i];
			int nextPos = pos;

			ms.Seek (pos, SeekOrigin.Begin);

			if (i == len - 1) 
				nextPos = (int)ms.Length;   // last element, read until EOF
			else             
				nextPos = indPoses [i + 1]; // read until the next occurence of the pattern

			List<int> indices = new List<int> ();
			while (ms.Position < nextPos) {
				indices.Add (reader.ReadInt16 ());
			}

			int max = indices.Max (e => e);
			vertCounts.Add (max + 1);
			allInds.Add (indices);
		}

		// Debug
		int sum = 0;

		foreach (var vc in vertCounts) {
			Debug.Log (vc);
			sum += vc;
		}

		Debug.Log ("Total : " + sum);
		// End

		int nextOff = 8; // vertex block start same for every file?

		for (int i = 0; i < vertCounts.Count; i++) {
			int vc = vertCounts [i];
			ms.Seek (nextOff + vc, SeekOrigin.Begin);
			nextOff += vc * 72;

			List<Vector3> vertices = new List<Vector3> ();
			for (int v = 0; v < vc; v++) {
				float xVal = shortToFloat (reader.ReadBytes (2)); 
				float yVal = shortToFloat (reader.ReadBytes (2));
				float zVal = shortToFloat (reader.ReadBytes (2));

				vertices.Add (new Vector3 (xVal, yVal, zVal));
				ms.Seek (18, SeekOrigin.Current); // Assumed 24 bytes for the  vertex block
			}
		}

		reader.Close();
	}
```
## Post #39
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T15:45:27+00:00
- Post Title: Re: Skyforge .bin

Great!

But for the "cloth set" I found 4 meshes, so I guess the first one at 0x1F3E8 to be ignored when analysing?

0xDD86C 4470 # edit: well, this is "fake", accidentially grasped from the body
Vb1
24 8
0x1F3E8 1071
020400
0x0 255

0xDD86C 4470
Vb1
24 8
0x5DBA8 1071
020400
0x0 255

0xDD86C 4470
Vb1
24 8
0x64010 1071
020400
0x0 255

0xDD86C 4470
Vb1
24 8
0x6A478 1071
020400
0x0 255
## Post #40
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-10T16:14:10+00:00
- Post Title: Re: Skyforge .bin

> Reply from shakotay2
>
> 
so I guess the first one at 0x1F3E8 to be ignored when analysing?

I would say yes. I am getting the first 2 meshes like this. First one is full body with clothes, and second one is just clothes.



So the first block : 

> Reply from shakotay2
>
> 
0xDD86C 4470
Vb1
24 8
0x1F3E8 1071
020400
0x0 255

is actually part of the full body, but it seems to work fine with the indices of the second index list too. Full body mesh seems to be put together from the vertices of other meshes in the file, and I guess you found the part related to cloth vertices, inside the full body vertices.

Btw this seems like an inefficient way to store model data to me. They are repeating lots of vertex blocks.
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T16:43:37+00:00
- Post Title: Re: Skyforge .bin

well, yes, inefficient, lol.
I updated the code of my Make_obj - project. It was so simple, but I still don't understand about the 4 "cloth meshes". I also don't understand why I get 3 bodies.  

Have to think about it when I have some spare time.

btw: nice to have someone like you here, akaderebur! Kudos.



bikiniGirl.jpg (68.75 KiB) Viewed 278 times
## Post #42
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-10T17:04:50+00:00
- Post Title: Re: Skyforge .bin

> Reply from shakotay2
>
> 
I also don't understand why I get 3 bodies.
I am not sure why there are 3 bodies either, but the last one seems to have no straps for bikini. So maybe different variations of the same bikini, with small differences.

> Reply from shakotay2
>
> 
btw: nice to have someone like you here, akaderebur! Kudos.
Thanks, I am flattered  I see you (and AceWell too) on the forums daily, helping people with almost every game. I just give a hand, when/if I can find out something.
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-05-10T17:12:28+00:00
- Post Title: Re: Skyforge .bin

(sorry for the misspelling of your nick, akderebur, seems I was thinking of "academic" which is spelled "akademisch" in german.)

well, seems I somehow grasped the "fourth" bikini from the body (starting at 0x0008).

This is the result for the Geometry.bin uploaded by lxxxk:



lxxxk Geometry-bin.jpg (125.87 KiB) Viewed 261 times
## Post #44
- Username: OriginOfWaves
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 08, 2011 8:58 pm
- Post datetime: 2018-05-11T09:12:04+00:00
- Post Title: Re: Skyforge .bin

my take on it is that the 3 bodies are there for the body sliders that are in the game. so there is a Skinny, Athletic and Thicc body for every character model. the game just morphs between these 3 bodies when you change the sliders.
## Post #45
- Username: ethanej
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 02, 2015 1:56 am
- Post datetime: 2019-01-23T22:35:57+00:00
- Post Title: Re: Skyforge .bin

> Reply from Acewell
>
> There's a big files which stores all information about any object in the game - mesh/textures/skeleton it's about ~270-280mb in size.
i'm still waiting for someone to upload this "big file", it supposedly contains all the secrets.

I had to compress the files in order to be able to upload them.

The only big file I could find is 389MB:
https://www.mediafire.com/file/k68q7a84eb1urno/xdbPack.7z

Not sure but I think this file has something in it. Towards the bottom it lists Geometry.bin, MaterialLayer.bin, and the animation bins:
https://www.mediafire.com/file/3129l5gq4b63gbp/atoc.7z/file
## Post #46
- Username: ethanej
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 02, 2015 1:56 am
- Post datetime: 2019-02-09T20:44:16+00:00
- Post Title: Re: Skyforge .bin

Did either of the files provide the information you need to get the models and textures to working correctly?
## Post #47
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-09T21:01:08+00:00
- Post Title: Re: Skyforge .bin

nothing really stood out to me, my guess is this issue has to be resolved
during extraction so that everything is cross referenced precisely.
maybe someone who has all the files can see something i don't.
## Post #48
- Username: ethanej
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 02, 2015 1:56 am
- Post datetime: 2019-02-09T22:23:41+00:00
- Post Title: Re: Skyforge .bin

> Reply from Acewell
>
> nothing really stood out to me, my guess is this issue has to be resolved
during extraction so that everything is cross referenced precisely.
maybe someone who has all the files can see something i don't.

Okay. I'm wondering if toc.developer is an index on how to unpack the pak files. An other file labeled links.temp.bin.index seems to have a few things in common with toc.developer. In both files it seems to point that the outputted file should be like Visual/Characters/Male/Skins/Armors/Football/Base.Skin-Geometry.bin.zip.

Edit: I'm looking at some other files also that are outside of the pak files one says something about triangulation and texcoord.
## Post #49
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-10T14:00:44+00:00
- Post Title: Re: Skyforge .bin

@ethanej: if you're really interested in "the big file" you should ask zaramot for its name. (Kinda funny that this isn't known since Sun Nov 22, 2015 12:55 pm now  )

If anyone ever managed to find suiting textures for a model I'd start from finding the belonging names in files rather than doing a blind search.

For the file list in toc.developer, you need to count the files, then try to make sense of the index table.
(Searching for Visual/ = 56697375616C2F, it's contained 75753 times but names like QA/Maps/TestFlowScript/CubeProbes/Probe_151756-ProbeCube.bin.zip are uncounted then.)
We have 108272 entries like such:
0x000010: F86E1A00 0D000000 FE6E1A00 43000000
...
0x1A6EF0: F25DF900 41000000 2C5EF900 41000000


the strings are just a non alphabetical file list:
[...]
Visual/Characters/Mounts/Deer/Animations/Run126FrontForwards_Male-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Paladin/Movement/JumpRun7FrontForwardsEnd-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Deer/Animations/Run126FrontLeftEnd_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Deer/Animations/Run126FrontLeftStart_Male-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/Paladin/Movement/JumpRun7FrontForwardsLand-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Deer/Animations/Run126FrontLeft_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Deer/Animations/Run126FrontRightEnd_Male-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Paladin/Movement/JumpRun7FrontForwardsStart-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Deer/Animations/Run126FrontRightStart_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Deer/Animations/Run126FrontRight_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Deer/Animations/Run8BackBackwardsLeft_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Deer/Animations/Run8BackBackwardsRight_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Deer/Animations/Run8BackBackwards_Male-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Necromancer/Poses/Ready03.Pose-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Deer/Animations/SitDown_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Deer/Animations/SpecialJump_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Deer/Animations/TurnJumpAdditive_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Deer/Animations/TwistRight_Male.Pose-SkeletalAnimation.bin.zip Visual/Creatures/Eye/Animations/Death01-SkeletalAnimation.bin.zip Visual/Creatures/Eye/Animations/Death02-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Other/Ready01To00-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Other/Ready02To00-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Other/Ready03To00-SkeletalAnimation.bin.zip Visual/Items/Loot/Cube_NY-Geometry.bin.zip

Visual/Items/Loot/Cube_NY-MaterialLayer.bin.zip Visual/Items/Loot/GradientMap-MaterialLayer.bin.zip Visual/Characters/Male/Animations/General/Movement/DashFrontRight-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/General/Movement/JumpRun7FrontForwards-SkeletalAnimation.bin.zip

Visual/Characters/Male/Animations/General/Movement/JumpRun7FrontForwardsEnd-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/General/Movement/JumpRun7FrontForwardsLand-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/General/Emotes/Beg-SkeletalAnimation.bin.zip
Visual/Characters/Male/Animations/Paladin/Movement/JumpIdleEnd-SkeletalAnimation.bin.zip
Visual/Characters/Male/Skins/Armors/Assassin/Corpse_04-Geometry.bin.zip Visual/Characters/Male/Skins/Armors/Assassin/Base-MaterialLayer.bin.zip Visual/Characters/Male/Skins/Armors/Assassin/GradientMap-MaterialLayer.bin.zip
Visual/Characters/Female/Skins/Armors/Assassin/Boss.GradientMap-MaterialLayer.bin.zip Visual/Characters/Male/Skins/Hats/Assassin/Base-MaterialLayer.bin.zip Visual/Characters/Female/Animations/General/Emotes/KneelLoop-SkeletalAnimation.bin.zip

Visual/Creatures/Worm/Corpse_02-Geometry.bin.zip

Visual/Characters/Female/Animations/General/Emotes/KneelStart-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Movement/JumpIdleLand-SkeletalAnimation.bin.zip Visual/Creatures/Worm/Corpse_01-Geometry.bin.zip
Visual/Characters/Female/Animations/GuardianOfLight/Movement/DashBackBackwardsLeft-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/BegFrontStand-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/BegUpKneel-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/BegUpStand-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Movement/JumpRun7BackBackwards-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/TalkListen-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/TalkListen01-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Movement/JumpRun7BackBackwardsEnd-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/TalkListenAgree-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/TalkListenBrutal-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Movement/JumpRun7BackBackwardsLand-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/TalkListenCarefullyEnd-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/TalkListenCarefullyLoop-SkeletalAnimation.bin.zip

Visual/Characters/Male/Animations/Paladin/Movement/JumpRun7BackBackwardsStart-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyForwardEnd-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/TalkListenCarefullyStart-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/TalkListenDisappointment-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/TalkSaysAgressive-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/TalkSaysAgressive01-SkeletalAnimation.bin.zip
Visual/Characters/Male/Animations/Paladin/Movement/JumpRun7FrontForwardsEnd-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/TalkSaysJustified-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/NPC/Emotes/TalkSaysPositive-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Movement/JumpRun7FrontForwardsLand-SkeletalAnimation.bin.zip

Visual/World/Generic/Environment/Capsule_Transformer/Base_01.OpenedMiddle-Geometry.bin.zip
Visual/World/Generic/Textures/Capsule_Transformer_01-MaterialLayer.bin.zip
Visual/World/Generic/Environment/Capsule_Transformer/Base_01.OpenedLeft-Geometry.bin.zip
Visual/World/Generic/Environment/Capsule_Transformer/Base_01.OpenedRight-Geometry.bin.zip Visual/Characters/Female/Animations/NPC/Emotes/TalkSpeech-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/Paladin/Movement/JumpRun7FrontForwardsStart-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyRightEnd-SkeletalAnimation.bin.zip

Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyForwardStart-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyLeftStart-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyRightStart-SkeletalAnimation.bin.zip
Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyBackwardStart-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyLeftEnd-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Witch/Attacks/BroomFlyBackwardEnd-SkeletalAnimation.bin.zip Visual/Characters/Male/Animations/MadAlchemist/Movement/Run5BackBackwardsRight-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Dragon/Mechanical/Animations/DashBackwards_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Dragon/Mechanical/Animations/DashForwards_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/DashLeft_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/DashRight_Male-SkeletalAnimation.bin.zip
Visual/Creatures/Triffid/Animations/ChannelDirect-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/FlyBackwards_Male.Pose-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Dragon/Mechanical/Animations/FlyForwards_Male.Pose-SkeletalAnimation.bin.zip Visual/Creatures/Triffid/Animations/ChannelDirect01-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/Idle_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/JumpRunForwardsEnd_Male-SkeletalAnimation.bin.zip Visual/Creatures/Triffid/Animations/Death-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/JumpRunForwardsLand_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Dragon/Mechanical/Animations/JumpRunForwardsLoop_Male-SkeletalAnimation.bin.zip
Visual/Creatures/Triffid/Animations/PreaggroEnd-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/JumpRunForwardsStart_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/KnockDownLoop_Male-SkeletalAnimation.bin.zip
Visual/Creatures/Triffid/Animations/PreaggroStart-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/KnockDownStart_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/Run126ForwardEnd_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/Run126Forward_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Dragon/Mechanical/Animations/Run126LeftEnd_Male-SkeletalAnimation.bin.zip
Visual/Characters/Mounts/Dragon/Mechanical/Animations/Run126Left_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/Run126RightEnd_Male-SkeletalAnimation.bin.zip Visual/Characters/Mounts/Dragon/Mechanical/Animations/Run126Right_Male-SkeletalAnimation.bin.zip
[...]
## Post #50
- Username: ethanej
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 02, 2015 1:56 am
- Post datetime: 2019-02-10T19:02:00+00:00
- Post Title: Re: Skyforge .bin

> Reply from shakotay2
>
> @ethanej: if you're really interested in "the big file" you should ask zaramot for its name. (Kinda funny that this isn't known since Sun Nov 22, 2015 12:55 pm now  )

The only big file from the pak files that I ever found was the xdbpack file that I posted a few weeks ago. I even searched the base directory where it splits files for the installer and game. 

> Reply from shakotay2
>
> If anyone ever managed to find suiting textures for a model I'd start from finding the belonging names in files rather than doing a blind search.

For the file list in toc.developer, you need to count the files, then try to make sense of the index table.
(Searching for Visual/ = 56697375616C2F, it's contained 75753 times but names like QA/Maps/TestFlowScript/CubeProbes/Probe_151756-ProbeCube.bin.zip are uncounted then.)
We have 108272 entries like such:
0x000010: F86E1A00 0D000000 FE6E1A00 43000000
...
0x1A6EF0: F25DF900 41000000 2C5EF900 41000000


the strings are just a non alphabetical file list:
[...]
Visual/Characters/Mounts/Deer/Animations/Run126FrontForwards_Male-SkeletalAnimation.bin.zip Visual/Characters/Female/Animations/Paladin/Movement/JumpRun7FrontForwardsEnd-

So basically toc.dev... is pretty much useless?

Edit: Game Directory: [https://www.mediafire.com/file/1mtzbd6k ... e.txt/file](https://www.mediafire.com/file/1mtzbd6kdeidhi9/Skyforge.txt/file)
Directory where pak are extracted: [https://www.mediafire.com/file/exzpvj4w ... ak.7z/file](https://www.mediafire.com/file/exzpvj4w3d4pmh2/Skyforgepak.7z/file)
## Post #51
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-02-10T21:44:04+00:00
- Post Title: Re: Skyforge .bin

> Reply from ethanej
>
> So basically toc.dev... is pretty much useless?I wouldn't say so; I counted 0000 in the string part and it's contained 108648 times. We'd need to understand whether the index lines contain just hashes only or something more.

Anyways, I searched for .dds in the string table part and it is contained 1827 times. On a quick glance I only found Visual/Interface/Portraits/Large/ClassIcon/Bard.dds.bin.zip, Visual/Interface/Promotion/MarketResource/Wide/DragonWings.dds.bin.zip, Visual/Interface/MarketPlace/PackLogos/Virgil.dds.bin.zip and such.

But there's Visual/Interface/Icons/Equipment/Weapons/BardWeapon_01.tga.bin.zip for example.
Maybe you could unpack the tgas contained (?) and search for the suiting weapon which should not be too hard?
## Post #52
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-10T23:18:51+00:00
- Post Title: Re: Skyforge .bin

> Reply from ethanej
>
> Game Directory: https://www.mediafire.com/file/1mtzbd6k ... e.txt/file
thanks! i see a lot of interesting files there, i guess i'll have to download the game to check many of them though.  

can you upload "toc" from here

```
I:\Steam\SteamApps\common\Skyforge\Skyforge MyCom\data\Packs
```
## Post #53
- Username: ethanej
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Dec 02, 2015 1:56 am
- Post datetime: 2019-02-11T15:22:48+00:00
- Post Title: Re: Skyforge .bin

> Reply from shakotay2
>
> ethanej wrote:So basically toc.dev... is pretty much useless?I wouldn't say so; I counted 0000 in the string part and it's contained 108648 times. We'd need to understand whether the index lines contain just hashes only or something more.

Anyways, I searched for .dds in the string table part and it is contained 1827 times. On a quick glance I only found Visual/Interface/Portraits/Large/ClassIcon/Bard.dds.bin.zip, Visual/Interface/Promotion/MarketResource/Wide/DragonWings.dds.bin.zip, Visual/Interface/MarketPlace/PackLogos/Virgil.dds.bin.zip and such.

But there's Visual/Interface/Icons/Equipment/Weapons/BardWeapon_01.tga.bin.zip for example.
Maybe you could unpack the tgas contained (?) and search for the suiting weapon which should not be too hard?

Managed to get the tga files to display the only thing I had to do was drop the bin part.

> Reply from Acewell
>
> ethanej wrote:Game Directory: https://www.mediafire.com/file/1mtzbd6k ... e.txt/file
thanks! i see a lot of interesting files there, i guess i'll have to download the game to check many of them though.  

can you upload "toc" from here
Code: Select allI:\Steam\SteamApps\common\Skyforge\Skyforge MyCom\data\Packs
[http://www.mediafire.com/file/lklasmb5cxt56um/toc/file](http://www.mediafire.com/file/lklasmb5cxt56um/toc/file) Doesn' feel like it contains much.

I was working with a texture file and it is displaying but it feels like I'm missing something and I don't quite know what. I've tried changing between DXT1, DXT3, and DXT5.
[Wood-MaterialLayer.png](https://xentaxbackup.github.io/file/15705_Wood-MaterialLayer.png)
## Post #54
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2020-07-25T18:11:35+00:00
- Post Title: Re: Skyforge .bin

Hello, have you by chance been able to obtain the mounts and weapons of this game with their respective textures? Or can you tell me if it is possible? , I don't have much free space on my disk so I wanted to know that before trying to download the game. Thanks in advance.
## Post #55
- Username: Reapperrayne
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Apr 25, 2019 5:54 am
- Post datetime: 2021-01-03T01:38:49+00:00
- Post Title: Re: Skyforge .bin

]how to fix this?
[modeloutout.jpg](https://xentaxbackup.github.io/file/19261_modeloutout.jpg)
## Post #56
- Username: revanr
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Oct 31, 2018 11:25 pm
- Post datetime: 2021-02-24T21:22:33+00:00
- Post Title: Re: Skyforge .bin

is it possible to extract hair model from this game guys?
Iam only want to export some of the hair model and textures, I really dont care about bone or animation etc...
## Post #57
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-31T08:09:11+00:00
- Post Title: Re: Skyforge .bin

Hello, I found this mount in a package, and can't be opened with the texture or model script, someone can take a look at it please? I'm pretty sure that it contain a very cool mount! Thanks.  

Model: [https://www.mediafire.com/file/ggo7uit7 ... y.bin/file](https://www.mediafire.com/file/ggo7uit7yzbck6h/Base01-Geometry.bin/file)
Textures: [https://www.mediafire.com/file/0qeg7deg ... r.bin/file](https://www.mediafire.com/file/0qeg7deglx0soij/Base01-MaterialLayer.bin/file)
[https://www.mediafire.com/file/hwg2n444 ... r.bin/file](https://www.mediafire.com/file/hwg2n444b2twnq0/Base02-MaterialLayer.bin/file)
## Post #58
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-31T18:30:09+00:00
- Post Title: Re: Skyforge .bin

For Base01-Geometry.bin you're better off to use hex2obj (since there's face indices blocks that don't start with 000001000200 which the Make_obj Skyforge version relies on).
.



Base01-Geometry-bin.png (92.49 KiB) Viewed 116 times
## Post #59
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-03-31T20:09:57+00:00
- Post Title: Re: Skyforge .bin

> Reply from shakotay2 ↑Thu Apr 01, 2021 2:30 am at Thu Apr 01, 2021 2:30 am
>
> 
For Base01-Geometry.bin you're better off to use hex2obj (since there's face indices blocks that don't start with 000001000200 which the Make_obj Skyforge version relies on).
.
Base01-Geometry-bin.png

Thanks! Shakotay gonna try it at night!
## Post #60
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-01T17:04:47+00:00
- Post Title: Re: Skyforge .bin

> Reply from Acewell ↑Thu Aug 10, 2017 10:19 pm at Thu Aug 10, 2017 10:19 pm
>
> 
heres a Noesis python script to open your sample  
tex_Skyforge_MaterialLayer_bin.zip
supports dxt5 and is set to display all mips   
if some textures appear invisible just press F11 to disable viewport transparency while viewing.
Hello! someone could point me how to modify this script to can open some textures that are 512*1024 and others that are this format RGBA= RGB + ALPHA (8888 = 24 + 8 ). Any kind of advices would be great!

[https://www.mediafire.com/file/gjbf5jpn ... 9.bin/file](https://www.mediafire.com/file/gjbf5jpnvrcp66e/Armor-MaterialLayer_%2528DXT5__512x1024%2529.bin/file)

[https://www.mediafire.com/file/0qeg7deg ... 9.bin/file](https://www.mediafire.com/file/0qeg7deglx0soij/Base01-MaterialLayer_RGBA%253D_RGB_%252B_ALPHA_%25288888_%253D_24_%252B_8%2529.bin/file)

[https://www.mediafire.com/file/hwg2n444 ... 9.bin/file](https://www.mediafire.com/file/hwg2n444b2twnq0/Base02-MaterialLayer_RGBA%253D_RGB_%252B_ALPHA_%25288888_%253D_24_%252B_8%2529.bin/file)
## Post #61
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-03T01:31:52+00:00
- Post Title: Re: Skyforge .bin

TextureFinder and Rawtex help me alot!  



mount.png (114.96 KiB) Viewed 151 times
## Post #62
- Username: maxy3bed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 01, 2023 11:02 am
- Post datetime: 2023-07-01T00:12:21+00:00
- Post Title: Re: Skyforge .bin

hello could someone help me with this samples plz : 

[https://mega.nz/file/SR4WjKCS#q4CnDC23w ... DvcTpXVV6I](https://mega.nz/file/SR4WjKCS#q4CnDC23wYlIH91c4WUdPtYwpXRLC5mO4DvcTpXVV6I)

here some files contain heads if this help its around 2GB size :

[https://mega.nz/file/XQxSRYAL#YxkPEzstr ... WbTTqFc0Xs](https://mega.nz/file/XQxSRYAL#YxkPEzstrFngO6CNViiW5PpHgAK6MKSk3WbTTqFc0Xs) 

all i need is the mesh
## Post #63
- Username: Valkorion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 6:30 am
- Post datetime: 2023-07-01T20:46:18+00:00
- Post Title: Re: Skyforge .bin

Good Afternoon,
I got recently interested in extracting some buildings with their textures from Skyforge, but from what I can gather the files are in .pak format, unless I'm looking at the wrong place as the comments here trying to give me indications appear out of time.
## Post #64
- Username: maxy3bed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 01, 2023 11:02 am
- Post datetime: 2023-07-01T21:04:59+00:00
- Post Title: Re: Skyforge .bin

> Reply from Valkorion ↑Sun Jul 02, 2023 4:46 am at Sun Jul 02, 2023 4:46 am
>
> 
Good Afternoon,
I got recently interested in extracting some buildings with their textures from Skyforge, but from what I can gather the files are in .pak format, unless I'm looking at the wrong place as the comments here trying to give me indications appear out of time.

just rename .pak file to .zip
## Post #65
- Username: Valkorion
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Aug 15, 2015 6:30 am
- Post datetime: 2023-07-01T21:09:33+00:00
- Post Title: Re: Skyforge .bin

> Reply from maxy3bed ↑Sun Jul 02, 2023 5:04 am at Sun Jul 02, 2023 5:04 am
>
> 
Valkorion wrote: ↑Sun Jul 02, 2023 4:46 am
Good Afternoon,
I got recently interested in extracting some buildings with their textures from Skyforge, but from what I can gather the files are in .pak format, unless I'm looking at the wrong place as the comments here trying to give me indications appear out of time.


just rename .pak file to .zip
Oh... oh shoot. Since ANNO 2070/2205 I forgot that detail. Thanks for reminding me.
## Post #66
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-01T21:59:52+00:00
- Post Title: Re: Skyforge .bin

> Reply from maxy3bed ↑Sat Jul 01, 2023 8:12 am at Sat Jul 01, 2023 8:12 am
>
> 
hello could someone help me with this samples plz :Usually I'm not too motivated to dig up things (i.e. C source here) 5 years later.
You might read here:

> Reply from shakotay2 ↑Thu May 03, 2018 7:19 pm at Thu May 03, 2018 7:19 pm
>
> 
Using the resulting Make_obj.exe as of May 2018 this is the raw result for the base.skin-geometry.bin you've uploaded.
Feel free to expand above linked source to gain a better result.
.



Skyforge_test.png (183.88 KiB) Viewed 54 times



> all i need is the meshHaha, yes. "All I need is love."
## Post #67
- Username: maxy3bed
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 01, 2023 11:02 am
- Post datetime: 2023-07-01T22:36:03+00:00
- Post Title: Re: Skyforge .bin

> Reply from shakotay2 ↑Sun Jul 02, 2023 5:59 am at Sun Jul 02, 2023 5:59 am
>
> 
maxy3bed wrote: ↑Sat Jul 01, 2023 8:12 am
hello could someone help me with this samples plz : 
Usually I'm not too motivated to dig up things (i.e. C source here) 5 years later.
You might read here:
shakotay2 wrote: ↑Thu May 03, 2018 7:19 pm
Using the resulting Make_obj.exe as of May 2018 this is the raw result for the base.skin-geometry.bin you've uploaded.
Feel free to expand above linked source to gain a better result.
.
Skyforge_test.png
all i need is the mesh
Haha, yes. "All I need is love."
i was working on hex2obj ,but i guess i am gonna try make_obj 
thanks alot
## Post #68
- Username: Moff
- Rank: n00b
- Number of posts: 19
- Joined date: Tue Apr 06, 2021 8:38 am
- Post datetime: 2023-08-30T20:00:49+00:00
- Post Title: Re: Skyforge .bin

I don't suppose that anyone have made progress in deciphering the big xdbPack.inplace file? The headers for model files are in it, i was able to find vertex\triangle counts for submeshes inside, skeletons seem to be in there as well, but i can't figure out it's structure, at least not the chunk which contains the headers (~ the first 256 mb). Has anyone looked at it?
