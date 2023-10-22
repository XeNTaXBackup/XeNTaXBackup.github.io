## Post #1
- Username: aske0874
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 04, 2019 5:45 pm
- Post datetime: 2019-08-09T22:04:11+00:00
- Post Title: 3D model ripping from Abzû

Hi ninja experts
I'm trying to rip models from the game Abzü, but haven't had much luck yet. I used UE viewer with some results, but only for the bigger fish. It seems they used some special form of static mesh so UE viewer can not view the majority of fish in the game. I then thought ninja ripper maybe could be the answar, since it treats the 3D models differently than UE viewer does. But for some reason ninja ripper does not work with Abzü at all, it does't even create a ripping folder for the game then I launch it. The game launches but nothing more happens. I tried opening Age Of Mythology in ninja ripper and it does open and create a folder, but then i try to extract something it doesnt do anything other than leaving a log. This is strange since i have succesfully ripped models from Age Of Mythology before, so now I'm thinking I am doing something wrong. I am running ninja ripper as admin and I am running Abzu in the 64 bit version and the directx 11 mode, which I think is what Abzu is made for. Does anyone maybe have a solution to this problem?
Thanks for the help and have a great day
## Post #2
- Username: fil1969
- Rank: veteran
- Number of posts: 146
- Joined date: Fri Sep 17, 2010 2:44 pm
- Post datetime: 2019-10-06T10:54:55+00:00
- Post Title: 3D model ripping from Abzû

umodel works perfectly with all the game, i used last Umodel built and overriding to ue4 version 4.11
## Post #3
- Username: aske0874
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 04, 2019 5:45 pm
- Post datetime: 2020-06-21T14:15:14+00:00
- Post Title: 3D model ripping from Abzû

Hi fil1969

I have tried using ue4, 4.11, and it works for some of the bigger models, but for many of the smaller ones it don't. I just tried fx the Anchovy and it gives me this error message:

RawArray item size mismatch: expected 286, serialized 12

SerializeBulkArray <- FPositionVertexBuffer4<< <- FStaticMeshLODModel4::SerializeBuffersLegacy <- FStaticMeshLODModel4<< <- TArray::Serialize:0/3 <- UStaticMesh4::Serialize <- LoadObject:StaticMesh4'Anchovy.Anchovy', pos=1BE2, ver=498/4, game=ue4.11 <- UObject::EndLoad <- LoadWholePackage:Anchovy <- CUmodelApp::ShowPackageUI <- UIMenuItem::HandleCommand <- UIMenuItem::HandleCommand <- CUmodelApp::WndProc <- VisualizerLoop <- Main:umodel_build=1216

I think they used some sort of custom mesh deformer or something that Umodel can't read, is there any way to bypass this so I can see the models?
