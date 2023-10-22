## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2012-02-01T02:08:15+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

When I was looking for this game's graphics, I couldn't find anything that was clearly labelled as graphics, unlike LEGOLAND. I think these files are the game's graphics, and if they aren't, then I'm not sure what is. Download 2 of each: [http://www.mediafire.com/download.php?46ff37xst13hwh4](http://www.mediafire.com/download.php?46ff37xst13hwh4)
## Post #2
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2012-03-03T14:16:14+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

hm,

the .bod files are index files for an archive. They contain filenames, offsets and sizes. The .bob files are the archives that contain the files raw data.

This script extractes the archives:

```
#use something like "quickbms bod.bms <filename>.bod ." for extraction

# internal open <filename>.bob
Open FDDE bob 1

goto -16
get FILEOFFSET long
get FILES long
get FILENAMEOFFSET long

goto FILEOFFSET  

set FULLPATH string ""
set NAME string ""

callfunction extractor

startfunction extractor
  string FULLPATH += NAME
  string FULLPATH += \

  getdstring FILETYPE 4 
  
  if FILETYPE == "DIRY"
    get CONTAINS long
    get Unk long
    get FOLDERNAMEOFFSET long    
    savepos FILEOFFSET
    goto FOLDERNAMEOFFSET
    get NAME string
    goto FILEOFFSET
    for i = 0 < CONTAINS
      callfunction extractor
    next i
  elif FILETYPE == "FILE"
    get LOGFILESIZE long
    get LOGFILEOFFSET long
    get FILENAMEOFFSET long    
    savepos FILEOFFSET
    goto FILENAMEOFFSET
    get FILENAME string
    goto FILEOFFSET
    set FULLNAME string FULLPATH
    string FULLNAME += FILENAME
    Log FULLNAME LOGFILEOFFSET LOGFILESIZE 1
    print "FILE %FULLNAME%"
  else 
    print "Unknown FILETYPE: %FILETYPE%"
    cleanexit
  endif
endfunction

```

Use this script with the .bod files. This script will open the .bob files itself.

If you extract the Bricks.bod archive, you will get many .msh files with the following struct: 

```
{
  float		fX;
  float		fY;
  float		fZ;
  byte    bUnk[0x14];
};
	
struct Normal
{
  float		fX;
  float		fY;
  float		fZ;
};

struct Group
{
  dword dwOffsetIndices;
  dword dwCntIndices;
  dword dwOffsetVertices;
  dword dwCntVertices;
};

struct MSH
{
  char		        VERT[4];
  dword		        dwCntVertices;
  struct Position sPositions[dwCntVertices];
  struct Normal   sNormals[dwCntVertices];
  
  char		        INDL[4];
  dword           dwCntIndices;
  word		        aIndices[dwCntIndices]; 
  
  char		        GRPL[4];
  dword           dwCntGroups;
  struct Group    sGroups[dwCntGroups];
};
```

I wrote a noesis py script for them:

```

import noesis

#rapi methods should only be used during handler callbacks
import rapi

#registerNoesisTypes is called by Noesis to allow the script to register formats.
#Do not implement this function in script files unless you want them to be dedicated format modules!
def registerNoesisTypes():
   handle = noesis.register("LEGO Island 2", ".msh")
   noesis.setHandlerTypeCheck(handle, mshCheckType)
   noesis.setHandlerLoadModel(handle, mshLoadModel) #see also noepyLoadModelRPG
       #noesis.setHandlerWriteModel(handle, noepyWriteModel)
       #noesis.setHandlerWriteAnim(handle, noepyWriteAnim)
   noesis.logPopup()
       #print("The log can be useful for catching debug prints from preview loads.\nBut don't leave it on when you release your script, or it will probably annoy people.")
   return 1

#check if it's this type based on the data
def mshCheckType(data):
   bs = NoeBitStream(data)
   if len(data) < 12:
      return 0
   if bs.readBytes(4).decode("ASCII") != "VERT":
      return 0
   return 1       

#load the model
def mshLoadModel(data, mdlList):
   ctx = rapi.rpgCreateContext()
   bs = NoeBitStream(data)

   if bs.readBytes(4).decode("ASCII") != "VERT":
      return 0   
      
   dwCntVertices = bs.readInt()
   sPositions = bs.readBytes(dwCntVertices*0x20)
   sNormals = bs.readBytes(dwCntVertices*0x0C)
   
   if bs.readBytes(4).decode("ASCII") != "INDL":
      return 0   
   
   dwCntIndices = bs.readInt()
   aIndices = bs.readBytes(dwCntIndices * 2)
   
   rapi.rpgBindPositionBufferOfs(sPositions, noesis.RPGEODATA_FLOAT, 0x20, 0)
   rapi.rpgBindNormalBufferOfs(sNormals, noesis.RPGEODATA_FLOAT, 0x0c, 0)
   #rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, dwCntVertices, noesis.RPGEO_POINTS, 1)
   rapi.rpgCommitTriangles(aIndices, noesis.RPGEODATA_USHORT, dwCntIndices, noesis.RPGEO_TRIANGLE, 1)
   
   mdl = rapi.rpgConstructModel()
   mdlList.append(mdl)         #important, don't forget to put your loaded model in the mdlList
   
   return 1

```

