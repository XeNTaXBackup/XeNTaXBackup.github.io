## Post #1
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-02-25T19:24:10+00:00
- Post Title: Initial D Extreme Stage [PS3]

Hi guys, maybe you can help me get 3D models of cars and tracks from the game InitialD Extreme Stage?)
There is some success in extracting archives,
All textures are able to extract from the archives in the DDS format using file ripper 
[](http://www.imagebam.com/image/7c19c2467461890) 

And maybe unpack archives (possible container) using this BMS script:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "AFS"
get DUMMY byte  # it's usually 0 but in some files (MULTSPQ2.AFS) it may be different
get FILES long
savepos INFO_OFF

math NAME_OFF = FILES
math NAME_OFF *= 8
math NAME_OFF += INFO_OFF
goto NAME_OFF
get NAME_OFF long
goto INFO_OFF

for i = 0 < FILES
    get OFFSET long
    get SIZE long

   if NAME_OFF == 0
      set NAME string ""
   else
      savepos INFO_OFF
      goto NAME_OFF
      getdstring NAME 32
      getdstring DUMMY 16
      savepos NAME_OFF
      goto INFO_OFF
   endif

    log NAME OFFSET SIZE
next i
```


I put the game files for the attempts to extract 3d models:
Cars archive: [https://www.dropbox.com/s/xho8nnna9il7ph2/car.afs?dl=0](https://www.dropbox.com/s/xho8nnna9il7ph2/car.afs?dl=0)
This presumably 3d models tuning parts that are not packed: [https://www.dropbox.com/s/1mkq0ot48voom ... P.efo?dl=0](https://www.dropbox.com/s/1mkq0ot48voomkz/BOOST_UP.efo?dl=0)
## Post #2
- Username: Takukun
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Sep 06, 2015 8:40 am
- Post datetime: 2016-10-13T18:39:23+00:00
- Post Title: Initial D Extreme Stage [PS3]

This is cool i have the game but never finished it, too hard for me  Congrats for getting the textures though
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-13T19:58:01+00:00
- Post Title: Initial D Extreme Stage [PS3]

efo-model:



boost_up-efo.jpg (154.75 KiB) Viewed 1475 times
## Post #4
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2016-10-14T20:55:32+00:00
- Post Title: Initial D Extreme Stage [PS3]

It is excellent!
Aluigi is helped with a BMS script to extract the *afs :

```
# script for QuickBMS http://quickbms.aluigi.org

math OFFSET_LIMIT = -1
for i = 0
    savepos TMP
    if TMP == OFFSET_LIMIT
        break
    endif
    get OFFSET long
    if i == 0
        math OFFSET_LIMIT = OFFSET
    endif
    get SIZE long
    get NAME string
    log NAME OFFSET SIZE
next i

```

How to get game resources: Extract *afs archive with QuickBMS Script (one post) or AFSExplorer Tool > Extract from container *efo with QuickBMS Script in this post.

I was able to learn that *efo may contain geometry or dds textures.
For extracting dds textures from texture.efo using X-Ripper.

Maybe someone has the skill to write a generic script for extracting 3d models?
## Post #5
- Username: xxdrifterxx
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 27, 2017 9:21 pm
- Post datetime: 2017-06-27T13:31:19+00:00
- Post Title: Initial D Extreme Stage [PS3]

I find InitialD arcade stage(6) resource file. but filetype is different(xaf)
[https://mega.nz/#!jBR0EAyD!d8XFF5_WTS6T ... d_NoFeIr8I](https://mega.nz/#!jBR0EAyD!d8XFF5_WTS6TJybaOqvkzD5E8e8vEfSdKd_NoFeIr8I)
someone extract this?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-02T11:39:39+00:00
- Post Title: Initial D Extreme Stage [PS3]

offzip didn't reveal senseful data but you can search for "YABX" or "yabukita::Object" in car.xaf, which are present 400 times
There's an uncompressed block at 0x17F000 for example:



Car_xaf_0x17F000.jpg (154.64 KiB) Viewed 1339 times

(sry for cutting his left arm mesh  )

btw: cut/copied that 16 kB block into a separate file, so offset 0x17F000 -> 0x0000
## Post #7
- Username: REDZOEU
- Rank: veteran
- Number of posts: 151
- Joined date: Thu Mar 10, 2011 3:03 pm
- Post datetime: 2017-08-06T18:22:28+00:00
- Post Title: Initial D Extreme Stage [PS3]

I am interested in this. Any workaround to a method for extracting the .xaf file? I tried the game on my pc and it's suprisingly good. Would be great to have the track models too.
## Post #8
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-11-09T09:19:43+00:00
- Post Title: Initial D Extreme Stage [PS3]

Hi guys, I have not been here for a long time, there was a problem with my hardware iMac )) 
I tried to write a script on Noesis, and I have some success, but the script contains a lot of mistakes ...
This script works with InitialD Extreme Stage/ InitialD Arcade Stage 6AA /  InitialD Arcade Stage 7AAX and InitialD Arcade Stage 8 Infinity with *.efo containers that contain meshes and textures.

At the moment the script does not work correctly, it reads not the hex offset in the files but it looks for the content labels
I could not fully understand the structure. * .efo, who knows how to handle hex, I will be glad to any help and advice in search of the necessary displacements and decoding of the structure.

Currently, the script reads only files containing single models (not group models)

```
import noesis
import rapi

def registerNoesisTypes():
    handle = noesis.register("InitialD", ".efo")
    noesis.setHandlerTypeCheck(handle, noepyCheckType)
    noesis.setHandlerLoadModel(handle, noepyLoadModel)
    #noesis.logPopup()
    return 1

NOEPY_HEADER = "YABX"
   
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 4:
      return 0
   if bs.readBytes(4).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1  

 
def noepyLoadModel(data, mdlList):
    ctx = rapi.rpgCreateContext()
    bs = NoeBitStream(data)
    fileName = rapi.getLocalFileName(rapi.getInputName()).rstrip(".efo")
    print("File Name: " + str(fileName))
        
        #Texture Name
    #bs.seek(0x3573, NOESEEK_ABS) 
    #textureNamesize = bs.readUShort()
    #textureName = bs.readBytes(textureNamesize).decode("ASCII").rstrip("\0")
    #rapi.rpgSetName(textureName)
    #print("Texture Name: " + str(textureName))
    rapi.rpgSetName("bodyD16")   # Texture Name FIX IT 
            
    # myString = bs.readBytes(len(data))
    # essd = myString.find(b"\x65\x73\x73\x64")
    # bs.seek(essd - 0x4, NOESEEK_ABS)
    # skipessd = bs.readUInt() 
    # skip = bs.readBytes(essd)
    
    myString1 = bs.readBytes(len(data))
    myIndex1 = myString1.find(b"\x27\x06\x00\x00\x00\x01\x00\x00\x00\x1A\x27\x04")   ##FIX IT
   
    myString2 = bs.readBytes(len(data))
    myIndex2 = myString2.find(b"\x47\x65\x6F\x6D\x30")                                                 ##FIX IT
   
        #Face Counts      
    bs.seek(myIndex1, NOESEEK_ABS)       
    skip = bs.readBytes(23) 
    #bs.seek(9E5, NOESEEK_ABS) 
    FaceCount = bs.readUInt()
    FaceBuffer = bs.readBytes(FaceCount * 2)
    print("Face Counts: " + str(FaceCount))
           
    bs.seek(myIndex2, NOESEEK_ABS)       
    skip = bs.readBytes(24)
    
        #UV Vertex Stride
    VertexStride = bs.readUInt()  
    print("UV Vertex Stride :" + str(VertexStride ))
    bs.seek(myIndex2, NOESEEK_ABS)
    skip = bs.readBytes(8)
    size = bs.readUInt()
    skip = bs.readBytes(size)
    skip = bs.readBytes(10)
    
        #Vertex Counts 
    VertexCount = bs.readUInt()
    print("Vertex Count :" + str(VertexCount))               
    VertexBuffer = bs.readBytes(VertexCount * VertexStride)
    if VertexStride == 12:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 12, 0) ## FIX IT
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 12, 16)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 12, 20)
    elif VertexStride == 16:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 16, 0) ## FIX IT
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 16, 16)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 16, 20)
    elif VertexStride == 20:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 20, 0) ## FIX IT
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 20, 16)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 20, 28) 
    elif VertexStride == 24:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 24, 0) 
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 24, 8)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 24, 16)   
    elif VertexStride == 28:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 28, 0) ## FIX IT
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 28, 24)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 28, 36)         
    elif VertexStride == 32:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 32, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 32, 12)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 32, 24)
    elif VertexStride == 36:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 36, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 36, 16)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 36, 28)
    elif VertexStride == 40:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 40, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 40, 20)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 40, 32)
    elif VertexStride == 44:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 44, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 44, 24) 
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 44, 36)
    elif VertexStride == 56:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 56, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 56, 12)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 56, 24)
    elif VertexStride == 60:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 60, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 60, 16)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 60, 28)
    elif VertexStride == 64:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 64, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 64, 20)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 64, 32)
    elif VertexStride == 68:
        rapi.rpgBindPositionBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 68, 0)
        rapi.rpgBindNormalBufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 68, 24)
        rapi.rpgBindUV1BufferOfs(VertexBuffer, noesis.RPGEODATA_FLOAT, 68, 36)
    else:
        print("This mesh not yet supported")

    rapi.rpgCommitTriangles(FaceBuffer, noesis.RPGEODATA_USHORT, FaceCount, noesis.RPGEO_TRIANGLE_STRIP, 1) #SHORT for word indices
    #rapi.rpgSetOption(noesis.RPGOPT_TRIWINDBACKWARD, 1) #Flip Mesh
    mdl = rapi.rpgConstructModel()                                                          
    mdlList.append(mdl)
    rapi.rpgClearBufferBinds()
    return 1
    
