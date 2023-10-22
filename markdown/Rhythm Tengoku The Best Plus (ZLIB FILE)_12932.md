## Post #1
- Username: Dorigon
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2012 3:04 am
- Post datetime: 2015-06-11T22:56:52+00:00
- Post Title: Rhythm Tengoku The Best Plus (ZLIB FILE)

Hi!
I'm trying to make a translation about this game ( Rhythm Tengoku The Best Plus for 3ds). I have the game decrypted but I stuck with zlib files that I can't decompress.
Can someone give me a little help with it? I leave here a file as example for the purpose

[https://mega.nz/#!GFYVQYJY!X265Pgp6_LlS ... x754TV5o1A](https://mega.nz/#!GFYVQYJY!X265Pgp6_LlSnmCK765u-w9I-dYV7rqgmx754TV5o1A)

Thanks a lot =)
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2015-06-13T14:27:40+00:00
- Post Title: Rhythm Tengoku The Best Plus (ZLIB FILE)

This one is pretty simple. Starts with the uncompressed size 32bit unsigned integer. Followed by the compressed data and the size for that can be obtained simply by subtracting 0x4 from the archive size, compressed data starts at 0x4... You should try Offzip i guess.

Regards.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-06-13T22:55:01+00:00
- Post Title: Rhythm Tengoku The Best Plus (ZLIB FILE)

the sample file has no language data

you can unzip as above
## Post #4
- Username: Dorigon
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2012 3:04 am
- Post datetime: 2015-06-14T18:55:34+00:00
- Post Title: Rhythm Tengoku The Best Plus (ZLIB FILE)

> Reply from WRS
>
> the sample file has no language data

you can unzip as above
Yeah, it was just a file example from the same game.

Just like this other [https://mega.co.nz/#!SBw2HSbZ!yAz7hr76a ... H6GPykrJJA](https://mega.co.nz/#!SBw2HSbZ!yAz7hr76atji2mycipmMsFUfoqZrgwgecH6GPykrJJA)

I can't use winrar or 7zip... I get allways error. I'm triying with offzip but nothing
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2015-06-14T21:16:43+00:00
- Post Title: Rhythm Tengoku The Best Plus (ZLIB FILE)

> Reply from Dorigon
>
> I can't use winrar or 7zip... I get allways error. I'm triying with offzip but nothing

run this from the command line:

```
offzip.exe -a -z 15 ctrTango_long.zlib . 0
```


you could also use a bms script (see quickbms)

```
get zsize asize
math zsize -= 4
clog "uncompressed.dat 4 zsize unsize

```
## Post #6
- Username: Dorigon
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jan 02, 2012 3:04 am
- Post datetime: 2015-06-14T22:39:42+00:00
- Post Title: Rhythm Tengoku The Best Plus (ZLIB FILE)

Thanks a lot WRS, that command line for offzip work fine, the .zlib became a.sar file. The quickbms script didn't work, 0% decompresed I don't know why