hf
## Post #3
- Username: gyeben
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 19, 2011 10:43 pm
- Post datetime: 2012-06-19T10:27:48+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

Hi! Is it possible to compile the decomplied .bob files?
I'm making a translation for LEGO Island 2, and I could extract messages.bob successfully, but I can't compile it again.
## Post #4
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2012-06-29T10:49:12+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

Hi,
I have a question to .BOD/.BOB-Files. So, I don't understand:
-.BOD-Files contains a table with names
-the position to the table-entries are given in the second table
-this table contains:
    -"FILE" (ASCII) - Unknown (4 Byte) - Unknown (4 Byte) - Offset to the nametable (4 Byte)

So, what does this .BOD-file stand for? For me, this file does'nt make any sense?!

The .BOD-files even have no information about the mesh-structure, inside the .BOB-file.

I would like to know, how to get to the mesh-data in the .BOB-files? Where are the containing offsets?

Thank you very much! (And sorry for my bad english)
## Post #5
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2012-06-29T19:33:36+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

hm,

the .bob files are archives like .zip archives without compression. The .bob archives contains files and folders (one after the other) without offsets and filenames. If you want to extract the .bob archives you have to look into the .bod files because they contain the filenames, sizes and offsets of the files inside the .bob archives. When you use quickbms with the script I posted, you can extract the .bob archives. You will get new files in a folder hirarchy. You will find new files with the extention .msh. The new .msh files contain the mesh data you are looking for.

hf
## Post #6
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2012-07-01T13:42:22+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

Hey RickyOs,
I was already able to read the files from the bod-archives. I've directly written a OBJ-Exporter, to look at the models at Blender. Small objects are looking really good, but big models like the helicopter or policecar are a bit transformed. Maybe you can help me, finding out what's wrong?
Here is the code I've written to extract BOD, BOB and MSH to OBJ files:
-.h-File: [http://codepad.org/Yz3cvzt2](http://codepad.org/Yz3cvzt2)
-.cpp-File: [http://codepad.org/pt9tOEkJ](http://codepad.org/pt9tOEkJ)

Here a screenshot from the helicopter: 
Here a screenshot from the locomotive: 

And another question: Where can I find the file with the mapdata? 

Thank you very much RickyOs!
## Post #7
- Username: RickyOs
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Nov 30, 2010 12:54 am
- Post datetime: 2012-07-01T16:29:06+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

hm,

sry. I don't own the game. I had only the two posted samples...

hf
## Post #8
- Username: pivke
- Rank: advanced
- Number of posts: 41
- Joined date: Tue Jun 26, 2012 4:53 pm
- Post datetime: 2012-07-03T17:30:40+00:00
- Post Title: LEGO Island 2 (PC) .BOB and .BOD Files

> Reply from RickyOs
>
> hm,

sry. I don't own the game. I had only the two posted samples...

hf
Hi again! 

I've noticed that the problem is the "GRPL". I don't really get, how to read in the groupdata. As you said, the group is defined as the following:
char Group[ 4 ];
int GroupCount;
Group[ GroupCount ];

struct Group
{
    int IndicesOffset;
    int IndicesCount;
    int VerticesOffset;
    int VerticesCount;
}

But when I'm looking at the values in the hex-editor, than it shows often, that "IndicesOffset" is 0. All values are looking a bit strange. Here a screenshot:


Thanks for help Ricky!

SOLUTION:

```
int CountGroups;
Group[ CountGroups ];

Group
{
   int Unknown;
   int FaceCount;
   int VertexOffset;
   int VertexNumber;
   int FaceOffset;
}
```


Have fun!
