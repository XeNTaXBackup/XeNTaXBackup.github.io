## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-02T13:29:19+00:00
- Post Title: [Help] import .hkx file

Hello everyone.
I'm trying to write maxscript for .hkx skeleton files. It's native Havok .hkx files, I can open them with Havok Content Tool, but there's no option to export it. Need help to understand bone matrix there, any tip or advice will be very helpful.

[c_skeleton.7z](https://xentaxbackup.github.io/file/6750_c_skeleton.7z)
## Post #2
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-02T16:50:44+00:00
- Post Title: [Help] import .hkx file

Edit: The tool below is both for animations and skeletons.

Are you writing a script based on the binary or xml version of the hkx ?

I haven't written a script yet but I was planning to do so based on this tool, which converts havok 2010 binary to xml and then to kf(niftools?) that can be imported to 3ds max
You might want to take a look
[https://github.com/figment/hkxcmd](https://github.com/figment/hkxcmd)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-11-03T18:21:37+00:00
- Post Title: [Help] import .hkx file

> Reply from zaramot
>
> [...]It's native Havok .hkx files, I can open them with Havok Content Tool, but there's no option to export it.If you have 3dsmax it would be useful to do it the reverse way: 
[](http://www.pic-upload.de/view-21226535/HavokToolsLaunchedFrom3dsmax.jpg.html)
This way I created a hkt file (==hkx, when 'Binary' chosen on export) and the corresponding xml.

```
			<hkobject>
				<hkparam name="name">Bip01</hkparam>
				<hkparam name="lockTranslation">false</hkparam>
			</hkobject>
...
...
	<hkobject name="#0154" class="hkxNode" signature="0x58b0eebe">
		<!-- memSizeAndFlags SERIALIZE_IGNORED -->
		<!-- referenceCount SERIALIZE_IGNORED -->
		<hkparam name="attributeGroups" numelements="0"></hkparam>
		<hkparam name="name">Bip01 R Toe0Nub</hkparam>
		<hkparam name="object">null</hkparam>
		<hkparam name="keyFrames" numelements="2">
			(1,000000 0,000000 0,000000 0,000000)(0,000000 1,000000 0,000000 0,000000)(-0,000000 0,000000 1,000000 0,000000)(3,639171 0,000000 0,000000 1,000000)
			(1,000000 0,000000 0,000000 0,000000)(0,000000 1,000000 0,000000 0,000000)(-0,000000 0,000000 1,000000 0,000000)(3,639171 0,000000 0,000000 1,000000)
		</hkparam>

```


For some weird reason hkxcmd.exe from Skyrim Nexus doesn't convert your hkx nor does it PEPE.
(Might be a version's issue cause I have an older (non skyrim) hkx which is being converted.)

Then I realized that it's possible to export to xml in the standalone HavokContentTool, too.
I think you just missed to scroll up in the Format's combo box of the File save to dialogue. 

So this being the bone matrix of c_skeleton.hkx:

```
				(0.000000 102.375999 0.000000)(0.000000 -0.707107 0.000000 0.707106)(1.000000 1.000000 1.000000)
				(0.000000 0.000000 0.000000)(0.499999 0.500000 0.500000 0.500001)(1.000000 1.000000 1.000000)
...
```
It has 83 lines, one for each bone
So this (0.000000 102.375999 0.000000) should be the position
and this (0.000000 -0.707107 0.000000 0.707106) the rotation of   0. Bip01 Pelvis, but that's just a guess.
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-06T10:52:16+00:00
- Post Title: [Help] import .hkx file

Thanks Shakotay2 for the tips, I exported this skeleton to XML like you did and tried those values as possition/rotation, but they didn't fit. I have no clue what to do with them now, hkxcmd.exe works only for files created with havok content tools 2010.02 and earlier, this skeleton was created with 2011.01 version of HCT, that's bad.
## Post #5
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-06T17:47:30+00:00
- Post Title: [Help] import .hkx file

You could try changing the ID version yourself in the file and then run hkxcmd, ir worked for me with another 2010 version (Resident Evil ORC animation files). (replace in offset 40 with this "hk_2010.2.0-r1".)

This code might also be useful as reference:
[https://github.com/figment/hktcnv](https://github.com/figment/hktcnv)

If nothing works, you should start digging into the code and/or contact figment to get the format specifications. One project of mine for the future is support hkx animations for Blender, so I will certainly dig into that code soon.


cheers.
## Post #6
- Username: Bastien
- Rank: advanced
- Number of posts: 70
- Joined date: Sun Apr 15, 2012 8:08 am
- Post datetime: 2013-11-06T17:49:24+00:00
- Post Title: [Help] import .hkx file

edit: Double post
## Post #7
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-11-06T20:44:21+00:00
- Post Title: [Help] import .hkx file

Thanks for the info Bastien, changing ID didn't help, but this tool hktcnv could be useful! I guess, it should convert 2011.1 version into 2010.2, since it converts 2011.3 .hkx files.
## Post #8
- Username: reichelmarcia
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 26, 2023 4:41 pm
- Post datetime: 2023-07-26T08:43:31+00:00
- Post Title: [Help] import .hkx file

With your help, Shakotay2, I was able to export the skeleton to XML and experiment with the suggested settings for position and rotation, but the results were inconclusive. Since hkxcmd.exe is only compatible with files made in HCT 2010.02 or prior (and this skeleton was made in HCT 2011.01), I'm at a loss as to what to do with them.
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-26T17:23:15+00:00
- Post Title: [Help] import .hkx file

I fear you*re digging up a deadly dead thread.  

My last words on "hkx" seem to be here:

> Reply from shakotay2 ↑Tue May 17, 2016 4:09 pm at Tue May 17, 2016 4:09 pm
>
> In the same thread you'll find Snaz (see github link) and wolfin who made significant progress both, afair.

There's also a project from PredatorCZ, Havok 3ds max/Noesis importer/exporter plugins, which should be mentioned here.
