## Post #1
- Username: SideQuests
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2016 7:03 am
- Post datetime: 2016-06-13T23:33:36+00:00
- Post Title: Transformers Earth Wars - Help Please!

Hi everyone,

First time on these forums but have used old posts in the past to extract audio from other games but this one has me stumped 

I really want to use the Optimus Prime audio from the Android / IOS app of Transformers Earth Wars which is a free to play game but so far I have managed to get as far as digging into the game the files and I can see files that end in .assets which based on their file size look like they may contain audio files, 3d models, etc.

I've researched into DisUnity but not having any luck on my mac in actually extracting anything from any of the .assets files  The below was my most recent effort using DisUnity 0.4:

daniels-mbp:Data danielba$ java -jar disunity.jar extract "resources.assets"
[info] DisUnity v0.4.0
[info] Processing resources.assets
[warning] TypeTreeDatabase: Unprecise match for class Class 21 (Material) (required: 5.2.2p4, available: 5.0.0f4)
[warning] TypeTreeDatabase: Unprecise match for class Class 21 (Material) (required: 5.2.2p4, available: 5.0.0f4)
[warning] TypeTreeDatabase: Unprecise match for class Class 128 (Font) (required: 5.2.2p4, available: 5.0.0f4)
[warning] AssetFile: Object -281384782397419 Class -21056 has no type information!
[warning] AssetFile: Object 90194313384 Class 0 has no type information!
[error] DisUnityCli: Fatal error, caused by java.lang.IllegalArgumentException
	at java.nio.ByteBuffer.allocate(ByteBuffer.java:334)
	at info.ata4.io.buffer.ByteBufferUtils.allocate(ByteBufferUtils.java:55)
	at info.ata4.unity.asset.AssetFile.loadObjects(AssetFile.java:219)
	at info.ata4.unity.asset.AssetFile.load(AssetFile.java:137)
	at info.ata4.unity.asset.AssetFile.load(AssetFile.java:114)
	at info.ata4.disunity.cli.command.AssetFileCommand.handleFile(AssetFileCommand.java:53)
	at info.ata4.disunity.cli.command.FileCommand.processFile(FileCommand.java:35)
	at info.ata4.disunity.cli.command.MultiFileCommand.run(MultiFileCommand.java:54)
	at info.ata4.disunity.cli.DisUnityCli.run(DisUnityCli.java:117)
	at info.ata4.disunity.cli.DisUnityCli.main(DisUnityCli.java:131)

Has anyone had any luck with this kind of thing before and could point me in the right direction?

Thanks in advance!

Cheers,

SQ
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2016-06-15T13:28:49+00:00
- Post Title: Transformers Earth Wars - Help Please!

What are you trying to extract exactly? Audio data, models, textures?

Post a sample of one of the .asset files
## Post #3
- Username: SideQuests
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2016 7:03 am
- Post datetime: 2016-06-15T22:34:36+00:00
- Post Title: Transformers Earth Wars - Help Please!

Thanks for the post  I'm looking for the game audio clips.

I've tried an alternative route and downloaded the game onto my android tablet and managed to get the .apk file when I rename this as a .zip file and extract the contents I can see loads of files within the asset folder but they all come up as Unix Executible File on my mac so not sure what are sounds, pictures, textures, etc.

My logic would tell me that the ones with a larger size could be sound files.

I'll try and upload some samples when I'm back at my desk
## Post #4
- Username: SideQuests
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2016 7:03 am
- Post datetime: 2016-06-22T23:41:24+00:00
- Post Title: Transformers Earth Wars - Help Please!

So I've got a bit further, I've managed to load the assets file into Unity Assets Explorer but get stream read error when trying to extract an audio clip.

I've posted a screenshot in the attached Dropbox folder, any help greatly appreciated!

[https://www.dropbox.com/l/scl/C1oFmeWm4XLPRjEEv3kGcu](https://www.dropbox.com/l/scl/C1oFmeWm4XLPRjEEv3kGcu)
## Post #5
- Username: SideQuests
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Jun 14, 2016 7:03 am
- Post datetime: 2016-06-23T05:57:39+00:00
- Post Title: Transformers Earth Wars - Help Please!

There is also the .asset file in the Dropbox folder if anyone is able to help
