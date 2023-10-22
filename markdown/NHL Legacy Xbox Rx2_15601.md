## Post #1
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2016-12-13T16:49:23+00:00
- Post Title: NHL Legacy Xbox Rx2

Hello, i'm trying to look for ways to edit rendering textures from Xbox NHL series. It would be great. Here is some .rx2 referee jersey samples. That's way the original files are in Big Endian, i swapped it using 010 Editor and get it recognizable in TextureFinder but textures seems to be swizzled. Is there any methods to unswizzle textures? 



Here is older topic for NHL 12 textures:
[viewtopic.php?f=18&t=7490](http://forum.xentax.com/viewtopic.php?f=18&t=7490)

files:
in attachments
[nhl legacy rx2.zip](https://xentaxbackup.github.io/file/12041_nhl legacy rx2.zip)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-13T17:44:39+00:00
- Post Title: NHL Legacy Xbox Rx2

if you undo that byte swap you did you can open your sample with this Noesis python script  


 tex_NHLLegacy_X360_rx2.zip
(689 Bytes) Downloaded 31 times



this script only works with this sample though, i need to look at more samples
before i can set auto detection of width, height and format if more than one.

mnn linked this post
[viewtopic.php?p=60292#p60292](http://forum.xentax.com/viewtopic.php?p=60292#p60292)
from this post
[viewtopic.php?p=60712#p60712](http://forum.xentax.com/viewtopic.php?p=60712#p60712)

i need to figure out what that all means
## Post #3
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2016-12-13T18:20:08+00:00
- Post Title: NHL Legacy Xbox Rx2

Thank you! It really works! Awesome! Here is some more samples. Jersey textures for example, are packed in texlib.rx2 and it contains font, jerseytexture etc. I'm very thankful if you get this all works for your  noesis plugin.
[https://www.dropbox.com/sh/igdllqlncjqi ... lMTDa?dl=0](https://www.dropbox.com/sh/igdllqlncjqir6h/AAAcygDvQQI0fo4HdsiqlMTDa?dl=0)
## Post #4
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2016-12-15T17:31:44+00:00
- Post Title: NHL Legacy Xbox Rx2

I changed the values of noesis script and opened jerseys texlib.rx2 file and got 1024x2810 sized template. It contains at least seven of mipmaps. Jersey data starts from 0xF1000 and there is also fonts data in file starting from 0x1000. When I convert files to tga or dds from noesis and editing it, is there way to convert it back to original type of data?

Here is changed noesis script and jpeg from Winnipeg jerseytemplate

```

def registerNoesisTypes():
	handle = noesis.register("NHL Legacy (X360)", ".rx2")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadRGBA(handle, noepyLoadRGBA)
	#noesis.logPopup()
	return 1

#check if it's this type based on the data
def noepyCheckType(data):
    bs = NoeBitStream(data)
    Magic = bs.readBytes(7)
    if Magic != b'\x89\x52\x57\x34\x78\x62\x32':
        return 0
    return 1
	
def noepyLoadRGBA(data, texList):
    datasize = len(data) - 0xf1000        
    bs = NoeBitStream(data, NOE_BIGENDIAN)
    #bs.seek(0x0, NOESEEK_ABS)
    imgWidth = 1024 #bs.readInt()            
    imgHeight = 2810#bs.readInt()           
    bs.seek(0xf1000, NOESEEK_ABS)        
    data = bs.readBytes(datasize)      
    data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 8)
    texFmt = noesis.NOESISTEX_DXT1
    texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, texFmt))
    return 1
```

[texlib_1_1_4out.jpg](https://xentaxbackup.github.io/file/12061_texlib_1_1_4out.jpg)
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-15T18:13:55+00:00
- Post Title: NHL Legacy Xbox Rx2

> Reply from Beedy
>
> I changed the values of noesis script and opened jerseys texlib.rx2 file and got 1024x2810 sized template. It contains at least seven of mipmaps. Jersey data starts from 0xF1000 and there is also fonts data in file starting from 0x1000.
yeah the samples with "texlib" in the name have more than 1 texture in it

> Reply from Beedy
>
> When I convert files to tga or dds from noesis and editing it, is there way to convert it back to original type of data?swapping the byte order and injecting the dxt data back is easy, but i have no clue how to re-tile the data.
## Post #6
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2016-12-15T18:47:00+00:00
- Post Title: NHL Legacy Xbox Rx2

> Reply from AceWell
>
> swapping the byte order and injecting the dxt data back is easy, but i have no clue how to re-tile the data.
Yes I tried to do copying all graphic data from extracted dds and placed it to original .rx2 starting from 0xf1000 then opened that new rx2 in noesis and got texture seems like big endian. Then I extracted that file again to dds and copied all graphics data  and placed it again to rx2 starting from 0xf1000. Then I opened again in noesis and got tiled graphic like my first post. 

Could programs Bundler/Unbundler  from Xbox SDK to be useful for re-tiling textures?
## Post #7
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2017-03-13T17:56:41+00:00
- Post Title: NHL Legacy Xbox Rx2

I made updated rx2 plugin for all rx2 textures using this xpr2 noesis plugin: [viewtopic.php?f=18&t=8102](http://forum.xentax.com/viewtopic.php?f=18&t=8102). (this is my first script and it’s not cleanest code but it works ).

Modding textures is possible with this method: (example: jersey_0_0_1_cm.Raster in texlib_0_0_1.rx2)

Use QuickBms to extract .big archive with this bms-script [http://aluigi.altervista.org/bms/fightnight.bms](http://aluigi.altervista.org/bms/fightnight.bms) or this AlphaTwentyThree script: Electronic Arts *.big extractor found in [viewtopic.php?f=13&p=79708#p79708](http://forum.xentax.com/viewtopic.php?f=13&p=79708#p79708)

extract nocacherender.big (includes jersey textures) to your HD. In extracted folder /rendering/jersey founds jersey texlib.rx2 files.

Step 1

Open Noesis with rx2-python plugin
Extract rx2-file to .tga

Use Bundler.exe to convert tga to .xpr ( Bundler.exe found in xbox360 SDK)
Drag rdf-file to Bundler.exe to make .xpr ( make sure that rdf-file and tga-file are in same folder than bundler.exe and source, format, width, height and levels are same as in original file) 

Step 2 (replacing jersey_0_0_1_cm.Raster)

Open created xpr-file and texlib_0_0_1.rx2 in hex-editor:

1. Select all data from offset 0x80C to end in .xpr-file and copy it (selected size is 720896 bytes)

2. Select range 0xf1000 to 0x1a1000 (720896 bytes) in .rx2-file and paste copied data here.

3. Save .rx2-file and test it using noesis that texture is right.

Step 3

Reimport modified rx2-files back to .big archive using quickbms ( tutorial here in section 3: [http://aluigi.altervista.org/papers/quickbms.txt](http://aluigi.altervista.org/papers/quickbms.txt).) 

Reimporting .big files will cause problems. It says that file sizes are changed. Type -y for all ”to skip this file” will continue reimporting but results may be incomplete. (half of texture might be converted but some of mipmaps or jerseyfonts not converted)

Here is in-game view of completely converted Tappara jersey

[http://imgur.com/4MJeM98](http://imgur.com/4MJeM98)

Is there other way to reimport these .big-files? Or way to create new .big file instead of reimporting
[tex_NHLLegacy_X360_rx2.py.zip](https://xentaxbackup.github.io/file/12621_tex_NHLLegacy_X360_rx2.py.zip)
## Post #8
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2017-03-13T18:01:18+00:00
- Post Title: NHL Legacy Xbox Rx2

Here is rdf-file for bundler.exe
[jersey_cm_dxt1.rdf.zip](https://xentaxbackup.github.io/file/12622_jersey_cm_dxt1.rdf.zip)
## Post #9
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2017-03-13T18:27:09+00:00
- Post Title: NHL Legacy Xbox Rx2

Could someone help me this?:

[http://zenhax.com/viewtopic.php?t=3556](http://zenhax.com/viewtopic.php?t=3556)

```
# 2) the input file is ignored, select the same script
# 3) the output folder is the folder containing the files to pack

set OUTPUT_ARCHIVE string "dump.pak"

# init the buffers
log MEMORY_FILE  0 0
log MEMORY_FILE2 0 0

# placeholders
put 0 long MEMORY_FILE  # BASE_OFF
put 0 long MEMORY_FILE  # FILES

for FILES = 0

    # copy&paste code
    scanDir "." NAME SIZE       # get the file from the current folder
    if NAME == ""               # no other files are available so append index
        break
    endif
    open "." NAME
    string NAME << 2            # remove ".\"
    if NAME != OUTPUT_ARCHIVE   # in case the archive already exists
        # end of copy&paste code

        # add information to the index table
        string NAME R \ /
        strlen NAMESZ NAME
        put NAMESZ long MEMORY_FILE
        putdstring NAME NAMESZ MEMORY_FILE
        put SIZE long MEMORY_FILE
        get OFFSET asize MEMORY_FILE2
        put OFFSET long MEMORY_FILE

        # add the file to the archive
        append
        log MEMORY_FILE2 0 SIZE
        append
        math FILES + 1
    endif

next

get BASE_OFF asize MEMORY_FILE
putvarchr MEMORY_FILE 0 BASE_OFF long   # BASE_OFF
putvarchr MEMORY_FILE 4 FILES    long   # FILES

get SIZE asize MEMORY_FILE2
append
log MEMORY_FILE 0 SIZE MEMORY_FILE2
append

get SIZE asize MEMORY_FILE
log OUTPUT_ARCHIVE 0 SIZE MEMORY_FILE
```


this is code to remake archive file with quickbms, but how to fit it to this kind of big archive?: [http://aluigi.altervista.org/bms/fightnight.bms](http://aluigi.altervista.org/bms/fightnight.bms)

Big file sample: [http://s000.tinyupload.com/index.php?fi ... 3140561837](http://s000.tinyupload.com/index.php?file_id=81129495493140561837)
## Post #10
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2018-02-11T12:22:46+00:00
- Post Title: NHL Legacy Xbox Rx2

I wrote a full tutorial for editing Xbox 360 NHL Legacy .rx2-files, compressing to chunklzx and re-importing into .big files. I'm sorry but I haven't permission to share bundler.exe which is needed for converting tga-files to xbox format.

Ps3 texture files are .rpsgl-format, I'm sorry but I have no idea how to convert it.

I hope that this tutorial is helpful to somebody.

Thank you AceWell, aluigi and Experiment5X (Big-file-extractor) for help.

Download here:
[https://app.box.com/s/8ldg6h1fn9wdnp8cxrqnofuuivvjnyb9](https://app.box.com/s/8ldg6h1fn9wdnp8cxrqnofuuivvjnyb9)
## Post #11
- Username: Beedy
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Dec 05, 2016 6:12 pm
- Post datetime: 2019-02-28T22:00:45+00:00
- Post Title: NHL Legacy Xbox Rx2

I made noesis script for rx2 3d models. There are script for stadiums and different one for jerseys, faces and others. Script doesn't support materials yet, Stadium containers have textures and models in same file and I have spent a lot of time how to identify material and texture indices for each meshes but didn't succeed. I think 00 EF 00 04 is shaders files in and 00 02 00 03 is textures . However materials can be added manually in Blender.
There are also script for Skate 3, It's slightly different than NHL.

I updated texture script supporting stadium textures and all rx2 files as well (include Skate 3 and Def jam).


 rx2 scripts.zip
(9.96 KiB) Downloaded 29 times
