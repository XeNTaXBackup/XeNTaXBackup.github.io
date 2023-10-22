## Post #1
- Username: XxYarnRulerxX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 10, 2015 1:50 am
- Post datetime: 2015-11-16T05:21:44+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

How do I go about extracting the 3d model files from the .g1m files of the game? I've been able to extract the .g1t files pretty easily, but I can't find any tools that work for g1m except a max script, but I don't have max. How do I convert .g1m to obj or another usable format??

[http://www.mediafire.com/download/umfj1 ... _MODEL.rar](http://www.mediafire.com/download/umfj1lfdpg5m9j7/PC00F_MODEL.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-16T15:32:00+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from XxYarnRulerxX
>
> [...] but I can't find any tools that work for g1m except a max scriptthen what is the name of that wonderful script?  

using hex2obj (view link in my sig):



PC00F_MODEL_P_M_Body1ALL_BK_xScAlphaTest_g1m.jpg (153.78 KiB) Viewed 1141 times
## Post #3
- Username: XxYarnRulerxX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 10, 2015 1:50 am
- Post datetime: 2015-11-17T01:01:35+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

The script is a .ms script meant for a game called dynaster warriors 7, but is supposed to import .g1m files.
[http://www.mediafire.com/download/beaau ... /dw7-1.rar](http://www.mediafire.com/download/beaauv2rx7jr0ne/dw7-1.rar)

atm, I'm trying to figure out how to work your mesh extractor. Thank you btw for replying! c:
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-17T12:58:44+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

yeah, it's one of chrrox' scripts.
Add this

```
	vx = ReadBEfloat f
	vy = ReadBEfloat f
	vz = ReadBEfloat f
	tu = 0
	tv = 0
	fseek f (VSizeA[(ElemArr[b].FaceID)] - 12)#seek_cur
)
```

to make it work with Yoru no nai Kuni g1m files if you have 3dsmax.

(The tex coords are at offset 44 of the FVFblock but I'm too lazy to apply this to the script.)
or wait, try this (untested):

```
	vx = ReadBEfloat f
	vy = ReadBEfloat f
	vz = ReadBEfloat f
	fseek f (32)#seek_cur
	tu = ReadBEfloat f
	tv = ReadBEfloat f
	fseek f (VSizeA[(ElemArr[b].FaceID)] - 52)#seek_cur
)
```
## Post #5
- Username: XxYarnRulerxX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 10, 2015 1:50 am
- Post datetime: 2015-11-18T02:53:09+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

Thanks so much!, but the problem is I don't have max, I have blender 2.7. Is it possible to convert the script to work for blender??
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-18T08:28:27+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from XxYarnRulerxX
>
> Is it possible to convert the script to work for blender??It surely is but I prefer using 'C' instead of python. And it's much easier to create a simple concept like searching for the string "G1M" in the concerning files than just converting other authors' work.
(I don't mean it's better because there's nothing better than chrrox' scripts  but it would be easier for me.)

Maybe I can start a small MakeH2O project as soon as I've more spare time.

here's another result (search for g_shadowColor to find the start of the vertices):



PC00F_MODEL_P_M_BodyALL_FR_xScAlphaTest.jpg (192.68 KiB) Viewed 1088 times


H2O file:
0x91320 10658
Vb1
84 44
0x1E34 4918
121000
0x0 255
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2015-11-21T16:28:28+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

Hi
Here is a blend importer for this model .
It requires installed Blender249 and Python 266 (all 32 bits).
How use:
-doubleclick Blender249.blend or copy all files to folder where is blender.exe and doubleclick Blender249.blend
-in Blender Text Window press alt+p and select g1t to unpack images
-press alt+p and select g1m
-PC00F_MODEL.g1m select last (skeleton)

Don't all meshes have vertex with weights.

I don't know if it works with others models.

[http://www.mediafire.com/download/38byl ... -24%5D.zip](http://www.mediafire.com/download/38byl2k25kmv846/Blender249%5BYoruNoNaiKuni%5D%5BPS3%5D%5Bg1m%5D%5Bgz%5D%5Beliksir%5D%5Bg1t%5D%5B2015-11-24%5D.zip)
[screen.jpg](https://xentaxbackup.github.io/file/10046_screen.jpg)
## Post #8
- Username: XxYarnRulerxX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 10, 2015 1:50 am
- Post datetime: 2015-11-22T00:54:09+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

So I tried the blender import script but then I press alt-p, and get the error:

Python script error: Check console.
I checked and it said the problem is the first line: "import newGameLib"

So I installed python 2.6.6 and still got the error. You mentioned 32-bit. I have 64-bit windows. Would that cause error?
## Post #9
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-11-22T02:38:51+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from XxYarnRulerxX
>
> So I tried the blender import script but then I press alt-p, and get the error:

Python script error: Check console.
I checked and it said the problem is the first line: "import newGameLib"

So I installed python 2.6.6 and still got the error. You mentioned 32-bit. I have 64-bit windows. Would that cause error?

Place the gamelib folder in your blender folder.
## Post #10
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2015-11-24T11:20:09+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from Darko
>
> XxYarnRulerxX wrote:So I tried the blender import script but then I press alt-p, and get the error:

Python script error: Check console.
I checked and it said the problem is the first line: "import newGameLib"

So I installed python 2.6.6 and still got the error. You mentioned 32-bit. I have 64-bit windows. Would that cause error?

Place the gamelib folder in your blender folder.
compiled with python version 2.6.2
checking for installed python........................................got it!
...
 file"starter.py",line 1, in <module>
  import newgamelib
  ............._init_.py"
 .................
..............bump_to_normal.py",line 3 ,in <module>
 import PIL
ImportError: no module named PIL
======================================
2.49 2.49b and python 2.52  2.66
show the same
[20151124190557.png](https://xentaxbackup.github.io/file/10065_20151124190557.png)
## Post #11
- Username: dian333
- Rank: beginner
- Number of posts: 36
- Joined date: Tue Sep 16, 2014 6:59 am
- Post datetime: 2015-11-24T11:34:47+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from XxYarnRulerxX
>
> How do I go about extracting the 3d model files from the .g1m files of the game? I've been able to extract the .g1t files pretty easily, but I can't find any tools that work for g1m except a max script, but I don't have max. How do I convert .g1m to obj or another usable format??

http://www.mediafire.com/download/umfj1 ... _MODEL.rar
===============================================
fmt_YoruNoNaiKuni_g1m.py work at noesis ,but noesis crash easily...
[20151124192925.png](https://xentaxbackup.github.io/file/10066_20151124192925.png)
## Post #12
- Username: XxYarnRulerxX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jun 10, 2015 1:50 am
- Post datetime: 2015-11-25T19:43:01+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

@dian333
Oh wow, noesis works fine thank you!!!!
## Post #13
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2016-05-21T08:14:47+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from Szkaradek123
>
> Hi
Here is a blend importer for this model .
It requires installed Blender249 and Python 266 (all 32 bits).

Hello. I write a converter from G1M to FBX. I have problem with index buffers. They look so:


If it is a tri strip then where is the delimiters?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-21T09:37:10+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from destrator
>
> If it is a tri strip then where is the delimiters?be informed that there's tristrip formats which don't use a delimiter (0xFFFF) in face indices blocks.

Looking at PC00F_MODEL_P_M_BodyALL_FR_xScAlphaTest.g1m there's no delimiter - but it's tristripped face indices. (You could easily check it using hex2obj).

You could try to export as fbx from Noesis - didn't check it but should work.

Also it would be helpful if you uploaded the model file in question.

(I always wonder how you guys think anyone could help you out while having nothing as reference but a picture with some numbers, really.  )
## Post #15
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2016-05-21T11:14:15+00:00
- Post Title: Yoru no nai Kuni - .g1m file extraction

> Reply from shakotay2
>
> destrator wrote:If it is a tri strip then where is the delimiters?be informed that there's tristrip formats which don't use a delimiter (0xFFFF) in face indices blocks.

Looking at PC00F_MODEL_P_M_BodyALL_FR_xScAlphaTest.g1m there's no delimiter - but it's tristripped face indices. (You could easily check it using hex2obj).

You could try to export as fbx from Noesis - didn't check it but should work.

Also it would be helpful if you uploaded the model file in question.

(I always wonder how you guys think anyone could help you out while having nothing as reference but a picture with some numbers, really.  )
Thank you, I understand.

It is a tristrip with a set of degenerated triangles. I parsed it:

```
{
	short v0;
	short v1;
	short v2;
};
std::vector<Triangle> triList;

for (int i = 2; i < indices.size(); i++)
{
	  Triangle tri;
	  bool isEven = (i % 2 == 0);

	  tri.v0 = indices[i - 2];
	  tri.v1 = isEven ? indices[i] : indices[i - 1];
	  tri.v2 = isEven ? indices[i - 1] : indices[i];

	  if (tri.v0 != tri.v1 && tri.v1 != tri.v2 && tri.v2 != tri.v0)
		   triList.push_back(tri);
}
```

Right now I have the following:


Part of this waste triangles was placed in to the mesh but it is no problem. They will be excluded by material's based sampling, I think so.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-05-21T12:20:59+00:00
- Post Title: Re: Yoru no nai Kuni - .g1m file extraction

"parsed it"? Looks like autocreating face indices - not reading them from a gmi file (as I thought you did)?

That's the reason why there's no shifting of indices (f1=f2; f2=f3) at the end -
compare here:
[viewtopic.php?f=16&t=12804&p=116369&hil ... te#p116369](http://forum.xentax.com/viewtopic.php?f=16&t=12804&p=116369&hilit=+duplicate#p116369)
## Post #17
- Username: destrator
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Aug 30, 2011 11:25 am
- Post datetime: 2016-05-22T13:46:56+00:00
- Post Title: Re: Yoru no nai Kuni - .g1m file extraction

> Reply from shakotay2
>
> "parsed it"? Looks like autocreating face indices - not reading them from a gmi file (as I thought you did)?

That's the reason why there's no shifting of indices (f1=f2; f2=f3) at the end -
compare here:
viewtopic.php?f=16&t=12804&p=116369&hil ... te#p116369

indices[] is a source array, which readed from G1M file.

Now my function is as follows:

```
{
	for (DWORD i = Start + 2; i < (Start + Count); i++)
	{
		  TRIANGLE triangle;
		  bool isEven = (i % 2 == 0);
	
		  triangle.v0 = indices[i - 2];
		  triangle.v2 = isEven ? indices[i] : indices[i - 1];
		  triangle.v1 = isEven ? indices[i - 1] : indices[i];

		  if (triangle.v0 != triangle.v1 && triangle.v1 != triangle.v2 && triangle.v2 != triangle.v0)
			   triangleList.push_back(triangle);
	}
}
```


And correct, I replaced  CW tri elements by CCW.
