## Post #1
- Username: dee4doa
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 20, 2011 8:02 am
- Post datetime: 2011-06-06T15:10:27+00:00
- Post Title: DOA2 .CHR model format (Dreamcast)

Hello my name is dee4doa, you might know me for making doa and soul calibur mods on youtube, I mainly post my mods on this forum:
[http://dcforums.co.uk/forum/index.php?showtopic=42472](http://dcforums.co.uk/forum/index.php?showtopic=42472)
I need help getting the mesh from these .CHR format files. I have uploaded a .CHR file which is Ayane's 2nd costume here is the link:
[http://www.megaupload.com/?d=13HO2WK0](http://www.megaupload.com/?d=13HO2WK0)
If anyone could have a crack at it, that would be awesome  
I hope we could import our own meshes into DOA2 ^^
## Post #2
- Username: terios
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Aug 14, 2010 10:24 am
- Post datetime: 2022-11-06T20:49:27+00:00
- Post Title: DOA2 .CHR model format (Dreamcast)

[VincentNL](https://github.com/VincentNLOBJ) cracked DOA2's CHR. 

You can import the models into Blender 2.83 LTS or Blender 2.90 with Vincent's NaomiLib add-on found here: [https://github.com/NaomiMod/blender-NaomiLib](https://github.com/NaomiMod/blender-NaomiLib)

DOA2 CHR Format details: [https://github.com/NaomiMod/games-Extra ... rchives.md](https://github.com/NaomiMod/games-ExtractTools/blob/main/DOA2/CHR_archives.md)
QuickBMS Unpacker Script: [https://github.com/NaomiMod/games-Extra ... packer.bms](https://github.com/NaomiMod/games-ExtractTools/blob/main/DOA2/CHR%20Unpacker.bms)
QuickBMS Application Homepage: [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)


DOA2 CHR Format details

```

DOA2 use `.CHR` archives to store model and partial PVR header data. Actual image data is located in the corresponding `.BIN` file.

# Header data

|Address	|Length|	Description|
|---------|------------|---------------|
|0x00	|0x04|	HEADER SIZE|
|0x00	|0x18|	HEADER DATA|
|0x04	|0x04|	TEXTURE POINTERS|
|0x08	|0x04|	MODEL POINTERS|
|0x0C	|0x04|	TOTAL MODELS|
|0x10	|0x04|	TOTAL TEXTURES|
|0x14	|0x04|	PADDING|


# Model pointers

|Address	|Length (hex)|	Description|
|---------|------------|---------------|
|0x00	|0x04|	SPECIFIED OFFSET - BASE ADDRESS `+0x18`|

* Please note base address is always the first model pointer.
i.e.
First pointer value is `0x0000400C` , the real address is calculated:
(`0x0000400C - 0x0000400C`) + `0x18`

# Texture pointers

They refer to a corresponding .BIN file, which is an headerless PVR data archive.
Each texture header is split in 3 chunks 0x4 bytes long each:

|Address	|Length|	Description|
|---------|------------|---------------|
|0x00|	0x04| PVR Image size |
|0x04|	0x04| PVR Pixel type |
|0x08|	0x04| SPECIFIED OFFSET - BASE ADDRESS|

* Please note base address is always the first texture pointer
i.e.
First pointer value is `0x0000400C` , the real address is calculated:
`0x0000400C - 0x0000400C`
```



QuickBMS Script

```
# Dead or Alive 2 (Dreamcast) .CHR Unpacker 
#
# *Script by VincentNL  06/10/2021
#
#
#----------------------------------------------------------------------

# TEXTURES_LOOP

set MEMORY_FILE2 binary ""
set MEMORY_FILE3 binary ""
set MEMORY_FILE4 binary "\x47\x42\x49\x58\x08\x00\x00\x00\x01\x00\x00\x00\x00\x00\x00\x00\x50\x56\x52\x54"    # GBIX+PVR header
set MEMORY_FILE5 binary ""


get name basename
String pvr_container P "%name%.bin"    # 
open fdsE "pvr_container" 1            # Open bin file to get pvr texture data
get binsize asize 1

goto 0x10
get total_tex long   #total textures
goto 0x8
get header_offset long  #where size, pixel data and lenght are stored



xmath base_address "header_offset+0x8"
goto base_address
get base_address long

goto header_offset

Math A = 1



for loop


	 #print  "--------TEXTURE %A%:"
     savepos currentpos
     get tex_size long
     
     #print "tex size: %tex_size|x%"
     

     log MEMORY_FILE2 currentpos 0x4
     math currentpos += 0x4

     
     get pixel_type long
     #print "pixel_type: %pixel_type|x%"
     

     log MEMORY_FILE3 currentpos 0x4
     math currentpos += 0x4

     
     
     get PVR_start long
     Math PVR_start -= base_address
     #print "PVR_start: %PVR_start|x%"
       
	    if A < total_tex
	   
	   
           xmath nextpos "currentpos +0xc"
           #print "next PVR start: %nextpos|x%"
           
           goto nextpos
           get PVR_end long
           
           Math PVR_end -= base_address
           #print "PVR_end: %PVR_end|x%"
           
           Xmath PVR_size "PVR_end-PVR_start"
           #print "PVR_size: %PVR_size|x%"
		   
		   #print  "-----------------"
           math nextpos -= 0x8
           goto nextpos
           math currentpos = nextpos
		   

	    else
		   
		   Xmath PVR_size "binsize-PVR_start"
		   #print "PVR_size: %PVR_size|x%"

		   break

		endif
           
     
	 
	 xMath PVR_size_val "PVR_size+0x8"
	 PutVarChr MEMORY_FILE5 0 PVR_size_val Long
	 
	 append
	 log MEMORY_FILE 0 20 -4
	 log MEMORY_FILE 0 4 -5
	 log MEMORY_FILE 0 4 -3
	 log MEMORY_FILE 0 4 -2
	 log MEMORY_FILE PVR_start PVR_size 1
	 append
	 
	 get tsize asize -1
	 String PVR_NAME P "%name%_tex_%A%.pvr"
	 log PVR_NAME 0 tsize -1
     
     Math A += 1
	 
	 log MEMORY_FILE 0 0
	 log MEMORY_FILE2 0 0
	 log MEMORY_FILE3 0 0
	 log MEMORY_FILE5 0 0
	 

next loop


# MODELS_LOOP


Math B = 1
get name basename

goto 0xc
get total_models long   #total models
goto 0x4
get models_pointers long
goto models_pointers

get base_address long

math model_offset = models_pointers


 for loop2

      String modelname P "%name%_model_%B%.bin"
      goto model_offset
      get model_start long
      xMath model_start "(model_start-base_address)+0x18"
      
        if B < total_models
	    
          get next_offset long
          Xmath model_end "(next_offset-base_address)+0x18"
		  Xmath model_size "model_end-model_start"
		  log modelname model_start model_size
          

		else
		  
		  xmath model_end "models_pointers-0x8"
		  Xmath model_size "model_end-model_start"
		  log modelname model_start model_size
		  
		  break

		  
        endif
		
		
	  Math B += 1
	  Math model_offset += 0x4
	  
 next loop2
```


Blender Batch Import Script

```
#Adapted to work with NaomiLib importer: https://github.com/NaomiMod/blender-NaomiLib

import os
import bpy

path_to_stl = os.path.join('Folder Directory Here', 'Subfolder name here')


file_list = sorted(os.listdir(path_to_stl))


stl_list = [item for item in file_list if item.endswith('.bin')]

for item in stl_list:
   path_to_files = os.path.join(path_to_stl, item)
   bpy.ops.import_scene.naomilib(filepath = path_to_files)
```


Custom Model Imports:



Blender:
