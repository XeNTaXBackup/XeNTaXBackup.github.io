## Post #1
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-10T19:43:10+00:00
- Post Title: [Xbox] Star Wars: The Clone Wars - data.zwp file

Hello i have some files from Pandemic Studio's 2003 game [Star Wars: The Clone Wars](http://www.gamespot.com/star-wars-the-clone-wars/platform/xbox/) for Xbox.
I am trying to get to the models and textures and hopefully find a way to convert them to a usable format.
I would be grateful if someone can help figure out how to extract the contents. 
Thank You! 

edit
after looking through the Gamecube version of these same files i was able to determine that all of the models and textures are compressed into the data.zwp file in the Xbox version, now we just need to find a way to unpack it. I think the models are already in msh format which is good news since there is already tools that can convert this format to usable ones.

I managed to unpack data.zwp with [offzip](http://aluigi.org/mytoolz.htm#offzip) using this:
offzip.exe -a data.zwp c:\offzip 0x0
All of the files will have a .dat extension but you can open the files in HxD and see which type they really are then change the extension accordingly.  
The best way to unpack the zwp file is to use aluigi's bms script (thank you aluigi!) posted in this thread, this way you'll have the file names and extensions intact.


The model files are msh files which can be viewed or converted in [SWBFViewer](http://sites.google.com/site/swbfmodding/swbf-tools), [MeshTool](http://www.gametoast.com/forums/viewtopic.php?f=64&t=14857) or [Unwrap3d](http://www.unwrap3d.com/u3d/index.aspx)(needs the msh import plugin).

The texture files are xbt files which can be opened in TextureFinder.v21. 
You'll have to shift them 32 pixels over then save as bmp and crop the bottoms off in Photoshop and flip them vertically before saving. The xbt files are just dds textures with custom headers, so if you don't want to mess with TextureFinder you can just remove the first 2 lines(32 bytes total) in the xbt file and insert a real dds header. You can use TextureFinder to quickly identify the width and height and dds type and then insert the right dds header.


xbt custom header info 
First 4 bytes is image width
next 4 bytes is image height
next 4 bytes is unknown
next 4 bytes is dxt type (0C=dxt1, 0E=dxt3)
next 4 bytes is unknown
next 4 bytes is unknown
next 4 bytes is unknown
next 4 bytes is unknown

image dimensions and their hex representation for xbt/dds
16 pixels = 10
32 pixels = 20
64 pixels = 40
128 pixels = 80
256 pixels = 01
512 pixels = 02
1024 pixels = 04
2048 pixels = 08

here is some information i found from converting various xbt files to dds based on their size on disk.
xbt file size - width/height - type
1kb - 32x32 - dxt1
2kb - 32x32 - dxt3

3kb - 64x64 - dxt1
6kb - 64x64 - dxt3

11kb - 128x128 - dxt1
22kb - 128x128 - dxt3

33kb - 512x128 - dxt1
65kb - 1024x128 - dxt1

43kb - 256x256 - dxt1
86kb - 256x256 - dxt3

129kb - 1024x256 - dxt1
257kb - 512x512 - dxt3

171kb - 512x512 - dxt1
342kb - 512x512 - dxt3

513kb - 1024x1024 - dxt1
1025kb - 1024x1024 - dxt3
## Post #2
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-10-11T07:13:17+00:00
- Post Title: [Xbox] Star Wars: The Clone Wars - data.zwp file

Simple zlib compressed files. But I think these are just animation data.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-10-11T22:58:23+00:00
- Post Title: [Xbox] Star Wars: The Clone Wars - data.zwp file

Thank you, did you successfully extract the files from both archives? 
The bin files from what i can see are the only resource files on the disc other than music and sound files, the bin files must contain animations, models, textures and scripts etc.  

here are some more bin samples
*Samples provided on request*

You said the bin file is compressed with "simple zlib" so i must use [offzip](http://aluigi.altervista.org/mytoolz/offzip.zip) to decompress it right?



edit
After looking through the other files again i found one that may also contain some of the game's sources, data.zwp is 116MB and upon inspection in HxD there are references to odf and msh files which look like the same type Pandemic Studio used in Star Wars Battlefront. Please have a look at it also. thanks


[other info]
The sound files (ambient, VO, effects and other streams) will play in Windows Media Player as they are but to play the music files i had to install the [ADCPM Codec](http://www.xbox-scene.com/tools/tools.php?page=driver#newsitemEpFuAlFpEFOmMnryQT).



edit2
*See first post
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-03T08:21:33+00:00
- Post Title: [Xbox] Star Wars: The Clone Wars - data.zwp file

script for quickbms:

```
get DUMMY long
get DUMMY long
get FULL_SIZE long
get FILES long
get OFFSET long
goto OFFSET
for i = 0 < FILES
    get ZERO long
    get NAMESZ byte
    getdstring NAME NAMESZ
    get OFFSET long
    get SIZE long
    get ZSIZE long
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #5
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2011-05-05T22:14:59+00:00
- Post Title: [Xbox] Star Wars: The Clone Wars - data.zwp file

I've looked at the Gamecube version of the game and it doesn't use ZWP archives, however it does show the folder structure for where all the files go. Would that be helpful at all in creating a recompiling script?
## Post #6
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2011-12-21T02:01:49+00:00
- Post Title: [Xbox] Star Wars: The Clone Wars - data.zwp file

The contents of this post was deleted because of possible forum rules violation.
