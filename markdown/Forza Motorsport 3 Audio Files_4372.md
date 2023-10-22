## Post #1
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-23T02:01:41+00:00
- Post Title: Forza Motorsport 3 Audio Files

Hi guys 

I want you to ask if you can help to decode the Audio Files of Forza 3.

With the Music it's really easy. Just extract XMA Files from the DVD.

I'll post both Decoded (with XMAEncode.exe) and Encoded Files. (If you need this, maybe?)

[http://ul.to/4a3zwt](http://ul.to/4a3zwt)

And now my problem: I have no luck with the files Inside FSB Containers. Tryed with FSBExtractor -a and -a -A Switches, no Luck. I think I'm dumb and it's only a File header issue (aka Attaching the right Header to the Files?!)

Here is a FSB File maybe someone can Decode it and tell me/us how, to do this, please? 

[http://ul.to/kwcnc0](http://ul.to/kwcnc0)
## Post #2
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-25T16:48:55+00:00
- Post Title: Forza Motorsport 3 Audio Files

Can't anyone help, please?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T17:15:40+00:00
- Post Title: Forza Motorsport 3 Audio Files

with fsbext the extraction is correct, the problem is xmaencode that it's not able to decode the obtained files.
the difference between these files and the one in your first link is that they are xma2 while that one is xma1 and no, if youdo an "injection" job (like putting the data content of one of these other files inside the first one) it returns a wav file with a glitch at its beginning (so a fail)

oh and yes I have tried also to force the xma1 header with fsbext but xmaencode is still not able to decode them
## Post #4
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-04-25T18:48:05+00:00
- Post Title: Forza Motorsport 3 Audio Files

aluigi, have you tried forcing a xma1 header and converting the xma2 stream to xma1, via xmatest -r ?
## Post #5
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-25T18:52:19+00:00
- Post Title: Forza Motorsport 3 Audio Files

Thanks for your help so far
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-25T19:48:44+00:00
- Post Title: Forza Motorsport 3 Audio Files

no hcs, I have not tested.
anyway if you want to force the xma1 header for this test it's enough that you substituite the reference to the xma2_header function in fsbext.c with xma1_header (it's already implemented)
let me know if you get a result in which case I will add an option to let the user to choose the xma1 header instead of the xma2 one without the need of recompiling
## Post #7
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-04-25T21:53:04+00:00
- Post Title: Forza Motorsport 3 Audio Files

xmatest.exe ExhR_04231.xma -r new.xma
XMA/XMA2 stream parser 0.8 by hcs

filename: ExhR_04231.xma
version: XMA2
offset: 0
block size: 8000
data size: 608c
rebuild output filename: new.xma
------------------

error reading bitstream

I changed of course the Source Code from fsbext that it outputs a xma1 header first
## Post #8
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-10T14:01:06+00:00
- Post Title: Forza Motorsport 3 Audio Files

Git it working with towave
## Post #9
- Username: CodeWrestler
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 22, 2008 12:55 am
- Post datetime: 2010-05-11T05:48:55+00:00
- Post Title: Forza Motorsport 3 Audio Files

Sommergemeuse did you get the .xma file working with ToWave or the extracted .fsb file?
## Post #10
- Username: Simon
- Rank: mega-veteran
- Number of posts: 180
- Joined date: Mon Sep 21, 2009 12:41 am
- Post datetime: 2010-05-11T16:40:15+00:00
- Post Title: Forza Motorsport 3 Audio Files

FSB File
## Post #11
- Username: fifomaniak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 30, 2010 10:11 pm
- Post datetime: 2010-06-01T16:51:34+00:00
- Post Title: Forza Motorsport 3 Audio Files

So, has anyone figured this out? Cause I need this to make engine sounds for other games
## Post #12
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2010-08-05T16:44:54+00:00
- Post Title: Forza Motorsport 3 Audio Files

Where I can download a program "towave"
## Post #13
- Username: RedDeadRedemption
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jul 13, 2010 10:23 pm
- Post datetime: 2010-08-06T14:47:49+00:00
- Post Title: Forza Motorsport 3 Audio Files

toWAV.exe :
[http://www.box.net/shared/zd9blkhsuo](http://www.box.net/shared/zd9blkhsuo)
## Post #14
- Username: matt55
- Rank: beginner
- Number of posts: 36
- Joined date: Mon Apr 19, 2010 8:13 pm
- Post datetime: 2010-08-10T21:57:05+00:00
- Post Title: Forza Motorsport 3 Audio Files

Well I've got one question. Where toWAV export files??? because  I drop one file on it, shows some .wav files, but I can't find them 

EDIT: I found them thanks for all!!
## Post #15
- Username: JT22
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 02, 2010 2:58 am
- Post datetime: 2010-10-02T08:46:34+00:00
- Post Title: Forza Motorsport 3 Audio Files

The contents of this post was deleted because of possible forum rules violation.
