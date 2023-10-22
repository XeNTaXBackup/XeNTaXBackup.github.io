## Post #1
- Username: ferar720
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 09, 2016 12:37 am
- Post datetime: 2021-08-08T16:02:47+00:00
- Post Title: Tropico 4 HPK translation

Good evening,

I was trying create Update1.hpk with edited text file but translated text don´t show. Using HPK.exe.

Steam version or GOG don´t show.

Thank you for advice.
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-08T18:40:53+00:00
- Post Title: Tropico 4 HPK translation

What is HPK.exe and how exactly did you use it?

Can you upload some samples of the language files?
## Post #3
- Username: ferar720
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 09, 2016 12:37 am
- Post datetime: 2021-08-09T18:24:33+00:00
- Post Title: Tropico 4 HPK translation

HPK.exe unpacker and packer
[https://github.com/nickelc/hpk](https://github.com/nickelc/hpk)

Use cmd-line and no problem with unpacking and packing.

Sure.
[https://www.dropbox.com/s/c0lofswh8g2zj ... 1.hpk?dl=0](https://www.dropbox.com/s/c0lofswh8g2zjqd/Update1.hpk?dl=0)
## Post #4
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-08-09T19:30:18+00:00
- Post Title: Tropico 4 HPK translation

I'm getting this error while unpacking:

```
Error: Hpk(Io(Custom { kind: InvalidData, error: "stream did not contain valid UTF-8" }))
```


So maybe you didn't encode your text files in proper way? Try to save them as UTF8 files.
## Post #5
- Username: ferar720
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 09, 2016 12:37 am
- Post datetime: 2021-08-09T19:39:16+00:00
- Post Title: Tropico 4 HPK translation

No, file is original from Steam.

And my edited file.
[https://www.dropbox.com/s/3soi0f0ayqofc ... z.hpk?dl=0](https://www.dropbox.com/s/3soi0f0ayqofcrk/Update1%20cz.hpk?dl=0)

And yes, file saved with utf-8 coding.
[https://www.dropbox.com/s/s2txg6t5qfhb3 ... s.lua?dl=0](https://www.dropbox.com/s/s2txg6t5qfhb37t/game.trans.lua?dl=0)
## Post #6
- Username: nickelc
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 17, 2021 1:20 am
- Post datetime: 2021-09-16T17:37:16+00:00
- Post Title: Tropico 4 HPK translation

Hi,

There was an issue with the processing of the file dates after unpacking. 
The argument --ignore-filesdates would prevent this error but I also released a new version of [my tool](https://github.com/nickelc/hpk/releases/tag/v0.3.9) that should fix the problem.
