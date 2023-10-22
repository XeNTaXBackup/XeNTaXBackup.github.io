## Post #1
- Username: zouzou69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Mar 10, 2011 6:46 pm
- Post datetime: 2011-03-10T20:47:44+00:00
- Post Title: fifa 11 xbox 360 compression method ?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: zouzou69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Mar 10, 2011 6:46 pm
- Post datetime: 2011-03-11T19:37:49+00:00
- Post Title: fifa 11 xbox 360 compression method ?

anyone to help me please?
## Post #3
- Username: zouzou69
- Rank: n00b
- Number of posts: 17
- Joined date: Thu Mar 10, 2011 6:46 pm
- Post datetime: 2011-03-17T00:39:47+00:00
- Post Title: fifa 11 xbox 360 compression method ?

> Reply from zouzou69
>
> anyone to help me please?

my english is so bad? no one help me?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-17T11:43:49+00:00
- Post Title: fifa 11 xbox 360 compression method ?

no problems with the english.
the problem was that you wrote too much and the first part looked like a graphic/3d problem so I ignored the post completely.

luckily I already did this job with another game so it took me 1 minute to extract the chunklzx part of the code and making a quickbms script jor for this type of files:
[http://aluigi.org/papers/bms/chunklzx.bms](http://aluigi.org/papers/bms/chunklzx.bms)
## Post #5
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-03-17T13:32:00+00:00
- Post Title: fifa 11 xbox 360 compression method ?

Thanks aluigi
## Post #6
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-03-31T21:15:28+00:00
- Post Title: fifa 11 xbox 360 compression method ?

Any file which i try to decompress using the chunklzx script with quickbms gives a "incomplete input file number 0 and can't read # of bytes" error. any idea how to get around this?
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-01T22:44:01+00:00
- Post Title: fifa 11 xbox 360 compression method ?

are you using the latest version of quickbms (0.4.10b)?
[http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)

IF yes then upload the file which gives you that error.
## Post #8
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-04T11:24:29+00:00
- Post Title: fifa 11 xbox 360 compression method ?

yes, it still doesn't work. I am trying to decompress files which aren't from FIFA 11 XBOX360 but from previous versions: WC2010, FIFA10 and FIFA09. The last one involves .rx2 files.

EDIT: it's not a specific file but any file from XBOX360 which i try to open. Nothing works.

Try any one from these:

[http://www.gamefront.com/files/20175836 ... inaldo.rar](http://www.gamefront.com/files/20175836/Files+for+Rinaldo.rar)

[http://www.gamefront.com/files/20175939/00000002.rar](http://www.gamefront.com/files/20175939/00000002.rar) 

[http://www.gamefront.com/files/20148819 ... BOX360.rar](http://www.gamefront.com/files/20148819/3+Stads+to+Convert+from+XBOX360.rar)

Also other people which have tried and gotten something have had this bug:
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-04T12:39:37+00:00
- Post Title: fifa 11 xbox 360 compression method ?

thanx for the report, it revealed to be a different format... yeah same signature but a deeply different format.
I have updated the script to version 0.2:
[http://aluigi.org/papers/bms/chunklzx.bms](http://aluigi.org/papers/bms/chunklzx.bms)

note that in the Rinaldo folder you provided there are also non-chunklzx files so you can't handle them with this script.
## Post #10
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-04T22:07:04+00:00
- Post Title: fifa 11 xbox 360 compression method ?

Thanks for the update. It works tentiatavely. I've only tested on stadiums, Textures are perfectly placed. However, I'm unable to decompress BIG files.
## Post #11
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-04T23:05:11+00:00
- Post Title: fifa 11 xbox 360 compression method ?

because BIG files are not chunklzx, just like I said.

I gave a quick look at them but I don't understand exactly what they should be because they don't seem archives containing multiple files, maybe someone else is interested in checking them
## Post #12
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-05T09:18:16+00:00
- Post Title: fifa 11 xbox 360 compression method ?

are you able to make a decompression script for XBOX360 big files?

EDIT: Big files for the NG version don't have various files, they are for menu images. The third files in the bigs are the most important, they should be in an image format (.dds). I can upload a NG PC big file if you want to have a look to compare.

Also, I'm unable to convert the .rx2 files for the millenium stadium from FIFA09. Again the compression is different from chunklzx. Any idea how to convert a .rx2 to .rx3 filetype?
## Post #13
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-07T21:28:26+00:00
- Post Title: fifa 11 xbox 360 compression method ?

Another Update, I have all files for the Millenium Stadium decompressed (luckily found as .rx3 files) except for the container model. Can anyone please help with this?
## Post #14
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-09T23:37:00+00:00
- Post Title: fifa 11 xbox 360 compression method ?

Another update, I am having the same problem with the graphic file not rendering properly. It renders fine ingame, but when trying to view the file with a gprahics editor for FIFA, it shows lots of different colours, which are all pixelated. What can i do to fix this?
## Post #15
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-10T23:09:58+00:00
- Post Title: fifa 11 xbox 360 compression method ?

Files attached include an example stadium from FIFA11 PC (Parc des Princes) and the stadium to be converted from FIFA09 X360 (Millenium Stadium)

[http://www.gamefront.com/files/20210735 ... amples.rar](http://www.gamefront.com/files/20210735/Stadium+Container+Examples.rar)
## Post #16
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-11T15:00:28+00:00
- Post Title: Re: fifa 11 xbox 360 compression method ?

I guess you are going a bit off-topic because the initial problem was about the chunklzx files and it has been solved.
the one you have now seems a 3d/graphic problem so I don't know if there are people that can help you in this specific section of the forum.
## Post #17
- Username: RobbieDPL
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Apr 01, 2011 5:13 am
- Post datetime: 2011-04-16T00:03:13+00:00
- Post Title: Re: fifa 11 xbox 360 compression method ?

> Reply from aluigi
>
> I guess you are going a bit off-topic because the initial problem was about the chunklzx files and it has been solved.
the one you have now seems a 3d/graphic problem so I don't know if there are people that can help you in this specific section of the forum.

With regards to the decompression, I found out that the PS3 version's files work exactly the same as in PC, so I don't need to worry about XBOX360 games for PC graphics. Now my only question that remains is how to convert .rx2 to .rx3?
