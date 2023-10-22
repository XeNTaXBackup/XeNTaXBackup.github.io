## Post #1
- Username: apple896321
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 19, 2018 2:07 am
- Post datetime: 2018-03-09T05:25:17+00:00
- Post Title: [Request] Primal Prey

Hello there, I got these models from Primal Prey, but I have no idea on how to convert them since my knowledge on this is very very limited. 

In the Carnivores Gamepedia as we have primal prey listed in the wiki so having these model files documented could help the wiki
[https://carnivores.gamepedia.com/Carnivores_Wiki](https://carnivores.gamepedia.com/Carnivores_Wiki)

Here are the sample files, but the thing is I don't know which one is the model file, so I just put all three of them. All you need to know that both of these files, .SSM and .STX, are important to each other

[Fish.SSM](http://www.mediafire.com/file/0a52enndbip2sqc/fish.SSM//url)

[Fish.STX](http://www.mediafire.com/file/pgxqhpwq3qerm0w/fish.stx//url)

[Fish_A.STX](http://www.mediafire.com/file/36mm4lvti8it73x/fish_a.stx//url)

If you somehow converted them, plz convert the rest of these models

[Animal](http://www.mediafire.com/file/g9ynxsov3pejnju/animals.zip//url)

[Trees And Wildlife](http://www.mediafire.com/file/kpfhonfp0y8v3za/trees.zip//url)

[Weapons](http://www.mediafire.com/file/ruavksr8102sxgw/weapons.zip//url)

[Worldbuilding Models](http://www.mediafire.com/file/7c0yszjis3cg2h3/world%20models.zip//url)

Here's the full game
[Primal Prey](http://www.mediafire.com/file/tkn66srqzn2mb0x/Primal+Prey.zip//url)

Also Note: that this game is a decade old, so it might not work on your pc if you do want to play it

Here's a rough scheme of the structure of the .stx files from Machf:

```
4 bytes
4 bytes
4 bytes
4 bytes
4 bytes
4 bytes
4 bytes
4 bytes: #variable-value pairs
4 bytes
STEX
2 bytes: variable string length
variable string
2 bytes: value string legth
value string
...
2 bytes: string length
string

22 4-byte values

palette (256 entries, 4 bytes per entry)

2 bytes: #variable-value pairs
2 bytes: variable string length
variable string
2 bytes: value string legth
value string
...

7 4-byte values

offset1, 4 bytes
offset2, 4 bytes
@offset1: 48 bytes
@offset2: 16 bytes
```


If you guys need any further info on the files, I will do the best I can to get the info.
## Post #2
- Username: vhuser2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Apr 19, 2023 5:40 am
- Post datetime: 2023-04-18T21:44:57+00:00
- Post Title: [Request] Primal Prey

Hi! Im currently working on a remake for Primal Prey in UE5, but Im having a lot of problems ripping those models. I just manage to get all the equipment, and just two dinosaurs. I suppose there is a better way of doing it, than using the NinjaRipper tool. But Im not familiar with the files type or how to get data from them.

At the moment there is a discussion in this link: [https://www.tapatalk.com/groups/the_car ... 0-s40.html](https://www.tapatalk.com/groups/the_carnivores_saga/primal-prey-modding-theard-t500-s40.html)

But I havent had a reply, lets hope that someone understands this a lil bit better. So that we can learn a thing or two.

PD: I think I will not be able to get the animations :C, but I really hope so
