## Post #1
- Username: senkay
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 18, 2020 8:06 pm
- Post datetime: 2022-05-06T17:42:26+00:00
- Post Title: Days Gone umodel error

Hi,
i wanted to extract some meshes from Days Gone but i fail to exctract the .pak or .pkg files. Tried that with umodel but get this error:

ERROR: Memory: bad allocation size 1098050420 bytes
appMalloc: size=1098050420 (total=253 Mbytes) <- FArray::Empty: -624323681 x 12 <- FPackageFileSummary::Serialize4 <- FPackageFileSummary<<: Ver=500/0 <- UnPackage::UnPackage: /Game/Maps/ORWorld/CraterLake/15-08/15-08.umap, ver=500/34, game=ue4.11 <- UnPackage::LoadPackage(info): /Game/Maps/ORWorld/CraterLake/15-08/15-08.umap <- CUmodelApp::ShowPackageUI <- Main: umodel_build=1587

I wanted to get the Models like here: [viewtopic.php?f=16&t=21602](https://forum.xentax.com/viewtopic.php?f=16&t=21602) and for that i need the umap and uassets

Someone can help me maybe?
## Post #2
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2022-05-07T10:01:58+00:00
- Post Title: Days Gone umodel error

use game specific override option and from engine dropdown menu choose Unreal 4 -> Days Gone
