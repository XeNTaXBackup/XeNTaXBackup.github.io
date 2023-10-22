## Post #1
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-10-13T01:02:18+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

I have expend the last hours trying to get models from this game but so far I have only found a way to open the texture format (.gt1)
Every Linkdata the game use I have unpack but it unpack the whole data as a whole without folder, making more hard to pin-point which is which.
After unpack, it unpack in different formats (beside the texture one): dat, sdb, _m1, and nfc.
I have Google each for find nothing about those formats. And even opening them on Hex doesn't give clues about what are them (aside from lack of knowledge using Hex).

I made a sample of each of those formats with include a .bms that worked for unpack the game data and a .py that open the texture on Noesis without any problem so far.

[https://mega.nz/file/8f8TTBLS#Xm0hAw4iB ... IRraG1OfaY](https://mega.nz/file/8f8TTBLS#Xm0hAw4iBlJqZY1PfUY-Xku44G3zkfHXCIRraG1OfaY)

If anyone with more knowledge or experience want to give a try or know how unpack models from that game will be of a real help, because I haven't found nothing about it in several pages.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-13T11:03:35+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

> Reply from Darkhowlings ↑Thu Oct 13, 2022 9:02 am at Thu Oct 13, 2022 9:02 am
>
> And even opening them on Hex doesn't give clues about what are them (aside from lack of knowledge using Hex)..nfc mesh format looks simple:
.



0172-nfc.jpg (133.84 KiB) Viewed 143 times

(maybe one superfluous face...)
## Post #3
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-10-13T17:05:14+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

> Reply from shakotay2 ↑Thu Oct 13, 2022 7:03 pm at Thu Oct 13, 2022 7:03 pm
>
> 
Darkhowlings wrote: ↑Thu Oct 13, 2022 9:02 amAnd even opening them on Hex doesn't give clues about what are them (aside from lack of knowledge using Hex)..nfc mesh format looks simple:
.
0172-nfc.jpg(maybe one superfluous face...)

Thanks for take the time to look on the files. Even do I never learned or have the brain for use your tool... but it help for find out at least what archive format is what and if the method I unpack the game data is the correct one.
I literally don't know which is which on the game data for as you may have see each data is named in number and all in the same folder. The only different is the extension.
## Post #4
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-10-16T19:02:55+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

An small update and a reason for give up on this game:

I couldn't find anyway for get the models with bones. But while searching, I read that people several years ago did unpack models from the game but end on rigging them for tools like XNALara: [EXAMPLE](https://www.deviantart.com/armachamcorp/art/Samurai-Warriors-4-Kai-459499409) and for what I read on the comments, they used NinjaRipper for get the models.

I end doing the same, but NinjaRipper doesn't extract perfectly the diffuse texture. Lucky among the data I share on the link on the first post, they is one plugging for see the texture on Noesis and can be used for fix the diffuse texture by searching the character texture in the game data.

And there you've people: They is no way for get models with actual bones from this, unless you use NinjaRipper and have the patient for rigging the model from 0.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-10-16T19:50:10+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

> Reply from Darkhowlings ↑Mon Oct 17, 2022 3:02 am at Mon Oct 17, 2022 3:02 am
>
> 
An small update and a reason for give up on this game:A samurai doesn't give up. Never.  

Anyways, found some mesh in a _m1 file:
.



051c _m1.jpg (178.18 KiB) Viewed 104 times
## Post #6
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-10-16T20:57:49+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

> Reply from shakotay2 ↑Mon Oct 17, 2022 3:50 am at Mon Oct 17, 2022 3:50 am
>
> 
Darkhowlings wrote: ↑Mon Oct 17, 2022 3:02 am
An small update and a reason for give up on this game:A samurai doesn't give up. Never.  

Anyways, found some mesh in a _m1 file:
.
051c _m1.jpg

I'm not a Samurai and I know nothing how hex work as you do for use that tool, even less creating scrip like the rest here.
I just give up and at least give a way for get the models somehow for anyone that read in the far future.
## Post #7
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-10-21T03:17:06+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

> Reply from shakotay2 ↑Mon Oct 17, 2022 3:50 am at Mon Oct 17, 2022 3:50 am
>
> 
A samurai doesn't give up. Never.
like 

> Reply from Darkhowlings ↑Mon Oct 17, 2022 4:57 am at Mon Oct 17, 2022 4:57 am
>
> 
I'm not a Samurai
it's never too late to be  


*(without format parsing, should not be considered as a full-fledged plugin. search for the keyword "cRefl". if it is not there, then it will not open, for example, from all provided "0000000000000172.nfc" does not have this)
[fmt_m1_nfc.zip](https://xentaxbackup.github.io/file/22943_fmt_m1_nfc.zip)
## Post #8
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-10-21T20:38:21+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

> Reply from Durik256 ↑Fri Oct 21, 2022 11:17 am at Fri Oct 21, 2022 11:17 am
>
> 
it's never too late to be  


*(without format parsing, should not be considered as a full-fledged plugin. search for the keyword "cRefl". if it is not there, then it will not open, for example, from all provided "0000000000000172.nfc" does not have this)
That was unexpected. Thanks? I gonna give a try after re-installing the game because I uninstalled it after give up & use NinjaRipper.
## Post #9
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-10-21T22:06:00+00:00
- Post Title: Samurai Warriors 4 unknow model format (Steam)

I believe Samurai Series can be loaded with Joschuka's g1m plugin.
If remove the scrap data at the top, you can probably load it.
