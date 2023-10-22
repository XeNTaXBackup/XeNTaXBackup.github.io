## Post #1
- Username: GilgameshKOFGC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 29, 2021 4:46 am
- Post datetime: 2021-03-28T20:53:15+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

Hello

I want to mod a pc game (The King of Fighters XIII) it's a Japanese 2d fighting game

But all the content I want to change is packed, I tried using QuickBMS but can't find a working script, the game has almost zero mods except a boss unlocker and an hitbox viewer

I have zero experience in modding but I really want to mod that specific game, my modifications are pretty basic, just some tweaks on dmg/hp/speed...etc

Thanks for your time
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-28T22:11:08+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

Can you upload some archive samples?
## Post #3
- Username: GilgameshKOFGC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 29, 2021 4:46 am
- Post datetime: 2021-03-29T06:36:51+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

I uploaded and archive about 120 Mo of various files of various folders
[https://mega.nz/file/2pwgiZjK#u7Lwz0oz1 ... OC2zFcl8eI](https://mega.nz/file/2pwgiZjK#u7Lwz0oz1I_bVw6AF7jr5mM9EYn3Dvk8POC2zFcl8eI)


Most files are .lua / .pcs / .pso
I think i identified character files, opened with an hex editor but can't seem to find what matches to what

Like i said the modifications i want to do are nothing funky 

-Edit character variable (name,speed,hp,dmg,states,colors)
-Edit hitboxes,sprites
-Edit a move input
-Swap stages,voices


A look of the game folder

[](https://ibb.co/1X2x4Cn)


Thank you very much
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-29T13:52:05+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

As for PCS files, we have already documentation on this [http://wiki.xentax.com/index.php/King_O ... CS_TEXLIST](http://wiki.xentax.com/index.php/King_Of_Fighters_XIII_PCS_TEXLIST)
Images can be extracted using Game Extractor and then vieved in texture finder [https://i.imgur.com/RxXg0T4.png](https://i.imgur.com/RxXg0T4.png)

As for BNK files, they seems to be standard Wwise SoundBanks [http://wiki.xentax.com/index.php/Wwise_ ... nk_(*.bnk)](http://wiki.xentax.com/index.php/Wwise_SoundBank_%28*.bnk%29)
and they can be played in foobar without any issues [https://i.imgur.com/RNIwz4s.png](https://i.imgur.com/RNIwz4s.png)

As for LUA files, they probably contain values you are looking for, but they seems to be encrypted.
Someone needs to figure out encryption method before doing any changes in these files will be possible.
## Post #5
- Username: GilgameshKOFGC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 29, 2021 4:46 am
- Post datetime: 2021-03-29T19:38:54+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

I have found that on another forum

> .luas are XORed with 0x66 key and compiled. I used unluac (unluac_2015_06_13.jar) for decompiling.
## Post #6
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-29T20:52:03+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

Ok, yeah, in this case it is easy.

First you need to use xor tool from aluigi's site [http://aluigi.altervista.org/mytoolz/xor.zip](http://aluigi.altervista.org/mytoolz/xor.zip)

For example:

```
xor.exe game_config.lua game_config.lua_new 0x66
```


Then you just need to decompile it with this decompiler [https://sourceforge.net/projects/unluac ... r/download](https://sourceforge.net/projects/unluac/files/Unstable/unluac_2015_06_13.jar/download)

For example:

```
java -jar unluac_2015_06_13.jar game_config.lua_new > game_config.lua_out
```


And then you will see decompiled code [https://i.imgur.com/TA0Q3z1.png](https://i.imgur.com/TA0Q3z1.png)
## Post #7
- Username: GilgameshKOFGC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 29, 2021 4:46 am
- Post datetime: 2021-03-31T10:42:32+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

I am sorry to be such a mess but i don't know how to use xor tools, if i undestood well it runs on python (which i have absolutely no knowledge) i tried to download it and inserted your code but it does nothing

For .pcs when i use game extractor and i try to open some random background or character files i get some unamedfile00001.l8 or .dxt file

The other post for the same game on Zenhax [https://zenhax.com/viewtopic.php?f=12&t ... f+fighters](https://zenhax.com/viewtopic.php?f=12&t=4899&hilit=king+of+fighters)

Thanks
## Post #8
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-31T11:25:16+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

> i don't know how to use xor tools, if i undestood well it runs on python (which i have absolutely no knowledge) i tried to download it and inserted your code but it does nothing
This tool fro aluigi is compiled C program and can be run from command line.
Please google something like "how to run command line program" and then follow the tutorial.


> i get some unamedfile00001.l8 or .dxt file
Yes, those are unpacked image files and they can be viewed in texture finder or in raw texture cooker with the proper settings.
I have posted one example of the correct settings in the previous post. Just look at the file extension to determine pixel format.
## Post #9
- Username: GilgameshKOFGC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 29, 2021 4:46 am
- Post datetime: 2021-03-31T16:03:34+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

I managed to recreate the .lua you did + one another decompiling

thanks you very much that's 1st big step for me

what is the procedure when i modified my file to recompile it and put it in my game ?
## Post #10
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-31T16:15:10+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

I would say that you need to find a compiler that will generate the same output as the original and after compiling you should xor your lua file with 0x66 and replace the original file.
But I'm not sure if it is 100% correct way, I've never done any lua compiling.
## Post #11
- Username: GilgameshKOFGC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 29, 2021 4:46 am
- Post datetime: 2021-03-31T16:32:44+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

Thanks,

By the way is there a way to mass xor then decompile all my .lua files?
## Post #12
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-03-31T20:17:31+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

Yeah, you could use BAT script for that.
Here are some example scripts:
[https://github.com/bartlomiejduda/Tools ... FOLDER.BAT](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/DO%20FOR%20ALL%20FILES%20IN%20FOLDER.BAT)
[https://github.com/bartlomiejduda/Tools ... mplate.bat](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/TEMPLATES/bat_script_template.bat)
## Post #13
- Username: GilgameshKOFGC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Mar 29, 2021 4:46 am
- Post datetime: 2021-04-02T09:22:13+00:00
- Post Title: The King of Fighters XIII - PCS, BNK and LUA files

Hi

I manage to xor and unluac with 0x66 key the .lua files for the game i want to mod but i don't know how to recompile them and put them in my game.

I have almost zero experience in modding / compiling / decompiling.

Thanks for your time
