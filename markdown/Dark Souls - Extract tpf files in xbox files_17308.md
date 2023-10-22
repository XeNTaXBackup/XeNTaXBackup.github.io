## Post #1
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-11-20T19:42:12+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

Hi.
I'm wanting extract the content of .tpf files from Dark Souls in xbox, to translate messages as "You Died" to another language.
I tried BinderTool, but it seems to work only with PC .tpf pc files.
Any hint here?
Thanks in advance,
cfarl
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-21T00:12:10+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

[viewtopic.php?p=64858#p64858](http://forum.xentax.com/viewtopic.php?p=64858#p64858)

some X360 samples would be a good start, 
but if you want to translate i'm guess you have to reswizzle them before repacking, i don't know this.  
i guess you could use Bundler.exe to create xpr file and copy the data back to dds file or something.  

edit
ah yes here is some instruction for reswizzle texture  

> Use Bundler.exe to convert tga to .xpr ( Bundler.exe found in xbox360 SDK)
>
> Drag rdf-file to Bundler.exe to make .xpr ( make sure that rdf-file and tga-file are in same folder than bundler.exe and source, format, width, height and levels are same as in original file)
[viewtopic.php?p=128596#p128596](http://forum.xentax.com/viewtopic.php?p=128596#p128596)

example of rdf file is here
[viewtopic.php?p=128597#p128597](http://forum.xentax.com/viewtopic.php?p=128597#p128597)
and another here
[viewtopic.php?p=74989#p74989](http://forum.xentax.com/viewtopic.php?p=74989#p74989)
## Post #3
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-11-21T14:03:37+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

Very thanks for your help, Acewell! 

I used your hint: got Noesis program ([http://www.richwhitehouse.com/index.php ... sv4295.zip](http://www.richwhitehouse.com/index.php?content=inc_projects.php&filemirror=noesisv4295.zip)), and using chrrox plugin ([download/file.php?id=4965](http://forum.xentax.com/download/file.php?id=4965)), I could see the textures with "You Died" and areas names (they are in menu_local.tpf file).

Then, using the export option, I could also extract the textures in .dds format (and also in .png, .jpg).





Now, after editing the .dds file, how can I put it back in a tpf file?

Edit: Here is my xbox .tpf file: [https://drive.google.com/open?id=1c4R6r ... PVMUXlbwHu](https://drive.google.com/open?id=1c4R6rCH7TkVIOoc8S9GNRTPVMUXlbwHu)

Edit2: In time, someone knows what is the .tpf file format?
## Post #4
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-11-21T18:05:04+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

Edit3. I found the following data in my .tpf:



In this case, the .tpf file have 4 texture files inside (magenta data). 
The orange data is the more interesting: the offset to the texture file data (in this case, the data is a .dds file with no header). 
The green data is the number of bytes of the .dds data inside the .tpf file. 
The red data says that it is a DXT5 .dds file
The blue data says that the 1º, 2º and 3º files have 1024 x 1024 bytes (or 0x0400 x 0x0400 size). The 4º file has 1024 x 256  bytes (or 0x0400 x 0x0100 size).
The pink data is the offset to the file name. It is a string ending with 00.
The gray and black data are zeros

So, the data of the first .dds starts at offsetc c0 (as marked in orange for the first file).
Is my analysis correct? 

This is the first .dds, extracted from Noesis:



As you can see, this is the data that appears inside the .tpf file, but without the .dds header. 
Also, each pair of bytes of the .dds file are inverted in the .tpf file (2b fe, 06 fe in the dds, fe 2b, fe 06 in the tpf)

So, I think that, using the file offsets in the .tpf file, and reversing the bytes of the modified .dds file, this new .dds can be in the place of the original .dds inside the .tpf file.
Right?
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-22T01:40:31+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

here is bms script can be used to reimport  

```
#Dark Souls X360 reimport to tpf script

endian big
idstring "TPF\0"
get TOTAL_DATA_SIZE long
get FILES long
get UNK long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get FORMAT long
    get WIDTH short
    get HEIGHT short
    get ZERO long
    get NAME_OFF long
    get ZERO2 long
    savepos TMP
    goto NAME_OFF 
    get NAME string
    log NAME OFFSET SIZE
    goto TMP
next i

```

before you reimport you need to swap data to big-endian and re-tile image data, i guess bundler.exe can do both, though not sure.
then you remove extension and header before image data, then you can reimport and test out ingame.  

edit
also keep in mind the name of the first exported file is named wrong, it should be "Menu14" and not "menu_localout",
i don't know why Noesis names the first exported file by the archive name instead of name assigned by script.
## Post #6
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-11-22T02:20:48+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

Thanks for your bms script, Acewell! 
It works as desired to extract the something-like-dds files from the .tpf file. 
After reading this script I saw that my analysis in the tpf fields was correct.
Now, my problem is with this untile and re-tile....
Looking at what the python script does in Noesis, after getting the dds file data, I found this:

```
data = rapi.imageUntile360DXT(rapi.swapEndianArray(Tpfdata, 2), WIDTH, HEIGHT, 16)
```

As you said, this code is doing the swap data trick (swapEndianArray) and also is doing the untile.... The problem is I could not found the imageUntile360DXT code to get how this untile is done....
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-22T08:37:19+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

no don't use the bms script to extract, use only for reimport edited image data.
if you extract with the bms script the image data is still big-endian and tiled. 
and like i posted already you probably need to use bundler.exe to re-tile the image.
## Post #8
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-11-22T16:10:47+00:00
- Post Title: Dark Souls - Extract tpf files in xbox files

Thanks again, Acewell!

I got the Bundler.exe from Xbox SDK, as suggested, and made some tests.
First, I found that it don't work with .dds files. So, I converted my texture file do .tga.
Then, I made a .rdf file for each .tga file, a exemple here:

```
<RDF Version="XPR2">
<Texture
   Name   = "Menu14"
   Source = "Menu14.tga"
   Format = "D3DFMT_DXT5"
   Width  = "1024"
   Height = "1024"
   Levels = "0"
/>
</RDF>
```

Using this .rdf file, and Bundler.exe, the .tga file was converted to .xpr file.

Then, I used you bms script, extracted the texture files from the original .tpf. From those, I opened the Menu14 file in hexa editor. 
I opened my Menu14.xpr file in hexa editor, selected the data in this file (ignoring the xpr header), copied and pasted it in the extracted Menu14 file.

Then, I used your bms script again, to reimport the extracted files to my .tpf (including the modified Menu14)
When I opened the .tpf in Noesis.... Voilá! The translated image appeared!



Very, very thanks!     

I still have to test this .tpf file in my xbox, as soon I do this, I will report the result here.

Edit. Confirmed. It works in xbox.
