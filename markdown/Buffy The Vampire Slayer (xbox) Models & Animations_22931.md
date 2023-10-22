## Post #1
- Username: PRP1986
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Mar 26, 2018 1:18 am
- Post datetime: 2020-11-01T14:36:21+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

Hi, 

I was was wondering whether any of you talented folk would be interested in taking a look at the model and animation formats for this game.

The game uses the Slayer Engine, which was also used for Indiana Jones, Star Wars Episode 3 and Silent Hill Homecoming. The PAK container files and the texture format (mtx) has already been solved a few years back ([https://zenhax.com/viewtopic.php?f=9&t=7630&hilit=buffy](https://zenhax.com/viewtopic.php?f=9&t=7630&hilit=buffy)

I attach samples of the models and animations if anyone is interested in looking into them - the models are .msh and the animations are .boneanim.

Thanks in advance!

Samples: [https://1drv.ms/u/s!Amua2WvdGonP_EfnLr_ ... w?e=yrJFTU](https://1drv.ms/u/s!Amua2WvdGonP_EfnLr_zCmDO-9Hw?e=yrJFTU)
## Post #2
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2020-11-02T17:09:32+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

Mark Ecko's Getting Up also uses the slayer engine, and shakotay2 figured out the .msh model files for me 

[viewtopic.php?f=16&t=21138](https://forum.xentax.com/viewtopic.php?f=16&t=21138)

Maybe this helps you
## Post #3
- Username: Decemberius
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 01, 2020 12:38 pm
- Post datetime: 2020-11-02T20:06:41+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

Any idea how to convert those animations so they can be used in Indiana Jones and the Emperor's Tomb?

Both games are using Slayer engine, and both are .boneanim.
## Post #4
- Username: PRP1986
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Mar 26, 2018 1:18 am
- Post datetime: 2020-11-04T19:30:24+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

@Henchman - Thank you, I will take a look. I was hoping that I would be able to obtain the rigged mesh, which I don't think I would be able to do via Hex2Obj (I may be wrong on that), but it should be useful to static meshes. 

@Decemberius - I don't think that is possible, unfortunately the animation formats for either game has not been reverse engineered yet. Also I am not sure how easy it would be to mod Indiana Jones in terms of adding new content, I think there are mesh swap mods, but I belive that these are achieved via debug menus rather than injecting new assets into the game.

If anyone is interested in looking into reverse engineering these formats I would happily pay them for their time, as I appreciate, it's not something tht can be done overnight!
## Post #5
- Username: Decemberius
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 01, 2020 12:38 pm
- Post datetime: 2020-11-06T03:34:46+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

I did a small mod [vids on Youtube and other posts], and i can play as Buffy, i've managed to swap some animations, so she can kick now, a few kick combos added.
I know it's possible to insert enemies, and objects into existing levels, from other Indiana Jones levels, and there are some vampire like enemies, mesh swapping works, so i also have Siren demons swimming in water, instead of crocodiles with different animations. It looks really cool.
Buffy levels also work on PC Indiana Jones, but i guess You all know that already.
I have some ideas as to how Buffy port could work.
Of course without her super powered slo-mo moves working the same way, but some of those animations are still there, in Indiana Jones, some characters are using them, like air spin kick, or super punch and a few others.

All i need is to learn how to mod the game, the same way as modders from Youtube and MODDB for example Dragon Pearl's mod. I'm guessing it has something to do with game scripts? Or is it something in the level files that contain this information?

Buffy levels could be incorporated into Indy's levelset, placing some enemies, and key / lever objects would work, even in this state, a couple of levels can be completed.

I need to replace enemies[Indiana Jones enemies from later levels, to any other level in the game], objects, swap some textures, like fonts, and logos, HUD, music isn't a problem, mostly, just those hellish rpe files that contain dialogue.

I'm really a noob with this, but i've waited almost 20 years for this possibility to happen, so i'll keep trying, and trying.
I can swap enemies models, i can change their animations, so most enemies will act vampire like [Indiana Jones has vampire like enemies with appropriate animations], if that makes sense, i think i know how to make Buffy use "stake" weapon, and there are a few animations that could be used as a substitute.
But i'm not so powerful, and skilled when it comes to altering, and moding games to such extent, i'm just really enthusiastic   
And that's why i'm here, to ask for some help. 

I've also discovered that Indiana Jones flamethrower is actually altered Holy Water Soaker from Buffy.
And Indy game probably contains lots of leftovers from Buffy, and Buffy files are containing unused weapons, like Bone for stabbing enemies, coat rack, candle stand or something like that, and Indy uses the same crossbow, with different mesh and texture. And there are many other cool secrets in both games.

Oh, and one more thing

I'm not sure if this helps, but i think that some old games, might be using / reusing the same stuff as Buffy, in one form or another, whether it's texture, or sound effect, or animation.

1. Xena Warrior Princess [PSX 1999]

2. American Mc Gee - Alice [PC 2000]

3. Clive Barker's Undying [PC 2001]

4. Harry Potter and the Philosopher's Stone [PC 2001]

5. Harry Potter and the Chamber Of Secrets [PC 2002]

Each game was released by EA games.

There are many similarities in all of those games, not on first glance, but i've replayed them all, many times, so i know what i'm talking about.

I believe that Xena game engine could be the early blueprint for the Slayer engine.
I might be wrong though, but if anyone here is interested in my theories, i can share my ideas.

I'm writing this, because, maybe, just maybe this could help in one way or another, in porting Buffy The Vampire Slayer to the PC.
## Post #6
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-11-08T05:25:37+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

I don't know how to get the faces for this mesh.



buffybronze(base).png (33.26 KiB) Viewed 217 times
## Post #7
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-11-08T05:37:08+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

The only mesh I can get with the correct faces, there are other sub-meshes in the file.



buffybronze(base).png (23.85 KiB) Viewed 217 times



Maybe in position 0x4162C it is the bone count, so it has 10 bytes to store the name of the bones, then it has the data of the bones and then 2 bytes to store the parent index, but I could be wrong.
## Post #8
- Username: PRP1986
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Mar 26, 2018 1:18 am
- Post datetime: 2020-11-08T22:32:09+00:00
- Post Title: Buffy The Vampire Slayer (xbox) Models & Animations

Thanks for the progress so far Reh