```

 

several primitive models for tests here:
[https://www.dropbox.com/s/geejzobp9m6yw ... 6.zip?dl=0](https://www.dropbox.com/s/geejzobp9m6ywh1/primitivesID6.zip?dl=0)

example structure cube.efo
I was not able to find the offset at the beginning of the file to these blocks, I can not understand where they can be in * .efo (((
## Post #9
- Username: skys215
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 23, 2017 10:58 pm
- Post datetime: 2017-12-23T15:17:28+00:00
- Post Title: Initial D Extreme Stage [PS3]

> Reply from blackracer
>
> Hi guys, I have not been here for a long time, there was a problem with my hardware iMac )) 
I tried to write a script on Noesis, and I have some success, but the script contains a lot of mistakes ...
This script works with InitialD Extreme Stage/ InitialD Arcade Stage 6AA /  InitialD Arcade Stage 7AAX and InitialD Arcade Stage 8 Infinity with *.efo containers that contain meshes and textures.
...

May I ask how to open the .efo file?
Thanks in advance!

Updated:
I know how to use this script now.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-12-24T09:26:57+00:00
- Post Title: Initial D Extreme Stage [PS3]

> Reply from blackracer
>
> I was not able to find the offset at the beginning of the file to these blocks, I can not understand where they can be in * .efo (((you don't need to; just search for 1A 27 04 00 as a signature in the efo file, add 10 bytes to the offset you'll find.
Should result in the start of face block size; tested with cube, wheel_rays_te37 and torus.efo.

edit: well, see, you did it already in your script. So what's "wrong" with that solution?
## Post #11
- Username: skys215
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 23, 2017 10:58 pm
- Post datetime: 2017-12-25T04:50:10+00:00
- Post Title: Initial D Extreme Stage [PS3]

> Reply from shakotay2
>
> blackracer wrote:I was not able to find the offset at the beginning of the file to these blocks, I can not understand where they can be in * .efo (((you don't need to; just search for 1A 27 04 00 as a signature in the efo file, add 10 bytes to the offset you'll find.
Should result in the start of face block size; tested with cube, wheel_rays_te37 and torus.efo.

edit: well, see, you did it already in your script. So what's "wrong" with that solution?

How about .efo file which starts with "YS" not "YABX"?
## Post #12
- Username: zoloat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 25, 2017 3:09 pm
- Post datetime: 2017-12-25T18:32:13+00:00
- Post Title: Initial D Extreme Stage [PS3]

Why not try using TeknoParrot to play Initial D Arcade Stage 6? I think you can use Cheatengine to find game running code. But I'm not an expert, I'm just trying to help. Looking forward to your result.
## Post #13
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-12-26T14:44:20+00:00
- Post Title: Initial D Extreme Stage [PS3]

> Reply from shakotay2
>
> blackracer wrote:I was not able to find the offset at the beginning of the file to these blocks, I can not understand where they can be in * .efo (((you don't need to; just search for 1A 27 04 00 as a signature in the efo file, add 10 bytes to the offset you'll find.
Should result in the start of face block size; tested with cube, wheel_rays_te37 and torus.efo.

edit: well, see, you did it already in your script. So what's "wrong" with that solution?

This data block in files is different (( 
I do not know the universal offset for all *.efo files



> Reply from skys215
>
> 

How about .efo file which starts with "YS" not "YABX"?
Give me a sample file?

> Reply from zoloat
>
> Why not try using TeknoParrot to play Initial D Arcade Stage 6? I think you can use Cheatengine to find game running code. But I'm not an expert, I'm just trying to help. Looking forward to your result.
Thanks, I'll take this into consideration
## Post #14
- Username: skys215
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 23, 2017 10:58 pm
- Post datetime: 2017-12-27T15:31:38+00:00
- Post Title: Initial D Extreme Stage [PS3]

I guess this is the main body of AE86L.
AE86L_Body_genuine_00.efo this is just one of the extracted file for AE86L. 
[https://www.dropbox.com/s/c2o60uko4873e ... 0.efo?dl=0](https://www.dropbox.com/s/c2o60uko4873epj/AE86L_Body_genuine_00.efo?dl=0) 

And there's another file called texture.efo, which I believe it combines all parts into a car.
[https://www.dropbox.com/s/fdkklq9le0nsz ... e.efo?dl=0](https://www.dropbox.com/s/fdkklq9le0nszhm/texture.efo?dl=0)

Both file was under the AE86L folder.
## Post #15
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-12-28T15:07:45+00:00
- Post Title: Initial D Extreme Stage [PS3]

> Reply from skys215
>
> I guess this is the main body of AE86L.
AE86L_Body_genuine_00.efo this is just one of the extracted file for AE86L. 
https://www.dropbox.com/s/c2o60uko4873e ... 0.efo?dl=0 

And there's another file called texture.efo, which I believe it combines all parts into a car.
https://www.dropbox.com/s/fdkklq9le0nsz ... e.efo?dl=0

Both file was under the AE86L folder.

Unfortunately the files with YS header have compression, I already asked for help with from Aluigy but he could not understand the method of file compression.
## Post #16
- Username: skys215
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 23, 2017 10:58 pm
- Post datetime: 2017-12-29T08:28:32+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

> Reply from blackracer
>
> skys215 wrote:I guess this is the main body of AE86L.
AE86L_Body_genuine_00.efo this is just one of the extracted file for AE86L. 
https://www.dropbox.com/s/c2o60uko4873e ... 0.efo?dl=0 

And there's another file called texture.efo, which I believe it combines all parts into a car.
https://www.dropbox.com/s/fdkklq9le0nsz ... e.efo?dl=0

Both file was under the AE86L folder.

Unfortunately the files with YS header have compression, I already asked for help with from Aluigy but he could not understand the method of file compression.

Thanks anyway.
The next thing I want to "crack" is the path of the course. If that is possible, then I can make a course from real life(though it can't be so accurate as reality).
Are you interested?
## Post #17
- Username: zoloat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 25, 2017 3:09 pm
- Post datetime: 2017-12-29T14:44:45+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

> Reply from skys215
>
> blackracer wrote:skys215 wrote:I guess this is the main body of AE86L.
AE86L_Body_genuine_00.efo this is just one of the extracted file for AE86L. 
https://www.dropbox.com/s/c2o60uko4873e ... 0.efo?dl=0 

And there's another file called texture.efo, which I believe it combines all parts into a car.
https://www.dropbox.com/s/fdkklq9le0nsz ... e.efo?dl=0

Both file was under the AE86L folder.

Unfortunately the files with YS header have compression, I already asked for help with from Aluigy but he could not understand the method of file compression.

Thanks anyway.
The next thing I want to "crack" is the path of the course. If that is possible, then I can make a course from real life(though it can't be so accurate as reality).
Are you interested?

I'm also interested in courses. But I'm a tech noob, I know nothing about coding. But if you interested, I want to help as anyway as I can. Such as emulator tests, finance...(I'm not rich, though)
## Post #18
- Username: skys215
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 23, 2017 10:58 pm
- Post datetime: 2018-01-07T15:24:50+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

> Reply from blackracer
>
> Hi guys, I have not been here for a long time, there was a problem with my hardware iMac )) 
I tried to write a script on Noesis, and I have some success, but the script contains a lot of mistakes ...
This script works with InitialD Extreme Stage/ InitialD Arcade Stage 6AA /  InitialD Arcade Stage 7AAX and InitialD Arcade Stage 8 Infinity with *.efo containers that contain meshes and textures.

At the moment the script does not work correctly, it reads not the hex offset in the files but it looks for the content labels
I could not fully understand the structure. * .efo, who knows how to handle hex, I will be glad to any help and advice in search of the necessary displacements and decoding of the structure.

Currently, the script reads only files containing single models (not group models)

several primitive models for tests here:
https://www.dropbox.com/s/geejzobp9m6yw ... 6.zip?dl=0

example structure cube.efo
I was not able to find the offset at the beginning of the file to these blocks, I can not understand where they can be in * .efo (((

I can only open the cube.efo with this script.
The other files in the package which has YABX header is still not openable.
## Post #19
- Username: gmodoza
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 15, 2018 7:21 am
- Post datetime: 2018-04-01T23:40:06+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

Hey if anyone can get me takumi's 3d model and textures (of the character) id be more than happy to pay for it
## Post #20
- Username: blinky5788
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 22, 2018 7:11 pm
- Post datetime: 2018-05-22T11:26:32+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

Hi guys,

I too am after images, not the models but the actual files to convert id6/7/8 to English.

I have done some research on the .xaf file type used in the game (based on ACROBATA_PATCH.xaf (ID8))
(Linux) (i know it's not a linux game nor am i trying to make it one.)

maybe someone can find a use here,

and the strings in the header are :
[https://pastebin.com/fUY6Lq4L](https://pastebin.com/fUY6Lq4L) (too many to list here)

EDIT, found some more interesting things,

there is a Id5 dump on the net (linux game) contains a file called xafMaker.exe, there are dll files with it as well, but each game has newer versions and the exe does not work with those, anyway, extracting the XAF, gives, .abd .abr. and a huge amount of .efo

the dlls also point to some sort of SDK called "Tea SDK" and that's where the yabukita object is referenced from, and all the other references, there is heaps. each file is signed by who compiled it and has a email address, i won't post it here and i won't contact him as i doubt very much he will give me the sdk or any info on it.

here is some infor on the xaf with the program executed:
from initial D5
ACROBATA.xaf
--- xaf volume information [ACROBATA.xaf] ---
 title        : InitialD ArcadeStage 5
 comment      : (c) SEGA CORPORATION, 2008.
 format type  : xaf0
 major version: 1
 minor version: 3
 sector size  :  2048 bytes
 total volumes:     1
 total records:  1159
 total dirs   :    23
 total files  :  1136
 header size  :     112640 bytes (      55 sectors)
 body size    :  389384192 bytes (  190129 sectors)
 total size   :  389496832 bytes (  190184 sectors)
[https://pastebin.com/P8YmQY5M](https://pastebin.com/P8YmQY5M)
## Post #21
- Username: Band
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 07, 2015 10:57 am
- Post datetime: 2019-05-18T01:47:32+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

So, anyone had any success in unpacking/packing textures since the last message? To see ID8 in english, mmm...
## Post #22
- Username: Neitancrost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 29, 2019 7:21 pm
- Post datetime: 2019-05-29T11:34:17+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

I had success on extracting textures and models manually from Arcade Stage 4, with those I've made some Playermodels for Gmod, like this one: [https://steamcommunity.com/sharedfiles/ ... 1694762111](https://steamcommunity.com/sharedfiles/filedetails/?id=1694762111)
To extract the models the way I did, you will need:
-QuickBMS and a .xaf script to decompress .xaf files (you can find both here: [https://aluigi.altervista.org/quickbms.htm](https://aluigi.altervista.org/quickbms.htm)) 
-X-Ripper program to extract textures ([http://www.zeus-software.com/downloads/xripper](http://www.zeus-software.com/downloads/xripper)) 
-3D Model Researcher to get the mesh (I recommend this tutorial to understand the program: [http://lazov.ru/mr/tutorial.php](http://lazov.ru/mr/tutorial.php)) 

.If you extract the xaf file from Arcade Stage 4, it you give you a bunch of files.The useful files are: CHARACTERNAME.efo and CHARACTERNAME_texture.efo(this is the file to use xripper)
.In order to get the mesh, you will need to put these values on Model Researcher: [Vertices(Padding-24)][Faces(Type-short;Format-Tri Strip)]
.What I found is that the vertices content is divided in three blocks: 12 bytes of mesh/12 bytes of a "3D UVMap"/12 bytes of a sphere , and it repeats in the entire file

Hope that helps.
## Post #23
- Username: Undividual
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 09, 2018 7:53 am
- Post datetime: 2019-06-04T21:32:55+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

Neitancrost, thank you for sharing this information with us, however I am a noob when it comes to extracting game models, especially with the hex editor. I was able to get all of the software to work and open the file for the model I wanted, but I can't figure out where the data for the vertices and faces begins. I've viewed a couple of tutorials on this and most say to look for the large buffer or area without any text, and there does seem to be buffers here and there but none large enough for me to tell whether it is separate data or not. The model I am specifically trying to get is FC3S_FBumper_amemya_03.efo found in CARS.xaf.
## Post #24
- Username: Neitancrost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 29, 2019 7:21 pm
- Post datetime: 2019-06-04T23:54:33+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

So, I tried to extract some car models and found that their vertices are sometimes separate by a "desciption", wich is a problem for Model Researcher, so you can have some problems with cars. But I'll give some tips to extract it.(I'll exemplify with FC3S_FBumper_amemya_02)
First, you will need the vertices, that can be found on the "dense" part of the file.
To find what to put in Offset, copy the "coordinate" of the byte that seems to be the byte you want and paste as DEC, after it, check in the text tab if it is a mess, if so, just add 1 to the number you put in offset; and the value to put on Count, just put a value that end at the start of a new "description"
Then, to find the faces, go to the part that have a sequence of _ _ 00 _ _ 00 _ _, and follow the same steps made with vertices. 
You are going to have a lot of faces problems, like messages of face erros because some vertices are "missing", and some other faces are going to be clearly wrong, wich can be fixed in a 3d program, like blender. Good luck with it.



hex2.png (141.27 KiB) Viewed 307 times
## Post #25
- Username: Neitancrost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 29, 2019 7:21 pm
- Post datetime: 2019-08-11T02:24:47+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

Hi everyone, I am trying to extract the content of map files, but they all have YS header. What I found was that IDAS8 has some compressed (YS) files that are the same as IDAS4 uncompressed (YABX) files. So with this is it possible to create a script to extract all YS files?
## Post #26
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2019-12-26T22:54:59+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

hey there,

so i am currently looking at the arcade version of initial d stage zero because of the top secret supra v12. as far as i can tell the efo files are still the same structure compared to the files already posted here from previous games

[http://www.mediafire.com/file/9jvpdxpf0 ... C.rar/file](http://www.mediafire.com/file/9jvpdxpf04g6wq2/JZA80C.rar/file)

i am still learning the hex editing / hex2obj - try and error - so excuse me if my way is confusing or nonsense 

shakotay2 wrote to search for "1a 27 04 00" - what i can see is that this differs from file to file. for example on the jza80_cage_inid_01.efo it is "19 27 04 00"
i am looking for the combination of "27 06" followed by "27 04" adding 15 bytes offset leads me to the face indices hex "DF5"

[https://imgur.com/a/NnzVSwk](https://imgur.com/a/NnzVSwk)

neitancrost wrote the face indices ends with an description but it seems to end a few bytes before that - for the cage i was testing hex "111C" as an end

ignore this if it is totaly wrong but i tried: 111C minus DF5 gives me dec 807 divided by 2 ending up with dec 403 as a face count? which gives me a verex count of 185

i simply copied step 2 from shatokay2 example fvfsize 36 and uv pos 28

just after the description of cage_geom0 adding again 15 bytes, the vertices seems to start at hex "121E"
[https://imgur.com/a/sdKQeb0](https://imgur.com/a/sdKQeb0)

the result seems to be correct - i could only guess that the uv is correct here - since i dont think that there is an interior view or any details 
[https://imgur.com/a/dMnzsJL](https://imgur.com/a/dMnzsJL)

sadly this "method" does only work on files with one object only, tested on cages of a few cars, calipers and so on.

i still strugle on the other parts like the supra body - something went wrong here
[https://imgur.com/a/IndJlIj](https://imgur.com/a/IndJlIj)

would be nice if someone could help me out here

cheers!
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-27T09:42:41+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

I'd use another vertex start address:
.



JZA80C_Body_genuine_00-efo.png (51.5 KiB) Viewed 235 times


The face indices count seems to be 18425 but gives some superfluous faces.
(Maybe look for start/stop of submeshes.)

better:

0x382D 14700
Vb1
28 99
0xC92A 8348
021000
0x0 255
## Post #28
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2020-01-02T22:41:54+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

sooo i'm still trying to get the top secret supra

JZA80C_Body_genuine_00
0x382D	14752
28	99
0xC92A	8348
JZA80C_Muffler_genuine_00
0xDDD	205
28	99
0x10cc	146
JZA80C_NSeat_genuine_00
0xE11	123
38	28
0x1002	44
JZA80C_TailL_genuine_00
0x71A2	885
36	28
0x12D2	560
JZA80C_WHEEL_genuine_18_gold_FL
0x1236	200
36	28
0x2887	150
JZA80C_Window_genuine_00
0x7146	389
28	99
0xFBA	259
JZA80C_Wiper_genuine_00
0xBC4	796
28	99
0x1307	549

[https://imgur.com/a/154In05](https://imgur.com/a/154In05)


for the body i went back from the 18425 indices to ~14752 ... this should be the complete body - found one broken face next to the door - also there is no UV available for 28 - 99

single meshes like the muffler, cage, are pretty easy this way - but i still struggle to locate the submesh start

vertices starts could be at
0xDBC - MODEL_BD_mask6_BD_mask6Shape_Shape0
0xFC9 - MODEL_BD_mask6_BD_mask6Shape_Geom0
0xC92A - MODEL_BD_body1_BD_bodyShape1_Geom0
0x494F1 - MODEL_BD_body1_BD_bodyShape1_Shape0
0x4973E - MODEL_BN_bonpin_bolt_BN_bonpin_boltShape_Shape0
0x4996C - MODEL_BN_bonpin_bolt_BN_bonpin_boltShape_Geom0
0x49A36 - MODEL_MR_body_MR_bodyShape_Shape0
0x49C52 - MODEL_MR_body_MR_bodyShape_Geom0
0x49D22 - MODEL_MR_mirror_MR_mirrorShape_Shape0
0x49F1E - MODEL_MR_mirror_MR_mirrorShape_Geom0
0x49FF0 - MODEL_RF_antenna_RF_antennaShape_Shape1
0x4A211 - MODEL_RF_antenna_RF_antennaShape_Geom1
0x4A2DE - MODEL_BD_body1_BD_bodyShape1_Shape1
0x4A514 - MODEL_BD_body1_BD_bodyShape1_Geom1
0x4A5E1 - MODEL_MR_light_MR_lightShape_Shape0
0x4A900 - MODEL_MR_light_MR_lightShape_Geom0
0x4A991 - MODEL_BD_parting_BD_partingShape_Geom0
0x515E2 - MODEL_BD_parting_BD_partingShape_Shape0
0x519C7 - MODEL_BD_parting_BD_partingShape_Geom0
0x51A8E - MODEL_FB_net_FB_netShape_Shape0
0x51E3A - MODEL_FB_net_FB_netShape_Geom0

many of them seem to contain only a few vertices? badges?
looks like the body also contains a LOD mesh - maybe that is the reason for the broken mesh going on 18425?
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-02T23:56:08+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

> Reply from guki ↑Fri Jan 03, 2020 6:41 am at Fri Jan 03, 2020 6:41 am
>
>  - but i still struggle to locate the submesh startSearch for "_Geom0" as a guideline (for example 10 findings, 3 hits for vertex blocks some bytes behind)
Counts are also easy to track (left part of picture).
The problem is to understand the rules for separating the submeshes (right part):
.



efo - countsAndSM.png (136.99 KiB) Viewed 214 times


(both parts of the pic have no relation; just didn't want to create a second post for the right part)
## Post #30
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2020-01-04T00:08:54+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

thanks again for helping me out here 

i think i found the correct starting points of the submeshes now
starting with 0x382D for the bodymesh, the superfluous faces are part of the backfacing mesh(pointcloud), followed by the hoodpin detail, a tiny broken bit, the mirrors without any issues, again something broken and the mirror object, ending on 0xC821 covering all of your 18425 / 18426 faces

with an offset i found the underbody starting at 0xFC9 and the doorseam at 0x4A991(pointcloud).

[https://imgur.com/a/ym7xvyW](https://imgur.com/a/ym7xvyW)

Bodymesh - mesh looks good - uv doesnt
0x382D	14752
28	99
0xC92A	8348
backfacing mesh? - Pointcloud looks right? FVF Size?
0xAB6B	2437
28	99
0xC92A	855
Hoodpin Badges - correct again
0xBE75	112
28	99
0xC92A	8432
Exhaust Badge? - cant tell what this tiny bit is
0xBF53	8
28	99
0xC92A	8741
Mirror Body mesh - looks right again here
0xBF61	960
28	99
0xC92A	8816
Exhaust Diffusor? - again something broken?
0xC6DF	58
28	99
0xC92A	8826
Mirror Chrome Wiper? - Mirror looks good again - there is also a tiny part in the area of the rear screen wiper - cant tell where the broken face comes from
0xC751	104
28	99
0xC92A	8877
Underbody mesh - pointcloud - cant tell where the face indices start
???
36	28
0xFC9	855~
Doorseam mesh - same here
???
36	28
0x4A991	750~

pretty close to a proper result
## Post #31
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2020-01-07T23:32:18+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

sorry for the double post but i managed to fix the body mesh

the face indices sector starting at ab6b was split into two parts - those parts are using the offset vertices starts + using a different fvf size

first one is the underbody backfacing stuff

0xAB6B	1539
12	99
0xFC9	855
+++++++++++
0xB771	898
36	99
0x4A991	726

second one is the doorseam mesh

[https://imgur.com/a/2myeQpq](https://imgur.com/a/2myeQpq)

yet i cant tell if the mapping is right - but for me the meshes are enough 

maybe someone is able to update blackracers script for noesis to make this a bit easier
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-01-08T15:24:50+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

Until someone updates the script you might use Make_obj-efo as a helper tool for getting some params.
(Not perfect, so don't blame me in case...)
.


 Make_obj-efo.zip
(83.41 KiB) Downloaded 42 times



Problem with JZA80C_Window_genuine_00.efo for example, vertex counts do not match
(Point cloud using the lower count looks ok, though.)

submeshNo FIaddr [blocksize] FIcount
0. 0xe74 [4] 0
1. 0x7146 [3446] 1721 -> vCount= 889, from FIs

 vStart at 0x8776, vCount: 292, FVFsize: 36 )
## Post #33
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2020-01-08T23:30:42+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

Thanks again shakotay 

Uv position seems to be 28, but some parts are not even mapped.

[https://imgur.com/a/e5qkKOJ](https://imgur.com/a/e5qkKOJ)

Still need to do the aftermarket rims but the first car is done. Some errors here and there but looks good overall

They do have some decent bodykits in this game, need to check out the other cars as well
## Post #34
- Username: guki
- Rank: beginner
- Number of posts: 32
- Joined date: Mon Apr 12, 2010 3:55 am
- Post datetime: 2020-01-15T18:49:32+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

[https://mega.nz/#!1j51kIwC!wwxab4f0xeH2 ... wQ_2vhqkvo](https://mega.nz/#!1j51kIwC!wwxab4f0xeH2MaiwuqdXiG3tYV3liQCUdwQ_2vhqkvo)

If anyone is interested, these are the object startpoints of all supra meshes

I may missed a few bytes - for example the body mesh contains two false faces (start of another sub mesh)
## Post #35
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2021-09-25T21:22:13+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

I know I've made a thread for this, but since I think a lot of people are following this one, I'm posting this here.

I wrote a Blender Addons 2.8+ (tested in Blender 2.92.0) to import the models. More details [here](https://github.com/GreenTrafficLight/efo_BlenderAddons).



The characters are all skinned now, except one which is Miki (since he has 4 bone weights, and the bone indices isn't in the right order in the vertex buffer).

[Miki sample (one vertex buffer at offset 0xC64A8, stride 40, last 8 bytes being the bone indices and bone weights) ](https://drive.google.com/file/d/1KNZr1WLeF4kqTNhuB3rhnNRpcX5tTg66/view?usp=sharing)

In order to import the trees, you will need the folder path with the extension .pa8. There are some values in the .pa8 that I skipped (It might not be important though). The file format is like this :

```
int 	Unknown
uint	FileSize
uint	TransformationCount
bytes	zeros[16]

