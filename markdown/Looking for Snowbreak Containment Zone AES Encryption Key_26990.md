## Post #1
- Username: hahayeye
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 20, 2023 12:58 am
- Post datetime: 2023-07-19T17:08:44+00:00
- Post Title: Looking for "Snowbreak: Containment Zone" AES Encryption Key

its a Gacha Game that is about to come out. 
It has a PC Client you can get directly here: 
[https://snowbreak-content.amazingseasun ... _Setup.exe](https://snowbreak-content.amazingseasuncdn.com/ob202307/launcher/seasun/setup/Snow_Setup.exe)
Or just from their main website (windows download button right at the bottom)
[https://snowbreak.amazingseasun.com](https://snowbreak.amazingseasun.com)
Its preloadable already, 10gb in size

I tried getting the AES Encryption key via some easy public methods.

It returned 5 different ones, none of them work, tried to use multiple or single ones.

These are the ones I got (NOT WORKING!)

```
0x000000400000F0410000803F0000803F0000A04000004040000020410000A040
0x9A99993E0000803F0000003F0000003F04000000060000000000003F00030303
0x6F168073B9B21449D742241700068ADABC306FA9AA3831164DEE8DE34E0EFBB0
0x0000803F0000803F0000803F0000803F000048430000F0410AD7A33C0000803F
```


From what I gathered
Its a standalone Launcher (no steam, no epic games)
It runs on Unreal 4
The shipping binary .exe is there
Just the .pak files are encrypted

I am not skilled enough to do reverse engineering.. Would be cool if someone can manage to get the working one, this game has some neat character but the shaders they used in-game suck so it would be interesting to see them with proper toon shading.
## Post #2
- Username: Esbeckett
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 17, 2014 1:12 pm
- Post datetime: 2023-07-20T14:47:21+00:00
- Post Title: Looking for "Snowbreak: Containment Zone" AES Encryption Key

The other site that has a collection of them has 
```
0xC14735FB5A872D2AFA76A5C38521AB8B8E21072C08525B913307608BD1182FA7
```

listed as the main AES key. There's a protection .sys file similar to what Genshin uses?

The engine is 4.26.2.0, from what I can see. Would the external protection be relevant?
## Post #3
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2023-07-20T20:35:23+00:00
- Post Title: Looking for "Snowbreak: Containment Zone" AES Encryption Key

Have you managed to extract anything from the game?!. I seem to be unable to extract the packs because umodel says they are version 12 or something like that.

Edit: if you manage to extract some of the files would you mind sending me a private message to talk?
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-07-21T19:00:36+00:00
- Post Title: Looking for "Snowbreak: Containment Zone" AES Encryption Key

The game is using custom package format. Afaik, fmodel supports it out the box with respective option, for other tools you need to extract packages first with quickbms script from specific scripts bundle, available via my signature (you need to be registered at rin forum to see attachments there). 

P.S. After zenhax closure I don't feel like creating similar UE topic here (you can still check some pages via [archive.org](https://web.archive.org/web/20230601001200/https://zenhax.com/viewtopic.php?f=9&t=1005&p=56251)), so if you have related questions, please address them to the rin topic.
