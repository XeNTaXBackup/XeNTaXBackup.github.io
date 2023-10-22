## Post #1
- Username: XRaptor
- Rank: mega-veteran
- Number of posts: 226
- Joined date: Sat Jul 12, 2008 11:42 pm
- Post datetime: 2010-01-31T11:51:31+00:00
- Post Title: The Settlers 7 BETA

Hi,
simple question - anyone tried to reverse/unpack new version of *.bba archives from last Settlers game? It seems that everything is now encrypted.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-02-02T23:40:46+00:00
- Post Title: The Settlers 7 BETA

I started but haven't done much yet, it's pretty complex.
Format seems similar to the last one: [http://wiki.xentax.com/index.php/Settle ... _An_Empire](http://wiki.xentax.com/index.php/Settlers_-_Rise_Of_An_Empire)

Don't know if the encryption routines changed though.
## Post #3
- Username: OlaHaldor
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 04, 2007 11:17 pm
- Post datetime: 2010-03-21T12:54:22+00:00
- Post Title: The Settlers 7 BETA

Any news on this one?
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-03-22T09:58:44+00:00
- Post Title: The Settlers 7 BETA

Nope.
## Post #5
- Username: ednet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 31, 2008 8:27 pm
- Post datetime: 2010-03-29T20:14:51+00:00
- Post Title: The Settlers 7 BETA

Hello guys,

At first i have to say i own the retail version. I find out some new informations. I did research to the patch process (done by the gameudate) and i think i could find out the filestructure inside the BBA files.

I hope with these informations and with the specific patcher executable you are able to find a working encryption and decryption. You dont have to analysis the ~12MB game executable and maybe it is easier to find the algorythm by analysing the 207KB patch executable.

Please see the attachment, inside you can find some bba-files and the patcher and a readme how to use the patcher!
Hope i could help!

Download attachment: [S7.rar](http://www.sendspace.com/file/potweh) 

Greetings
ednet
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-03-29T21:22:20+00:00
- Post Title: The Settlers 7 BETA

That's pretty interesting indeed. Gonna have a look
## Post #7
- Username: vizipok
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jun 23, 2009 7:13 pm
- Post datetime: 2010-04-01T13:00:22+00:00
- Post Title: The Settlers 7 BETA

I am also very interested in the texts of The Settlers 7.
Unfortunately, last year I couldn't translate The Settlers 6: Eastern Realm.

Good luck, Rheini!
## Post #8
- Username: nevermind
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 09, 2007 10:38 pm
- Post datetime: 2010-04-01T16:57:38+00:00
- Post Title: The Settlers 7 BETA

Can't believe that someone buys a game with a DRM "copy protection" ;D

So here are some hints:

- Archive format is almost the same as the Settlers 6 format
- Encryption algorithms are (almost) the same
- Directory is not compressed any more
- Most of the files are compressed using zlib, use inflate() to uncompress the data after the initialization inflateInit2(&strm, 31);
-> First 16 bytes of the compressed data are encrypted using a simple xor algorithm
- e.g. MP3 files are not compressed but encrypted now
-> Same encryption algorithm that was used for the directory
-> Decrypt in blocks of 32KB
- All encryption keys are 4 x 32 bit
-> If you want to decrypt file data xor each word of the key with the corresponding filename length

Hope that helps. Good luck!
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-01T18:33:35+00:00
- Post Title: The Settlers 7 BETA

> Reply from vizipok
>
> Good luck, Rheini!
I gotta put this on ice. Don't have the time to spend hours on a game I probably won't play any longer than a few hours anyway.
Especially since nevermind seems to have all the knowledge necessary for writing an unpacker.
## Post #10
- Username: nevermind
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 09, 2007 10:38 pm
- Post datetime: 2010-04-01T21:14:32+00:00
- Post Title: The Settlers 7 BETA

knowledge: yes
time and motivation: no

I played with the demo archives, extracted some files - but that's all. As long as the game is "protected" with DRM I will not spend any more time on this game, sry.
## Post #11
- Username: vizipok
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jun 23, 2009 7:13 pm
- Post datetime: 2010-04-02T12:38:02+00:00
- Post Title: The Settlers 7 BETA

I am very disappointed. I can't solve the problem myself (unpacking text files). 
I'm just a translator, not a programmer.
Could anyone help me, please?
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-03T11:09:27+00:00
- Post Title: The Settlers 7 BETA

> Reply from nevermind
>
> As long as the game is "protected" with DRM I will not spend any more time on this game, sry.
So wait for the crack 

How is the decryption algorithm chosen/where are the keys?
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-14T09:34:06+00:00
- Post Title: The Settlers 7 BETA

I have not understood what should be the step-by-step for extracting the archived files.
all the rest is done and works perfectly except this final part.

example from shr.bba:
filename: Config\Castles.xml
type: 0x11
compressed size: 6557
decompressed size: 143349

```
96 7d de a9 9a ff 90 ca fb 6c 93 00 49 91 55 e9   .}.......l..I.U.
4c 4d b2 9d 4e d5 da db 5d 51 76 67 6a 5f ba 34   LM..N...]Qvgj_.4
11 93 a8 5a 96 bc b2 dc 9d cc af 5f c9 b2 d3 72   ...Z......._...r
```
encryption table:

```
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
00 00 00 00 42 7b 7d b5 96 76 7f 7d 00 00 00 00
```


if necessary I have also an mp3 example.
come on, last effort and we can remove this game from the todo list :)
## Post #14
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-16T15:20:51+00:00
- Post Title: The Settlers 7 BETA

my doubts derive by the fact that the wiki about settlers6 doesn't really explain the method for dumping the archived files, it tells only about xor and encryption table in an inconsistent way or a way that doesn't apply to settlers7.

for example there are references to the filetype identifier used for an array and about its values 0 or 1 for compressed/encrypted files and obviously this has no sense because their job must be one of them (since one excludes the other) and in my tests it's the second the correct one:
0x02 for non-compressed mp3s, 0x11 for compressed files, so type&1 = 0 and 1.

settlers7 has 2 different tea decryptions (ok, only different constants) that use ever the same 2 fixed keys (at least in the handling of the header) and are used for the encryption ids 0x6d1a8389 and 0x7d7f7696 but trying both the decryptions on the files give no results.
indeed in the blind tests I have made here with both encryptions and a "guessed" xoring it's all invalid.

so the informations are wrong or incomplete or simply different than the demo.

now I could get settlers6, reversing it and then applying the differences to settlers7, yeah but I would prefer the "easy life" at least one time moreover because this is only a test and the end seems not much far.

the following are the info about an archived mp3 in case it helps:
filename: Spoken\MessagesTutorial\Map_10\MessageMap10Dracorian11.mp3
type: 0x02
compressed size: 0x10a53 (not compressed)
decompressed size: 0x10a53

```
71 e5 68 33 b9 8a a7 23 3c 7e 1a ac bb a0 02 79   q.h3...#<~.....y
4d 64 33 27 f4 25 a9 ff 74 8f ed be 93 af 85 38   Md3'.%..t......8
03 33 e0 d7 cf 05 6e 28 90 e3 5a a7 ae d3 b5 f6   .3....n(..Z.....
52 d6 79 27 7d 5c 6d e2 ac 49 2a 4b b4 30 56 9f   R.y'}\m..I*K.0V.
e7 43 9a 6b 28 ef 91 14 3d 33 ad 8c 7c 02 e8 e5   .C.k(...=3..|...
ac 32 70 ca 7d fe ce 7e d4 bf d1 87 c6 3b bd 01   .2p.}..~.....;..
...
```
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-16T15:49:51+00:00
- Post Title: The Settlers 7 BETA

> Reply from aluigi
>
> my doubts derive by the fact that the wiki about settlers6 doesn't really explain the method for dumping the archived files, it tells only about xor and encryption table in an inconsistent way or a way that doesn't apply to settlers7.
The wiki page was written by nevermind as well.
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-16T16:22:02+00:00
- Post Title: Re: The Settlers 7 BETA

uhmmm just for my curiosity, don't exist extractors for all the games of the series?
on the settlers6 thread there is only a reference about nkcss but it looks like a work-around and not a real tool (the nde files that are a list of offset/size/name).

if that's the situation it looks like a big hole in my opinion.
if I had a real interest for it and desire to do it (definitely not now) I would have done it.
## Post #17
- Username: TheMachine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 26, 2010 7:23 am
- Post datetime: 2010-04-26T17:06:01+00:00
- Post Title: Re: The Settlers 7 BETA

Hi,
I've written a Settlers 7 BBA Decompressor/Decrypter. You should be able to decompress the BBA files of the demo and the fullversion.
The program should be self-explanatory.
If you find a bug, please leave a post.
Here you go:
[Click](http://ul.to/9cr7bu)

Enjoy
## Post #18
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-26T23:20:31+00:00
- Post Title: Re: The Settlers 7 BETA

@TheMachine:
"thanx" for having not shared the details we were interested to.

just for your note, your program doesn't work correctly with various big files due to a particular "thing" (although it says that it's all ok, wrongly) and I guess there is another small error in the decryption of the 32kb blocks
## Post #19
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-27T18:51:46+00:00
- Post Title: Re: The Settlers 7 BETA

> Reply from TheMachine
>
> I've written a Settlers 7 BBA Decompressor/Decrypter. You should be able to decompress the BBA files of the demo and the fullversion.
Thanks for the tool. Please also share some code that demonstrates how the whole unpacking works or at least the information that are still missing.
## Post #20
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-27T19:16:21+00:00
- Post Title: Re: The Settlers 7 BETA

it's too late, that's no longer needed because I already did the reversing job before writing my previous message yesterday and completed my script.
the missing information was that for the compressed files is necessary to perform a particular 32bit xor procedure on the first 16 bytes of the data using the length of the filename and some constants (plus another particular thing).
while for the non-compressed data (mp3) is used the same tea encryption used for the header (the one using the second type of init and constants) with a fixed key for each block of 32kb.
## Post #21
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-27T19:29:47+00:00
- Post Title: Re: The Settlers 7 BETA

What script?
## Post #22
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-27T19:33:40+00:00
- Post Title: Re: The Settlers 7 BETA

the script I started for curiosity and to which I referred in my previous posts: [settlers7.bms](http://aluigi.org/papers/bms/settlers7.bms)
## Post #23
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-27T19:47:21+00:00
- Post Title: Re: The Settlers 7 BETA

nice, though there still seems to be some stuff to do?!

> "Maps\Campaign\c00_m11_The_Return_of_the_Old_King\TerrainData.bin.gz"
>
> set ZSIZE long 10   # this file uses something different from offset 0x100003c

EDIT:
It doesn't extract anything with retail version 1.02.
"0 files found"
## Post #24
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-27T19:49:01+00:00
- Post Title: Re: The Settlers 7 BETA

I can't play the extracted Mp3s ..
## Post #25
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-27T20:02:40+00:00
- Post Title: Re: The Settlers 7 BETA

yeah, that file gives problems due to the usage of that "particular thing" about I referred.
while for the other files it seems to be a fixed "xor" offset (0, 0xb000b and so on) the same is not valid for that file... oh well.
there is also a discrepancy in the usage of the gzip compression in the game, that's why I adopted the unzip_dynamic work-around.

anyway I don't think that script is good to understand the format because it's a bit complex.
while on the "extraction side" as far as I have seen all the files (yeah except that one) are extracted perfectly for real because quickbms reports errors if the deflate stream is wrong, so if it gets extracted means it's ok.
if you compare or binary compare the results in the extraction of maps.bba through my script with those of that tool you can understand what I mean.

for the mp3s, I have tested with success the lngDE.bba archive while there was no luck with lngPL.bba.
obviously it's the same with the tool of themachine except that the last part of the lngde mp3 differs because the original settlers7 function refuses to code non padded data so I can't say what of the 2 resulted mp3 is the correct one.

anyway I highlight that I don't have the game so that's the max I can say at the moment.
let me know if you have other feedback for my script
## Post #26
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-27T20:55:17+00:00
- Post Title: Re: The Settlers 7 BETA

@rheini
I have read only now your edit.
all the tests have been performed on The Settlers 7 1.03

do you have the same result also with the tool of themachine?

I'm downloading the other old patches in this moment, mainly for curiosity to know what it's missing.
## Post #27
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-27T21:01:00+00:00
- Post Title: Re: The Settlers 7 BETA

never mind. for some reason it didn't save your script correctly to my disc.
maybe there should be an error message if a bms script is empty.
## Post #28
- Username: Skymmer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Mar 25, 2010 8:50 am
- Post datetime: 2010-04-27T22:47:01+00:00
- Post Title: Re: The Settlers 7 BETA

aluigi, thanks for your efforts ! But unfortunately I'm here to report the issue with script. I tried it on Gfx.bba file and got:

```

Error: there is an error with the decompression
       the returned output size is negative (-1)

```


Anyway, thanks once again !
## Post #29
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-28T07:56:36+00:00
- Post Title: Re: The Settlers 7 BETA

can you try it with version 0.4.2b of quickbms?
I forgot to specity it in the script because this version fixed just a bug in the "unzip_dynamic" function.

if the problem persists tell me what version of the game you are extracting (all the tests have been made with retail 1.03)
## Post #30
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2010-04-28T09:06:52+00:00
- Post Title: Re: The Settlers 7 BETA

> Reply from TheMachine
>
> Hi,
I've written a Settlers 7 BBA Decompressor/Decrypter. You should be able to decompress the BBA files of the demo and the fullversion.
Works perfectly.
Are you planning on adding compression? (Or share the source so someone else could do it?  )
## Post #31
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-28T13:58:28+00:00
- Post Title: Re: The Settlers 7 BETA

quickbms is open source.
## Post #32
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2010-04-28T14:47:00+00:00
- Post Title: Re: The Settlers 7 BETA

> Reply from Rheini
>
> quickbms is open source.
That's fine, but I do not see the relevance of that because I replied on the tool TheMachine posted.
## Post #33
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-28T14:56:21+00:00
- Post Title: Re: The Settlers 7 BETA

Ah correct, didn't notice that.
## Post #34
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2010-04-28T16:00:48+00:00
- Post Title: Re: The Settlers 7 BETA

> Reply from Rheini
>
> Ah correct, didn't notice that.
No prob.
## Post #35
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-04-28T17:30:38+00:00
- Post Title: Re: The Settlers 7 BETA

I have the same error  in the same file (Gfx.bba -Md5: e4308a78cc5769d35d782773a89e8a01)

> Error: invalid zlib compressed data (-3)
>
> 
>
> Error: there is an error with the decompression
>
>        the returned output size is negative (-1)
The last file it's

> 0000000a 5505152    Graphics\Textures\Buildings\S_Port_N_l3.dds
And using the latest version of quickbms 

> QuickBMS generic files extractor 0.4.2b and the game it's updated to 1.02

I tried with the sounds and movies but i get corrupted files..
## Post #36
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-28T20:19:21+00:00
- Post Title: Re: The Settlers 7 BETA

mah, I have downloaded the full 1.01 patch and the 1.01->1.02 patch and so I have fully tested all the 1.01, 1.02 and 1.03 versions of this game and everything gets extracted perfectly.

BUT it's needed to note that I don't have the game so I use only the patches that are bigs but probably don't contain all the files (that's why our md5s differ).

if this gfx.bba file is not too big can you upload it on sendspace or other file sharing websites?
have you tried to extract it also with the tool of themachine?
## Post #37
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-04-28T20:42:04+00:00
- Post Title: Re: The Settlers 7 BETA

It's 1.4GB.
I can confirm that it fails (v1.02).
## Post #38
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-04-28T21:18:17+00:00
- Post Title: Re: The Settlers 7 BETA

Sure i can upload, but like Rheini said, it's 1.4gb's, where i can upload a really big file, and if i have place my upload maybe takes 20 hours..
## Post #39
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-28T21:35:07+00:00
- Post Title: Re: The Settlers 7 BETA

oh no no, don't worry.
1gb and half is too much for a curiosity :)

