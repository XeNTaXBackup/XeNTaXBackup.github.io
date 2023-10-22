## Post #1
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-21T06:52:47+00:00
- Post Title: Shadowverse - *.unity3d files

ok shadowverse has these emote files in it, i assume its for the leader skins? any ideas how it works?
## Post #2
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-25T06:27:10+00:00
- Post Title: Shadowverse - *.unity3d files

ok, then heres a sample, any ideas how to extract stuff from this kind of file?(had to zip it otherwise i cant place it as attachment)
[master_emote_chara_1.zip](https://xentaxbackup.github.io/file/20506_master_emote_chara_1.zip)
## Post #3
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-25T08:55:13+00:00
- Post Title: Shadowverse - *.unity3d files

This is unity3d file. You can open it wit AssetStudio [https://i.imgur.com/3xZBVN6.png](https://i.imgur.com/3xZBVN6.png)
## Post #4
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-27T15:11:45+00:00
- Post Title: Shadowverse - *.unity3d files

oh that i know, but is there a way to extract contents of the file(if theres any)? cuz i feel like theres something hidden inside that file like maybe the emote model for the leader skins perhaps?
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-27T17:17:37+00:00
- Post Title: Shadowverse - *.unity3d files

There is nothing hidden inside. This unity3d file contains only one compressed data block, which is standard *.assets file as far as I know and there is only one TextAsset inside it (which you can see in AssetStudio after loading archive).
## Post #6
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-07-28T06:32:49+00:00
- Post Title: Shadowverse - *.unity3d files

oh okay then thanks for the heads up, but now im curious, how do you know which data files would contain emote model data or has it hidden inside?
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-07-28T18:08:17+00:00
- Post Title: Shadowverse - *.unity3d files

I don't know which files contain model data, because I don't have that game,
but if I were you I would just load whole game directory (File > Load Folder)
in AssetStudio and just search for it on the "Asset List".
