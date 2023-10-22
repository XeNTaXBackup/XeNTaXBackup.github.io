## Post #1
- Username: kovalevich007
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Nov 12, 2010 11:03 pm
- Post datetime: 2015-11-05T16:29:28+00:00
- Post Title: God of War Origins Collection [PS3]

Hi. I researched the format and do not know how to fix the problem.


Here's the problem:


```
import noesis
import rapi

def registerNoesisTypes():
   handle = noesis.register("God of War Origins Collection", ".bin")
   noesis.setHandlerTypeCheck(handle, noepyCheckType)
   noesis.setHandlerLoadModel(handle, noepyLoadModel) #see also noepyLoadModelRPG
      #noesis.setHandlerWriteModel(handle, noepyWriteModel)
      #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   #noesis.logPopup()
      #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

NOEPY_HEADER = ""

#check if it's this type based on the data
def noepyCheckType(data):

   return 1

#load the model
def noepyLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   #rapi.rpgSetOption(noesis.TRIWINDBACKWARD, 1)
   bs = NoeBitStream(data)
   bs.setEndian(NOE_LITTLEENDIAN)
   rapi.rpgSetOption(noesis.RPGOPT_BIGENDIAN, 1)


   VtxBytes = 68
   VtxCount = (2893,)
   VtxOffset = (0x667D0,)

   for i in range(0, 1):
      bs.seek(VtxOffset[i], NOESEEK_ABS)
      VtxBuff = bs.readBytes(VtxCount[i] * VtxBytes)
      rapi.rpgBindPositionBufferOfs(VtxBuff, noesis.RPGEODATA_FLOAT, VtxBytes, 24)
      rapi.rpgBindNormalBufferOfs(VtxBuff, noesis.RPGEODATA_FLOAT, VtxBytes, 12)
      UVBuff = rapi.rpgBindUV1BufferOfs(VtxBuff, noesis.RPGEODATA_FLOAT, VtxBytes, 0)
      rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VtxCount[i], noesis.RPGEO_TRIANGLE_STRIP, 1)

   mdl = rapi.rpgConstructModel()
   #mdl.setBones(Skeleton)
   mdlList.append(mdl)
   rapi.rpgClearBufferBinds()
   return 1
```


This script works only with automaton.bin



I do not know how to read several different vertex block

