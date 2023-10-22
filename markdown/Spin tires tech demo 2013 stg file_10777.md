## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2013-09-15T06:12:59+00:00
- Post Title: Spin tires tech demo 2013 stg file

Hi,

I found this great tech demo.
[http://www.oovee.co.uk/games/upcoming-games/spin-tires/](http://www.oovee.co.uk/games/upcoming-games/spin-tires/)

How to extract the kickstarter.stg file this file contains dds dxt1 dxt5 textures for the level.
Maybe heightmap?

[https://dl.dropboxusercontent.com/u/685 ... tarter.stg](https://dl.dropboxusercontent.com/u/68586225/kickstarter.stg)

Thanks
## Post #2
- Username: SWTOR fan
- Rank: veteran
- Number of posts: 112
- Joined date: Fri Nov 18, 2011 12:33 am
- Post datetime: 2013-09-16T15:00:40+00:00
- Post Title: Spin tires tech demo 2013 stg file

I was bored, so I took a look at the file. QuickBMS is probably the wrong program to read the file, but I got the format figured out.

Here is the map:


```
# script for QuickBMS http://quickbms.aluigi.org

get unknownInt1 long
get width float # 512
get height float # 512
get float3 float
get float4 float
get float5 float

# terrains, consisting of two textures
get numTerrains long
print "--- %numTerrains% TERRAINS ---"
for i = 0 < numTerrains
   get ground1Length short
   getdstring ground1 ground1Length
   get ground2Length short
   getdstring ground2 ground2Length
   print "%ground1% + %ground2%"
next i

# overlays
get numOverlays long
print "--- %numOverlays% OVERLAYS ---"
for i = 0 < numOverlays
   get overlayLength short
   getdstring overlay overlayLength
   print "%overlay%"
next i

# map
get mapFileSize long
savepos curOffset
log "map.dds" curOffset mapFileSize
goto mapFileSize 0 SEEK_CUR

# grass
get numGrass long
print "--- %numGrass% GRASS ---"
for i = 0 < numGrass
   get grassLength short
   getdstring grass grassLength
   print "%grass%"
   get fileSize long
   savepos curOffset
   log grass curOffset fileSize
   goto fileSize 0 SEEK_CUR
next i

# plants
get numPlants long
print "--- %numPlants% PLANTS ---"
for i = 0 < numPlants
   get plantLength short
   getdstring plant plantLength
   print "%plant%"
next i

# vertices
get zero long
get numSections long # each section is up to 4096 vertices long
set totalVertices = 0
for i = 0 < numSections
   get numVertices long
   math totalVertices + numVertices
   for j = 0 < numVertices
      get plantIndex short
      get floatX float
      get floatY float
      get floatZ float
      get unknown2 long
      get unknown3 long
   next j
next i
print "--- %totalVertices% VERTICES ---"

get unknownWidth long
get unknownHeight long

print "--- %unknownWidth%x%unknownHeight% UNKNOWN TEXTURES ---"
for i = 0 < unknownWidth
   for j = 0 < unknownHeight
      get fileSize long
      savepos fileEnd
      math fileEnd + fileSize

      get type byte # can be 0 or 2
      for k = 0 < 10
         get float float
      next k

      for k = 0 < 5
         get ddsSize long
         set filename ""
         string filename + i
         string filename + "/"
         string filename + j
         string filename + "_"
         string filename + k
         string filename + ".dds"
         savepos curOffset
         log filename curOffset ddsSize
         goto ddsSize 0 SEEK_CUR
         if k = 0
            get numFloats byte
            if numFloats < 255
               get float float
               get float float
               get float float
               get float float
            endif
         endif
      next k

      goto fileEnd 0

      #skip remaining bytes - unknown!
#      get numIntegers long
#      for k = 0 < numIntegers
#         get integer long
#      next k
#
#      get zero long
#      get const2 long # 2 or 3 or 4
#      get zeroShort short
#
#      if const2 = 2
#         get zero long
#
#         for k = 0 < 16
#            get integer long
#         next k
#      elif const2 = 3
#         get integer long
#         for k = 0 < 16
#            get integer long
#         next k
#
#         get byte byte
#         get byte byte
#         get byte byte
#         get byte byte
#         get byte byte
#         get byte byte
#
#         for k = 0 < 16
#            get integer long
#         next k
#      elif const2 = 4
#         get zero long
#
#         for k = 0 < 16
#            get integer long
#         next k
#      endif
#
#      get const4 long # 4 or 5
#      get zeroShort short
#
#      for k = 0 < 16
#         get integer long
#      next k
   next j
next i

get numModels long
print "--- %numModels% MODELS ---"
for i = 0 < numModels
   get modelLength short
   getdstring model modelLength
   print "%model%"
   # position + rotation?
   get float1 float
   get float2 float
   get float3 float
   get float4 float
   get float5 float
   get float6 float
next i

get numUnknown long
print "--- %numUnknown% UNKNOWN ---"
for i = 0 < numUnknown
   get type long
   if type = 1
      get unknownLength short
      getdstring unknown unknownLength
      print "%unknown%"
      get numFloats1 long
      for j = 0 < numFloats1
         get float1a float
         get float1b float
         get float1c float
      next j
      get numFloats2 long
      for j = 0 < numFloats1
         get float12 float
      next j
   elif type = 3
      get unknownLength short
      getdstring unknown unknownLength
      print "%unknown%"
      get numFloats1 long
      for j = 0 < numFloats1
         get float1a float
         get float1b float
      next j
   elif type = 2
      get subType short
      for j = 0 < 16
         get float float
      next j
   endif
next i

get numUnknown2 long
for i = 0 < numUnknown2
   for j = 0 < 14
      get float float
   next j
next i

# END OF FILE
```
