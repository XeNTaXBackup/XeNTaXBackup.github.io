## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-07-22T08:08:55+00:00
- Post Title: Iron Man II XBox360/PS3 Manual Extraction Guide

Iron Man II XBox360/PS3 PKG Archive Unpacker & Decompressor Plus Manual Extraction Guide

An experimental BMS scripts pack for unpacking/decompressing .pkg archives from Iron Man II, supporting both XBox360 and PS3 versions.

The unpacker has three different versions with various functions for different demands. Their differences are showed as following:

IronMan2_Unpacker

It's the most simple version among the three which will extract everything into one folder named after the input file name.

IronMan2_Unpacker_SF

As you might see extracting everything to one folder things may look like a mess. This version will extract everything into 
separate folders named after the loop order. This could be very useful when you're trying to unpack those tremendous archives which contain
tens of thousands of files. It actually sorts files by file types so it also can be helpful if you want to handle just textures
or meshes.

IronMan2_Unpacker_Plus

It shares all features with the previous one, additionally it logs every data chunk(i.e. temporary file) to a separate archive with the same name 
as the folder except if the chunk was compressed without a specified unzip size, in which case the file would suffix with "_Deompressed"
and the original directory in the archive no longer makes sense. Just in case it's needed.

In the most ordinary circumstance, I recommend you to use the middle one coz it's not necessary to take notice of temporary file.

Since the script breaks the archive into pieces(skeleton and weights as individual files as well), plus I'm a little bit lazy, currently I have no plan
to write any additional scripts/tools to handle meshes or textures. So if anyone is gonna to make this happen, please be my guest.  

An individual decompressor should help quicken the process:

IronMan2_Decompressor 

It decompresses the archive and updates the original entries/directories, with padding size changed to 0x100, which can be modified at the very
end of this script. And it replaces the original zip size fields by ZERO so the structure of the archive does change at all.

But I will attach a short manual extracting guide instead. See my next post.


 IM2_BMS.zip
(4.76 KiB) Downloaded 32 times


Edit: Automated tools have been released here. You may use this obsolete thread as practice for Hex2Obj.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-07-22T08:45:06+00:00
- Post Title: Iron Man II XBox360/PS3 Manual Extraction Guide

I. Model Extraction
Previews





First and foremost, knowledge of using Hex2Obj is required.

I'll take "DVD_SuitUpIronManMark6.pkg" from PS3 as an example, XBox360 version should be similar. 

After unpacking the archive with "IronMan2_Unpacker_SF.bms" there should be five folders named from "0" to "4". 
In the folder "0" there are files suffixing with "_ib_gpudata", for face indices; and "_vb_gpudata", for vertices/UV data or both. 

