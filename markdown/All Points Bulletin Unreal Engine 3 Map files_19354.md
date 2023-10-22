## Post #1
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-01-19T16:49:53+00:00
- Post Title: All Points Bulletin Unreal Engine 3 Map files

Hi all, i want to dump list of coordinates for models from map file like position rotation scale and model name.
I already was able to find coordinates and dump them to list but the problem is that i have no idea how to find model name for them. 
Coordinates are stored in cStreamedBuildingActor object which starts with "F8 FF FF FF F8 FF FF FF FF FF FF FF" each (you can extract upk file so each object will be as separate file with this tool by Gildor: [http://www.gildor.org/down/43/umodel/extract.zip](http://www.gildor.org/down/43/umodel/extract.zip), i also included 1 extracted file in examples). As i fugured there is some object types that you can read if you skip 32 bytes from object start and if its value is "E5" then you can skip 275 bytes after that to get to coordinates, if value "E4" then you need to skip 303 bytes (there might me more types in other files but i saw only 2 in block01) . Then you will get to 3 single float values that is coordinates. With upk extractor objects come out as just "cStreamedBuildingActor_1000 cStreamedBuildingActor_1001" etc. But i need actual model names that are stored in name table in that file. I hope somebody could help me with that because i have no idea what to do.

Here is example files: [https://mega.nz/#!l4snyKgb!dT1CtatJ12rJ ... s5VLlUfTJc](https://mega.nz/#!l4snyKgb!dT1CtatJ12rJSw9UZ6QRy8eHvhaIOhN6Js5VLlUfTJc)

P.S. Here is also all 60 model names from block01:
WaterfrontDistrict_Block01_Generic_0001_LOD
WaterfrontDistrict_Block01_Generic_0001_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0002_LOD
WaterfrontDistrict_Block01_Generic_0002_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0003_LOD
WaterfrontDistrict_Block01_Generic_0003_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0004_LOD
WaterfrontDistrict_Block01_Generic_0004_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0005_LOD
WaterfrontDistrict_Block01_Generic_0005_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0006_LOD
WaterfrontDistrict_Block01_Generic_0006_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0007_LOD
WaterfrontDistrict_Block01_Generic_0007_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0008_LOD
WaterfrontDistrict_Block01_Generic_0008_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0009_LOD
WaterfrontDistrict_Block01_Generic_0009_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0010_LOD
WaterfrontDistrict_Block01_Generic_0010_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0011_LOD
WaterfrontDistrict_Block01_Generic_0011_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0012_LOD
WaterfrontDistrict_Block01_Generic_0012_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0013_LOD
WaterfrontDistrict_Block01_Generic_0013_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0014_LOD
WaterfrontDistrict_Block01_Generic_0014_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0015_LOD
WaterfrontDistrict_Block01_Generic_0015_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0016_LOD
WaterfrontDistrict_Block01_Generic_0016_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0017_LOD
WaterfrontDistrict_Block01_Generic_0017_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0018_LOD
WaterfrontDistrict_Block01_Generic_0018_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0019_LOD
WaterfrontDistrict_Block01_Generic_0019_VertexLit_LOD
WaterfrontDistrict_Block01_Generic_0020_LOD
WaterfrontDistrict_Block01_Generic_0020_VertexLit_LOD
WD_B01_Bridge_VertexLit_LOD
WD_B01_BridgeSupport_VertexLit_LOD
WD_B01_Hotel01_LOD
WD_B01_Hotel02_LOD
WD_B01_Hotel03_LOD
WD_B01_Hotel04_LOD
WD_B01_Hotel05_LOD
WD_B01_Hotel06_LOD
WD_B01_Hotel07_LOD
WD_B01_MiscBanners_VertexLit_LOD
WD_B01_VillanuevaSign1_LOD
WD_B01_VillanuevaSign1_VertexLit_LOD
WD_B01_VillanuevaSign2_LOD
WD_B01_VillanuevaSign2_VertexLit_LOD
WD_B01_VillanuevaSign3_LOD
WD_B01_VillanuevaSign3_VertexLit_LOD
WD_B01_VillanuevaSign4_LOD
WD_B01_VillanuevaSign4_VertexLit_LOD
WD_Block01_SignMPS_VertexLit_LOD
WD_Block01_SignNegrada_VertexLit_LOD
## Post #2
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2019-01-21T00:31:03+00:00
- Post Title: All Points Bulletin Unreal Engine 3 Map files

Nevermind, i found how to do that.
