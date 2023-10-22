## Post #1
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-05-18T18:47:45+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

IGI 1 .mef files are vertexes only and has one submesh. Any questions?
[bandicam 2021-05-18 11-45-14-882.jpg](https://xentaxbackup.github.io/file/20156_bandicam 2021-05-18 11-45-14-882.jpg)
## Post #2
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-05-18T18:50:16+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

[https://www.mediafire.com/file/zthuze2q ... s.zip/file](https://www.mediafire.com/file/zthuze2q3re40gx/IGI1_MEFs.zip/file)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-05-18T20:51:25+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

You need to get the structures before you can create a script.

For your first mesh you missed the 2nd part:

0xBA8 207
Vb1
40 99
0x3398 113
020000
0x0 255

(copy above 6 lines into a text file then save it as whatever.H2O)
-------------------------------------

To get further blocks search for "XTVC" (vertex block) and "ECFC" (face indices block, FIs).
You need to skip  an additional index/number in FIs' block (red rectangled 2).
.



400_01_1-a.png (92.67 KiB) Viewed 250 times
## Post #4
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-06-05T21:18:57+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

Can you write a maxscript please?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-06-05T22:02:13+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

I don't have 3dsmax installed, so sorry, no.

For coding I usually use the Make_obj project (click on the up arrow):

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 

edit: done (WIP, maybe)

> Reply from shakotay2 ↑Wed Dec 01, 2021 4:53 am at Wed Dec 01, 2021 4:53 am
>
>
## Post #6
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-06-06T08:29:51+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

[https://www.mediafire.com/file/40qpnkmw ... 1.mef/file](https://www.mediafire.com/file/40qpnkmwah74449/000_01_1.mef/file)
## Post #7
- Username: braveplayer50
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Sep 15, 2020 12:40 am
- Post datetime: 2021-09-16T20:40:38+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

[https://cdn.discordapp.com/attachments/ ... 8_01_1.mef](https://cdn.discordapp.com/attachments/493152982293282816/888150723978747924/108_01_1.mef)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-30T20:53:55+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

Hi there,
I saw your ms script doesn't care for uvs, does it?
I'm not sure whether uvs are ok created by the appended Make_H2O but I felt the need of a "slight" correction because it seems I misled you from the correct vertex start adress to be used (see opening post).
.


 Make_H2O-IGI_mef.zip
(81.9 KiB) Downloaded 32 times


(If u want to have a look onto the uvs, just in case.)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-30T20:55:02+00:00
- Post Title: IGI 1 .mef one submesh in model researcher/hex2obj

Tested 400_01_1.mef only, result:
.



400_01_1-uvs.png (30.42 KiB) Viewed 162 times



edit: tested 000_01_1.mef and it breaks my code...