anyway do you have the same result with the tool of themachine?
## Post #40
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-04-28T21:41:53+00:00
- Post Title: Re: The Settlers 7 BETA

> Reply from aluigi
>
> oh no no, don't worry.
1gb and half is too much for a curiosity 
anyway do you have the same result with the tool of themachine?
No, with themachine the unpacks works fine in graphics and movies files (i don't tested audios yet), the problem it's how make run the game without .bba files i can fake the files (in silly method of 0bytes) but the program still looking inside to decrypt something..
## Post #41
- Username: TheMachine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 26, 2010 7:23 am
- Post datetime: 2010-04-29T21:22:35+00:00
- Post Title: Re: The Settlers 7 BETA

Hi @all,
@aluigi: What's your problem? You don't have to be so sarcastic. I'm sorry that it didn't work for all files and I'm going to fix this problem this weekend. I can only spend time for it on the weekend. And because of that I couldn't write any wiki or something else. But I'm going to do that this weekend too. So please don't be that rude.
@all: Please tell me which files you couldn't extract so I can take a deeper look.
## Post #42
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-29T21:39:12+00:00
- Post Title: Re: The Settlers 7 BETA

> I couldn't write any wiki or something else. But I'm going to do that this weekend too.
perfect.

my reaction was caused by the fact that everytime there is no extraction tool for the settlers series and if exists it's a work-around or closed source which means that everytime a new game of the series is released it's necessary to reinvent the wheel (for example reversing your tool, that luckily allowed to the find the 2 problems I reported but this is another story).

only that, so keep up the good work and remember to check the errors returned by zlib otherwise you can't catch all the things that need to be fixed.
## Post #43
- Username: TheMachine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 26, 2010 7:23 am
- Post datetime: 2010-05-01T12:58:24+00:00
- Post Title: Re: The Settlers 7 BETA

Ok, I've finished Version 1.1
I think I've found all bugs. If you find a new bug, please leave a post.

Changelog Version 1.1:
* FIXED: The last block of all mp3 files was decrypted wrongly. Because of that all mp3 files with a size less than 32 KiB were scrambled and all other mp3 files got a scrambled ending.
* FIXED: All files that have a compressed size greater than 1 MiB were decompressed wrongly.

Get it [HERE](http://ul.to/ojl92q).

I've also started a wiki page ([HERE](http://wiki.xentax.com/index.php/Settlers_7:_Paths_to_a_Kingdom)). I'm trying my best to finish it this weekend.

@Csimbi: At the moment it's not planned to compress own BBA files. But maybe somebody is going to implement it after I've finished the wiki page.
## Post #44
- Username: TheMachine
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 26, 2010 7:23 am
- Post datetime: 2010-05-02T14:48:42+00:00
- Post Title: Re: The Settlers 7 BETA

I've finished the wiki page. If you've questions, please ask.
Bye
## Post #45
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-05-02T15:58:25+00:00
- Post Title: Re: The Settlers 7 BETA

Thanks for taking the time to explain it in detail.
Does anybody know if you can make the game use unpacked files?
## Post #46
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-02T18:06:19+00:00
- Post Title: Re: The Settlers 7 BETA

> Reply from Rheini
>
> Thanks for taking the time to explain it in detail.
Does anybody know if you can make the game use unpacked files?
The game only can works if the .bba are there, or maybe someone knows a "extra" parameter (like need for speed shfit)
## Post #47
- Username: ednet
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Aug 31, 2008 8:27 pm
- Post datetime: 2010-05-08T11:27:29+00:00
- Post Title: Re: The Settlers 7 BETA

Hello,
really nice tool. Good work @ TheMachine!

Have anyone the knowledge to program such a de- and ENcryptor?
It's nice to look into the files but unfortunately it is absolutely useless if the game don't use the extracted files. 

I guess TheMachine could create en encryptor in a couple of hours, couldn't you? 
I'm looking forward to mod that game cause i want to play the Limited Edition Map "The Race".

Greetings
## Post #48
- Username: vizipok
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jun 23, 2009 7:13 pm
- Post datetime: 2010-05-09T08:10:00+00:00
- Post Title: Re: The Settlers 7 BETA

I'm also waiting for a working repacking tool. 
Although I can translate text strings but can't use it in the game.
Is there any solution?
## Post #49
- Username: bhrun
- Rank: beginner
- Number of posts: 23
- Joined date: Sat Mar 20, 2010 8:20 pm
- Post datetime: 2010-07-06T14:24:53+00:00
- Post Title: Re: The Settlers 7 BETA

Where is the @TheMachine? Please help us with compression tool!

We need test the extracted files 

Thx for all!
## Post #50
- Username: vizipok
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jun 23, 2009 7:13 pm
- Post datetime: 2011-03-12T14:55:07+00:00
- Post Title: Re: The Settlers 7 BETA

Is there any news about The Settlers 7 BBA decrypter?
Where is TheMachine?
I would like to translate the game then to play with it.
## Post #51
- Username: Tolia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 13, 2011 6:44 pm
- Post datetime: 2011-08-06T15:18:23+00:00
- Post Title: Re: The Settlers 7 BETA

Is there compressor .bba files, or not?
## Post #52
- Username: MaximilianPs
- Rank: n00b
- Number of posts: 16
- Joined date: Tue Aug 30, 2011 3:01 am
- Post datetime: 2011-08-29T21:45:23+00:00
- Post Title: Re: The Settlers 7 BETA

s7bbaex 1.1 works prefectly !
## Post #53
- Username: Tolia
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jul 13, 2011 6:44 pm
- Post datetime: 2011-09-13T17:38:30+00:00
- Post Title: Re: The Settlers 7 BETA

s7bbaex 1.1 is wonderful decompressor but people need a compressor and decompressor for effective operations.
## Post #54
- Username: illian
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Feb 05, 2012 8:36 pm
- Post datetime: 2012-12-30T23:56:38+00:00
- Post Title: Re: The Settlers 7 BETA

Does someone have the s7bbaex 1.1?

Sory for pushin an old thread :p
## Post #55
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2012-12-31T14:36:05+00:00
- Post Title: Re: The Settlers 7 BETA

[Try This.](http://wikiwiki.jp/settlers7/?SettlersArchiver%A4%CE%BB%C8%A4%A4%CA%FD)
## Post #56
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2013-01-05T22:52:59+00:00
- Post Title: Re: The Settlers 7 BETA

@swuforce
Thanks, good stuff.
I took the liberty to localize this tool, please find it attached.
I think I fixed a bug, too, but I am not sure anymore...

Packing is a bit tricky, it takes some practice. I put some hints above the Pack button.
In general:
Create a directory to work. I.e. D:\MyMOD
Open the archive you want to update.
Select all files and unpack to D:\MyMOD.
Make the changes you want in any of the files, but do not add any new or remove any existing files.
When you're ready to pack, open the BBA file again - unless of course you still have it open -; the HashTable inside the BBA file is needed.
Click Pack and select the D:\MyMOD directory, then enter the name of the new BBA file to be created.
That's it.

Notes:
- some MP3 files (not all) come with additional encryption.
- some LUAs seem to be obfuscated - anyone here who could have a look?
- savegames are also BBA archives 

PS. Opening Gfx.bba will take a long long time - this is normal -, just sit tight.
[SettlersArchiver_v111en.rar](https://xentaxbackup.github.io/file/6115_SettlersArchiver_v111en.rar)
## Post #57
- Username: JonhOliver
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Mar 12, 2011 12:10 am
- Post datetime: 2013-01-17T21:45:24+00:00
- Post Title: Re: The Settlers 7 BETA

Which file contains the texts?