for i = 0 < TransformationCount
	float	Translation[3]
	float	MeshIndex  // the float is always a int, except in Gunsai sometimes
	float	MatrixValue1 // for y rotation ( 3x3 matrix indices [0][2] and [2][0] )
	byte	Unknown[4]
	float	MatrixValue2 // for y rotation ( 3x3 matrix indices [0][0] and [2][2] )
	byte	Unknown[4]
	float	Rotation[3] // In degrees
	float	Scale

```


I'm posting pa8 samples just in case : [https://drive.google.com/file/d/1bhCx-O ... sp=sharing](https://drive.google.com/file/d/1bhCx-OBYfU6mt2qHxfa2dy1fUwxo2SHy/view?usp=sharing)

Also, I admit I'm lazy to set up everything to play the Zero version, but I will be glad if someone could picture a high quality picture of this corner in Gunsai  since the index for one of the tree isn't precise, so I don't know if I'm importing the right one.



(Unrelated, but I can't believe I've been interested in this format since 2018)
[efo_BlenderAddons.zip](https://xentaxbackup.github.io/file/20923_efo_BlenderAddons.zip)
## Post #36
- Username: MrZasen
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 28, 2015 3:48 pm
- Post datetime: 2021-09-30T15:51:09+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

I just installed your addon in my Blender 2.82, but the import result was just a bone when trying to import Akagi, and a couple more bones when importing the S13 headlights, I can't get any meshes...
I saw you gave the folder tree some importance, that's why I haven't modified it.
This is the error I get:

```
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\__init__.py", line 77, in execute
    import_efo.main(self.filepath, self.clear_scene, self.import_textures, self.import_trees, self.import_gallery)
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\import_efo.py", line 545, in main
    build_hierarchy(efo, texture_dir, os.path.splitext(efoName)[0])
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\import_efo.py", line 97, in build_hierarchy
    bpy.ops.object.empty_add(type='PLAIN_AXES', location=dummy.translation, scale=dummy.scale)
  File "C:\Program Files\Blender Foundation\Blender 2.82\2.82\scripts\modules\bpy\ops.py", line 201, in __call__
    ret = op_call(self.idname_py(), None, kw)
