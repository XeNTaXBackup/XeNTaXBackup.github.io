## Post #1
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-01-24T15:19:48+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

Hey there,

I was recently looking at the files from the Prince of Persia HD Trilogy for PS3. They all have normal BF files that are easily extractable with a program called Persian Rug made for the original PoP games, but unlike the original PoP games, they also have separate BF files for textures and audio. They all start with "[ Gear BigFile ]" so I assumed it was the Yeti Engine and tried to use [aluigi's script](http://aluigi.altervista.org/papers/bms/yeti_gear.bms) for the Yeti Engine. It doesn't entirely work on this though, so I uploaded a cut of one of the files here. I hope to see this format cracked soon. 
*Snip
Just tell me if you need any other files, a bigger cut or an entire archive. 

Thanks!
Droolie.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-24T20:17:44+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

check if this quickbms script works:
[http://aluigi.org/papers/bms/yeti_gear.bms](http://aluigi.org/papers/bms/yeti_gear.bms)
## Post #3
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-01-24T22:26:59+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2012-05-16T02:30:08+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

For the record (unfortunately have to resurrect a dead thread to do it) I've figured this one out. It's nearly the same as aluigi's BMS script but with deflate compression. Here's a Python script to do the extraction. The script also creates a _stripped version of the extracted file which works in DecUbiSnd without the clicks at the end of each track.

[http://zenchreal.bitbucket.org/game/pop-hd-trilogy.py](http://zenchreal.bitbucket.org/game/pop-hd-trilogy.py)

Edit: changed link
## Post #5
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-05-17T11:55:08+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

> Reply from Zench
>
> For the record (unfortunately have to resurrect a dead thread to do it) I've figured this one out. It's nearly the same as aluigi's BMS script but with deflate compression. Here's a Python script to do the extraction. The script also creates a _stripped version of the extracted file which works in DecUbiSnd without the clicks at the end of each track.

http://zenchreal.bitbucket.org/game/pop-hd-trilogy.py

Edit: changed link
It wasn't completely dead, I was still waiting for a reply. Thanks a lot Zench, this works great as always! 
I'm a bit disappointed to see that the audio is only 28kHz though (at least for Sands of Time, haven't checked the other games yet)... I expected more when I saw that the PS3 start screen sound was in 48kHz. But anyway, great work! ^^
## Post #6
- Username: MoriyaMug
- Rank: Banned
- Number of posts: 7
- Joined date: Sat Sep 11, 2010 12:03 am
- Post datetime: 2012-05-27T01:37:47+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

Sorry to bring this back to life, but I was wondering if anyone ever tried pulling the Two Thrones music. If so, is it CD-quality? All of the other releases are only 24kHz, so I was hoping...

If no one's checked, can someone give me some assistance with checking for myself?
## Post #7
- Username: Droolie
- Rank: veteran
- Number of posts: 114
- Joined date: Fri Aug 19, 2005 11:31 pm
- Post datetime: 2012-05-27T21:17:35+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

> Reply from MoriyaMug
>
> Sorry to bring this back to life, but I was wondering if anyone ever tried pulling the Two Thrones music. If so, is it CD-quality? All of the other releases are only 24kHz, so I was hoping...

If no one's checked, can someone give me some assistance with checking for myself?
Nope, I've checked and the T2T music is 24khz in the HD version too :/
## Post #8
- Username: MoriyaMug
- Rank: Banned
- Number of posts: 7
- Joined date: Sat Sep 11, 2010 12:03 am
- Post datetime: 2012-05-27T22:28:08+00:00
- Post Title: [SOLVED] Prince of Persia HD Trilogy (PS3) - *.BF

Damn it! Ah, well. Thanks for your reply. I guess I can finally delete all this stuff.
