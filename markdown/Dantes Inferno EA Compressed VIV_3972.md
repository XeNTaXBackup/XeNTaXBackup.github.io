## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-12-24T22:56:28+00:00
- Post Title: Dantes Inferno EA Compressed VIV

[http://www.megaupload.com/?d=C9866GKD](http://www.megaupload.com/?d=C9866GKD)

its from the demo heres a cut from the 1gb big file.
## Post #2
- Username: JeffT
- Rank: n00b
- Number of posts: 12
- Joined date: Tue Jun 16, 2009 4:15 pm
- Post datetime: 2009-12-29T19:14:42+00:00
- Post Title: Dantes Inferno EA Compressed VIV

Interesting too. The file is similar to EA's .big, but FinalBig didn't work.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-28T02:33:39+00:00
- Post Title: Dantes Inferno EA Compressed VIV

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring BIGH
get VIV_SIZE long
endian big
get FILES long
get HEADER_SIZE long
for i = 0 < FILES
    get OFFSET long
    get SIZE long
    get NAME_CRC long
    log NAME_CRC OFFSET SIZE
next i
```

unfortunately the archive doesn't contain the names of the files but only their CRC
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-28T16:32:40+00:00
- Post Title: Dantes Inferno EA Compressed VIV

thanks luigi.
## Post #5
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2010-02-05T20:01:09+00:00
- Post Title: Dantes Inferno EA Compressed VIV

.....yeah, but, does someone know how to open them?I'm asking because in another post I read that someone has been able to extract sounds from the game.....thx
## Post #6
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-02-06T01:35:05+00:00
- Post Title: Dantes Inferno EA Compressed VIV

I don't know how you identify them, but for instance 196129365.bin can be decoded by:
1. Remove the first 0x20 bytes
2. Unpack with unpack1943:

```
unpack1943 infile outfile
```
3. Add a header and convert with your favorite XMA decoder

There are apparently some multichannel files as well, I put together a quick tool to deal with 6 channel ones like 80483832.dat (don't know if this was the original name or anything, just what OrangeC sent, he may have already cut the 0x20 byte header off or extracted it from a video):

```
ea_multi_xma 80438332.dat out1 out2 out3
```
out1, 2 and 3 can each be handled as normal XMA files (i.e. add header and decode).

unpack1943 and ea_multi_xma can be found on my page ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)).
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-02-06T02:09:59+00:00
- Post Title: Dantes Inferno EA Compressed VIV

Yes hcs the file i sent you was 20byte cutted, not from a video.
## Post #8
- Username: cryogen
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Aug 25, 2009 6:07 pm
- Post datetime: 2010-02-06T16:59:55+00:00
- Post Title: Dantes Inferno EA Compressed VIV

Finally I understand how u did it, I just had to paste the little green text above in a txt file and then rename it to bms instead of txt.
Thx Luigi
Thx HCS

Cryogen
## Post #9
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-10-31T23:05:28+00:00
- Post Title: Dantes Inferno EA Compressed VIV

Friends, if anyone knows how to extract the text has for a possible translation??
## Post #10
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-11-04T13:02:03+00:00
- Post Title: Dantes Inferno EA Compressed VIV

Friends, I am willing to translate Dante's PS3 for PT-BR, will they never get any tool to extract the strings? I need a loader to put it back later translated strings.

does any can help me?
## Post #11
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2010-11-29T19:03:12+00:00
- Post Title: Dantes Inferno EA Compressed VIV

Does anyone know what kind of compression of files?

help me guys.
