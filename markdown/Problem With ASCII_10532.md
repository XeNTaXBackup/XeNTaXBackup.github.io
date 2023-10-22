## Post #1
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-20T20:14:34+00:00
- Post Title: Problem With ASCII

what's the problem here ?
i do like the basic topic


Download Link
[http://www.mediafire.com/?60vbb9nhnk5ttth](http://www.mediafire.com/?60vbb9nhnk5ttth)

```

made-up format

from inc_noesis import *

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format 

modules!
def registerNoesisTypes():
   handle = noesis.register("Bots", ".bsc")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't 

leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = "GXXM0124"

#check if it's this type based on the data
def noepyCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 16:
      return 0
   if bs.readBytes(16).decode("ASCII").rstrip("\0") != NOEPY_HEADER:
      return 0
   return 1       

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)
   rapi.rpgClearBufferBinds()   
   return 1
```


Some Help For BSC Files

From Chrrox

> here is the layout of the bsc files.
>
> meshCount - byte
>
> unkCount - byte
>
> Null -byte
>
> then you read 12 bytes of data * the unkCount +1
>
> so if the number is 1 you read 24 bytes if it is 2 you read 36 bytes
>
> Then you end up at your mesh pieces
>
> for each mesh piece you read
>
> boneName - string
>
> then skip from the start of the bone name 0x42 bytes
>
> then read 2 longs
>
> vertCount - Long
>
> faceCount - long
>
> 
>
> then you read the mesh data
>
> vert Structure 0x2C
>
> 00 - 0C Vertex positions as floats
>
> 0C - 18 normals as floats
>
> 18 - 1C Vertex Color as bytes
>
> 1C - 24 UV's as floats
>
> 24 - 2C Null and not used
>
> 
>
> then read the faces as normal triangle lists. unsigned shorts
>
> 
>
> that is it just repeat this for the mesh count and your done.
>
> 
>
> there should be a global skeleton file somewhere that the mesh pieces attach to.

From Finale00

```
   66 bytes
   int32 numVerts
   int32 numIdx
   24 bytes
   numVerts Vertex
   numIdx indices
}
```
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2013-06-21T05:52:23+00:00
- Post Title: Problem With ASCII

This script is for files with GXXM0124 magic and none the files you provided have this magicid and that's why it can't be decoded as ascii.
## Post #3
- Username: Alsair
- Rank: advanced
- Number of posts: 66
- Joined date: Fri Jun 15, 2012 5:55 pm
- Post datetime: 2013-06-22T20:10:24+00:00
- Post Title: Problem With ASCII

> Reply from deepshit
>
> This script is for files with GXXM0124 magic and none the files you provided have this magicid and that's why it can't be decoded as ascii.

how did u know it is a magic file

isearched about magic files i didn't find anything  what did u meant by it's magic file anyways

look [http://goo.gl/WbC1C](http://goo.gl/WbC1C)
