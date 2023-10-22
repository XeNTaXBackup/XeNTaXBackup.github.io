## Post #1
- Username: Cerophono
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 19, 2014 7:42 am
- Post datetime: 2016-07-06T14:40:39+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

The .apak file is the file yielded after extracting it from the .cpk. I've been told it's a container for a model and its textures.
Each file has distinct sections, and some sections are more or less aligned when viewed under an at-glance, to my understanding meaning they aren't compressed.

TextureFinder doesn't reveal any raw textures, neither bitmap or DTX.

For my needs, a repackable QuickBMS script and a Noesis script (if the extracted work is not viewable in Maya or etc.) would be nice.

Sample: [http://www64.zippyshare.com/v/VXiULdtV/file.html](http://www64.zippyshare.com/v/VXiULdtV/file.html)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-07T03:41:42+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

i made a bms script to extract the files from your apak archive samples   
it works on the extracted pspk archive too

```
idstring "APAK"
get DUMMY long
get FILES long
get DUMMY longlong
get DUMMY longlong
for i = 0 < FILES
    get OFFSET long
    get DUMMY long
    get SIZE long
    get DUMMY longlong
    get DUMMY longlong
    getdstring NAME 0x20
    get DUMMY long
    log NAME OFFSET SIZE
next i
```


the bfres file extracted from model.apak looks like it could be a model
i think i see vertex blocks and face indices in there
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-07T05:12:47+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

model-apak-pc000_00-bfres.jpg (171.69 KiB) Viewed 492 times



first submesh:

0x6B40 1392
Vb1
32 99
0x1AC40 288
120000
0x0 255

uvs possibly at 1D044, size 8, WordUV
## Post #4
- Username: Cerophono
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 19, 2014 7:42 am
- Post datetime: 2016-07-07T12:10:40+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

> Reply from AceWell
>
> 
the bfres file extracted from model.apak looks like it could be a model
i think i see vertex blocks and face indices in there

The .bfres format is itself a container for graphics. It's documented for its use in Mario Kart 8, but I don't think a full map of the format has been done yet.
Typical tools to extract .bfres files don't seem to work properly for these .bfres, however.

[http://mk8.tockdom.com/wiki/BFRES_(File_Format)](http://mk8.tockdom.com/wiki/BFRES_%28File_Format%29)
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-07-07T17:27:44+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

Hi
Can someone send female samples with textures ?
[screen.jpg](https://xentaxbackup.github.io/file/11260_screen.jpg)
## Post #6
- Username: Cerophono
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 19, 2014 7:42 am
- Post datetime: 2016-07-07T18:49:10+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

> Reply from Szkaradek123
>
> Hi
Can someone send female samples with textures ?

Sure. This time, I'll give the 00 outfit of pc001, and the 01 outfit of pc001. Be sure to take pics 

The difference is the 01 outfit model.apak is 8 MB, while the 00 outfit was only 768 KB.
I'm assuming the 01 outfit actually has usable clothing meshes.

I'm pretty sure the textures are in the .apaks, just they are probably compressed by some nintendo algorithm or something.

Download: [http://www79.zippyshare.com/v/k6mgNDi1/file.html](http://www79.zippyshare.com/v/k6mgNDi1/file.html)

Also, does model_common.apak contain any useful data?
Edit: It seems to contain lua script and animation files for the characters.
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-07-09T08:39:58+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

Hi

Here is a blend file for importing rigged models from samples in this topic and samples from [http://zenhax.com/viewtopic.php?t=1225](http://zenhax.com/viewtopic.php?t=1225). 
How use:
1. install Blender version 249b and Python version 26
2. doubleclick file "Blender249.blend" 
3. press alt+p in Blender Text Window and select *.bfres files to import meshes or *.apak files to unpack archive

Fot textures use BFRESExtractor.exe (google) and "Wii U ripping tools pack" (google too)
[Blender249[TokyoMirageSessions][Wii][apak][bfres][2016-07-09].7z](https://xentaxbackup.github.io/file/11270_Blender249[TokyoMirageSessions][Wii][apak][bfres][2016-07-09].7z)
## Post #8
- Username: Cerophono
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Dec 19, 2014 7:42 am
- Post datetime: 2016-07-09T20:22:24+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

> Reply from Szkaradek123
>
> 

Fot textures use BFRESExtractor.exe (google) and "Wii U ripping tools pack" (google too)
Are you sure these work? They yield files named _dummy and when converted from .gtx to .dds, yield a black 256x256 texture.

It's only a hunch, but I don't think these follow typical BFRES usage.
Edit: Hold on, it might because 00 is totally just the dummy file.
Edit: Just me being dumb. Thanks for your work!
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2016-07-09T20:45:51+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

get bfres with size > 1 MB, drag and drop on BFRESExtractor.exe
move all new files (with ext gtx and without ext) to folder "Convert" from Wii U ripping tools pack and run convertGTX.bat
## Post #10
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2016-07-10T19:47:33+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

will it be possible to import .anm files
## Post #11
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2016-08-10T05:54:08+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

How were you guys able to extract the .cpk files to get the apak files? Can't find working tools or scripts for it.

Edit: I did find some tools on zenhax that could extract the cpk files but none of the apak files work with Szkaradek123's tools.
## Post #12
- Username: SCArkadia
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 24, 2021 7:50 am
- Post datetime: 2021-05-25T09:25:32+00:00
- Post Title: Tokyo Mirage Sessions / Genei Ibun Roku .apak

Hey there, I can't seem to extract APAK Files from model.apk or model_common.apak which is found in Enemy folder.

I wish to extract all enemies and mirage model and their animation so I can port it.
