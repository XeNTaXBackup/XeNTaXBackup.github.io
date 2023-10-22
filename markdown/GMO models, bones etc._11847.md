## Post #1
- Username: Lyserg1260
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 18, 2014 7:28 pm
- Post datetime: 2014-08-27T00:38:09+00:00
- Post Title: GMO models, bones etc.

I have a question about GMO models used in 2 games: "Tenchu San Portable" and "Tenchu Kurenai Portable".
They are on similiar engine, it's almost the same. I was trying to put San models to Kurenai or Kurenai models to San.

If i put Kurenai model to San game crashes
If i put San model to Kurenai it works...almost, there are some problems with legs.

It should look like this (Tenchu San original model):
[http://i.imgur.com/bqH73iO.png](http://i.imgur.com/bqH73iO.png)

But it looks like this(This model putted into Kurenai):
[http://i.imgur.com/SymyJ2y.png](http://i.imgur.com/SymyJ2y.png)

Maybe it is about models construction?
San models have 32 bones
Kurenai models have 28 bones

Maybe these "long legs" are cause because of additional bones or something like that?
San models have more bones so they work in Kurenai but are glitched.
Kurenai models have less bones so they don't work in San because they don't have enough bones.
Do you think it is possible? If it's because of bones, can it be fixed somehow? By removing/adding bones?

Do you have any idea? Just look at this, there are 2 almost the same models:
[http://i.imgur.com/yP6cACS.png](http://i.imgur.com/yP6cACS.png)
There have to be a way, because San models are almost working in Kurenai...

I've uploaded these 2 models:
[https://www.mediafire.com/folder/q0uejjldqpogm/](https://www.mediafire.com/folder/q0uejjldqpogm/)

Please help if you can, it would be awesome to have some of Kurenai/San characters in San/Kurenai.
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-08-27T10:18:21+00:00
- Post Title: GMO models, bones etc.

Did you take into account the weighting of the bones?

The weighting defines what parts of the mesh are affected by the bone, I'd suggest taking it into 3d software first to check the weighting for the bones.
## Post #3
- Username: Lyserg1260
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 18, 2014 7:28 pm
- Post datetime: 2014-08-27T10:26:40+00:00
- Post Title: GMO models, bones etc.

I don't understand. Do you mean this?
[http://i.imgur.com/KWHrYVi.png](http://i.imgur.com/KWHrYVi.png)
And is there a way to just put San/Kurenai bones settings to Kurenai/San model?
## Post #4
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2014-08-27T17:48:02+00:00
- Post Title: GMO models, bones etc.

> Reply from Lyserg1260
>
> I don't understand. Do you mean this?
http://i.imgur.com/KWHrYVi.png
And is there a way to just put San/Kurenai bones settings to Kurenai/San model?

Thats just the bones being shown, You'll want to take the models and bones into a 3d software if you want to swap the bones.

The polycount of the 2 is completely different, as is the number of bones, which means the bone influence is also completely different and thats what you'll want to fix.
## Post #5
- Username: Lyserg1260
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 18, 2014 7:28 pm
- Post datetime: 2014-08-27T18:01:15+00:00
- Post Title: GMO models, bones etc.

You mean 3dsmax, blender etc.? I can export GMO models to other format, but there is no way (or i don't know how) to convert them back to GMO.
## Post #6
- Username: Lyserg1260
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 18, 2014 7:28 pm
- Post datetime: 2014-08-27T19:44:52+00:00
- Post Title: GMO models, bones etc.

I've made progress. I've managed to edit Kurenai (28 bones) model and give it San (32 bones) structure, so it now has 32 bones and model looks very good, but there are no textures at all. Game doesn't crash (!) when i put this model, but it is invisible (because there are no textures) so i think it works. So what now? How to get that textures? They are still in this model file.

Kurenai model [28 bones] It is how model shoud look like:
[http://i.imgur.com/djnjH8s.png](http://i.imgur.com/djnjH8s.png)

San model [32 bones] used to give Kurenai model San bones structure:
[http://i.imgur.com/3aYJyxp.png](http://i.imgur.com/3aYJyxp.png)

Finished model [32 bones] San bones on Kurenai model:
[http://i.imgur.com/KfywVB0.png](http://i.imgur.com/KfywVB0.png)

As you see model is good, but there are no textures. Any ideas?
btw. It also shows that this model has 1 mesh, 0 textures, 1 material. It should have 4 mesher, 4 textures, 4 materials.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-30T12:57:20+00:00
- Post Title: GMO models, bones etc.

> Reply from Lyserg1260
>
> As you see model is good, but there are no textures. Any ideas?Since you didn't write what you did exactly there's only wild guessing.
This gmo format seems to be somewhat tolerant when inserting data.
For example I added 0x70 bytes bone data to Kurenai.GMO (without changing counts or offsets) and it loaded with textures.
...
  29 "a20-jnt-bone"  28
  30 "a21-jnt-bone"  29
  31 "EX-02-bone"  30
  32 "EX-0x-bone"  30 -- additional bone

If you sent me your changed Kurenai I could have a look at.
## Post #8
- Username: Lyserg1260
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Aug 18, 2014 7:28 pm
- Post datetime: 2014-08-30T14:31:34+00:00
- Post Title: GMO models, bones etc.

Hey, i've actually fixed that yesterday. Converting is very easy, but finding values was hard. You just need to replace bones (or you even don't have to do it, but model will look glitched in viewer, but it will look good in game, that's crazy) and change few values. Converting San models to Kurenai was little harder because there were problems with feet but i've managed to fix that too.
