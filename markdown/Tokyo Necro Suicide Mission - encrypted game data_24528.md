## Post #1
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-09-24T06:00:27+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

i have a question... if a mobile game data that you can access with asset studio suddenly cant be accessed with asset studio, does it mean the game file is encrypted somehow? and is there way to find the encryption method of the data by comparing 2 datas of same contents but different time?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-24T21:29:57+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

It can be encrypted as you said, but it can also mean that whole game engine has been updated and version of the assets has changed as well.
## Post #3
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-09-25T05:37:52+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

okay then... is there a way to enable the new ones to be able to be accessed with asset studio?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-25T10:31:10+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

Yes, you could decrypt them or raise an issue on asset studio github page.
## Post #5
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-09-26T06:19:26+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

is there a way to identify method by comparing the two files? cuz i have them right now, id like to put them here as attachment but uh... its 3 mb so over the limit for attachment
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-26T08:53:12+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

Hard to tell without seeing the files. You can upload them into google drive, mega.nz etc. and just share a public link with us.
## Post #7
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-09-29T05:59:36+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

i see... heres the link then... before can still be viewed in assetstudio, after cant be viewed in assetstudio... they both should have the same content
[https://mega.nz/file/LN1WjBTJ#_as2Gji89 ... bl9hgyDzfc](https://mega.nz/file/LN1WjBTJ#_as2Gji894VJCj_ZvA6HzLsEUBHxFwQnobl9hgyDzfc)
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-29T13:14:38+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

Maybe you're using old version of asset studio, because both samples can be opened
without any issues in AssetStudio v0.16.0.

Btw, from what game are those samples?
## Post #9
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-09-29T16:38:04+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

problem is i cant open version 0.16. even with .net framework 4.7.2 installed, also cant say what game its from... since they just recently updated the data structure, am afraid theyll upgrade the data security even further... also the data thats after, cant be extracted with neither version 2 nor version 3 of live2dextractor
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-09-29T18:42:42+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

> problem is i cant open version 0.16. even with .net framework 4.7.2 installed

Well, it should work fine with that version, I have 4.8 and it works.
Maybe try to install this on some virtual machine or on other computer?


Also, it's worth to try UnityEx. It also supports newer archives,
but it will work only in Advanced or Ultimate version, so you'll need to spend 10$ or 30$ to buy it
[https://forum.zoneofgames.ru/topic/36240-unityex/](https://forum.zoneofgames.ru/topic/36240-unityex/)
## Post #11
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-09-30T06:37:33+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

ah i see... thats a shame that means my hands are tied... gotta see if live2dextractor released anything new then... btw the data i sent is from tokyo necro suicide mission
## Post #12
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-10-19T17:32:03+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

ok but something i wanna ask... is it possible to extract moc data from both of the files?
## Post #13
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-19T20:29:26+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

What is "moc data"? Can you explain?
## Post #14
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2021-10-23T18:31:30+00:00
- Post Title: Tokyo Necro: Suicide Mission - encrypted game data

ah.... i meant the live2d model data, its model file, motions, and textures and stuff, as well as the json that connects all of those... so far i extracted the cubism 3.0 ones using unitylive2dextractor 1.0.2 and 1.0.3...
