## Post #1
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-07-21T08:34:10+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

It's a very cool game.

Its model is incredible.

But he can not find the file unpack tool

Who can help me? Thank you very much.

My email:  Mod Edit: Sensitive information removed
DL page:[http://wuxia.qq.com/download.shtml](http://wuxia.qq.com/download.shtml)



199_150321_d991c.jpg (46.18 KiB) Viewed 633 times
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-21T13:43:07+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

extract vfs with bms script
[http://zenhax.com/viewtopic.php?p=1420#p1420](http://zenhax.com/viewtopic.php?p=1420#p1420)

extract sfc with bms script
[http://zenhax.com/viewtopic.php?p=1427#p1427](http://zenhax.com/viewtopic.php?p=1427#p1427)

open models in 3ds max with max script
[viewtopic.php?f=16&t=12196](http://forum.xentax.com/viewtopic.php?f=16&t=12196)
maxscript for 2nd mesh type?
[viewtopic.php?p=100934#p100934](http://forum.xentax.com/viewtopic.php?p=100934#p100934)
## Post #3
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-07-22T05:21:51+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

> Reply from AceWell
>
> extract vfs with bms script
http://zenhax.com/viewtopic.php?p=1420#p1420

extract sfc with bms script
http://zenhax.com/viewtopic.php?p=1427#p1427

open models in 3ds max with max script
viewtopic.php?f=16&t=12196
maxscript for 2nd mesh type?
viewtopic.php?p=100934#p100934

thank you very much indeed

Your work is great.

But there are some problems with this script.

The game's official offset and compression has been changed.

Cause this script is currently unable to extract a new model

Can you help me? thank you very much indeed
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-22T06:51:18+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

> Reply from m545891031
>
> But there are some problems with this script.
The game's official offset and compression has been changed.
Cause this script is currently unable to extract a new model
i'm afraid i don't know much about archive extractions, you will have to upload a nonworking sample and see if aluigi will update his bms script.
## Post #5
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-07-23T06:24:57+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

> Reply from AceWell
>
> m545891031 wrote:But there are some problems with this script.
The game's official offset and compression has been changed.
Cause this script is currently unable to extract a new model
i'm afraid i don't know much about archive extractions, you will have to upload a nonworking sample and see if aluigi will update his bms script.

Your BMS can unpack almost all files

But the model name is still unpack the 0000000.dat file

Although can be opened with the max script

But there seems to be some confusion.

Want to find the corresponding map is difficult

Don't know if you can solve the problem of name confusion?

I read the next post

The resource name seems to be random.

But I don't think so.

His naming rules must be somewhere on the client side.

Just don't know which file is responsible for name definition

Can you find it?

thank you very much indeed
## Post #6
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-07-24T05:36:02+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

> Reply from AceWell
>
> m545891031 wrote:But there are some problems with this script.
The game's official offset and compression has been changed.
Cause this script is currently unable to extract a new model
i'm afraid i don't know much about archive extractions, you will have to upload a nonworking sample and see if aluigi will update his bms script.

I think I found a very important document.

This will help unlock the name of the file.

But I can't untie

There are some Chinese in it.

I translated some of them:

```
NIF file naming rules are:
Multi stage model name
#
The naming rules for each stage are:
Table name after the number of stages
#STHN002_g
STHN002_g1 = STHN002_g
STHN002_g2 = STHN002_a
STHN002_g3 = STHN002_b
STHN002_g4 = STHN002_c
STHN002_g5 = STHN002_d
#WHb_004
WHb_0041 = WHb_004
WHb_0042 = WHb_004
WHb_0043 = WHb_004
WHb_0044 = WHb_004
WHb_0045 = WHb_004
#WN_014b
WN_014b1 = WN_014b
WN_014b2 = WN_014b
WN_014b3 = WN_014b
WN_014b4 = WN_014b
WN_014b5 = WN_014b_die
#WN_054
WN_0541 = WN_054
WN_0542 = WN_054
WN_0543 = WN_054
WN_0544 = WN_054
WN_0545 = WN_054
#WH (a) _054a
WH (a) _054a1 = _054a (a) WH
WH (a) _054a2 = _054a (a) WH
WH (a) _054a3 = _054a (a) WH
WH (a) _054a4 = _054a (a) WH
WH (a) _054a5 = _054_die (a) WH
```

Sample connection: [http://pan.baidu.com/s/1eSoIos6](http://pan.baidu.com/s/1eSoIos6) 
Extract password: t4h5
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-24T10:15:31+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

i don't know anything about this game and know very little about archive extractions,
you have to get aluigi to update his scripts to support any format changes you run into. 

You will have better chance of getting this done by posting your concerns in this thread 
[http://zenhax.com/viewtopic.php?f=9&t=3 ... 6f104b8c43](http://zenhax.com/viewtopic.php?f=9&t=327&sid=572f2c12df105e2cca97ac6f104b8c43)
## Post #8
- Username: m545891031
- Rank: advanced
- Number of posts: 52
- Joined date: Thu Jul 21, 2016 4:04 am
- Post datetime: 2016-07-24T10:36:38+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

> Reply from AceWell
>
> i don't know anything about this game and know very little about archive extractions,
you have to get aluigi to update his scripts to support any format changes you run into. 

You will have better chance of getting this done by posting your concerns in this thread 
http://zenhax.com/viewtopic.php?f=9&t=3 ... 6f104b8c43

I really want to register the website

But Confirmation code could not be displayed properly

Do not know Confirmation code and can not enter

Can you help me?
## Post #9
- Username: cs1104264393
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 08, 2023 10:11 am
- Post datetime: 2023-04-14T18:41:45+00:00
- Post Title: 《Moonlight Blade online》 MMO model extract  help .vfs .SFC

> Reply from m545891031 ↑Sun Jul 24, 2016 6:36 pm at Sun Jul 24, 2016 6:36 pm
>
> 
AceWell wrote:i don't know anything about this game and know very little about archive extractions,
you have to get aluigi to update his scripts to support any format changes you run into. 

You will have better chance of getting this done by posting your concerns in this thread 
http://zenhax.com/viewtopic.php?f=9&t=3 ... 6f104b8c43


I really want to register the website

But Confirmation code could not be displayed properly

Do not know Confirmation code and can not enter

Can you help me?

Hello friend, I am unable to register through ZenHAX. I am not sure if you have updated dzs_ Qq.bms and qq_ Sfc.bms, if you have any, please share with me. Thank you
