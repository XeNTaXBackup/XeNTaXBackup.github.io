## Post #1
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-04-12T23:11:41+00:00
- Post Title: Star Wars First Assault (Xbox 360)

So this game is using a odd version of unreal engine 3 version 852.8 that for some reason only partly works with Umodel and i'm hoping someone can help with it on here.

Now you can get out some of the models and textures but you have to disable skelmesh and animations then it will partly extract them and then error

```
appMalloc:size=1429406512 (total=3 Mbytes) <- FArray::Empty:1163079731 x 16 <- TArray::Serialize:0/0 <- FStaticLODModel3<< <- TArray::Serialize:0/160 <- USkeletalMesh3::Serialize <- LoadObject:SkeletalMesh3'TriggerGame.amo_crates', pos=163BD83, ver=852/8, game=ue3 <- UObject::EndLoad <- CUmodelApp::ShowPackageUI <- Main:umodel_version=580
```


Alright so i'm only going to include 3 files that you really need to take a look at the but really only 1 of them you will be using which is the TriggerGame.xxx.

Also i'm not sure if it means anything but the file was compressed and i used the decompress.exe over on gildor.com and that is the version i'm uploading the decompressed .xxx.

[http://www.mediafire.com/file/iuj7b0x6g ... ressed.rar](http://www.mediafire.com/file/iuj7b0x6gq0077x/FA_Decompressed.rar)
