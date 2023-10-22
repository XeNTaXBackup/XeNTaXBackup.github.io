## Post #1
- Username: IAmASillyCat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 24, 2022 3:21 am
- Post datetime: 2022-07-23T20:55:31+00:00
- Post Title: [Unity3D] Kemono Friends: Kingdom - Unpacking Unity Asset Bundles

First post, so you may yell at me for being a newbie who is, in fact, new to all of this. Get it off your chest if you need to. I totally understand.

...I mean, hello! 

I've been scratching my head for the past few months trying to figure out any way to unpack the Unity asset bundles of Kemono Friends: Kingdom. Just spurts of me attempting different things here and there to not much avail.

Websites:
[https://kfk.qyzlgame.com/](https://kfk.qyzlgame.com/)
[https://kfksgmy.zlongame.com/](https://kfksgmy.zlongame.com/)
(I believe there's two different publishers for both inside Mainland China and outside of it, such as with Hong Kong, Macau, Singapore, etc.)

I tried doing what you average Joe would do and tried running the game through both AssetStudio and AssetRipper... to no avail. That's when I figured the game might be encrypted somehow. Stumbling around the inside of the Unity files I've come across the fact that the game's actual DLL files themselves aren't encrypted. General "remove UnityFS headers" type BMS scripts didn't fare much of a chance, either. This is where I gave up a month or so ago.

[viewtopic.php?f=10&t=25304#p184636](https://forum.xentax.com/viewtopic.php?f=10&t=25304#p184636)
Today, I stumbled across this, which is another game published by the same publisher as KFK, and though certain key things are different (such as the game using packets to store files), most of what Ares Chronicles does seems to apply to KFK as well.
Perhaps barncastle's tool with some reworking could do the trick? Unfortunately, I'm unfamiliar with C#, so I don't have the merit to try on my own.
[https://github.com/barncastle/AresChroniclesDumper](https://github.com/barncastle/AresChroniclesDumper)

However, I won't sugarcoat the fact that I don't have a full-on grasp as to whether or not that's truly what's going on. If only I was more familiar with all of this...

Any help is appreciated and I thank you all for your time.
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-07-25T03:13:54+00:00
- Post Title: [Unity3D] Kemono Friends: Kingdom - Unpacking Unity Asset Bundles

This method is different from AresChronicles.

0x1000byte is XORed with a non-repeating key. The keys seem to be different for each file, but there are obvious similarities. It seems that the shift is done using some kind of rule.

*The game appears to be 2D-only and does not include 3D models.
## Post #3
- Username: IAmASillyCat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 24, 2022 3:21 am
- Post datetime: 2022-07-28T19:08:00+00:00
- Post Title: [Unity3D] Kemono Friends: Kingdom - Unpacking Unity Asset Bundles

> Reply from einherjar007 ↑Mon Jul 25, 2022 11:13 am at Mon Jul 25, 2022 11:13 am
>
> 
*The game appears to be 2D-only and does not include 3D models.

I apologize for my mistake! I was under the assumption that "Unity3D" just referred to Unity as an engine and the fact that it has 3D capabilities. I hadn't seen any "Unity2D" posts so I figured this was just the go-to. Thank you for letting me know; I'm sorry I cannot change the title.

> Reply from einherjar007 ↑Mon Jul 25, 2022 11:13 am at Mon Jul 25, 2022 11:13 am
>
> 
This method is different from AresChronicles.

0x1000byte is XORed with a non-repeating key. The keys seem to be different for each file, but there are obvious similarities. It seems that the shift is done using some kind of rule.

It really seems like the developers wanted to encrypt it as much as reasonably possible, huh? Every file being different seems like a message honestly lol. This is definitely beyond my own scope...
