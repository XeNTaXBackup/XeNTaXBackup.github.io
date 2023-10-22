## Post #1
- Username: Silver
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-01-17T23:57:22+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

i always seem to get an process error when ever i try to open any of the rfa's.   ex. process error, get called with invalid datatype.  And Multiex3 could not process. so what am i doing wrong?
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-18T17:08:35+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

Well, only the DEMO verison of BF1942 RFA files are supported, as is also stated in the program. Not the reatil verison. Are you trying to open the demo version files or the retail version? Also, if you are opening the demo version RFA files, could you specify which don't work?
## Post #3
- Username: Silver
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-01-18T18:18:55+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

ah ic sorry, i guess i missed that part while i was reading it, i was trying to open the retail ones.  will there be upcomming support for the retail rfa's?
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-19T09:55:51+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

Not as of yet, as I don't know the crunching method they use on resources in retail RFA files.
## Post #5
- Username: tank
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-01-26T17:04:18+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

> Reply from Mr.Mouse/XeNTaX
>
> Not as of yet, as I don't know the crunching method they use on resources in retail RFA files.

Hi,
have a look at:

[http://prdownloads.sourceforge.net/r2at/](http://prdownloads.sourceforge.net/r2at/)

The file 'ratdcom-0.5.0-dynsrc.zip' contains the required c-source. 
Well, or download the binaries ...   

It works fine for BF Retail 1.2.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-01-26T18:43:13+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

Thanks!
## Post #7
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2003-03-23T10:14:27+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

well, i have dl the bin with a DLL - and what shall I do now? (sorry - newbie)
## Post #8
- Username: JEB
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 30, 2003 5:28 pm
- Post datetime: 2003-05-30T09:30:03+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

I'm also new, where do i but the ratdcom stuff from the zip?
## Post #9
- Username: AdamTheStudent
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Dec 11, 2005 8:52 am
- Post datetime: 2005-12-11T01:27:33+00:00
- Post Title: Why do all my bf1942 .rfa's not open?

Hi. I'm attempting to write a program that can use files archived in *.rfa archive files of the game Battlefield 1942. The wiki information had allowed me to know how to separate the files into the proper directories, but only in compressed form, which is unuseable for me.

What compression/encryption method is being used on the data files? The sourceforge project files linked to above aren't of much use since I've not been able to determine the correct algorithm to use from them.

Using a hex editor I have noticed that every compressed file has the following structure:

Header: 0100 0000 xxxx 0000 xxxx 0000 0000 0000

Last 3 bytes of file: 1100 00

The DragonUnpacker can properly extract both the retail and demo version archives, but the author has yet to reply to my email.

If you can help, please reply here or email me at [adamthestudent@hotmail.com](mailto:adamthestudent@hotmail.com)

Thank you....
