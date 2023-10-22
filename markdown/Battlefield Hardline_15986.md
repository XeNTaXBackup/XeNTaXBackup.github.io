## Post #1
- Username: DXFan619
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2015 5:03 am
- Post datetime: 2017-03-11T18:31:01+00:00
- Post Title: Battlefield Hardline?

Hi, I've been trying to extract Battlefield Hardline's models using various Battlefield 4 tools, and while the Python scripts to extract the game's contents and the .ebx to .txt converter seem to be working (in some areas, it returns errors in others), the import tools to 3DS Max have given multiple errors and the models loading improperly with distortions on the head models. 



On that, I get bone_section_error, while importing the mesh using BF4 mesh Importer.ms. As I understand it, one needs to import the skeleton first, but I haven't found any skeletons inside of the game's files. In BF4, it's Warsaw1pAntSke01, apparently, although "warsawanimations" in Hardline just gives me this once converted to .txt. No skeleton data there, I assume?

> AntProjectAsset d154c3c10d45bdf72fd3fffd11bb4d4c
>
>     $::Asset
>
>         $::DataContainer
>
>         Name Animations/WarsawAnimations
>
>     AntNativeProjectName Animations
>
>     SceneOp::AntRef
>
>         AssetGuid AB963D8DF524C148A701ADB7EFA9D39E
>
>         ProjectId 0
>
>     ProjectId 0

Even when I try to run BF4_Bone_Maker(1.3).ms on Warsaw1pAntSke01, which is supposed to work on Max 2012 x64, I get "--runtime error: replace end out of range: 10"

Was just wondering if model extraction from Hardline is actually possible and I've been doing something very wrong, or it isn't with these Battlefield 4 scripts because Hardline's models are of a slightly different format.

Attached the scripts in questions and some sample files from Hardline. Thanks.

[http://www.mediafire.com/file/6a7m9th6o ... amples.zip](http://www.mediafire.com/file/6a7m9th6oltdfhj/Battlefield+Hardline+Scripts+And+Samples.zip)
