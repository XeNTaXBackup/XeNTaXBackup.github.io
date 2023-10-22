## Post #1
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2022-05-12T02:54:35+00:00
- Post Title: To LoveRu Darkness True Princess extract sounds??

its possible to extract resources.assets or resources.resource? file from To LoveRu Darkness True Princess??

link: [https://mega.nz/file/yBoXgCQT#RNogxSQbn ... MXFbtlZS3Q](https://mega.nz/file/yBoXgCQT#RNogxSQbnmrarU7Lfyhug5KVgjDpjpZA_MXFbtlZS3Q)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-12T20:06:39+00:00
- Post Title: To LoveRu Darkness True Princess extract sounds??

Yes, it's possible. You can use AssetStudio to open resources.assets file and load assets without issues.
Other useful Unity tools are listed here [http://wiki.xentax.com/index.php/List_of_Unity_Tools](http://wiki.xentax.com/index.php/List_of_Unity_Tools)


Sounds and music can be extracted from resource.resource file using this script [http://aluigi.altervista.org/bms/dump_fsbs.bms](http://aluigi.altervista.org/bms/dump_fsbs.bms)
with quickbms.

Then you can play FSB audio files in foobar2000 with vgmstream plugin.
More info here [http://wiki.xentax.com/index.php/FMOD_Audio_FSB](http://wiki.xentax.com/index.php/FMOD_Audio_FSB)
## Post #3
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2022-05-13T04:43:36+00:00
- Post Title: To LoveRu Darkness True Princess extract sounds??

I get to extract resource.resource but I get this error  
how do i solve?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-13T13:15:30+00:00
- Post Title: To LoveRu Darkness True Princess extract sounds??

You need to type "y" and then press enter.
## Post #5
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2022-05-13T15:55:07+00:00
- Post Title: To LoveRu Darkness True Princess extract sounds??

thanks!, i got to extract in resources.assets but some get this error , can be extract AssetStudio or other program?
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-14T10:24:35+00:00
- Post Title: To LoveRu Darkness True Princess extract sounds??

Those "AudioClip" entries are in fact just audio headers (it seems AssetStudio doesn't support linking data to those headers). So they are not really useful for you,
because you probably need only audio data (FSB files) which are stored in resource.resource file.
(To extract just headers, you can go to Export > Raw > Selected assets [https://imgur.com/a/LZxrziQ](https://imgur.com/a/LZxrziQ))


So if you need FSB files, you should unpack resource.resource file with dump_fsbs.bms.