Folder "4" contains index files for all other files outside this folder. Here files suffixing with "_vb_gpumaindata" are the actual vertices file and in this case,
 "_vb_gpudata" suffixed files in folder "0" are just UV files. You can take a look at them to obtain a basic understanding of UV data. It shouldn't be too hard to calculate FI & vertices counts, and you don't even need to find their start address because they both are 0x0. Just copy everything into one file(face indices, vertices, UVs if it's separated) and record the needed offsets and counts. 

But of course these info can be found in the header files in the index folder, here the "4" folder.

For PS3 version:

```

_vb_gpumaindata				Vertex coordinate data, no UVs, UVs are in separate file with same basename but suffixs with _vb_gpudata
_ib								Face indices data header
_vb								Vertex data header
---------------------------------------------------------------------------------------------------------------------------------------
_ib_gpudata					Face indices data
_vb_gpudata					Vertex data, could contain UVs(depends upon whether _vb_gpumaindata exist or not)

```

Header file structures

_ib Structure

```
0x20	LONG	Face indices count
0x24	LONG	Vertex count

```

_vb Structure

```
0x40	LONG	Vertex stride size
0x44	LONG	Vertex coordinate data size

0x60	LONG	UVB size
0x64	LONG	UV data size
0x68	LONG	UV data start offset 

```

For XBox 360 version:

```

_ib											Face indices data header
_vb											Vertex data header
---------------------------------------------------------------------------------------------------------------------------------------
_ib_gpudata								Face indices data
_vb_gpudata								Vertex data, contains UVs
```


Header file structures

_ib Structure

```
0x24		LONG	Vertex count  

```

_vb Structure

```
0x1C		LONG	Vertex stride size

0x2C		LONG	UVB size
0x30		LONG	UV data start offset

```


To obtain UVs, just load your mesh with "HF_UV" type selected.

Extra information for Hex2Obj:
BigEndian; VB mode; Vertex data type set to Float(or HF_UV); FVFsize 12, 16, 28; UVB size 4, 12.


II. Textures Extraction
Full size image previews


In this case, textures are stored in folder "1" and "2" with different resolution. Chances are that the one with smaller size could sometimes contain bigger-res textures. Each file inside is a small textures pack containing at least 1 map, usually 2. Texture info stores in suffixal files with _Diffuse/_AmbientOcclusion/_Normal/_LightEmission in folder "4". Their structure is showed bellow:

```
  
0x00  	LONG  		Unknown, always be 0.
0x04  	LONG  		Entry size, 0x1C per entry.
0x08  	LONG  		Size of the entire entry, barring 0xC bytes header.
0x0C  	LONG  		DDS formats, 0x0 for dxt1, 0x3 for dxt5, 0x4 for dxt1 packed ATI1/BC4, 0x6 for DXT5 packed normal map(X360), or dxt5 NormalMap(PS3), 
  	  	  	  	  0x8 for ?
0x10  	LONG  		Image width
0x14  	LONG  		Image height
0x18  	LONG  		MIP maps number
0x1C  	LONG  		Texture data start offset in each texture pack, first entry for SurfaceResident, second for SurfaceStreamed when have two entries.
0x20    LONGLONG		0xFF FF FF FF FF FF FF FF, ending string of this directory.
Pattern repeats if entry number is larger than 1. The last four bytes represent the group amount containing the same map in different resolusion. 

```

I don't know how to handle MIP maps for XBox360 version in Noesis, but this Noesis script should do the trick:

```
def registerNoesisTypes():
    handle = noesis.register("Iron Man II XBox360 Textures", ".i2t")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadRGBA(handle, noepyLoadRGBA)
    return 1
def noepyCheckType(data):
    if len(data) < 8:
		return 0
	return 1
def noepyLoadRGBA(data, texList):
    datasize = len(data)        
    bs = NoeBitStream(data, NOE_BIGENDIAN)
    imgWidth =                   #Set your image width here       
    imgHeight =                  #Set your image height here
    data = bs.readBytes(datasize)      
    #data = rapi.imageUntile360DXT(rapi.swapEndianArray(data, 2), imgWidth, imgHeight, 16)   # XBox360 version needed, change 16 to 8 if format is dxt1
    texFmt = noesis.NOESISTEX_DXT5   # change 5 to 1 if format is dxt1
    texList.append(NoeTexture(rapi.getInputName(), imgWidth, imgHeight, data, texFmt))
    return 1

```
 
Before you use it remember split the texture group to individual file and rename them to .i2t format. Select "Reload Plugins" under "Tools" every time you modify the script. 
Some textures cannot be handled correctly. I guess it might be using a different order of RGB coz Alpha looks OK in Photoshop, or it's in different formats.
## Post #3
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-07-22T10:01:29+00:00
- Post Title: Iron Man II XBox360/PS3 Manual Extraction Guide

Man,this is amazing! i can't belive what someone managed to extract models/textures from this game after so many years! Thanks you so much!!
Btw,can you try to look into Igb files from Wii version of Marvel Ultimate Alliance? (this game is totally different ,but since you have skills in reversing game file formats i would ask you for a help,because no one couldn't help me)
Samples are here: [https://zenhax.com/viewtopic.php?f=7&t=4410](https://zenhax.com/viewtopic.php?f=7&t=4410)
Thanks in advance!
P.S And will these scripts work with 1st game?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-07-22T10:28:23+00:00
- Post Title: Iron Man II XBox360/PS3 Manual Extraction Guide

> Reply from Rutabaga
>
> And will these scripts work with 1st game?
I don't know. Never have looked into that so not sure if they share the same format or not

> Reply from Rutabaga
>
> 
Btw,can you try to look into Igb files from Wii version of Marvel Ultimate Alliance?
Well, I havn't been able to extract meshes successfully from Wii game yet. Things seem to be different there so I'm afraid I can't help too much.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-07-22T18:21:16+00:00
- Post Title: Iron Man II XBox360/PS3 Manual Extraction Guide

> Reply from Bigchillghost
>
> @AceWell Come and take a look if you're interested in it!
you have a lot going on here and too much to take in at one time   
i don't have the game or any of the sample files so there is no way for me to give input. 

> Reply from Bigchillghost
>
> Getting UVs is more complicated. First you save the mesh with "Float" type selected, then save another mesh again with "HF_UV". After that open both .obj files in Notepad and replace the UVs(the "vt ..." block) in the latter result with that in the first one and save it.
i'm a little confused about this here, you shouldn't need to save 2 meshes.
"HF_UV" automatically assumes your vertex data to be "Float" and therefore saves 
the mesh out like that, or maybe i am misunderstanding your process.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-07-24T05:41:49+00:00
- Post Title: Iron Man II XBox360/PS3 Manual Extraction Guide

> Reply from AceWell
>
> i don't have the game or any of the sample files so there is no way for me to give input.
I was waiting for you to say that.  
Here the [textures samples](http://www.datafilehost.com/d/8ac1355a).

Edit: You might need some [.pkg files](http://www.datafilehost.com/d/52170a33) as well to write a script.

> Reply from AceWell
>
> 
you have a lot going on here and too much to take in at one time
For textures info you could see it right above the Noesis script at the second post.

> Reply from AceWell
>
> you shouldn't need to save 2 meshes.
"HF_UV" automatically assumes your vertex data to be "Float" and therefore saves 
the mesh out like that, or maybe i am misunderstanding your process.
Whoops...I've just noticed that. Thanks for the hints.
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2017-09-07T04:30:10+00:00
- Post Title: Iron Man II XBox360/PS3 Manual Extraction Guide

Bug Fixed:
Simplify the entry name code part. Since the second name string table in those large archives do not refer to each entry at all, now the folder is named after the loop order only.
