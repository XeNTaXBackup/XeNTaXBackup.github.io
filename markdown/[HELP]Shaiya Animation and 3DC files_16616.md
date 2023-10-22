## Post #1
- Username: Bondax
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 22, 2017 6:15 pm
- Post datetime: 2017-07-31T01:23:19+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

Hello community i am new here and i like to ask if some people still working about it

I like to know how to edit shaiya .ani files i can edit 3DC files but adding another armors to shaiya i cant make it.

Well my question is anyone have any script for Blender or 3ds Max the old one that i searched in HERE and HERE are not working

I added some examples for shaiya 3DC and ANI file 

thanks
[Examples.rar](https://xentaxbackup.github.io/file/13157_Examples.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-31T05:53:13+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

> Reply from Bondax
>
> Well my question is anyone have any script for Blender or 3ds Max the old one tjat i searched in forum y re not workingHello,
which old script are you talking about? Please provide a link to it.

If you want someone to care for your request a .3dc sample and a suiting animation file would be required, too.
## Post #3
- Username: Bondax
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 22, 2017 6:15 pm
- Post datetime: 2017-07-31T06:38:19+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

> Reply from shakotay2
>
> Bondax wrote:Well my question is anyone have any script for Blender or 3ds Max the old one tjat i searched in forum y re not workingHello,
which old script are you talking about? Please provide a link to it.

If you want someone to care for your request a .3dc sample and a suiting animation file would be required, too.

I edited my first post thank you
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-31T17:35:09+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

well, the ANI file looks doable (though there are some caveats) but we'll need the skeleton before.



Saiya_ANI - red.jpg (254.56 KiB) Viewed 268 times


I'm missing the parenting bone ids in the .3DC file so the smd file (with dummy bone names) I created is useless so far.

Is there any additional file that might contain them? (plus the bonenames, which are missing, too)
## Post #5
- Username: Bondax
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 22, 2017 6:15 pm
- Post datetime: 2017-07-31T18:30:56+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

> Reply from shakotay2
>
> well, the ANI file looks doable (though there are some caveats) but we'll need the skeleton before.
Saiya_ANI - red.jpg
I'm missing the parenting bone ids in the .3DC file so the smd file (with dummy bone names) I created is useless so far.

Is there any additional file that might contain them? (plus the bonenames, which are missing, too)
Ani files are linked with 3dc files so if u want i can send u all sets that how it looks like but the problems i can not find bones in them
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-07-31T20:33:55+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

all files that belong to that demf npc would be nice.

Maybe you could check the first 8 bytes of different npcs/upper bodies?
For demf_upper012.3DC it's 00000000 2C000000, that means this upper body has 44 bones.

If all upper bodies have the same bone count I could think of that they share the same skeleton (file).

edit: well, so they don't

I checked the matrix (bone positions) in 3 .3DC files belonging together and found the positions being identical (more or less) except for the first one:
demf_torso001 pos:  (0.0011791660217568278,)   (-1.1010617017745972,)   (1.189897460562861e-07,)
demf_hand001 pos:  (0.004173637367784977,)   (-1.1010617017745972,)   (8.601360690363435e-08,)
demf_lower001 pos:  (0.004173636436462402,)   (-1.1010617017745972,)   (6.226488125093965e-08,)
## Post #7
- Username: Bondax
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 22, 2017 6:15 pm
- Post datetime: 2017-07-31T21:17:22+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

> Reply from shakotay2
>
> all files that belong to that demf npc would be nice.

Maybe you could check the first 8 bytes of different npcs/upper bodies?
For demf_upper012.3DC it's 00000000 2C000000, that means this upper body has 44 bones.

If all upper bodies have the same bone count I could think of that they share the same skeleton (file).

This game have 4 races i have listed all bone informations

```
Warrior Male	: 44 Bones
Warrior Female 	: 51 Bones
Hunter Male	: 42 Bones
Hunter Female	: 55 Bones

Elves;

Archer Male	: 50 Bones
Archer Female	: 60 Bones
Mage Mal		: 58 Bones
Mage Female	: 61 Bones

Humans;

Fighter Male	: All Armor Sets Changes like 36(older) / 38(older) / 40 (older) / 72 (Newest)
Fighter Female	: 41 Bones
Priest Male	: 56 Bones
Priest Female	: 65 Bones

Vails;

Pagan Male	: 51 Bones
Pagan Female 	: 55 Bones
Assassin Male	: 36 bones older armors / 72 bones new Armors
Assassin Female	: 44 Bones
```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-05T17:48:12+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

found a skeleton in a test file with 76 bones (where 36 were named bonexx only)
issues with parenting and rotation (set to 0.0 0.0 0.0)



Shaiya_skel_76bones.jpg (106.93 KiB) Viewed 237 times
## Post #9
- Username: Bondax
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 22, 2017 6:15 pm
- Post datetime: 2017-08-08T05:53:34+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

> Reply from shakotay2
>
> found a skeleton in a test file with 76 bones (where 36 were named bonexx only)
issues with parenting and rotation (set to 0.0 0.0 0.0)
Shaiya_skel_76bones.jpg

I got it but can u send me import/ export things for blender?
Maybe i can check like that
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-09T19:17:53+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

dunno what you mean exactly - I used Blender Source Tools for import of an smd file
which I created from the afore mentioned test file. (I'll pm you the raw bone matrices from the test file.)
## Post #11
- Username: Bondax
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 22, 2017 6:15 pm
- Post datetime: 2017-08-13T10:03:54+00:00
- Post Title: [HELP]Shaiya Animation and 3DC files

> Reply from shakotay2
>
> dunno what you mean exactly - I used Blender Source Tools for import of an smd file
which I created from the afore mentioned test file. (I'll pm you the raw bone matrices from the test file.)
Thays wham i am asking i dont have thay source tool for shaiya files
