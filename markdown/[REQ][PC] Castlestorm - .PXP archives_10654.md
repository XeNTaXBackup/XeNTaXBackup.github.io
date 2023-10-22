## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-08-02T20:36:31+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

A message from Czarnobrody:

> Can somebody help me with open these .pxp files? They are coming from Castlestorm [PC].

< link expired >
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-03T13:52:30+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

Well files are compressed with unknown algo. Here useless unpacker because can't decompress files.

PS: Inside archive algo included. Maybe someone know what this.
## Post #3
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-04T10:46:32+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

Updated. Decompress func for test.
[CSPXPUnpacker_0.2.rar](https://xentaxbackup.github.io/file/6543_CSPXPUnpacker_0.2.rar)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-08-04T21:47:21+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

It works. Thank you very much. ^^
## Post #5
- Username: springfall
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 07, 2013 1:21 pm
- Post datetime: 2013-08-07T06:08:47+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

It's not right work with file "hud.pxp", can anyone help to fix this problem?  Thanks!
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-07T06:21:52+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

I did everything. Problem in decompress function.
## Post #7
- Username: springfall
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 07, 2013 1:21 pm
- Post datetime: 2013-08-07T06:33:09+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

Could you share me the source code of this unpacker, let me try if possible. 
Thank you very mush!
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-08-07T11:18:56+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

If you know assembler i can share, but if not then I do not see sense
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2015-04-18T22:42:50+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

I know assembler.
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-04-25T12:13:58+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

Well, here source of decompress lib
[ZENLib_Src.rar](https://xentaxbackup.github.io/file/9104_ZENLib_Src.rar)
## Post #11
- Username: Northstar2
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Feb 14, 2016 6:42 pm
- Post datetime: 2016-02-14T11:08:22+00:00
- Post Title: [REQ][PC] Castlestorm - *.PXP archives

It's quite old, yes, but here's a question:

So the unpacking tool from Ekey (stated as h4x0r in program) crashes while decompressing most of archives (usually after 4* mark like [43/255]) and stops working.
Plus the output files are in .px* format (like .pxt, .pxa, etc.), which is unreadable except for "PX." header.
What am I missing or what am I doing wrong?   
I am totally clueless as .px* files do not seem to be documented at all.

Plus I did some editing to the included Batch script, to make it slightly easier to use:

```
set /p FileName=Enter name of file you wish to unpack: 
color a
CSPXPUnpacker.exe "%FileName%"
pause
```
