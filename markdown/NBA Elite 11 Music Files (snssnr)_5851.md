## Post #1
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2011-01-19T19:48:22+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-01-23T16:26:43+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

Try this eaxa header and convert with towav

```
........ ..........D..i.........
```
## Post #3
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2011-01-23T22:13:28+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

You know, I'm pretty sure support for this can be added to vgmstream. We already have the basic decoder so all it needs a few modifications and support for this file's header.
## Post #4
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2011-01-24T04:02:42+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

> Reply from OrangeC
>
> Try this eaxa header and convert with towav
Code: Select all........ ..........D..i.........

Just wanted to make sure I got this right



downloaded this
[http://wiki.xentax.com/index.php/Game_T ... _and_ToWav](http://wiki.xentax.com/index.php/Game_Tools#UnBF_and_ToWav)

I tried dragging the file into towav, running the convert music bat, renaming the extension to what the batch file had, and trying to convert it with towav filename.bin in cmd.  Is there any help file with towav or a way to have it give me the commands?
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-01-24T13:31:06+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

You have the wrong towav.

[http://www.ctpax-x.ru/index.php?goto=files&down=24](http://www.ctpax-x.ru/index.php?goto=files&down=24)

this is the right one.
## Post #6
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2011-01-25T00:28:31+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

Unfortunately that didnt work.  I tried the file I edited, the normal file without that header, renamed it to other EA game extensions that towav actually supports and nada.


This is what I tried before, did I miss something simple?  Was anyone able to convert the example I gave in the first post?

[viewtopic.php?f=17&t=4922](http://forum.xentax.com/viewtopic.php?f=17&t=4922)
[viewtopic.php?f=17&t=4068](http://forum.xentax.com/viewtopic.php?f=17&t=4068)

If I need to explain myself, Elite 11 had a custom made soundtrack that obviously won't be released now, so I'm really interested to see what they have in there.
## Post #7
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-01-25T07:54:44+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

It decodes flawless (SNS) with towav using the dead space snu header.

Made a quick & dirty BAT converter which processes all *.SNS in folder the bat file is run in, copies the header in place and runs towav on it to give output wav, just a note, since we have to "insert" khz and channels values, i set default to 44khz and stereo and included also 48khz header to use just incase... i guess snr in this game stores the khz and channel/format info so better check and augment as see fit. could have bothered i guess implement the snr file into the batch for values but all snr may not be same way... atleast in other games surely not.

WARNING. This bat is very basic and does NO check to source file so if ealayer3 file stream or stream is mono is fed to it, towav may try decode it with horrible results.

the fact if SNS is ealayer3 or xas stream depends on a game but in this game, should check from the SNR if present that it starts by 04 to confirm.
[xasstreamconvertbatch.rar](https://xentaxbackup.github.io/file/3844_xasstreamconvertbatch.rar)
## Post #8
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2011-01-26T15:20:31+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

awesome, thank you very much....unfortunately they are all instrumentals, OK but nothing special.  Will YouTube them later.

1 didn't convert but I'm not too worried about it, thank you again.

if possible, do you think you guys could help out the rest of the NLSC community in this thread? 
[viewtopic.php?f=17&t=5234](http://forum.xentax.com/viewtopic.php?f=17&t=5234)
## Post #9
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-01-27T07:23:50+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

Well, if you want, i can take a look on the file that didn't convert, it could be ealayer3 or different block system in place. As for the other game, the format looks unknown to me as I can't recall having seen such  "AA" padding before.
## Post #10
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2011-01-28T05:20:44+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: razzledazzle
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 18, 2022 1:22 pm
- Post datetime: 2022-06-18T21:40:34+00:00
- Post Title: NBA Elite 11 Music Files (sns/snr)

> Reply from Apollo ↑Tue Jan 25, 2011 3:54 pm at Tue Jan 25, 2011 3:54 pm
>
> 
It decodes flawless (SNS) with towav using the dead space snu header.

Made a quick & dirty BAT converter which processes all *.SNS in folder the bat file is run in, copies the header in place and runs towav on it to give output wav, just a note, since we have to "insert" khz and channels values, i set default to 44khz and stereo and included also 48khz header to use just incase... i guess snr in this game stores the khz and channel/format info so better check and augment as see fit. could have bothered i guess implement the snr file into the batch for values but all snr may not be same way... atleast in other games surely not.

WARNING. This bat is very basic and does NO check to source file so if ealayer3 file stream or stream is mono is fed to it, towav may try decode it with horrible results.

the fact if SNS is ealayer3 or xas stream depends on a game but in this game, should check from the SNR if present that it starts by 04 to confirm.
Thanks Apollo! Your .bat file works extremely well on all the NBA Elite 11 .sns files!
