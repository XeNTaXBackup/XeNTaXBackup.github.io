## Post #1
- Username: seonply
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jun 21, 2020 9:02 pm
- Post datetime: 2022-07-07T08:12:23+00:00
- Post Title: Bendy and the Ink Machine (Unity) - DAT files

Hi I wanna translate an unity game but I don't know how to extract or edit .dat files can someone help me please?   

here is the file:
[https://www.mediafire.com/file/0r38g1y5 ... 3.dat/file](https://www.mediafire.com/file/0r38g1y5h73xh46/unnamed_asset-03c9d82c244d847469060a4bd3f2c40d-3.dat/file)
## Post #2
- Username: moderjack
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 09, 2021 9:20 am
- Post datetime: 2022-07-09T15:04:07+00:00
- Post Title: Bendy and the Ink Machine (Unity) - DAT files

Hello, there are two files named resource in the unity games folder, take a backup of them, then open the resource file with special tools for unpack unity, the text file is always in this file, the mono behuver files
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-07-10T10:24:11+00:00
- Post Title: Bendy and the Ink Machine (Unity) - DAT files

It seems that this game use I2 Localization package for storing texts.

Here is some more info on the format [http://wiki.xentax.com/index.php/Unity_ ... ion_Assets](http://wiki.xentax.com/index.php/Unity_I2_Localization_Assets)

And here is the link for the package in Unity store [https://assetstore.unity.com/packages/t ... tion-14884](https://assetstore.unity.com/packages/tools/localization/i2-localization-14884)
## Post #4
- Username: luatsenpai
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Apr 21, 2020 8:08 am
- Post datetime: 2022-07-12T02:29:25+00:00
- Post Title: Bendy and the Ink Machine (Unity) - DAT files

First, you need use Il2cpp for dump dll file, then copy dummy dll to folder manage. If don't have just create one
Then use uabe and load .assets file, choose tools> get script information.
And dump monobehaviour. 
Text in monobehavior
For font file, use unity same version with game, and build TextMeshPro
## Post #5
- Username: nonamebatbai
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Sep 22, 2019 10:32 am
- Post datetime: 2022-07-12T07:43:40+00:00
- Post Title: Bendy and the Ink Machine (Unity) - DAT files

> Reply from luatsenpai ↑Tue Jul 12, 2022 10:29 am at Tue Jul 12, 2022 10:29 am
>
> 
First, you need use Il2cpp for dump dll file, then copy dummy dll to folder manage. If don't have just create one
Then use uabe and load .assets file, choose tools> get script information.
And dump monobehaviour. 
Text in monobehavior
For font file, use unity same version with game, and build TextMeshPro

Can you guide me how to create TextMesh Pro font for unity game?
## Post #6
- Username: seonply
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Jun 21, 2020 9:02 pm
- Post datetime: 2022-07-31T10:38:15+00:00
- Post Title: Bendy and the Ink Machine (Unity) - DAT files

> Reply from luatsenpai ↑Tue Jul 12, 2022 10:29 am at Tue Jul 12, 2022 10:29 am
>
> 
First, you need use Il2cpp for dump dll file, then copy dummy dll to folder manage. If don't have just create one
Then use uabe and load .assets file, choose tools> get script information.
And dump monobehaviour. 
Text in monobehavior
For font file, use unity same version with game, and build TextMeshPro
How can I find the dll file?
