## Post #1
- Username: Diol
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 05, 2017 6:37 am
- Post datetime: 2017-02-06T04:46:16+00:00
- Post Title: [Request] Fighters Club Hero Models

Hello Xentax, first time posting here!
I'm looking to rip the models from the game Fighters Club Hero / 파이터스 클럽 In Korean / 格斗联盟 In Chinese 

This is a fighting side scroller 3d game from KOG, it closed the korean servers in 2014 and there was a chinese server which died too, can you please help me to find a way to rip the models? This game was so fun to play! I will leave the chinese client download below. (It took me a while to find a working link)
I don't know programing but I will help with what I can.

I really want to rip models, UI, sound, animations and everything.
There was a quickbms script for Fighters Club Hero, it can be found here: [viewtopic.php?f=10&t=3433&start=90](http://forum.xentax.com/viewtopic.php?f=10&t=3433&start=90)

```
goto 0x34
get FILES long
get UNK long
math LENGTH += 0x10c
math LENGTH *= FILES
MATH LENGTH += 0x3C

for i = 0 < FILES
getdstring NAME 0x100
get SIZE long
get ZSIZE long
get OFFSET long
math OFFSET += LENGTH

clog NAME OFFSET ZSIZE SIZE

next i
```


But it doesn't work with this version, because the version I found is chinese. But the game is exactly the same.
Also, I know this is not the forum for this, but, do you guys think there is a way to play this game with an offline emulator?
Any help will be really appreciated!

Websites:

Link to the webpage
[http://www.youxicheng.net/gdlm/](http://www.youxicheng.net/gdlm/)
【格斗联盟官网下载】格斗联盟ol好玩么_格斗联盟激活码_游戏城
Client Download
[http://www.youxicheng.net/gdlm/gongju_23368.html](http://www.youxicheng.net/gdlm/gongju_23368.html)
