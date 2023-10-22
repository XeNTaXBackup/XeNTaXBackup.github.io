## Post #1
- Username: DevilQueen
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 14, 2015 10:04 am
- Post datetime: 2015-10-06T19:24:44+00:00
- Post Title: Lost Odyssey unknown file type

I'm trying again.  I extracted the contents of Disc 1 which gave me a lot of .fpd files. From those I extracted the contents of xenon_vfx.fpd and this gave me 12 files that simply say File. Someone's guide said that adding .xxx to the end of the file names worked for them but I tried it and it didn't fix anything for me. Converting the files to another format like .mp3 doesn't work either. I'm trying to extract the voices from the game, specifically the battle dialogue of four characters if anyone is wondering. What should I do now?
[Files.PNG](https://xentaxbackup.github.io/file/9838_Files.PNG)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-10-07T15:38:35+00:00
- Post Title: Lost Odyssey unknown file type

Can you post a sample up please?
## Post #3
- Username: DevilQueen
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 14, 2015 10:04 am
- Post datetime: 2015-10-07T18:42:53+00:00
- Post Title: Lost Odyssey unknown file type

It was taking so long for the file to upload here that I kept getting logged out so I put it on zippyshare instead. Here you go.  [http://www17.zippyshare.com/v/YYgGCIWb/file.html](http://www17.zippyshare.com/v/YYgGCIWb/file.html)
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-10-08T13:23:28+00:00
- Post Title: Lost Odyssey unknown file type

That didn't seem to contain any audio from what I could see.

And I think the forum has a 10MB limit on uploads as well.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-08T16:21:03+00:00
- Post Title: Lost Odyssey unknown file type

> Reply from DevilQueen
>
> xenon_vfx.fpd

That is probably visual FX, not voices. You need to try another fpd
## Post #6
- Username: DevilQueen
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 14, 2015 10:04 am
- Post datetime: 2015-10-08T20:05:59+00:00
- Post Title: Lost Odyssey unknown file type

I tried xenon_snd.fpd first but quickbms couldn't extract anything from it. Maybe the battle audio is in xenon_battle.fpd instead? [http://www96.zippyshare.com/v/w1A5wbe8/file.html](http://www96.zippyshare.com/v/w1A5wbe8/file.html)
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-10T06:11:04+00:00
- Post Title: Lost Odyssey unknown file type

can you also upload xenon_snd.fpd ?
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-10-10T11:48:38+00:00
- Post Title: Lost Odyssey unknown file type

Xenon Battle didn't have any audio either I'm afraid.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-10T14:08:17+00:00
- Post Title: Lost Odyssey unknown file type

Its UE3 and all sounds are usually in a separate file. Audio package, sfx package. Or WAD files.
## Post #10
- Username: DevilQueen
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 14, 2015 10:04 am
- Post datetime: 2015-10-10T16:54:36+00:00
- Post Title: Lost Odyssey unknown file type

Thank you so much for helping me, I really appreciate it.  Here is xenon_snd.fpd. If quickbms had been able to extract the files from it I would have started here but... Here's the link: [https://www.dropbox.com/s/4khy3ui0k83t9 ... d.fpd?dl=0](https://www.dropbox.com/s/4khy3ui0k83t92z/xenon_snd.fpd?dl=0)
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-10T17:30:38+00:00
- Post Title: Lost Odyssey unknown file type

> Reply from DevilQueen
>
> Here is xenon_snd.fpd

That's the one! It contains all the sounds in XMA format, with separate headers. I think other people here know the easy way to extract them all. I just checked and manually converted a couple in the beginning.
## Post #12
- Username: DevilQueen
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 14, 2015 10:04 am
- Post datetime: 2015-10-11T01:04:15+00:00
- Post Title: Lost Odyssey unknown file type

This is SUCH great news! Thank you, daemon!    Can I have a list of programs and instructions to extract and convert the sounds to a format I can listen to? Hard instructions or easy ones, either way is fine as long as I get to accomplish my goal here. Thanks so much to everyone for not giving up!
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-11T05:41:37+00:00
- Post Title: Lost Odyssey unknown file type

I used VGMToolbox. But its no good to extract all audio manually selecting its channels, frequency and offset. All these values are in this file, I can see them. You need some script or tool to do it automatically.
## Post #14
- Username: DevilQueen
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 14, 2015 10:04 am
- Post datetime: 2015-10-12T20:22:41+00:00
- Post Title: Lost Odyssey unknown file type

Oh. Well... if anyone makes a tool or script for this purpose please post it here. I won't hold my breath but I'll come back and check this from time to time. Thank you.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-13T15:37:58+00:00
- Post Title: Lost Odyssey unknown file type

I'm now busy with NFS and then Darkness II is in queue. After that I can look into this. But as I said, I never worked with XMA before and I hope someone else would help you.
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-14T20:24:46+00:00
- Post Title: Re: Lost Odyssey unknown file type

well, I found that this one will be easy, so today i made the first version of extractor.

It extracts first 1100 files and then fails. But you can already try it. Use it on xenon_snd.fpd and it will produce files what can be converted to WAV with TOWAV.EXE
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-10-15T19:27:54+00:00
- Post Title: Re: Lost Odyssey unknown file type

New version. Extracts all 13000+ files. These include:

600+ big xwav files, which are cutscenes. About 90 of them are multilayered, and these will not convert properly, because they need demuxing, and I don't know how to do it yet. Anyway, you said you don't need those.

About 12000 small files, coming from 2000+ audio banks, named [bank number]_[file number]
These are all voices in all languages and SFX.

If you want proper filenames, I need other gamefiles to find them.
[Xenon_s.rar](https://xentaxbackup.github.io/file/9860_Xenon_s.rar)
## Post #18
- Username: DevilQueen
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Sep 14, 2015 10:04 am
- Post datetime: 2015-10-19T22:42:13+00:00
- Post Title: Re: Lost Odyssey unknown file type

Thanks, daemon! You're amazing!  I thought it would take weeks for you to get to this so I haven't been here in a while. Proper file names would be nice but I won't ask for them because you've already helped a lot. I'll download your extractor right now. Thanks again.
## Post #19
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2018-04-21T18:57:26+00:00
- Post Title: Re: Lost Odyssey unknown file type

Hi, this tools only to xenon_snd.fpd ?
Tell me please how to unpack xenon_chr.fpd
xenon_chr.fpd - [https://drive.google.com/file/d/1tY3Umd ... sp=sharing](https://drive.google.com/file/d/1tY3UmdmGTNemR3Vb2BF5UOklTEJ_w2Qk/view?usp=sharing)
xenon_obj.fpd - [https://drive.google.com/file/d/1LzYzdu ... sp=sharing](https://drive.google.com/file/d/1LzYzdu-mju11xjrtMD5AiuJp86XfpgVC/view?usp=sharing)