Samples: [https://yadi.sk/d/qCKilbT2kFiui](https://yadi.sk/d/qCKilbT2kFiui)
Thanks
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-11-10T01:53:30+00:00
- Post Title: God of War Origins Collection [PS3]

I was looking through the inc_noesis.py and on line 956 it is said this that might help

> #all vertex types (positions, normals, uv's, etc) are expected to match in count, as they all share a single triangle list.
>
> #it's recommended that you use the rapi.rpg interface if you want a convenient means to convert different data/primitive types into a NoeModel with NoeMeshes.

I'm not a programmer and you seem to know what you're doing so you'll probably understand that better than i do.

I hope someone helps this guy because i'm trying to make a generic model import plugin where i can transfer inputs from Hex2obj for scanning a whole model file for all submeshes and displaying it in the viewer, and i would also like to know an expert answer about what he is asking because i think i'm going to need the same thing.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-10T07:20:55+00:00
- Post Title: God of War Origins Collection [PS3]

> Reply from AceWell
>
> and i would also like to know an expert answeryeah, that's what we all are looking for  

Meanwhile my advice would go as this: first of all he should try to find the vertice start addresses of all submeshes automatically via a magic table or something else, dunno.

Then it would be rather easy to decide whether the FVF size is 68, 64 whatever by the pattern xx xx xx FF. Means look for FF then check for three identical bytes before it and calculate the offset to the next finding (I wouldn't do this using python, of course.  ).



end-of-submesh.JPG (152.71 KiB) Viewed 261 times



(Sometimes the vertex stride size can be identified by a characteristic byte (type byte) - but where to find in a 2 MB file?)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-10T22:21:23+00:00
- Post Title: God of War Origins Collection [PS3]

guess you need to be a coder to understand what I mean?

Anyway, here's the result for automation.bin:
initial start: 0x667D0

FVFsize: 68, 2893 vertices; next SM1 at 96884
FVFsize: 64, 729 vertices; next SM2 at a1ec8
FVFsize: 68, 2260 vertices; next SM3 at c7714
FVFsize: 64, 737 vertices; next SM4 at d2f58
FVFsize: 68, 1724 vertices; next SM5 at ef944
FVFsize: 64, 783 vertices; next SM6 at fbd08
0 vertices

The code needs the FVF startaddress of the first submesh (dwStart= 0x667D0)
and it stops at 0xFBD08 'cos there's a change to FVFsize 60 which is not handled so far (only 68 and 64).

But from the code you should get the idea:

```
{
   char * pFBuf ;
   BYTE cnt, FVFsize= 68 ;
   WORD wVertsCnt ;         //
   bool bStop= false ;

   pFBuf = (char *) lpFBuf ;    // pointer to model data
   pFBuf += dwStart ; j = dwStart ;
   pFBuf += 11 ; j += 11 ;                                 // point to FF of first "xx xx xx FF" group
   if ((*pFBuf&255)!= 0xFF) { chMB("FF not found!\nCheck the FVF starting address you entered.") ;  return ; }
   SendMessage(GetDlgItem(hwnd, ID_LIST), LB_ADDSTRING, 0, (LPARAM) " creating H2O files:") ;
   cnt= 1 ; wVertsCnt=0 ;
   do {
        if ((*(pFBuf+FVFsize)&255)!=0xFF) {
            fprintf(stream, "FVFsize: %d, %d vertices; next SM%d at %x\n", FVFsize, wVertsCnt, cnt, j+121-FVFsize) ;
            cnt++ ; wVertsCnt= 0 ;                                                 // next submesh
            FVFsize = 132 - FVFsize ;
        }
        if ((*(pFBuf+FVFsize)&255)!=0xFF) bStop = true ;
        else {pFBuf += FVFsize ; j += FVFsize ;}
        wVertsCnt++ ;
   } while (!bStop&&(j<dwFileSize)) ;
   fprintf(stream, "%d vertices\n", wVertsCnt-1) ;
}
```


(May occur to be a little bit cryptical but to be honest: I love such code: only a few lines which provide FVFsize, vertexcount and FVF start. No need of f...ing magic tables and such.)

umpf, yes, I didn't check for three identical bytes before the FF - so may terribly fail with other models...



automation_bin.JPG (28.3 KiB) Viewed 237 times
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-22T09:10:08+00:00
- Post Title: God of War Origins Collection [PS3]

> Reply from kovalevich007
>
> Samples: https://yadi.sk/d/qCKilbT2kFiui
here is a bms script to split those bin files to make them easier to work with  

```
endian big
goto 0xc
get FILES long
goto 0x40
for i = 0 < Files
	get SKIP long
	get OFFSET long
	get SIZE long
	get SKIP long 
	savepos TMP
	goto OFFSET
	log "" OFFSET SIZE
	goto TMP
next i
```


the largest sized mcf file has the data you are working with
the ida files are textures, just dxt data with custom header

shakotay, i don't see any face indices data in the file, did you
create those faces yourself or did you read them from the data?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-10-22T12:21:19+00:00
- Post Title: God of War Origins Collection [PS3]

> Reply from AceWell
>
> did you create those faces yourself or did you read them from the data?to be honest, I don't remember - don't even find the code. But seems to work with hex2obj:



automation_GofWar.JPG (48.74 KiB) Viewed 150 times


method is:
f 1/1 2/2 3/3
f 2/2 4/4 3/3
f 3/3 4/4 5/5
f 4/4 6/6 5/5

From the noesis obj output you see another method (right part of pic):
first line: a, a+1, a+2
2nd line a+3, a+2, a+1
3rd line: a+2, a+3, a+4
4th line: a+5, a+4, a+3

(where a=1; each line starts with lastindex_of_previous_line+1; even lines have decreasing face indices)
Don't have a texture to check which method is the better one.

You might simply use
rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VtxCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
from kovalevich's script; should work, shouldn't it?

In hex2obj there's the problem that it doesn't use negative uvpos - so if you try 44 you'll get a wrong uv map.
But you could add an additional line vt 0.0 0.0 before the uv start in the obj file to circumvent this (more or less  ).
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-22T13:01:25+00:00
- Post Title: God of War Origins Collection [PS3]

> Reply from shakotay2
>
> first line: a, a+1, a+2
2nd line a+3, a+2, a+1
3rd line: a+2, a+3, a+4
4th line: a+5, a+4, a+3

(where a=1; each line starts with lastindex_of_previous_line+1; even lines have decreasing face indices)
This is pure gold right here thank you! i'm gonna add it to my notes  

> You might simply use
>
> rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, VtxCount, noesis.RPGEO_TRIANGLE_STRIP, 1)
>
> from kovalevich's script; should work, shouldn't it?
yes that works, been a while since i tested his script  

good stuff here thanks for the info
