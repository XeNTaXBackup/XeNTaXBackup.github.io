## Post #1
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-06-05T23:47:31+00:00
- Post Title: [XBOX360] Red Dead Redemption .awc audio file format

Hi mates.

All right, first of all I want to notify that I know OpenIV can now read this audio format but as you can know XBox360 .rpf archives are not supported by the software. Before extract the rpf archive from RDR, I thought that the audio format would be XMA encoded. How silly I was! It's not the case of course ( it would be too easy ).

Xma_test result:

```
version: XMA2
offset: 0
block size: 8000
data size: 10104c
------------------

Parse error: skip bits (2088) did not match previous packet overflow (0)
```


So, I can provide a file sample to any kind soul that would help me:

[Here](http://rapidshare.com/files/3478450853/ftr_violin_01.awc)

EDIT: Okay, it's very strange because after investigation, I found XMA mono header ( " FC 03 80 00 " ) in some other files so it would means that those files are really XMA encoded?

EDIT2: Yes, This is XMA encoded. I tried on the C96 mauser .awc and it gave me a good .wav sample but for now, it is reasonable to remain cool. Waiting for some feedback about the sample I've uploaded because it seems to be different.

Many thanks in advance guys.

PS: There is some .xml files and .dat files as well ( if you need ).

Cordialy

Vosvoy
## Post #2
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2013-06-21T07:45:29+00:00
- Post Title: [XBOX360] Red Dead Redemption .awc audio file format

It appears to contain two XMA mono files, potentially perhaps a archive of sorts, however for some reason xma_parse gets errors and decode attempt comes back bad.

FC 03 80 00 is mono marker indeed, repeated twice in the file, you can simply cut out those streams by including 6 bytes prior to the mono marker... either way something is eluding on it... ah I just needed to put 44khz into the header, actual output file is 17khz for proper decode.

basicly cut out the files, give the xma riff header (mono) and decode, i left out xma parse entirely.
## Post #3
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2013-06-22T21:47:45+00:00
- Post Title: [XBOX360] Red Dead Redemption .awc audio file format

> Reply from Apollo
>
> It appears to contain two XMA mono files, potentially perhaps a archive of sorts, however for some reason xma_parse gets errors and decode attempt comes back bad.

FC 03 80 00 is mono marker indeed, repeated twice in the file, you can simply cut out those streams by including 6 bytes prior to the mono marker... either way something is eluding on it... ah I just needed to put 44khz into the header, actual output file is 17khz for proper decode.

basicly cut out the files, give the xma riff header (mono) and decode, i left out xma parse entirely.

All right, many thanks Apollo for your feedback. I have to admit that I'm not a pro about XMA files at all but I've never seen a XMA file like that.
## Post #4
- Username: ZT111
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Jul 20, 2013 5:48 am
- Post datetime: 2013-07-19T22:37:15+00:00
- Post Title: [XBOX360] Red Dead Redemption .awc audio file format

-
## Post #5
- Username: reditec
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 28, 2015 11:08 pm
- Post datetime: 2015-11-22T13:18:51+00:00
- Post Title: [XBOX360] Red Dead Redemption .awc audio file format

Any news?
I'm working on some tool to extract the .awc files.
They are archives containing XMA decoded files.
I do not know much about those XMAs yet, but [https://github.com/koolkdev/libertyv](https://github.com/koolkdev/libertyv) LibertyV is OpenSource and is able to extract Red Dead Redemption audio files.
(not every file, the tool has a bug I think)

If someone could provide more informations about how .awc exactly work, that would be awesome
