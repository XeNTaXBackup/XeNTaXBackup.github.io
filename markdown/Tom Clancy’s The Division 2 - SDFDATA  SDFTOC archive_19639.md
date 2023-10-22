## Post #1
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2019-03-11T11:44:09+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

For legal reasons, this does not include the AES key and IV. When you get then, put them inside sd_key.txt and sd_iv.txt respectively.

Please also note that you'll need to get a copy of oo2core_7_win64.dll (renamed older/newer versions might also work).

[Download](http://sktest.aruarose.com/Division2Extract_v001.7z)
## Post #2
- Username: lunger
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 03, 2016 3:09 am
- Post datetime: 2019-03-11T11:54:22+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

Nice work Sir Kane!
## Post #3
- Username: edpedpe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 04, 2016 2:43 am
- Post datetime: 2019-03-14T23:27:23+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

Sorry for my ignorance, but where do I get that AES key and IV from?
## Post #4
- Username: jackiiiiii
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 10, 2016 1:19 am
- Post datetime: 2019-03-16T12:26:52+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

I would like to use that as well, but I do not understand a single word. Please explain!
## Post #5
- Username: PatrickJr
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 28, 2017 11:11 am
- Post datetime: 2019-03-20T09:50:31+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

Great stuff, but a hint to where to get the keys would be fantastic!
## Post #6
- Username: SEB851
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jan 05, 2017 12:12 am
- Post datetime: 2019-07-06T15:55:44+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

How to find AES-IV Key ?
## Post #7
- Username: Naden
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jun 20, 2017 10:09 pm
- Post datetime: 2020-01-13T12:54:21+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

If anyone could send me the aes keys, that would be great.
## Post #8
- Username: jj5567
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 02, 2021 5:32 am
- Post datetime: 2021-10-04T19:28:38+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

So nobody still knows how to get the keys?
## Post #9
- Username: John76
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 18, 2020 6:02 am
- Post datetime: 2021-11-28T13:27:08+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

I don't think it works! I don't think he has the keys either, so he writes nonsense for legal reasons! Posting something on a forum and you don't even know what it's for is ridiculous
## Post #10
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2021-12-23T14:01:30+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

I don't think TD2 files are encrypted (TD1 wasn't ...) it just will be PITA to unpack it as it was in TD1 case. On github you can find source code for an app called 'rouge_sdf' - with slight modification I'm sure you can make it work for TD2 (format is almost the same).
## Post #11
- Username: John76
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 18, 2020 6:02 am
- Post datetime: 2021-12-28T17:26:03+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

When at position 97 byte is 0 then it works normally and data is usually compressed with zlib, but when byte is 1 as in the picture....
it seems to be encrypted 



Untitled1.jpg (180.54 KiB) Viewed 542 times
## Post #12
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-01-14T01:43:23+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

Try LZ4 or send the file.
## Post #13
- Username: John76
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Apr 18, 2020 6:02 am
- Post datetime: 2022-01-16T03:05:59+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

Here is [https://drive.google.com/file/d/1a-On_i ... sp=sharing](https://drive.google.com/file/d/1a-On_iOzIiz1FJaL1u9w4WmLL0srqxSS/view?usp=sharing)
## Post #14
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-03-18T20:21:38+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

You're probably right. I've checked several compression methods without success ... although SCPACK ( QBMS scanner of compression algorithms) gives some readable reslts - dunno how accurate it is (decompressed size doesn't match).
## Post #15
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-15T14:33:56+00:00
- Post Title: Tom Clancy’s The Division 2 - SDFDATA / SDFTOC archive

Q: Just an idea but did you checked all platforms (consoles and PC)? Very often they are diffrent - sometimes not encrypted or vce versa.

Update:
I've checked your file (40,217,037 bytes) against PC demo version (56,710,938 byte) and the 1st four bytes are the same - so the encrypton key is static and/or it's not a Zlib compresson.
## Post #16
- Username: Dankius Memus
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 15, 2016 5:58 pm
- Post datetime: 2022-04-16T09:19:17+00:00
- Post Title: Re: The Division 2

> Reply from VendorX ↑Fri Apr 15, 2022 10:33 pm at Fri Apr 15, 2022 10:33 pm
>
> 
Q: Just an idea but did you checked all platforms (consoles and PC)? Very often they are diffrent - sometimes not encrypted or vce versa.

Update:
I've checked your file (40,217,037 bytes) against PC demo version (56,710,938 byte) and the 1st four bytes are the same - so the encrypton key is static and/or it's not a Zlib compresson.

Yes they are all the same. But would u be willing to rip the encryption key from the game? The game uses EAC so x64dbg is likely to get u banned but I dont mind supplying test accounts.
## Post #17
- Username: VendorX
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 13, 2018 5:16 am
- Post datetime: 2022-04-17T07:28:35+00:00
- Post Title: Re: The Division 2

... Good one ...
I see, you know what to do so ...
Tip: exe is also encrypted - dump it from the memory. If you are lucky, unencrypted sdftoc will be there also.
## Post #18
- Username: Crazy Potato
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Mar 26, 2018 11:56 am
- Post datetime: 2022-12-13T22:14:50+00:00
- Post Title: Re: The Division 2

I've been searching around and nothing really opens D2's files.
Got the universal bms script from Luigi and a few more for other titles just in case like Rayman and Sparks of Hope. Nothing worked, Now there are some posts but that was when the game was in it's alpha/beta state lol
I'll provide the sdftoc of the game from it's latest patch as of 13,December,2022.
[https://www.mediafire.com/file/tit1gk1u ... dftoc/file](https://www.mediafire.com/file/tit1gk1uw1vzqpp/sdf.sdftoc/file)
## Post #19
- Username: legitcoder
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 07, 2023 5:49 pm
- Post datetime: 2023-05-01T05:34:52+00:00
- Post Title: Re: The Division 2

Hello there! any news aout dumping sdfdata/sdftoc files?
