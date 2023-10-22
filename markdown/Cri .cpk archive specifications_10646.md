## Post #1
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2013-07-31T14:59:34+00:00
- Post Title: Cri *.cpk archive specifications

Hi there,

i know there are plenty ways to unpack cpk files but i can't find informations about the format specifications ?
Has anybody documents about how the format is build up or how to unpack?

thanks
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-07-31T20:30:30+00:00
- Post Title: Cri *.cpk archive specifications

both the source code for quickbms and hcs64's cpkunpack are freely available. both have cpk unpack code. as far as i know no specification exists.
## Post #3
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2013-08-01T08:57:12+00:00
- Post Title: Cri *.cpk archive specifications

thanks for your reply.

I had already checked these scripts but had problems to understand whats going on.
I'am really surprised that there are no specification available for such a popular file format.

p.s. Is there a graphical debugger for bms scripts?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-01T10:04:00+00:00
- Post Title: Cri *.cpk archive specifications

> Reply from Riigel
>
> p.s. Is there a graphical debugger for bms scripts?Don't think so. Sure you'll need one?

Just use debug option -v for quickbms.

This is an example output (not for cpk but dzip but shouldn't matter):
In bold the addresses of the archive being extracted.

  offset   filesize   filename
------------------------------
             .start_bms start: -1 0 0

00000000 09  1   idstring DZIP

00000004 19  2   comtype COMP_LZF

00000004 06  3   get unk01 long
             >set unk01 (0) to 0x00000002

00000008 06  4   get files long
             >set files (1) to 0x00000001

So you can see at which address which values to be filled into the vars of the script.
## Post #5
- Username: Riigel
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Jul 08, 2011 1:32 am
- Post datetime: 2013-08-01T10:51:39+00:00
- Post Title: Cri *.cpk archive specifications

thank,
i will try the debug mode.

Just a quick Question to the syntax. (Can't find informations in the readme)
"set query->offset long 0"

Is "query->" somthing like a list in .Net?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-08-01T12:37:03+00:00
- Post Title: Cri *.cpk archive specifications

You could (as a test) replace all the "query->" in the cpk.bms by "query_" and see whether the script will run correctly.

I guess it will.
## Post #7
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2013-08-01T14:44:26+00:00
- Post Title: Cri *.cpk archive specifications

The format itself is a little bit complicated to understand, but once you understand how everything works it's easy to write a tool for it,

[](http://www.imagebanana.com/view/murp8zpr/CriToolpack.jpg)
This is my try to make a tool, it currently supports:
- decompress CRILAYLA
- decrypt UTF if UTF is encrypted
- read TOC, ITOC and ETOC tables
TODO:
- implement GTOC table
- some optimizations
- replace files
- relink files
- repack into cpk/create cpk from folder

It's written in C# and therefore easy to debug in visual studio.
Here source code + binary:
[http://www.mediafire.com/download/xgx73 ... oolpack.7z](http://www.mediafire.com/download/xgx73n19lo2xmo3/CriToolpack.7z)
## Post #8
- Username: todzy
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Sep 25, 2014 9:47 pm
- Post datetime: 2016-10-06T13:59:01+00:00
- Post Title: Cri *.cpk archive specifications

I check cpk and in it files have the same names and when unpacking they replace each other.
Only unpacker that work was CpkFileExplorer from [https://github.com/esperknight/CriPakTools](https://github.com/esperknight/CriPakTools) (Link go here) 
Pls look and help me with it, because i try all tools that i find on internet already...
File: [https://mega.nz/#!aldiwY4D!wgrYjIrFZsf4 ... ZFeXhdh4hc](https://mega.nz/#!aldiwY4D!wgrYjIrFZsf42yCV_ebSAKDB_RHKRMGb6ZFeXhdh4hc)
## Post #9
- Username: jonhsame
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 15, 2016 7:16 pm
- Post datetime: 2016-10-15T11:21:44+00:00
- Post Title: Cri *.cpk archive specifications

both the source code for quickbms and hcs64's cpkunpack are freely available. both have cpk unpack code. as far as i know no specification exists.
## Post #10
- Username: wmltogether
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 25, 2011 8:39 pm
- Post datetime: 2016-10-31T05:03:52+00:00
- Post Title: Cri *.cpk archive specifications

> Reply from todzy
>
> I check cpk and in it files have the same names and when unpacking they replace each other.
Only unpacker that work was CpkFileExplorer from https://github.com/esperknight/CriPakTools (Link go here) 
Pls look and help me with it, because i try all tools that i find on internet already...
File: https://mega.nz/#!aldiwY4D!wgrYjIrFZsf4 ... ZFeXhdh4hc
Try this fork :[https://github.com/wmltogether/CriPakTools/tree/mod](https://github.com/wmltogether/CriPakTools/tree/mod)
based on the scripts from falo & esperknight
