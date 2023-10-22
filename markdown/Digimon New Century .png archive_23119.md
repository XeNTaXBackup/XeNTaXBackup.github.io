## Post #1
- Username: BSoD38
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 29, 2016 5:15 am
- Post datetime: 2020-12-04T16:41:43+00:00
- Post Title: Digimon New Century .png archive

Hi, there's a new Digimon mobile game made for China (it's an official game, not a bootleg) that got an open beta session about a month ago, and I've managed the game's .apk, and it seems that at least some of the game's data is inside (it's a 1.4GB apk file).
The game seems to have unique 3D models, so I wanted to rip them, as I was expecting the game to be made in Unity.

I've extracted the .apk's contents, and it seems to be indeed a Unity game, but the data seems to be archived in a file called first_source.png. Don't be mistaken, it's not a PNG image, as it's 1.28GB big. There's also a file called first_source.ifs.res.png, but I'm not sure what it's for.

I'm not really sure if it's all of the game's data, because I didn't get the chance of running the game during the open beta period. But I uploaded the two .png files and you can find them here :
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1ltChpy4YCv0Orzu4Qc4zfxD9nl12aejj?usp=sharing)

I really don't have any reverse-engineering knowledge, so I'm stuck here.
Do you guys have an idea what the files are and if I can extract them? Thanks in advance.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2020-12-04T18:46:37+00:00
- Post Title: Digimon New Century .png archive

This png archive has "nifs" magic. It seems that there is an work-in-progress script here [http://aluigi.altervista.org/bms/monste ... r_nifs.bms](http://aluigi.altervista.org/bms/monster_hunter_nifs.bms)
You need quickbms to run this [http://aluigi.altervista.org/papers/quickbms.zip](http://aluigi.altervista.org/papers/quickbms.zip)

After unpacking you will see a lot of "uni" files. You can load them in Asset Studio [https://github.com/Perfare/AssetStudio/releases](https://github.com/Perfare/AssetStudio/releases)


Btw. you can get some knowledge in our tutorials section 
[viewtopic.php?f=29&t=22266](https://forum.xentax.com/viewtopic.php?f=29&t=22266)
## Post #3
- Username: BSoD38
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 29, 2016 5:15 am
- Post datetime: 2020-12-04T23:57:28+00:00
- Post Title: Digimon New Century .png archive

Oh, thank you very much for that script!

I tried using it, but it ended up crashing while extracting the archive. I do have about 400MB of usable extracted assets though.


None of them are the digimon's models (maybe they are downloaded using the app's built-in updater, like many mobile games do?), but it's definitely a step in the right direction.
## Post #4
- Username: BSoD38
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 29, 2016 5:15 am
- Post datetime: 2020-12-05T11:33:20+00:00
- Post Title: Digimon New Century .png archive

Heyo, just a little update.

I managed to find a solution, it's so simple that I kinda feel stupid that I didn't find this earlier.

When installing and running the game for the first time on a device, the game actually extracts all of its assets into the /android/data/com.tencent.dm folder, and these assets can easily be read with AssetStudio.

As I thought, the models are unique, and are actually of pretty high quality.
Thanks for the help!
