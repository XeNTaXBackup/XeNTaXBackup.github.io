## Post #1
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2016-10-16T05:30:23+00:00
- Post Title: MKXL .xxx UModel Error

When you try to unzip the file .xxx with using umodel, but I get the error:

Trying to allocate -773094096 bytes

Call stack:
appMalloc:size=-773094096 <- FArray::Empty:1052266988 x 36 <- TArray::Serialize:0/0 <- UAnimSequence::Serialize <- LoadObject:AnimSequence'CHAR_Alien_A.Cloth_Duckstance', pos=12B4E64, ver=677/157, game=8103 <- UObject::EndLoad <- LoadWholePackage:CHAR_Alien_A <- CUmodelApp::ShowPackageUI <- Main:umodel_version=467
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-10-16T14:23:04+00:00
- Post Title: MKXL .xxx UModel Error

Animations aren't supported, as far as I know. Skip animations and you should get content extracted
## Post #3
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2016-10-16T15:58:14+00:00
- Post Title: MKXL .xxx UModel Error

Wow, thank you very much. A I've been puzzled, sat.
## Post #4
- Username: SporeAltair
- Rank: advanced
- Number of posts: 63
- Joined date: Sun Mar 20, 2016 1:47 am
- Post datetime: 2016-10-28T13:14:33+00:00
- Post Title: MKXL .xxx UModel Error

And another problem. When unpack some files, it is in other gamesis also but .xxx the file format. After unpacking only texture appear in the folder, no meshes.
