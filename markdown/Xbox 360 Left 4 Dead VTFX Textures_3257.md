## Post #1
- Username: TheGeneral
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Dec 13, 2008 8:35 am
- Post datetime: 2008-12-19T18:07:15+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

I'm working on doing some texture editing on the Xbox 360 version of Left 4 Dead. I've found out that the textures are using a slightly modified version of valves vtf format as seen here. 

[http://developer.valvesoftware.com/wiki/VTF](http://developer.valvesoftware.com/wiki/VTF)

This is what I've figured out so far.

```
{
  int fileSignature; // 0x56544658
  int version1; // 0x00000360
  int version2; // 0x00000008
  int headerSize; // 00000044
  int unknown;
  short width;
  short height;
  short unknown;
  short unknown;
  short unknown;
  short unknown;
  float reflectivityX;
  float reflectivityY;
  float reflectivityZ;
  float bumpMapScale;
  int imageFormat;
  int unknown;
  int unknown;
  int unknown;
  int headerSize2; // 00000044
}
```


This was enough info to slap a dds header on the image data an be able to view it in an image editing program that supports .dds files  The textures appear to be swizzled though 

ex.



If someone can help me figure out the rest of the header format and how to dewizzle the textures that would be great!

Here's a vtfx texture and an example of it as a dds 

[http://www.sendspace.com/file/xtrrz5](http://www.sendspace.com/file/xtrrz5)

Oh yeah.. the files are in big endian so make sure your byte swap the file before trying to see the image
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2009-02-04T10:43:51+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

The Texture isn't swizzled but in up-side-down order!
Which means the smallest mip map come first and the biggest at the end!
## Post #3
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-11-20T18:58:19+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

Hi, I found that the files provided in the first post is no more available. Can you post it again?
In time, has someone developed a tool to extract the dds file from the vtfx? And the reverse process, to update the vtfx with the dds file?
It seems there is a LZMA data inside the vtfx, but I can't figure out how do extract it too...
Any hint here?
Thanks!

Ps. I want to extract and edit the image in howtoplay01.360.vtf file of Portal Still Alive (the image with xbox controller commands), to translate the commands to another language.
## Post #4
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-12-01T12:51:48+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

I had some progress....

I found that there is a LZMA compressed file inside the VTFX, and with the help of ata4 BspSource source code ([https://github.com/ata4/bspsrc/releases](https://github.com/ata4/bspsrc/releases)), now I finally coud extract it.

This is my vtfx file: [https://drive.google.com/file/d/10DighN ... sp=sharing](https://drive.google.com/file/d/10DighNvp533U9yH3fTvRzqmkWWrBo_1K/view?usp=sharing)

And this is my source code, (in Java, Eclipse), is here: [https://drive.google.com/open?id=1ef9lQ ... 7ThrpHfPse](https://drive.google.com/open?id=1ef9lQVCfeivo-1P-G06XhU7ThrpHfPse)

The extracted data, however, has no header. Looking at the vtfx file, I suppose that it is a image having width: 1.024px and height: 512px.

So, I placed a .dds header (using a hex editor), and got the following image (the .dds file is here [https://drive.google.com/file/d/1YEIBGR ... sp=sharing](https://drive.google.com/file/d/1YEIBGRxYM61-P4h86_oFBRdFw4Y5bd4Q/view?usp=sharing)):



Now I'm stucked in this point. Any ideas here?

Ps. This image must show the xbox controller.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-01T17:11:42+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

this bms script can also decompress your vtfx sample  

```

endian big
idstring "VTFX"
goto 0xc
get LZMA_OFF long
endian little
goto LZMA_OFF
get LZMA long
get SIZE long
get ZSIZE long 
getdstring LZMA_PROP 5
comtype lzma_dynamic LZMA_PROP
savepos OFFSET
get NAME basename
get EXT extension
string NAME + "_decmp."
string NAME + EXT
clog NAME OFFSET ZSIZE SIZE

```


the image is 1024x512 dxt5 big-endian
the header info for this image looks like is in the compressed sample header
at 0x14 - 2bytes - width
at 0x16 - 2bytes - height
this image has mipmaps too, the main one is last in the uncompressed data
need more samples to compare and figure the rest


 howtoplay01.360.dds.zip
converted image, main mip only (63.68 KiB) Downloaded 18 times
## Post #6
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-12-01T17:28:14+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

Thank you, AceWell!
Your bms script is doing the same thing that my source code was supposed to to!! 
And the image you got is just the image I was trying to get!
Can you explain how do you get this .dds file from the data extracted from the vtfx?
Very thanks!

Ps. What I want to do is edit this .dds file, and then put it again in a vtfx file.

Ps2. Do you have a Noesis plugin for vtfx files?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-01T23:07:03+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

> Reply from cfarl
>
> Can you explain how do you get this .dds file from the data extracted from the vtfx?
sure   
dxt5 data size = width x height  
the largets mip is stored last in the data, so go to end of the uncompressed file and count back the size you just calculated to get to the start of the main mip. 
now place cursor and hold shift and page down and select all the way to the end.
copy this data to new file, swap endianess and add dxt5 header and voila you're done!  

> Reply from cfarl
>
> Ps. What I want to do is edit this .dds file, and then put it again in a vtfx file.
don't forget the mipmaps too, i don't know why an image like this has them but it does.
modding is not my area so i can't help much with that.   

> Reply from cfarl
>
> Ps2. Do you have a Noesis plugin for vtfx files?
no i don't, need more than one sample before making a script, if just need one image quicker to do it by hand. 


here is a bms script to swap endianess for when you get to that step  

```

get NAME basename
get EXT extension
string NAME + _byteswapped.
string NAME + EXT
get SIZE asize
encryption swap 2
log NAME 0x0 SIZE
```
## Post #8
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-12-02T02:21:36+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

Thanks again!
I did what you said:
- Used the bms script to extract the lzma file
- Got the dds data from the end of the extracted file
- Swap the endiannes from the dds data
- put a dds header in the dds data
And then I got the same .dds file as you!
I tried edit this .dds and do the reverse process, but it shows a bugged image in xbox.
The dds file is compacted, right? 
I tried just open your .dds file and save as a new .dds file in Xnview, but it generates different file... The header of the dds file is not the same! I tried with gimp, having the same results...
Do you have any editor that mantains the .dds with the same header, when editing it?
Thanks in advance!

Ps. Not only the header is diferent, the data too. I will check the process again, as the vtfx header.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-02T15:14:12+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

i can't really help with the modding stuff, but i'm sure you need to maintain 
the same image format, size, mipmaps etc when reusing original headers.
you also need to byte swap back to big-endian after saving your edited image.
maybe use Noesis instead of XnView to maintain data consistency.
## Post #10
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-12-03T15:55:53+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

Acewell, 

Thanks again for your help, I was doing some tests here...

Your script to extract the lzma data from the vtfx (following down), can be used to reimport the data to the vtfx?

```

endian big
idstring "VTFX"
goto 0xc
get LZMA_OFF long
endian little
goto LZMA_OFF
get LZMA long
get SIZE long
get ZSIZE long 
getdstring LZMA_PROP 5
comtype lzma_dynamic LZMA_PROP
savepos OFFSET
get NAME basename
get EXT extension
string NAME + "_decmp."
string NAME + EXT
clog NAME OFFSET ZSIZE SIZE
```


This is the output of the reimport process, when I try to import the same extracted data:

```
--------------------------------------

Error: file "howtoplay01.360_ext"
       the reimport option acts as a reimporter and so you cannot reinsert a
       file if it's bigger than the original otherwise it will overwrite the
       rest of the archive or cannot be loaded correctly:

         new size: 95818 (699088 uncompressed)
         old size: 94227 (699088 uncompressed)

- do you want to skip this file? (y/N/force)
  y will continue with the next file
  N (default) will terminate QuickBMS
  force will force the reimporting of the file
```


The new lzma data looks to be bigger that the original vtfx data... 

It was not supposed to have the same size, or the same script cannot be used to reimport the lzma data to the vtfx file?

Thanks!
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-03T16:56:56+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

> Reply from cfarl
>
> Your script to extract the lzma data from the vtfx, can be used to reimport the data to the vtfx?
no because the compressed size is different
## Post #12
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-12-03T19:00:13+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

OK, we are having some progress here!

As quickbms import to generate the lzma file from the script is not reliable, I used my source code to compress the extracted file to lzma. And now it worked!   

This is the vtfx running in my xbox game:



Now I had another problem, as can be seen in the image. My edited file is in portuguese, but you can see some english text in the background.

This is happening because I updated only the last dds? The other miniframes remained in english.

If yes, how can I extract the other miniframes? How many are in the extracted file? There is some type of header in the extracted file?

Thanks!

Ps. Find a solution! I put all bytes as zero before the dds image, and now it is working as desired! No more english shadow in background!

Good, good job, Acewell! Thanks a lot!
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-12-03T20:01:53+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

> Reply from cfarl
>
> Ps. Find a solution! I put all bytes as zero before the dds image, and now it is working as desired! No more english shadow in background!
great! nice simple solution to the mipmap thing good job!
## Post #14
- Username: cfarl
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Nov 21, 2017 2:49 am
- Post datetime: 2017-12-04T13:30:04+00:00
- Post Title: Xbox 360: Left 4 Dead VTFX Textures

Just to help other people, here is my bms script to extract the dds file from the vtfx:

```

endian big
idstring "VTFX"

# ------------------------------------------------------------
# Step 1. Extract lzma data from the vtfx file
# ------------------------------------------------------------
# Get header size from vtfx file. 
# The lzma data begins after the header.
goto 0xc
get LZMA_OFF long
print "=>lzma data starts at %LZMA_OFF|x%"

# Get the width and height of the dds file that is inside the vtfx
goto 0x14
get IMG_WIDTH short
get IMG_HEIGHT short
print "=>dds file width: %IMG_WIDTH% dds file height: %IMG_HEIGHT%"


# Go to lzma data to read size of the uncompressed file and lzma size
goto LZMA_OFF
endian little
getdstring LZMA 4
get SIZE long
get ZSIZE long 
print "=>lzma header id: %LZMA% uncompressed file size: %SIZE% compressed data size: %ZSIZE%"

# Get properties of lzma uncompress
getdstring LZMA_PROP 5

# The lzma uncompressed file has .textures extension
get NAME basename
string NAME + ".textures"

# Extract the lzma data to the uncompressed file
comtype lzma_dynamic LZMA_PROP
savepos OFFSET
clog NAME OFFSET ZSIZE SIZE

# ------------------------------------------------------------------
# Step 2. Extract the dds data from the end of the .textures file
# ------------------------------------------------------------------
# Open the lzma uncompressed file
Open . NAME 1
get SIZE_TEXTURES_FILE asize  1


# The start of the dds data begins at file size - image size
XMath IMG_SIZE "(IMG_WIDTH * IMG_HEIGHT)"
XMath OFFSET_IMG "(SIZE_TEXTURES_FILE - IMG_SIZE)"
print "=> uncompressed file size: %SIZE_TEXTURES_FILE%  start of last texture: %OFFSET_IMG%"

# Extract the dds data to the .texture file
get NAME basename
string NAME + ".texture"
log NAME OFFSET_IMG IMG_SIZE 1

# ------------------------------------------------------------------
# Step 3. Invert the dds data from .textures file
# ------------------------------------------------------------------
# Open the .texture file
Open . NAME 2

# Invert each pair of bytes of the .texture file
xmath NUM_SHORTS "IMG_SIZE / 2"
for i = 0 < NUM_SHORTS
   encryption swap 2
next i


# Write the .texture file with swapped bytes 
get NAME basename
string NAME + "_swp.texture"
log NAME 0x0 IMG_SIZE 2

# ------------------------------------------------------------------
# Step 4. Insert a dds header in the swapped .textures file
# ------------------------------------------------------------------
# Open the swapped .texture file
Open . NAME 3

# Define a dds header to the texture file
encryption "" ""
set MEMORY_FILE binary "\x44\x44\x53\x20\x7c\x00\x00\x00\x07\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x02\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"
putVarChr MEMORY_FILE 0xc IMG_HEIGHT short
putVarChr MEMORY_FILE 0x10 IMG_WIDTH short

# Write the dds header to the .dds output file
string NAME += ".dds" 
get SIZE asize MEMORY_FILE
append
log NAME 0 SIZE MEMORY_FILE

# Write the swapped .texture data to the .dds file
log NAME 0 IMG_SIZE 3

```
