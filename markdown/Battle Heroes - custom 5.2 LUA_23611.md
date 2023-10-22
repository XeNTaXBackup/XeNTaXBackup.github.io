## Post #1
- Username: Sekretmnicha
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 20, 2021 6:42 pm
- Post datetime: 2021-03-20T15:10:40+00:00
- Post Title: Battle Heroes - custom 5.2 LUA

Hello
I want to mod a LUA file from game called Battle Heroes:
[https://play.google.com/store/apps/deta ... l=pl&gl=US](https://play.google.com/store/apps/details?id=com.rbx.battle.android&hl=pl&gl=US)

The game uses LUA 5.2 but its not a standard LUA setup. Header is modified: altered from LuaR to nxsR. The fromat byte is 01 and header tail is changed.

```
nxsR.nx
```

I tried use luadec, unluac,chunkspy but all failed due to custom header so i cant manage to make the LUA "readable". Those LUA is not encrypted but just compiled bytecode.
I think nx in header stands for nx-crypto Linux library (im not 100%sure).

I tried use IDA pro on *.so from apk but its black magic to me.
Can any1 help me on how to make the file readable?

In attachments i added one LUA file. Cant add *.so due to file size.


 HeroWerewolf.rar
(669 Bytes) Downloaded 15 times
