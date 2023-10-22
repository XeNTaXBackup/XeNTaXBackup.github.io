## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-09-10T10:10:38+00:00
- Post Title: Tekken Tag Tournament 2 .bin

Hello everyone! 
I need help with extracting files from X-Box 360 version of TTT-2. It stores data in .bin files, here is one of them <link removed due forum rules violation> . Thanks in advance.
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-09-11T20:09:08+00:00
- Post Title: Tekken Tag Tournament 2 .bin

Inside .bins - models, textures have NDXR, NTXR header, they could be manually extracted with HEX editor and viewed with noesis, but it will take ages to get them that way. Maybe someone create bms script to extract them?
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-11T21:53:08+00:00
- Post Title: Tekken Tag Tournament 2 .bin

already working on it; it will take a week. there are thousands of models and grouping is not obvious.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-11T22:58:40+00:00
- Post Title: Tekken Tag Tournament 2 .bin

Almost there...
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2012-09-12T11:45:55+00:00
- Post Title: Tekken Tag Tournament 2 .bin

Thanks a lot , it's a great news! Howfie you are amazing, excellent work.
## Post #6
- Username: IvoryCutter
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jan 15, 2012 4:25 pm
- Post datetime: 2012-09-18T06:26:13+00:00
- Post Title: Tekken Tag Tournament 2 .bin

> Reply from howfie
>
> Almost there...

Wow, howfie you're at it again! 
So fast! Game's only been out for a week and you've already figured it out!
Any update?
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-18T07:23:21+00:00
- Post Title: Tekken Tag Tournament 2 .bin

Rich did all the work. Tekken 6 noesis works for most models except level geometry. It's done. Daz will post my utilities here tonight. I am far from home. Only got phone 3g connection.
## Post #8
- Username: xemnas26
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 09, 2011 2:03 pm
- Post datetime: 2012-09-21T06:01:10+00:00
- Post Title: Tekken Tag Tournament 2 .bin

hello i was wondering if you guys could help me i cant seem to find where the bins are in the iso because all im seeing is system update folder,video ,audio and a default.xex files, thanks
## Post #9
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-09-24T10:50:32+00:00
- Post Title: Tekken Tag Tournament 2 .bin

> Reply from xemnas26
>
> hello i was wondering if you guys could help me i cant seem to find where the bins are in the iso because all im seeing is system update folder,video ,audio and a default.xex files, thanks

lol
you need an xbox iso extractor to see the files
## Post #10
- Username: xemnas26
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 09, 2011 2:03 pm
- Post datetime: 2012-09-26T06:20:28+00:00
- Post Title: Tekken Tag Tournament 2 .bin

ok thanks i got it extracted and im trying to use the bin2nmd tool to decompress the bins but all im getting is 

C:\Documents and Settings\Owner\My Documents\Downloads\ttt2 models>bin2nmd
File 1 of 42: C:\Documents and Settings\Owner\My Documents\Downloads\ttt2 models
\data001.bin
Expecting 0x14.

and then nothing can some one please tell me what im doing wrong , thanks
## Post #11
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-09-26T07:08:35+00:00
- Post Title: Tekken Tag Tournament 2 .bin

You must run xbdecompress on the bin files first.
## Post #12
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2012-09-26T17:44:30+00:00
- Post Title: Tekken Tag Tournament 2 .bin

> Reply from xemnas26
>
> ok thanks i got it extracted and im trying to use the bin2nmd tool to decompress the bins but all im getting is 

C:\Documents and Settings\Owner\My Documents\Downloads\ttt2 models>bin2nmd
File 1 of 42: C:\Documents and Settings\Owner\My Documents\Downloads\ttt2 models
\data001.bin
Expecting 0x14.

and then nothing can some one please tell me what im doing wrong , thanks
You should use the tutorial I wrote: [viewtopic.php?f=16&t=9645](http://forum.xentax.com/viewtopic.php?f=16&t=9645)
Explains everything you need to do, including using xbdecompress
