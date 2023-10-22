## Post #1
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-26T03:08:29+00:00
- Post Title: Subnautica .bank files

So I've literally tried every way I could think of to extract audio from the game Subnautica by Unknown Worlds, but to no avail. It seems the files are heavily locked down, the closest I got was using an FSB extractor tool (which I've unfortunately forgotten the name of) which could open the banks, but couldn't get the sound headers. Therefor, it was really no use since the sounds wouldn't play. Has anyone ever had experience successfully extracting sounds from a .bank file? Help would be very much appreciated!
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-26T12:52:39+00:00
- Post Title: Subnautica .bank files

unless we see some of these files, we can't help you
## Post #3
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-26T19:49:59+00:00
- Post Title: Subnautica .bank files

> Reply from daemon1
>
> unless we see some of these files, we can't help you
Right, here's one of the sound banks. [http://www.mediafire.com/download/5hesq ... yclops.rar](http://www.mediafire.com/download/5hesqn0yin8b9g6/Cyclops.rar)
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-26T20:11:44+00:00
- Post Title: Subnautica .bank files

Use this dumper (or cut it manually) to get FSB5 from bank file:

[http://zenhax.com/viewtopic.php?p=6506#p6506](http://zenhax.com/viewtopic.php?p=6506#p6506)

Then use [viewtopic.php?f=17&t=13615](http://forum.xentax.com/viewtopic.php?f=17&t=13615) to extract audio.
## Post #5
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-26T20:28:48+00:00
- Post Title: Subnautica .bank files

> Reply from daemon1
>
> Use this dumper (or cut it manually) to get FSB5 from bank file:

http://zenhax.com/viewtopic.php?p=6506#p6506

Then use viewtopic.php?f=17&t=13615 to extract audio.
The files are encrypted with a password of sorts unfortunately. I can't even dump the .bank files.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-26T20:55:23+00:00
- Post Title: Subnautica .bank files

> Reply from keithy
>
> daemon1 wrote:Use this dumper (or cut it manually) to get FSB5 from bank file:

http://zenhax.com/viewtopic.php?p=6506#p6506

Then use viewtopic.php?f=17&t=13615 to extract audio.
The files are encrypted with a password of sorts unfortunately. I can't even dump the .bank files.

No! No passwords. It is very simple FMOD container. I just decoded all the sounds from this bank. I told you how to do this.
## Post #7
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-26T21:52:27+00:00
- Post Title: Subnautica .bank files

> Reply from daemon1
>
> keithy wrote:daemon1 wrote:Use this dumper (or cut it manually) to get FSB5 from bank file:

http://zenhax.com/viewtopic.php?p=6506#p6506

Then use viewtopic.php?f=17&t=13615 to extract audio.
The files are encrypted with a password of sorts unfortunately. I can't even dump the .bank files.

No! No passwords. It is very simple FMOD container. I just decoded all the sounds from this bank. I told you how to do this.
Oh... what the hell? I can't get it to work. I must be doing something wrong. Can you tell me the exact steps you did?
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-27T04:52:48+00:00
- Post Title: Subnautica .bank files

Better you tell what are you doing and what error you get.

You ever used BMS scripts or hex editor?
## Post #9
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-27T05:14:11+00:00
- Post Title: Subnautica .bank files

> Reply from daemon1
>
> Better you tell what are you doing and what error you get.

You ever used BMS scripts or hex editor?
Well, I get the files extracted, but I can't play them. I think they're still encoded. And I've only ever used a hex editor once or twice. As for BMS, no.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-27T05:41:50+00:00
- Post Title: Subnautica .bank files

That means you extracted them wrong. What did you use to extract them?
## Post #11
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-27T07:24:45+00:00
- Post Title: Subnautica .bank files

> Reply from daemon1
>
> That means you extracted them wrong. What did you use to extract them?
I used fsbext.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-27T09:21:33+00:00
- Post Title: Subnautica .bank files

Why? fsbext will NOT work. I already told you exactly which tools you should use.
## Post #13
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-27T10:25:55+00:00
- Post Title: Subnautica .bank files

> Reply from daemon1
>
> Why? fsbext will NOT work. I already told you exactly which tools you should use.
The first link you sent led me to an fsbext page though. Unless you wanted me to use a script from that page, which I don't know what to use with.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-27T10:37:48+00:00
- Post Title: Subnautica .bank files

> Reply from keithy
>
> daemon1 wrote:Why? fsbext will NOT work. I already told you exactly which tools you should use.
The first link you sent led me to an fsbext page though. Unless you wanted me to use a script from that page, which I don't know what to use with.

Yes, I told you to use script from that page, and then use tool from the second link. If you don't know how to use scripts, read some help on quickbms.
## Post #15
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-27T18:46:55+00:00
- Post Title: Subnautica .bank files

> Reply from daemon1
>
> keithy wrote:daemon1 wrote:Why? fsbext will NOT work. I already told you exactly which tools you should use.
The first link you sent led me to an fsbext page though. Unless you wanted me to use a script from that page, which I don't know what to use with.

Yes, I told you to use script from that page, and then use tool from the second link. If you don't know how to use scripts, read some help on quickbms.
Okay well I got the .bank into an .fsb correctly but how do I use the program from the second link?
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-03-27T19:52:02+00:00
- Post Title: Re: Subnautica .bank files

Good. To use the second tool just drag FSB file onto it.

As it's written there, you need FMOD official DLL's for it to work. You can download them from their site (or anywhere else from the internet).
## Post #17
- Username: keithy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 26, 2016 11:04 am
- Post datetime: 2016-03-27T20:23:13+00:00
- Post Title: Re: Subnautica .bank files

Ah okay, finally got it. Thank you so much for all your help.