TypeError: Converting py args to operator properties: : keyword "scale" unrecognized

location: <unknown location>:-1
```
## Post #37
- Username: GreenTrafficLight
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Apr 26, 2021 6:54 am
- Post datetime: 2021-09-30T17:28:22+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

> Reply from MrZasen ↑Thu Sep 30, 2021 11:51 pm at Thu Sep 30, 2021 11:51 pm
>
> 
I just installed your addon in my Blender 2.82, but the import result was just a bone when trying to import Akagi, and a couple more bones when importing the S13 headlights, I can't get any meshes...
I saw you gave the folder tree some importance, that's why I haven't modified it.
This is the error I get:
Code: Select allTraceback (most recent call last):
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\__init__.py", line 77, in execute
    import_efo.main(self.filepath, self.clear_scene, self.import_textures, self.import_trees, self.import_gallery)
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\import_efo.py", line 545, in main
    build_hierarchy(efo, texture_dir, os.path.splitext(efoName)[0])
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\import_efo.py", line 97, in build_hierarchy
    bpy.ops.object.empty_add(type='PLAIN_AXES', location=dummy.translation, scale=dummy.scale)
  File "C:\Program Files\Blender Foundation\Blender 2.82\2.82\scripts\modules\bpy\ops.py", line 201, in __call__
    ret = op_call(self.idname_py(), None, kw)
TypeError: Converting py args to operator properties: : keyword "scale" unrecognized

location: <unknown location>:-1

I didn't test with Blender earlier versions, only with Blender 2.92. But it seems it was tied to the version, especially Blender 2.8. I made a new release that should fix this.
[efo_BlenderAddons.zip](https://xentaxbackup.github.io/file/20922_efo_BlenderAddons.zip)
## Post #38
- Username: MrZasen
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 28, 2015 3:48 pm
- Post datetime: 2021-09-30T19:28:50+00:00
- Post Title: Re: Initial D Extreme Stage [PS3]

> Reply from GreenTrafficLight ↑Fri Oct 01, 2021 1:28 am at Fri Oct 01, 2021 1:28 am
>
> 
MrZasen wrote: ↑Thu Sep 30, 2021 11:51 pm
I just installed your addon in my Blender 2.82, but the import result was just a bone when trying to import Akagi, and a couple more bones when importing the S13 headlights, I can't get any meshes...
I saw you gave the folder tree some importance, that's why I haven't modified it.
This is the error I get:
Code: Select allTraceback (most recent call last):
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\__init__.py", line 77, in execute
    import_efo.main(self.filepath, self.clear_scene, self.import_textures, self.import_trees, self.import_gallery)
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\import_efo.py", line 545, in main
    build_hierarchy(efo, texture_dir, os.path.splitext(efoName)[0])
  File "C:\Users\Dani\AppData\Roaming\Blender Foundation\Blender\2.82\scripts\addons\efo_BlenderAddons\import_efo.py", line 97, in build_hierarchy
    bpy.ops.object.empty_add(type='PLAIN_AXES', location=dummy.translation, scale=dummy.scale)
  File "C:\Program Files\Blender Foundation\Blender 2.82\2.82\scripts\modules\bpy\ops.py", line 201, in __call__
    ret = op_call(self.idname_py(), None, kw)
TypeError: Converting py args to operator properties: : keyword "scale" unrecognized

location: <unknown location>:-1



I didn't test with Blender earlier versions, only with Blender 2.92. But it seems it was tied to the version, especially Blender 2.8. I made a new release that should fix this.
Fixed, thanks!!
Awesome work man
