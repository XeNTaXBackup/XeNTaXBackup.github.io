## Post #1
- Username: RageX
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 25, 2015 2:15 am
- Post datetime: 2016-11-03T23:43:24+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

Can anyone please analyze the following resources ? Most probably compression used on imagefile pak's and .ff's is LZ4 and for sound pak's FLAC audio format is used mostly. Although the resources may almost look like MW remastered, but they are just a bit different. Here are the samples :-

imagefile9.pak

```
https://www.datafilehost.com/d/2b42b72a
```

phstreets_hill_tr.ff

```
https://www.datafilehost.com/d/598dcdb1
```

ja_asteroid.sabl

```
https://www.datafilehost.com/d/d120c50b
```

patch_common_core_mp.sabs

```
https://www.datafilehost.com/d/c3486413
```

A note, after opening the download link, pls untick "Download with Secured Download manager" to download the file.

Please share your thoughts here or if possible write an extractor.
## Post #2
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-11-04T14:31:10+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

The links you posted don't work they keep leading to maleware.

Anyway I have the game and they are using the same format as BO2/BO3

I'm interested in the sounds but BO sound studio doesn't open them I get 
```
Invalid Version Detected, Expected 14 or 15 but got:4
```


I've included a sample below hopefully somebody can have a look at it, though I would assume it shouldn't be too hard considering it's the same format.
[common_cp.zip](https://xentaxbackup.github.io/file/11874_common_cp.zip)
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-11-04T15:02:03+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

The Flac files have no header, that's why it doesn't recognize them.
## Post #4
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2016-11-04T16:45:13+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

@durandal217, or anyone who tries to download the given samples, you need to untick "Download with Secured Download manager" after opening the link so that the download starts for the correct file. Also format is same only when it comes to sounds, but for other assets its completely different than BO2/BO3.
## Post #5
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-11-04T18:26:52+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

Thanks ranger that worked. So now in addition to the first question of how to open the SABL, it is now how to add a flac header.. Is flac headers generic or are they unique? because I tried to add a flac header, referencing Advanced Warfare's Flac's but that didn't work. Unless I did it wrong...
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-11-04T18:34:54+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

I tried this header from Black ops 3 and it works. The FF F8 is the flag where the header ends. So i found that in the files for with the weird custom headers.

```
664C614300000022040004000000000000000BB802F0009E40800000000000000000000000000000000084000028200000007265666572656E6365206C6962464C414320312E322E3120323030373039313700000000FFF8A918000716FF1BFEFBFE
```


so just replace the custom header with this.
## Post #7
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-11-04T18:39:47+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

aha that did work!

Now if I could only open the SABL files from infinite warfare.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2016-11-04T18:43:17+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

I wonder if there was a way to automate this process?
## Post #9
- Username: RageX
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Aug 25, 2015 2:15 am
- Post datetime: 2016-11-04T18:48:44+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

Also with BO3, we could get the sounds with names exported. Is there anyone who can automate the process and add names support for the extraction of audio files in Infinite Warfare ?
## Post #10
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-11-04T18:53:15+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

There is a way, it just isn't available yet.
## Post #11
- Username: yung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri May 06, 2016 12:16 pm
- Post datetime: 2016-11-04T21:53:52+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

Would Wraith be able to rip OBJ's from Infinite Warfare right now?
## Post #12
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-11-06T04:53:14+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

Wraith just updated and now supports both IW and MW:R, if your extracting sounds from IW, filenames are included as well.

My infinite thanks based Wraith team.
## Post #13
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2016-11-25T12:17:16+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

> Reply from durandal217
>
> Wraith just updated and now supports both IW and MW:R, if your extracting sounds from IW, filenames are included as well.

Where i can download it? i really wanna extract sound from CoD IW, Thank you!
## Post #14
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-25T16:16:36+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

[http://aviacreations.com/modme/forum/topic.php?tid=69](http://aviacreations.com/modme/forum/topic.php?tid=69)
## Post #15
- Username: XxsimonexX
- Rank: beginner
- Number of posts: 36
- Joined date: Fri Dec 18, 2015 6:17 am
- Post datetime: 2016-11-28T13:28:59+00:00
- Post Title: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

> Reply from AceWell
>
> http://aviacreations.com/modme/forum/topic.php?tid=69
THANK YOU SO MUCH!
## Post #16
- Username: Proteus37
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 02, 2020 5:50 pm
- Post datetime: 2020-02-04T05:54:04+00:00
- Post Title: Re: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

hopefully someone is out there to help resurrect this thread.

when I use the latest version of Wraith to extract sound files from code_post_gfx.sabl and code_post+gfx.sabs, the extracted sound files are cut short at 1 second. the menu loop files, for example. which really sucks, because those are examples of exactly what I'm trying to get my hands on.

can anyone be the GOAT and help find a solution to this?
## Post #17
- Username: Proteus37
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Feb 02, 2020 5:50 pm
- Post datetime: 2020-02-04T09:04:36+00:00
- Post Title: Re: CoD: Infinite Warfare (.pak, .ff, .sabl/.sabs) Help

> Reply from Proteus37 ↑Tue Feb 04, 2020 1:54 pm at Tue Feb 04, 2020 1:54 pm
>
> 
hopefully someone is out there to help resurrect this thread.

when I use the latest version of Wraith to extract sound files from code_post_gfx.sabl and code_post+gfx.sabs, the extracted sound files are cut short at 1 second. the menu loop files, for example. which really sucks, because those are examples of exactly what I'm trying to get my hands on.

can anyone be the GOAT and help find a solution to this?

i figured it out. the .sabs files are the ones that export full audio tracks. however, I notice that the .sabs files total 8gb, while the .sabl files total 13gb. i wonder what's in there that isn't in the .sabs archives.
