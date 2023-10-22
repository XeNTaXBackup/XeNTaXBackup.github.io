## Post #1
- Username: ProbPeriPlum
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Nov 24, 2021 8:39 pm
- Post datetime: 2022-09-20T18:54:07+00:00
- Post Title: Cookie Run: Munjil Munjil (쿠키런 문질문질) .dez text files

This game was a Korea-only spin off to the Cookie Run series that had a short-lived existence from 2014 to 2016. The text files for it have not yet been decrypted, though in theory it seems a bit easy.

The text is all in Base64, followed by another layer of what seems to be Xor. Not sure what else is to be used or done, but if ajyone can take a look I will be very grateful. Thanks!

[https://cdn.discordapp.com/attachments/ ... tables.zip](https://cdn.discordapp.com/attachments/569235314086772748/1021856185592332408/datatables.zip)
## Post #2
- Username: barncastle
- Rank: beginner
- Number of posts: 32
- Joined date: Wed Apr 14, 2021 12:13 am
- Post datetime: 2022-09-22T20:26:15+00:00
- Post Title: Cookie Run: Munjil Munjil (쿠키런 문질문질) .dez text files

Second layer is AES 256 in CTR (Counter) mode.

```
IV:   44C5512BA70CF3836AE36C83084DD406

```
