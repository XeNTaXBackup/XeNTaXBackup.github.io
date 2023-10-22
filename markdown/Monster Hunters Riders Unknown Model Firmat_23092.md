## Post #1
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-11-30T23:47:59+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

I was surprised the data of game it is not rooted on the phone, so I give a look at it for see the data is easy to access, but it has no format or clue to what format could it be.

So, I come here for see what can you guys find out, of course with two examples:

[https://drive.google.com/file/d/1W44cag ... sp=sharing](https://drive.google.com/file/d/1W44cagXQcIUDHGGEySqMWynGt0fQPrw-/view?usp=sharing)

One character and monster folder of what I think it could be the model.

Hope anyone got luck with it.
## Post #2
- Username: Silvris
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jul 16, 2019 5:44 am
- Post datetime: 2020-12-01T08:27:05+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

It's encrypted Unity asset bundles, not sure on the decryption method but I know someone was able to decrypt it. The encryption is actually rather recent, used to be unencrypted.
## Post #3
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2020-12-02T03:09:31+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

It's simple xor on header part of model and atlas files (the rest is not encrypted). Key is dynamic for every file, probably derived from hash128 value, included in manifests. Here is workaround, which should work fine too. Tested on a few assets from 2.03 version of the game.


 MHR_decrypt.zip
(414 Bytes) Downloaded 52 times
## Post #4
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-12-03T01:43:09+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

Wow! It actually works!! Thank so much!!
## Post #5
- Username: CuchiPol
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 29, 2020 11:29 pm
- Post datetime: 2020-12-05T05:54:50+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

Hello, how do I open the file after using quickbms?

it only gives me a "filename_decrypted" file. Thanks
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2020-12-05T13:05:17+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

They are unity bundles, so they're compatible with any unity tools like AssetStudio.
## Post #7
- Username: CuchiPol
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 29, 2020 11:29 pm
- Post datetime: 2020-12-07T13:22:49+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

Hello again, I've managed to extract the bundle using uTinyRipper but it only gives me a a bunch of .asset, .meta, and .prefab files. Just want to get some 3d models. I also got the texture from TinyRipper
## Post #8
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2020-12-07T21:36:59+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

> Reply from CuchiPol ↑Mon Dec 07, 2020 9:22 pm at Mon Dec 07, 2020 9:22 pm
>
> 
Hello again, I've managed to extract the bundle using uTinyRipper but it only gives me a a bunch of .asset, .meta, and .prefab files. Just want to get some 3d models. I also got the texture from TinyRipper
Use:

> Reply from Spiritovod ↑Sat Dec 05, 2020 9:05 pm at Sat Dec 05, 2020 9:05 pm
>
> 
They are unity bundles, so they're compatible with any unity tools like AssetStudio.


Did that way and I was able to unpack models with textures and bones.
## Post #9
- Username: CuchiPol
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 29, 2020 11:29 pm
- Post datetime: 2020-12-08T12:32:14+00:00
- Post Title: Monster Hunters Riders Unknown Model Firmat

Nice! I've managed to get the 3d models with that is fbx - with bones. Thanks! Another question. What program do I need to use in order to open the obb/data folder of MHRiders game? I tried winrar but its giving me an error.
